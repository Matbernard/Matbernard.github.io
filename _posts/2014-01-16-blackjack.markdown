---
layout: post
title:  "Un jeu de blackjack simplifié qui tourne en ruby"
date:   2014-01-15 10:44:32
---

# Règles du jeu

Le blackjack est un jeu de cartes. Nous allons vous distribuer plusieurs cartes. Vous pourrez continuer ou vous arréter quand vous le souhaitez. 
Vous jouez contre la banque et vous devez vous rapprochez au plus près de 21. 



{% highlight ruby %}
player_money = 100

score = 0
score_bank = 0

puts "How much money do you want to play?"
answer_money = gets.chomp.to_i

puts "Thanks dude, you played #{answer_money} €"
if result = "loose"
		player_money -= answer_money
	elsif result = "win"
		player_money += answer_money
	else result += 2 * answer_money
end	


while ( score < 21 )
	puts "Do you want a card?"
	answer = gets.chomp
	if answer == "yes"
		score = score + rand(1..11)
		if 
			score_bank <= 16
			score_bank += rand(1..11)
		end
		puts "Your score is #{score} and bank score is #{score_bank}"
	else 
		while ( score_bank <= 16 )
			score_bank += rand(1..11)
			puts "Your score is #{score} and bank score is #{score_bank}"
		end
		break
	end
end

if score_bank > 21
	result = "win"
	puts "You win #{answer_money} €"
elsif score > 21
	result = "loose"
	puts "You loose #{answer_money} €"
elsif score == 21
	result = "blackjack"
	puts "So cool, you have a black jack and you win #{2 * answer_money} €"
elsif score > score_bank
	result= "win"
	puts "You win #{answer_money} €"
else
	result = "loose"
	puts "You loose #{answer_money} €"
end
{% endhighlight %}

Va sur BeMyBoat mec [BeMyBoat][bemyboat] pour plus d'infos.

[bemyboat]: http://fr.bemyboat.com/

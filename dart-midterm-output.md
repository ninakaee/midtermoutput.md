import 'dart:math';
import 'dart:io';

void main(){
    int score_bot = 0;
    int score_player = 0;
    
    print("Number of rounds you want to play:");
    int total_rounds = int.parse(stdin.readLineSync());
    
  for (var i = 1; i <= total_rounds; i++){
    print("Round $i: Papel, Gunting, Bato! What's your Pick?");
    String players_pick = stdin.readLineSync().toUpperCase();
    print("$players_pick");
  
  //BOT 
  var bot = ['PAPEL', 'GUNTING', 'BATO'];
  var answer = (bot[new Random().nextInt(bot.length)]);
  
  //-------------------------------------------------------------
    if(players_pick == "PAPEL")
      {
        if(answer == "PAPEL") {
           print("Bot: Papel 📄 - It's a Tie!");
      }
        else if(answer == "BATO") {
           print("Bot: Bato 🌑  - You Win!");
           score_player++;
      }
        else if(answer == "GUNTING") {
           print("Bot: Gunting ✂️ - You Lose!");
           score_bot++;
      }
  }
  //-------------------------------------------------------------
    else if(players_pick == "GUNTING")
    {
        if(answer == "PAPEL") {
           print("Bot: Papel 📄 - You Win!");
           score_player++;
      }
        else if(answer == "BATO") {
           print("Bot: Bato 🌑  - You Lose!");
           score_bot++;
      }
        else if(answer == "GUNTING") {
           print("Bot: Gunting ✂️ - It's a Tie!");
      }
  }
  //-------------------------------------------------------------
    else if(players_pick == "BATO")
    {
        if(answer == "PAPEL"){
           print("Bot: Papel 📄 - You Lose!");
           score_bot++;
      }
        else if(answer == "BATO"){
           print("Bot: Bato 🌑  - It's a Tie!");
      }
         else if(answer == "GUNTING"){
           print("Bot: Gunting ✂️ - You Win!");
           score_player++;
      }
  }
  //-------------------------------------------------------------
    else {
      print("Invalid Input!");
  }
  }
    if(score_player > score_bot) {
      print("You Win! Bot: $score_bot, You: $score_player");
  }
    else if(score_player < score_bot) {
      print("You Lose! Bot: $score_bot, You: $score_player");
  }
    else {
      print("It's a tie!");
  }
}


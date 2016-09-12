# Xelnaga-Starcraft-game-AI-bot-AIIDE2014
This is an StarCraft AI bot for RTS game competitions (IEEE CIG RTS AI competition and AAAI AIIDE RTS AI competition). This AI bot uses the influence map, navigation system, expert system, and planning.

#Method
##Structure between functions
<img src="https://github.com/chc2212/Xelnaga-Starcraft-game-AI-bot-AIIDE2014/blob/master/Xelnaga_pic.jpg" width="300">

##influence map and confidence system
The influence map representation was adopted to spatially analyze the influence of units. Through influence map, each unit has confidence and it is used to judge status of units in various situations.   
* Changing confidence of each unit
<img src="https://github.com/chc2212/Xelnaga-Starcraft-game-AI-bot-AIIDE2014/blob/master/p3.gif" width="300">
* Searching effectively attact point for area attack (attack to multiple units at once)
<img src="https://github.com/chc2212/Xelnaga-Starcraft-game-AI-bot-AIIDE2014/blob/master/p1.gif" width="300">
* Judging whether an unit is in danger and order fleeing 
<img src="https://github.com/chc2212/Xelnaga-Starcraft-game-AI-bot-AIIDE2014/blob/master/p2.gif" width="300">

#Screen Captures


#Competition Results
<img src="https://github.com/chc2212/Xelnaga-Starcraft-game-AI-bot-AIIDE2014/blob/master/pic1.png" width="500">

#References
* [H.-S. Park, **H.-C. Cho**, K.-Y. Lee, and K.-J. Kim, “Prediction of early stage opponent strategy for StarCraft AI using scouting and machine learning,” Workshop at SIGGRAPH ASIA (Computer Gaming Track), pp. 7-12, 2012.](http://cilab.sejong.ac.kr/home/lib/exe/fetch.php?media=public:paper:wasa_2012_park.pdf) 
* [**H.-C. Cho**, and K.-J. Kim, “Design and evaluation of intelligence architecture for RTS games: Case Study of StarCraft,” Fall Conference of Korea Culture & Contents Technology Association, 2012.](http://cilab.sejong.ac.kr/home/lib/exe/fetch.php?media=public:paper:2012:ctkorea_2012_ho_chul_cho.pdf)

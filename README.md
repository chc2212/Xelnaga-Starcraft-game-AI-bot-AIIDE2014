# Xelnaga-Starcraft-game-AI-bot-AIIDE2014
This is an StarCraft AI bot for RTS game competitions (IEEE CIG RTS AI competition and AAAI AIIDE RTS AI competition). This AI bot uses the influence map, navigation system, expert system, and planning. 

#Method
##Structure between functions
<img src="https://github.com/chc2212/Xelnaga-Starcraft-game-AI-bot-AIIDE2014/blob/master/Xelnaga_pic.jpg" width="500">

##Automatic build order and build order change
We applied order of priority and rules to make build order automatically. And enemy's build order information acquired by scouting is used to judge enemy's strategy, especially whether enemy intends to attak on early stage. If Xelnaga judges enemy's stretegy is fast attack, then Xelnaga changes build order to focus on making militery units. 

<img src="https://github.com/chc2212/Xelnaga-Starcraft-game-AI-bot-AIIDE2014/blob/master/autoBulid1.gif" width = "350" align = "Left">

<img src="https://github.com/chc2212/Xelnaga-Starcraft-game-AI-bot-AIIDE2014/blob/master/autoBuild2.gif" width = "350">


##Attack and defence
For effcient attack and defence, each unit allocates enemy units through appropriate algorithms.
<img src="https://github.com/chc2212/Xelnaga-Starcraft-game-AI-bot-AIIDE2014/blob/master/p5.gif" width = "300">
<img src="https://github.com/chc2212/Xelnaga-Starcraft-game-AI-bot-AIIDE2014/blob/master/p7.gif" width = "300">

* Xelnaga (Orange) vs Skynet

<img src="https://github.com/chc2212/Xelnaga-Starcraft-game-AI-bot-AIIDE2014/blob/master/defense.gif" width = "400">

* Xelnaga (Green) vs Skynet

<img src="https://github.com/chc2212/Xelnaga-Starcraft-game-AI-bot-AIIDE2014/blob/master/defenseAndAttack.gif" width = "400">


##Navigation (Scouting)
The purpose of this step is to find the opponent’s base and collect data about it. The scouting unit is a worker (resource collector) from one of the races. Instead of mining the resources, they explore the dark area to find the opponent’s base. The first step is to find the location. There are several possible areas for the opponent’s position on the general game map. A scouting unit checks all candidate areas. 

After finding the opponent base area, then the recon unit scouts the area. There are two important goals in this step. (1) The recon unit should survive in the hostile area as long as possible. (2) The unit should reveal as many of the opponent’s structures/units as possible. However, it is not trivial to satisfy both of them.  To collect data precisely, the recon unit should be close to the opponent’s structures/units. But, this increases the risk that the recon unit will be damaged or destroyed. So, the recon unit has to be close to them, but not too close to be attacked.

Our recon unit is mimicking the human player’s scouting. They continuously rotate the area keeping constant distance to the buildings. If the unit is inside the opponent’s area, the first task is to go to the main building (Nexus, Command Center, or Hatchery). When the opponent’s building hits the visible area of the scouting unit, it changes the navigation path. We only consider an opponent’s buildings to decide the direction of movement. When the recon unit sees an opponent’s building, it changes its direction 90° CCW (Counter Clock Wise) or CW (Clock Wise). So, the recon unit orbits round the opponent’s structure. CCW or CW is not important in this method. 

Ideally, the recon unit orbits perfectly around the opponent’s building keeping the same distance. However, the recon unit is not rotating in an ideal circle. This is caused by the update rate (update per 13 game ticks). If the update rate is increased, the recon unit’s movements are close to the circle but it consumes much computational resource (critical to a real-time game). Instead of adjusting the updating rate, we change the rotation angle. Testing on 75, 80, 85, and 90 degrees show that 80 is the best one.

When there is more than one opponent structure in the recon unit’s view, it regards them as one big virtual building. If there are N opponent’s buildings in the recon unit’s view, each building is identified as O1, O2, O3, …, and ON. The position of the Oi is defined as (xi, yi). If the position of the recon unit is defined as (rx, ry), the vector for each building is defined as Vi(xi-rx, yi-ry). V Rotate CCW with 80 degree, the final vector is the direction of the recon unit.
<img src="https://github.com/chc2212/Xelnaga-Starcraft-game-AI-bot-AIIDE2014/blob/master/p4.png" width = "400" align="Left">
<img src="https://github.com/chc2212/Xelnaga-Starcraft-game-AI-bot-AIIDE2014/blob/master/Picture3.png" width = "350">

* Average of survival time of scouting unit (Xelnaga)

<img src="https://github.com/chc2212/Xelnaga-Starcraft-game-AI-bot-AIIDE2014/blob/master/Picture4.png" width = "300">

* Xelnaga (Green) vs. Skynet
 

<img src="https://github.com/chc2212/Xelnaga-Starcraft-game-AI-bot-AIIDE2014/blob/master/scouting.gif" width = "450">

##Influence map and confidence system
The influence map representation was adopted to spatially analyze the influence of units. Through influence map, each unit has confidence and it is used to judge status of units in various situations.   
* Confidence of each unit by influence map

<img src="https://github.com/chc2212/Xelnaga-Starcraft-game-AI-bot-AIIDE2014/blob/master/p3.gif">
* Searching effectively attact point for area attack (attack to multiple units at once)

<img src="https://github.com/chc2212/Xelnaga-Starcraft-game-AI-bot-AIIDE2014/blob/master/p1.gif">
* Judging whether an unit is in danger and order fleeing 

<img src="https://github.com/chc2212/Xelnaga-Starcraft-game-AI-bot-AIIDE2014/blob/master/p2.gif" width = "350">
<img src="https://github.com/chc2212/Xelnaga-Starcraft-game-AI-bot-AIIDE2014/blob/master/p6.gif" width = "350">

* Effective area attack (psionic storm) using influence map


<img src="https://github.com/chc2212/Xelnaga-Starcraft-game-AI-bot-AIIDE2014/blob/master/storm.gif" width = "400">


#Results
##Competition Results
<img src="https://github.com/chc2212/Xelnaga-Starcraft-game-AI-bot-AIIDE2014/blob/master/pic1.png" width="500">
##Xelnava vs Human
The result of Xelnaga (2011 version) vs. Human (random players in Battle.net) is as follows. 
<img src="https://github.com/chc2212/Xelnaga-Starcraft-game-AI-bot-AIIDE2014/blob/master/XelnagaHuman2.png" width="500">

#References
* [H.-S. Park, **H.-C. Cho**, K.-Y. Lee, and K.-J. Kim, “Prediction of early stage opponent strategy for StarCraft AI using scouting and machine learning,” Workshop at SIGGRAPH ASIA (Computer Gaming Track), pp. 7-12, 2012.](http://cilab.sejong.ac.kr/home/lib/exe/fetch.php?media=public:paper:wasa_2012_park.pdf) 
* [**H.-C. Cho**, and K.-J. Kim, “Design and evaluation of intelligence architecture for RTS games: Case Study of StarCraft,” Fall Conference of Korea Culture & Contents Technology Association, 2012.](http://cilab.sejong.ac.kr/home/lib/exe/fetch.php?media=public:paper:2012:ctkorea_2012_ho_chul_cho.pdf)
* AAAI AIIDE RTS game AI competitions (https://webdocs.cs.ualberta.ca/~cdavid/starcraftaicomp/)
* IEEE CIG RTS game AI competitions (http://cilab.sejong.ac.kr/sc_competition2015/)

Contact:            Ho-Chul Cho <chc2212@naver.com>, In-Seok Oh <ohinsuk@naver.com>, Kyung-Joong Kim <kimkj@sejong.ac.kr>

Submission Type:    Standalone dll module

File I/O:           Xelnaga uses the folders ('bwapi-data/read' and 'bwapi-data/write'). 

Libraries:          BWAPI 3.7.4 (included in submission)

                    BWTA (included in submission)

Web-Site : https://code.google.com/p/xelnaga/


Compilation Instructions: 



- Xelnaga_cig2013\Xelnaga\Xelnaga.sln in MSVC++ 2008 Express Edition


- Build solution in Release mode


The resulting Xelnaga_cig2013\Release\Xelnaga.dll is the dll binary to use for BWAPI.


(Note: To use FILE I/O, you have to make folders ('bwapi-data/read' and 'bwapi-data/write'), both of which will be in the standard location under the StarCraft root.



-------------------------------------------------------------------------------------- 

Xelnaga (BWAPI 3.7.4)


AIIDE 2014 version(add-functions)
 
- This bot includes various strategy and micromanagement systems of previous version of Xelnaga. It records game result by using file I/O and changes system based on previous game result.



cig2013 version(add-functions)
 

- observing system : We extracts information of enemy from scouting data. In order to get successful observation data, our scouting unit must survive for a long time. So we have created movement of the unit.  

 
- attack unit control : We have calculated the number of enemy units and our units around our each unit. So, we can know the dangerous level of each unit and do appropriate control for them.

 
- auto-build : We have implemented automatic build order generation system by analyzing replays.


 

cig2011 version & overview 

 

Starcraft is one of the most popular games in Korea. There are pro-gamers and even proleagues for the game. I have also played starcraft for a long time and gained lots of information about it.
 
Based on my abundant infomation about the game, I have found not only the strategies for winning but also cunning tactics that hardly require complex artificial intelligence.


-----------------------------------------------------------------------------------------------------------

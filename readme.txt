Make sure you read this file carefully before running Casaran Scheduler and follow all instructions exactly.  In order for Casaran Scheduler to run, you must have the scores input file set up properly with the correct name.  If that file does not exist, Casaran Scheduler will not be able to produce a table or a schedule for the following matchday. If that or any other input file is set up incorrectly, Casaran Scheduler may return unpredictable results.

-------
Running Casaran Scheduler
-------

To run Casaran Scheduler, you must have the current version of Java installed on your computer. The file that you need to run is called "CasaranScheduler.class". If you're using Windows, run "CasaranScheduler.bat" instead. If you're using another operating system, load a command prompt, cd into the appropriate directory and type "java CasaranScheduler". This file should work on any computer that has Java 8 or later installed. If you want to run the test file under Linux, delete scores.txt and rename scores_linux.txt to scores.txt.

NOTE: If you attempt to run Schedule.class, Score.class or Table.class, nothing will happen because those files contain code used by Casaran Scheduler to store data internally. If you delete any of those files, Casaran Scheduler will not work properly.

-------
Accessing Output
-------

Casaran Scheduler outputs three things into output.txt whenever it is run. Firstly, it produces a table based on the scores provided. Second, it produces a list of matchups based upon that table. Third, it produces a list of each team's opponents so far.

In the list of matchups, you will notice that some matchups are *ed on both sides. This is what Casaran Scheduler does when it flags a matchup as a rematch of a previous matchup. When you see *ed matchups, you should make swaps based upon the table and the list of past opponents to remove rematches from the schedule. If multiple different swaps are possible, make the swap that causes the least change in the relative strength of opposition of each team involved.

-------
scores.txt
-------

The scores.txt file is a file that should contain results in the format:

[Team 1 Name] [Team 1 Score]-[Team 2 Score] [Team 2 Name]

If you have any games that went to an overtime of any sort and this is designated in the score, you must adjust the score into the above format. An example of what that format actually looks like in practice is:

West Saintland 2-2 Free Republics

-------
skills.txt
-------

The skills.txt file contains a list of teams followed by their skill. It is used in the sort order just before RNG and consists of a number of lines in the following format:

Saintland;30.81

Put the name of the team before the semi-colon and the team's rank, RP bonus or rank + RP bonus afterward.

This file is optional. If teams are included in this file that didn't play any games, Casaran Scheduler will place them in the table. If this file is blank, Casaran Scheduler will just move on to RNG.

-------
Sort Order
-------

This version of Casaran Scheduler supports a single Sort Order (also known as "tiebreakers") which are as follows:

Points (3 for a win, 1 for a draw)
Strength of Victory (3 * points earned by teams beaten + points earned of teams drawn)
Strength of Schedule (points earned by all opponents)
Goal/Point/Run/Korf Difference (how many more goals/points/runs/korfs/whatever they're called for that particular sport you scored than your opponent)
skills.txt (the numbers contained in that file for each team)
RNG (Casaran Scheduler generates what is known as a random boolean which has a 50% chance of being true and a 50% chance of being false and whichever team is ranked higher in the table depends on whether it is true or false)

-------
Note Regarding the Table
-------

By default, Casaran Scheduler produces tables that contain PF, PA and PD (Points For, Points Against and Point Difference). If you're scorinating a sport where teams score goals or runs or korfs or something else instead of points, change the letters accordingly.

-------
License
-------

Casaran Scheduler is Copyright 2017 to the NationStates.net user behind the nations Saintland, Free Republics, Nordernious, Falatulu and Ilyseum (amongst others).  Casaran Scheduler is open-source software, licensed to all who download it for any non-commercial use.  Full permission is granted to modify or re-use the source code of this program for non-commercial purposes, so long as proper credit is given.  Full permission is also granted to redistribute this program as long as it is distributed with this readme file intact and is distributed at no cost to the end user.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY, even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.


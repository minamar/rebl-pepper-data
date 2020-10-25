
# General information

### 1. Title of Dataset: : 

REBL_Pepper/executable_animations



### 2. Contact

Name: Mina Marmpena	

Institution: University of Plymouth, UK

Email: asimina.marmpena@plymouth.ac.uk



### 3. Date of data collection: 
2017-2019



### 4. Geographic location of data collection: 

SoftBank Robotics Europe, Paris, France



### 5. Information about funding sources that supported the collection of the data: 

European Commission (EU), APRIL 674868, Applications of Personal Robotics for Interaction and Learning




# Sharing/access information

### 1. Licenses/restrictions placed on the data: 


Shield: [![CC BY 4.0][cc-by-shield]][cc-by]

This work is licensed under a
[Creative Commons Attribution 4.0 International License][cc-by].

[![CC BY 4.0][cc-by-image]][cc-by]

[cc-by]: http://creativecommons.org/licenses/by/4.0/
[cc-by-image]: https://i.creativecommons.org/l/by/4.0/88x31.png
[cc-by-shield]: https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg



### 2. Recommended citation for this dataset: 

<a id="1">[1]</a> 
Marmpena M., Lim, A., and Dahl, T. S. (2018). How does the robot feel? Perception of valence and
arousal in emotional body language. Paladyn, Journal of Behavioral Robotics, 9(1), 168-182.
[DOI](https://doi.org/10.1515/pjbr-2018-0012)




# File list
The executable_animations set is part of the public animation library created 
by [SoftBank Robotics](https://www.softbankrobotics.com) for the Pepper robot. 
The following have been used and tested with NAOqi Python SDK 2.5 and Choregraphe 2.5.
This directory includes the following:


1. ```plymouthemotionanimationset.cbl```
		
For preview in Choregraphe: You can open it by using the Open Icon 	in the Box 
Libraries panel in Choregraphe. If you click on The animation, you can preview 
it in the Inspector panel.


2. ```plymouthemotionanimationset```

To upload the animations on the robot so that you can run them from a naoqi 
script (with ```session.service("ALAnimationPlayer"))```,	you click Open project and 
browse to the plymouth-animations.pml file. This will load the project that 
includes the animations. Then click *Package and install current project to the 
robot* in the Robot applications panel of Choregraphe. 




# Executing the animations

1. In Python we used the following dictionary to call the animations:

		anim_list = {
			1: "Positive/Calm/Happy_4",	
			2: "Positive/Calm/Interested_2", 
			3: "Positive/Calm/Joy_1",	
			4: "Positive/Calm/Loving_01",	
			5: "Positive/Tired/Confident_1", 
			6: "Positive/Tired/Heat_1", 
			7: "Positive/Tired/Optimistic_1",	
			8: "Positive/Tired/Peaceful_1",	
			9: "Positive/Excited/Content_01", 
			10: "Positive/Excited/Excited_01",	
			11: "Positive/Excited/Happy_01",
			12: "Positive/Excited/Joyful_01", 
			13: "Negative/Calm/Angry_3",	
			14: "Negative/Calm/Frustrated_1",	
			15: "Negative/Calm/Hot_1",	
			16: "Negative/Calm/SadReaction_01",
			17: "Negative/Excited/Angry_4",	
			18: "Negative/Excited/Fear_1",	
			19: "Negative/Excited/Fearful_1",	
			20: "Negative/Excited/Sad_01",	
			21: "Negative/Tired/Bored_01",
			22: "Negative/Tired/Disappointed_1",	
			23: "Negative/Tired/Lonely_1",	
			24: "Negative/Tired/Shocked_1",	
			25: "Neutral/Calm/AskForAttention_3",	
			26: "Neutral/Calm/Chill_01",
			27: "Neutral/Calm/Puzzled_1",	
			28: "Neutral/Calm/Relaxation_2",	
			29: "Neutral/Excited/Curious_01",
			30: "Neutral/Excited/SurprisedBig_01",	
			31: "Neutral/Excited/Surprised_01",
			32: "Neutral/Excited/Surprised_1",	
			33: "Neutral/Tired/Alienated_1",	
			34: "Neutral/Tired/Hesitation_1",	
			35: "Neutral/Tired/Innocent_1",	
			36: "Neutral/Tired/Stretch_2",	
		}



2. To call any animations for execution from a naoqi script:

		animation_player_service = session.service("ALAnimationPlayer")
		animation_player_service.run("plymouth-animations-xxxxxx/"+"Positive/Calm/Happy_4")

	where ```plymouth-animations-xxxxxx``` is your Application ID (found in the project properties).




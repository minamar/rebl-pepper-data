
# General information

### 1. Title of Dataset: 

REBL_Pepper/original_animations



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

<a id="2">[2]</a> 
Marmpena M., Lim, A., Dahl, T. S., and Hemion, N. (2019). Generating robotic emotional body
language with Variational Autoencoders. In Proceedings of the 8th International Conference
on Affective Computing and Intelligent Interaction (ACII), pages 545–551.
[DOI](https://doi.org/10.1109/ACII.2019.8925459)

<a id="3">[3]</a> 
Marmpena M., Garcia, F., and Lim, A. (2020). Generating robotic emotional body language of
targeted valence and arousal with Conditional Variational Autoencoders. In Companion of
the 2020 ACM/IEEE International Conference on Human-Robot Interaction, HRI ’20, page
357–359. [DOI](https://doi.org/10.1145/3371382.3378360)




# File list

	- data_raw.csv


	- data_augmented.csv


	- labels_raw.csv


	- labels_augmented.csv 




# Methodological information

### 1. Description of methods used for collection: 

	- data_raw.csv: 	

To obtain these data, we had the 36 hand-designed animations executed on a 
physical Pepper robot with a speed of 15 fps and we used ```ALMotion::getAngles()``` 
and ```ALLeds::getIntensity()``` functions from Naoqi 2.5 SDK to record the values of 
the joints and eye LEDs with a sampling rate of 25 fps. Before the recording, 
we ensured all animations begin and end with the StandInit position for 
a clear onset and offset [[2]](#2), [[3]](#3). 
				
		
	- labels_raw.csv:	
	
For each animation, we acquired a label of valence and arousal in [0,1] by 
averaging the ratings of 20 participants, after they had been checked for intra-
and inter-rater reliability [[1]](#1). 



### 2. Methods for processing the data: 

	- data_augmented.csv:	

The raw data were augmented by mirroring each posture from left to right and 
vice versa. This augmentation, besides providing us with more training data, 
it was also a way to avoid biases related to posture orientation with respect 
to the vertical axis of the body. More specifically, we assumed  that left or 
right orientation of the body is not significant in emotion recognition, as 
opposed to motions on the horizontal axis (e.g. leaned head upward or downward).
To create a mirrored posture we swapped the values of the entire chain of arm 
joints between the left and right arm. For the roll and yaw joints of the arm, 
we had to additionally invert the signs of their values because the ranges of 
these joints had inverse signs between left and right. Furthermore, we also 
mirrored the head yaw and hip roll joints since these also move right and left 
with respect to the vertical axis of the body (only the signs were inverted).
The animation id for the mirrored postures is indicated with a '_tr' suffix 
(i.e., transformed) in the name tag [[2]](#2), [[3]](#3).


	- labels_augmented.csv: 
		
The original labels were also augeneted to include the animation tags ending 
in -'_tr'.




# Data-specific information 

## Files: data_raw.csv, data_augmented.csv

1. Number of variables: 66 (17 joints, 48 LEDs, 1 animation id)



2. Number of cases/rows (without header): 
		
	- ```data_raw.csv```: 		5074
		
		
	- ```data_augmented.csv```: 	10148



3. Variable List: 

	- id: Animation name tag. Assigned by the animators during the design phase.


	- Pepper's joints (17 values in radians): 

			HeadPitch, HeadYaw, HipPitch, HipRoll, KneePitch, 
			LElbowRoll, LElbowYaw, LHand, LShoulderPitch, LShoulderRoll, LWristYaw, 
			RElbowRoll, RElbowYaw, RHand, RShoulderPitch, RShoulderRoll, RWristYaw

	
	- Pepper's eye LEDs (48 values flattened from 16 LEDs with RGB values):
		
			R0R,R0G,R0B,L0R,L0G,L0B,
			R1R,R1G,R1B,L1R,L1G,L1B,
			R2R,R2G,R2B,L2R,L2G,L2B,
			R3R,R3G,R3B,L3R,L3G,L3B,
			R4R,R4G,R4B,L4R,L4G,L4B,
			R5R,R5G,R5B,L5R,L5G,L5B,
			R6R,R6G,R6B,L6R,L6G,L6B,
			R7R,R7G,R7B,L7R,L7G,L7B




## Files: labels_raw.csv, labels_augmented.csv

1. Number of variables: 3



2. Number of cases/rows: 
		
	- ```labels_raw.csv```: 36
	

	- ```labels_augmented.csv```: 72



3. Variable List: 

	- **id**:		Animation name tag. Assigned by the animators during the design phase.	

	
	- **valence**:	Valence ratings averaged over participants. Valence is a core affect
					dimension that indicates how pleased or displeased the robot appears.
					A continuous value in [0,1] where 0 is related to "displeased" and 
					1 to "pleased".


	- **arousal**:	Arousal ratings averaged over participants. Arousal is a core affect
					dimension that indicates how activated or deactivated the robot appears.
					A continuous value in [0,1] where 0 is related to "deactivated" and 
					1 to "activated".





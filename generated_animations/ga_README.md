
# General information

### 1. Title of Dataset: 

REBL_Pepper/generated_animations



### 2. Contact

Name: Mina Marmpena	

Institution: University of Plymouth, UK

Email: asimina.marmpena@plymouth.ac.uk



### 3. Date of data generation: 
2019



### 4. Geographic location of data generation: 

SoftBank Robotics Europe, Paris, France



### 5. Information about funding sources that supported the generation of the data: 

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
Marmpena M., Lim, A., Dahl, T. S., and Hemion, N. (2019). Generating robotic emotional body
language with Variational Autoencoders. In Proceedings of the 8th International Conference
on Affective Computing and Intelligent Interaction (ACII), pages 545–551.
[DOI](https://doi.org/10.1109/ACII.2019.8925459)

<a id="2">[2]</a> 
Marmpena M., Garcia, F., and Lim, A. (2020). Generating robotic emotional body language of
targeted valence and arousal with Conditional Variational Autoencoders. In Companion of
the 2020 ACM/IEEE International Conference on Human-Robot Interaction, HRI ’20, page
357–359. [DOI](https://doi.org/10.1145/3371382.3378360)




# File list

		- neutral_low_LD2_130.csv
		- neutral_low_LD3_127.csv
		- neutral_medium_LD1_187.csv
		- neutral_medium_LD3_184.csv
		- neutral_high_LD1_232.csv
		- neutral_high_LD2_232.csv
    
		- negative_low_LD1_141.csv    
		- negative_low_LD2_132.csv     
		- negative_medium_LD1_186.csv  
		- negative_medium_LD2_177.csv  
		- negative_high_LD2_216.csv    
		- negative_high_LD2_225.csv     

		- positive_low_LD2_128.csv
		- positive_low_LD3_134.csv
		- positive_medium_LD1_191.csv
		- positive_medium_LD3_185.csv
		- positive_high_LD1_239.csv
		- positive_high_LD3_230.csv

		
		- labels_gen_anim.csv




# Methodological information

The 18 animation files describe the motion and eye LEDs patterns of the animations
generated with a Conditional Variational Autoencoder (CVAE). The generated animations have 
three levels of valence (negative, neutral, and positive) which were generated using 
an attribute c (equal to 0, 0.5, and 1 respectively) to condition the CVAE. Also
the generated animations have three different levels of arousal (low, medium, 
and high), which were generated using an attribute r (equal to 3, 4, and 5 
respectively) to condition the radius of sampling the latent space of the CVAE.

The directory also includes a file with valence, arousal and dominance labels 
for each of the generated animations. The labels were derived from the averaged 
ratings assigned to each animation by 20 participants.  




# Data-specific information 

## Files: 18 generated animations files 

1. Number of variables: 65 (17 joints, 48 LEDs)



2. Number of cases/rows (without header): 

		- neutral_low_LD2_130.csv:		285
		- neutral_low_LD3_127.csv:		285
		- neutral_medium_LD1_187.csv:		380
		- neutral_medium_LD3_184.csv:		380
		- neutral_high_LD1_232.csv:		475
		- neutral_high_LD2_232.csv:		475


		- negative_low_LD1_141.csv:		285
		- negative_low_LD2_132.csv:		285
		- negative_medium_LD1_186.csv: 	380
		- negative_medium_LD2_177.csv:		380
		- negative_high_LD2_216.csv:    	475
		- negative_high_LD2_225.csv:  		475

		- positive_low_LD2_128.csv:		285
		- positive_low_LD3_134.csv:		285
		- positive_medium_LD1_191.csv:		380
		- positive_medium_LD3_185.csv:		380
		- positive_high_LD1_239.csv:		475
		- positive_high_LD3_230.csv:		475



3. Variable List: 

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



## Files: labels_gen_anim.csv

1. Number of variables: 4



2. Number of cases/rows: 18



3. Variable List: 

	- **generated_animation**: Identifier of the generated animation.		

	- **valence**:	Valence ratings averaged over participants. Valence is a core affect
					dimension that indicates how pleased or displeased the robot appears.
					A continuous value in [0,1] where 0 is related to "displeased" and 
					1 to "pleased".

	- **arousal**:	Arousal ratings averaged over participants. Arousal is a core affect
					dimension that indicates how activated or deactivated the robot appears.
					A continuous value in [0,1] where 0 is related to "deactivated" and 
					1 to "activated".
	
	- **dominance**:	Dominance ratings averaged over participants. Dominance 
						is additional dimension to core affect dimensions of valence 
						and arousal. It indicates how submissive or dominant the robot 
						appears. A continuous value in [0,1] where 0 is related to "submissive" and 
						1 to "dominant".


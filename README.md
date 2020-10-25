# REBL_Pepper: A dataset of Robotic Emotional Body Language for a Pepper robot


## Overview

The REBL-Pepper dataset has been used to train a Conditional Variational Autoencoder 
for the generation of novel Robotic Emotional Body Language (REBL) for a Pepper
robot. The training set has been compiled with a selection of 36 hand-designed 
animations from a broader animation library created by 
[SoftBank Robotics](https://www.softbankrobotics.com).  

The selected animations were chosen to convey emotion through body motion, 
eye LEDs colour and patterns, and non-linguistic sounds. A user study (N=20) 
was conducted to derive reliable core affect labels for each animation. Core 
affect is defined by two dimensions: valence (displeased to pleased), 
and arousal (deactivated to activated). Valence and arousal ratings
were collected as continuous values in the interval [0,1] and they were aggregated 
across participants, for each animation [[1]](#1). 

Subsequently, the audio data were excluded and the rest of the modalities 
(motion and eye LEDs) were recorded with a sampling rate of 25 fps, augmented, 
and used to train an emotion-agnostic Variational Autoencoder [[2]](#2), 
and later a Conditional Variational Autoencoder for the generation of targeted 
emotion animations [[3]](#3). A second user study was conducted to evaluate a set
of generated animations in terms of valence, arousal, and dominance [[3]](#3). 




## Directories 

#### 1. ```executable_animations```

This directory contains files for executing the original 36 hand-designed 
animations:


* ```plymouthemotionanimationset.cbl:``` To preview the animations using the 
Choregraphe simulator for Pepper.

* ```plymouthemotionanimationset:``` To upload and execute the animations on the
robot.

* ```ea_README.md:``` Details and instructions


#### 2. ```original_animations```

This directory contains the original 36 hand-designed animations in the sampled
representation recorded directly from the physical robot in execution time. 
Furthermore, the directory contains files with the valence and arousal labels. 


* ```data_raw.csv:``` Each row represents the configuration of the 17 joints of 
the robot, as well as the 48 values describing the eye LEDs state, at a timestep 
(approximately every 0.04 secs), for each animation.  

* ```data_augmented.csv:``` The augmented version of ```data_raw.csv``` (double 
size).


* ```labels_raw.csv:``` Labels of valence and arousal for each animation in 
```data_raw.csv```.

* ```labels_augmented.csv:``` Augmented labels of valence and arousal for each 
animation in ```data_augmented.csv```.

* ```oa_README.md:``` Details and instructions



#### 3. ```generated_animations```
This directory contains 18 animations that were generated with a Conditional 
Variational Autoencoder trained with the 36 original animations.

* 18 files, one for each generated animation. The valence content of the 
generated animations was conditioned on the levels: _negative_, _neutral_ and 
_positive_. The arousal content of the generated animations was conditioned on 
the levels: _low_, _medium_, and _high_.

* ```labels_gen_anim.csv:``` Labels of valence, arousal, and dominance for each 
generated animation file.

* ```ga_README.md:``` Details and instructions 																												

#### 4. ```rebl-scripts```
Python code to run the original or generated animations (dataframes) on 
the physical robot or the Choregraphe simulator. Requires Python 2.7, pandas, 
numpy and qi. 																								


## Contact
Name: Mina Marmpena	

Institution: University of Plymouth, UK 

Email: asimina.marmpena@plymouth.ac.uk



## Date of data collection

2017-2019



## Geographic location of data collection

SoftBank Robotics Europe, Paris, France



## Funding sources 

European Commission (EU), APRIL 674868, Applications of Personal Robotics for 
Interaction and Learning



## Licence


Shield: [![CC BY 4.0][cc-by-shield]][cc-by]

This work is licensed under a
[Creative Commons Attribution 4.0 International License][cc-by].

[![CC BY 4.0][cc-by-image]][cc-by]

[cc-by]: http://creativecommons.org/licenses/by/4.0/
[cc-by-image]: https://i.creativecommons.org/l/by/4.0/88x31.png
[cc-by-shield]: https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg


## Acknowledgements

Many thanks to [Olivier Landais](http://www.stase.fr/) for his contribution to 
the preselection of the original animations as an expert animator, [Mehdi Abbana 
Bennani](https://github.com/MehdiAbbanaBennani) for his advice on the recording
of the animations, [Fernando Garcia](https://github.com/FerranGarcia) for the 
contribution to the evaluation of the generated animations, and supervisors
[Angelica Lim](https://scholar.google.com/citations?user=1jQEmPUAAAAJ&hl=en), 
[Nikolas Hemion](https://scholar.google.com/citations?user=8v_dBkgAAAAJ&hl=en), 
and [Alban Laflaquière](https://scholar.google.com/citations?user=8oiJxs0AAAAJ&hl=en)
for their guidance and support.




## References

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




# Sweep-to-Unlock-Datasets
Details for a Sweep-to-Unlock dataset used for smartphone fingerprinting based on their loudspeaker characteristics. 

# Fingerprinting Smartphones based on Loudspeaker Roll-off Characteristics

Abstract: Fingerprinting smartphones based on acoustic characteristics of their loudspeaker may have a number of applications in device-to-device authentication as well as in forensic investigations. In this work we propose an efficient fingerprinting methodology by using the roll-off characteristics of the device speaker, i.e., the transition between the low and high stopbands to the passband segment of the speaker. We extract roll-off characteristics from sweep signals, also know as chirps, that are commonly used in practice to test speaker response. This procedure appears to be more stable against variations of the volume level and allows the use of simple linear approximations, which are intuitive and easy to compute, in order to extract the fingerprint. To increase detection accuracy, on the basis of the proven performance of deep learning techniques, a convolutional and a bi-directional long short term memory neural network are further proposed and their performance demonstrated for authentication purposes. While numerous applications may be envisioned, we specifically focus on the use of speaker characteristics in relation to in-vehicle infotainment units, checking if recordings from these units can be used to fingerprint a specific phone.

# 1. Concept
We fingerprint smartphones based on their loudspeaker response to sweep signals (also known as chirps). As a potential area of application we target in-vehicle environment, a reason for which the recordings were performed with an in-vehicle Android headunit.

![image](https://user-images.githubusercontent.com/22617786/156363415-3412c8af-26f6-4a32-9590-406661994996.png)


# 2. Dataset
Dataset content The dataset is structured as described below. We provide the clean recordings as audio data (PCM or WAV) as well as the power spectrum (FFT as .txt). For recordings affected by noise, we provide only the FFT results (as .txt).

## Summary of devices and associated measurements ##

 

 No. | Phones | Label  | No. | Msr.   | Total   
---- | :------: | :------: | :-------: | :--------: | :------
1 |	Samsung Galaxy J5	| A, C and F to P |	13	| 100	| 1300
&nbsp; 	|(distinct speakers in phone)|	B, D, E	|3|	500	|1500
2 |	Samsung Galaxy S7 Edge|	S7	|1	|5	|5
3 |	LG Optimus P700	|LG|	1	|5|	5
4 |	Allview V1 Viper I	|AV	|1|	5|	5
5 |	Samsung Galaxy J5 (other)	|J5′|	1	|5|	5
6 |	Samsung Galaxy J5 (other)	|J5′′ /J5′′′|	2	|10	|20
7 |	Samsung Galaxy Note 8|	N8|	1	|10|	10
8 |	Samsung Galaxy A21s	|A21|	1	|10|	10
9 |	Samsung Galaxy Tab S7|	T7|	1|	10|	10
10 |	Xiaomi Mi A3	| X3|	1|	10|	10
11 |	Xiaomi Redmi 7A|	X7|	1|	10 | 10
12 |	Leagoo Z10	| LE|	1	|10|	10
 &nbsp;|	Total	| 	|&nbsp;|28|	 	2900|



![image](https://user-images.githubusercontent.com/22617786/156363539-dff69c4d-02cb-4398-be5a-cf29a6928d6d.png)

## Folder structure ##

** RAW RECORDINGS (folder, 131 files)** \
|------ Clean recordings identical loudspeakers (Samsung J5) \
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;       |------ speakers B, D, E (3 loudspeakers x 500 samples) \
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;       |------ speakers A to P (16 loudspeakers x 100 samples) \
|------ Clean recordings distinct loudspeakers (12 phones x 5-10 samples) 

Dataset Download Link: http://www.aut.upt.ro/~bgroza/projects/RAW_RECORDINGS.zip (2.06GB) 

** FFT EXTRACTIONS (folder, 6300 files)** \
|------ Clean recordings identical loudspeakers (Samsung J5) \
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;       |------- speakers B, D, E (3 loudspeakers x 500 samples) \
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;      |------- speakers A to P (16 loudspeakers x 100 samples) \
|------- 2-7Khz passband extracted (16 loudspeakers x 100 samples) \
|------- AWGN affected (16 loudspeakers x 100 samples) 

Dataset Download Link: http://www.aut.upt.ro/~bgroza/projects/FFT_EXTRACTIONS.zip (76.5MB)

Note that the RAW files are very large and uncut, it is advisable that you use the FFT extractions.

## File structure ##

The RAW RECORDINGS folder contains the clean recordings as audio data. For clean recordings with distinct speakers we used WAV files, each file contains one linear sweep. For clean recordings with identical speakers we used PCM files, each file contains slightly over 100 linear sweeps.

The FFT EXTRACTIONS folder contains the power spectrum of the liner sweep signal for the identical speakers (with and without noise). For each sample we build a .TXT file which contains two columns, the first column represents the frequency and the second is the amplitude of the power spectrum for the specific frequency. There are 1914 lines in each file which represent the amplitudes of the power spectrum between 700Hz and 11kHz at ~5Hz resolution.


Feel free to use our dataset for research purposes by giving credit to our paper below.
# 3. Publication
A. Berdich, B. Groza, R. Mayrhofer, E. Levy, A. Shabtai and Y. Elovici, "Sweep-to-Unlock: Fingerprinting Smartphones based on Loudspeaker Roll-off Characteristics", IEEE Transactions on Mobile Computing, accepted 2021. 


```
@article{BerdichGMLSE,
title={Sweep-to-Unlock: Fingerprinting Smartphones based on Loudspeaker Roll-off Characteristics},
author={Berdich, Adriana and Groza, Bogdan and Mayrhofer, Rene and Levy, Efrat and Shabtai, Asaf and Elovici, Yuval},
journal={IEEE Transactions on Mobile Computing},
year={2021},
publisher={IEEE}
}
```

# 4. Contact
For any questions about our work and dataset, don't hesitate to contact us (adriana.berdich at aut.upt.ro or bogdan.groza at aut.upt.ro).


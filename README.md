# Project description
The UofM-Fault-Simulation-Testbed-for-Rotating-Equipment consists of a platform capable of testing mechanical faults in rotating machines in different degrees of severity. The goal of this testbed is to induce faults on the rotating machine demonstrating how the severity of the mechanical failure affects the machine's behavior, simulating a degradation condition in a controlled manner. Some of the faults that can be simulated on the testbed are: unbalance, mechanical looseness at one bearing, mixed misalignment (parallel misalignment and angular misalignment), cracked shafts, and general ball-bearing faults. The fault simulator testbed is presented in [image 1](https://drive.google.com/file/d/13Zrx77L_z7o0V7Fgm34pfWxXfzqFMriP/view?usp=sharing).

## Database description
Although multiple faults can be simultaneously induced on the testbed, the database is composed of data sets with vibration signals of two distinct rotating machines ([image 2](https://drive.google.com/file/d/1KVbWYW7mL9nqJiGLbRcqub3Ulmi3ViM2/view?usp=sharing)) operating in several degradation conditions of unbalance and mechanical looseness. The rotating machines selected for this database are significantly different, as depicted in [image 2](https://drive.google.com/file/d/1KVbWYW7mL9nqJiGLbRcqub3Ulmi3ViM2/view?usp=sharing). Machine 1 has a 10 $mm$ diameter shaft 960 $mm$ long and two aluminum disks of approximately 3.4 $kg$, width of 18 $mm$, and outer diameter of 150 $mm$  attached to the machine shaft to increase system's inertia. On the other hand, machine 2 is composed of a 10 $mm$ diameter shaft 660 $mm$ long with one disk attached to the shaft. When both machines are compared, it can be concluded that machine 1 presents higher inertia and lower stiffness when compared to machine 2, leading to significantly different dynamic behavior, which is depicted in [image 3](https://drive.google.com/file/d/1JB5ilGumk_LdCRRZFJ5Z07NGvhI0D-Y-/view?usp=drive_link).

To build the database, the vibration of both machines is collected when the systems experience different unbalance or mechanical looseness levels. All data sets are composed of 4 time-series displacement signals (one from each inductive sensor) of at least 30 $s$ duration recorded at a sample-frequency of 10 $kHz$. The testbed presents two IF6030 inductive analog sensors near each bearing, accurately measuring mechanical vibration in vertical and horizontal directions using National Instrument LabView and a myRIO-1900. Each data set experimentally demonstrates the machine behavior for a unique severity of one mechanical fault, originating one distinct operating condition per data set, as shown in [image 4](https://drive.google.com/file/d/12DjziPI3JOqYJiGK-tZdmU2gSAwgfBD3/view?usp=sharing). The rule of thumb is that the higher the operating condition number, the higher the severity of the fault.

The signals are in mV and need to be converted to mm using the sensor and data acquisition system sensitivity. 
   
* myrio_sen    = 1/0.41 # [mV/mV] Data acquisition system sensitivity
* sens_prob1   = 1/3100 # [mm/mV] Prob 1 sensitivity 
* sens_prob2   = 1/3021 # [mm/mV] Prob 2 sensitivity
* sens_prob3   = 1/3100 # [mm/mV] Prob 3 sensitivity 
* sens_prob4   = 1/3100 # [mm/mV] Prob 4 sensitivity


## Individual Data set description 

All the data sets are in a .lvm format. The way the data is saved on the .lvm file is presented below:

**OBS 1:** Refer to [image 1](https://drive.google.com/file/d/13Zrx77L_z7o0V7Fgm34pfWxXfzqFMriP/view?usp=sharing) to identify the probes on the actual system.

**OBS 2:** The file  [Converting .lvm file to dataframe](https://github.com/ipereiraumich/UofM-Fault-Simulation-Testbed-for-Rotating-Equipment/blob/main/Converting%20.lvm%20file%20to%20dataframe) shows how to extract data from a .lvm file to a Pandas dataframe.

### Machine 1 -  Unbalance - Rotating speed: **750 rpm** - Data set can be downloaded [here](https://drive.google.com/file/d/1rjrSVkfxXYo6RFrCbwi5fmAUTP33p9r8/view?usp=drive_link).

* prob 1 = **data[:,2]** # Extracting experimental data from the dataframe - Vertical proximity prob 1
* prob 2 = **data[:,1]** # Extracting experimental data from the dataframe - Horizontal proximity prob 2
* prob 3 = **data[:,4]** # Extracting experimental data from the dataframe - Vertical proximity prob 3
* prob 4 = **data[:,3]** # Extracting experimental data from the dataframe - Horizontal proximity prob 4

### Machine 1 -  Mechanical Looseness - Rotating speed: **750 rpm** - Data set can be downloaded [here](https://drive.google.com/file/d/1xhyyNhh-xeeVCFSAPXpUkuMj_PWIk0vK/view?usp=sharing).

* prob 1 = data[:,1] # Vertical proximity sensor 1
* prob 2 = data[:,2] # Horizontal proximity sensor 2
* prob 3 = data[:,3] # Vertical proximity sensor 3
* prob 4 = data[:,4] # Horizontal proximity sensor 4

### Machine 2 -  Unbalance - Rotating speed: **1000 rpm** - Data set can be downloaded [here](https://drive.google.com/file/d/14CaRC3DGBYduW_lbYqBNNCiYPBGcOKYS/view?usp=drive_link).

* prob 1 = data[:,1] # Vertical proximity sensor 1
* prob 2 = data[:,2] # Horizontal proximity sensor 2
* prob 3 = data[:,3] # Vertical proximity sensor 3
* prob 4 = data[:,4] # Horizontal proximity sensor 4

### Machine 2 -  Mechanical Looseness - Rotating speed: **1000 rpm** - Data set can be downloaded [here](https://drive.google.com/file/d/13RKKHxWZWS6TbSUywhX147wwbV2qcLME/view?usp=sharing).

* prob 1 = data[:,1] # Vertical proximity sensor 1
* prob 2 = data[:,2] # Horizontal proximity sensor 2
* prob 3 = data[:,3] # Vertical proximity sensor 3
* prob 4 = data[:,4] # Horizontal proximity sensor 4



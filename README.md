# Edge AI powered Woman Violence Detection

## Table of Contents ##

* [Introduction](https://github.com/youcode-in/Violence-against-Women#introduction)
* [The Problem](https://github.com/youcode-in/Violence-against-Women#the-problem)
  * [Analysis of the Problem](https://github.com/youcode-in/Violence-against-Women#analysis-of-the-problem)
* [Proposed Solution](https://github.com/youcode-in/Violence-against-Women#proposed-solution)
  * [Solution Workflow](https://github.com/youcode-in/Violence-against-Women#solution-workflow)
  * [Algorithms](https://github.com/youcode-in/Violence-against-Women#algorithms)
  * [Evaluation of the Proposed Solution](https://github.com/youcode-in/Violence-against-Women#evaluation-of-the-proposed-solution)
* [Deployment in NVIDIA Deepstream](https://github.com/youcode-in/Violence-against-Women#deployment-in-nvidia-deepstream)
* [Getting Started](https://github.com/youcode-in/Violence-against-Women#getting-started)

- - - -

## Introduction ##

Jetson deepstream based Project to detect Violence against Women.We have built a custom code on top of the Human Pose estimation model to detect human poses during Violence and classify them as  

* Neck Grab 
* Punch 
* Kick 
* Lying Down 
* Normal Scenario 
* Slap

- - - -

## The Problem ##

### Analysis of the Problem ###

<img src="https://github.com/youcode-in/Violence-against-Women/blob/main/resources/Analysis%201.jpg">

- - - -

<img src="https://github.com/youcode-in/Violence-against-Women/blob/main/resources/UN%20Women.jpg" width="20%">

#### Key Facts ####

* Globally, 35 per cent of women have ever experienced physical and/or sexual intimate partner violence, or sexual violence by a non-partner.
* 137 women are killed by a member of their family every day
* Less than 40 per cent of the women who experience violence seek help of any sort.
* At least 155 countries have passed laws on domestic violence, and 140 have laws on sexual harassment in the workplace
* 15 million adolescent girls worldwide, aged 15–19 years, have experienced forced sex. 
* In the Middle East and North Africa, 40–60 per cent of women have experienced street-based sexual harassment


- - - -      
      
<img src="https://github.com/youcode-in/Violence-against-Women/blob/main/resources/National%20Crime%20Records%20Bureau.jpg">      


As per the Report from Government of India __National Crime Records Bureau (NCRB)__ published on __September 29, 2020__

2018 Total Number of Cases of Crime Against Women = 3,78,236 cases

2019 Total Number of Cases of Crime Against Women = 4,05,861 cases 

India recorded an average of 87 rape cases daily in 2019 

2018 Reported Rape cases= 33,356 

2019 Reported Rape cases = 32,033 (7.3% of all crimes against women) 

Majority of these cases under Indian Penal Code were registered under 
‘cruelty by husband or his relatives’ (30.9 per cent), 

‘Assault on women with intent to outrage her modesty’ (21.8 per cent),

‘kidnapping and abduction of women’ (17.9 per cent), the NCRB data for 2019 showed

The crime rate registered per lakh women population stood at 62.4 in 2019 in comparison with 58.8 in 2018, it showed

- - - -

## Proposed Solution ##

<img src="https://github.com/youcode-in/Violence-against-Women/blob/main/resources/Violence%20against%20Women.jpg">

| Topic | Description |
| ---------- | ---------- |
| Goal of the Project | How Latest Technologies Like AI can be leveraged to detect  crime against Women. <br> AI Powered Violence Detection from Real-time CCTV Footage to create a smart, safe environment for women. |
| What is Unique about this Project | Probably first of its kind Initiative in India ( AI for social good ). <br> To identify dangerous environments and respond effectively to the violent interactions with Women. |
| Benefits | The integration of AI powered violence detection technology into the  existing CCTV surveillance system allows to: <br> Dramatically reduce the processing time of the CCTV footages. <br> Free surveillance staff to cope with major non-monitoring security tasks. <br> Improve decision-making. <br> Help in law enforcement and crime prevention. <br> Extract revealing insights from visual data. |
| Areas of Application | Schools, Parks, Airports, Railway Stations , Indoor and Outdoor public spaces, Shopping Malls entertainment venues etc. |

### Solution Workflow ###Prerequisites

<img src="https://github.com/youcode-in/Violence-against-Women/blob/main/resources/Workflow%20Visualization.jpeg">

<img src="https://github.com/youcode-in/Violence-against-Women/blob/main/resources/Solution%20Workflow.jpeg">

### Algorithms ###

__The body pose model provides a total amount of 18 keypoints per person.__

<p float-"left">

<img src="https://github.com/youcode-in/Violence-against-Women/blob/main/resources/Women%20Violence%20Kick%20Algorithm.jpg" width="48%">

<img src="https://github.com/youcode-in/Violence-against-Women/blob/main/resources/Women%20Violence%20Slap%20Algorithm.jpg" width="48%">

</p>

<p float-"left">

<img src="https://github.com/youcode-in/Violence-against-Women/blob/main/resources/Women%20Violence%20Neckgrab%20Algorithm.jpg" width="48%">

<img src="https://github.com/youcode-in/Violence-against-Women/blob/main/resources/Women%20Violence%20Punch%20Algorithm.jpg" width="48%">

</p>

<img src="https://github.com/youcode-in/Violence-against-Women/blob/main/resources/Women%20Violence%20Lying%20Algorithm.jpg" width="48%">

### Evaluation of the Proposed Solution ###

<a href="https://youtu.be/yTFO9huYuPo" target="_blank"><img src="https://github.com/youcode-in/Violence-against-Women/blob/main/resources/AI%20powered%20Women%20Violence%20Detection.jpeg" 
alt="AI powered Women Violence Detection" width="75%" /></a> 

- - - -

## Deployment in NVIDIA Deepstream ###

You will need 

1. DeepStreamSDK 5.0

2. CUDA 10.2

3. TensorRT 7.x

Note : We have tested and deployed in Jetson Nano.


## Getting Started:

To get started, please follow these steps.

1. Install [DeepStream](https://developer.nvidia.com/deepstream-sdk) on your platform, verify it is working by running deepstream-app.

2. Clone the repository preferably in `$DEEPSTREAM_DIR/sources/apps/sample_apps`.

3.Download the [Nvidia deepstream pose estimation models](https://drive.google.com/drive/folders/1vNVxDTPC-mRLIQcQ91gEjxit0aNLeIGU?usp=sharing)

4. Replace the OSD binaries (x86 or Jetson) in `$DEEPSTREAM_DIR/libs` with the ones provided in this repository under `bin/`. Please note that these are not inter-compatible across platforms.

5. Compile the program
 
 ```
  $ cd deepstream-pose-estimation/
  $ sudo make
  $ sudo ./deepstream-pose-estimation-app <file-uri> <output-path>
```

6. The final output is stored in 'output-path' as `Pose_Estimation.mp4`

7. In the deepstream_pose_estimation_app.cpp file only detects kicks on night vision. so if you check the other violence action use the different_violences folder codes.

NOTE: If you do not already have a .trt engine generated from the ONNX model you provided to DeepStream, an engine will be created on the first run of the application. Depending upon the system you’re using, this may take anywhere from 4 to 10 minutes.

## Conclusion ##


We have presented a technique for violence detection on women based on human Pose Tracking.This is done for demonstration purpose. Further work is needed to improve the Violence Classification Algorithm. We have made this as an open source so that more people can work on it and bring real solutions sooner than later.

- - - -

## References ##


__India Today News - No country for women: India reported 88 rape cases every day in 2019__
__http://bit.ly/2PcN5hr__

__Reuters News - One woman reports a rape every 15 minutes in India__
__http://reut.rs/3dPLYOW__

__Reuters News - Statistics on rape in India and some well-known cases__
__http://reut.rs/3krzfmQ__

__Average 87 Rape Cases Daily, Over 7% Rise in Crimes Against Women in 2019: NCRB Data__
__http://bit.ly/3uMLyPE__

__UN Women__
__https://www.unwomen.org/en/what-we-do/ending-violence-against-women/facts-and-figures__

__https://interactive.unwomen.org/multimedia/infographic/violenceagainstwomen/en/index.html#home-2__





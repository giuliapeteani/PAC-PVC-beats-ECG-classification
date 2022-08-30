# PAC-PVC-beats-ECG-classification

The analysis of ECG signals allows to infer very significative information on a patient’s health. If an ECG signal shows a heartbeat rhythm which is irregular, either faster (>100 beats/min), or slower (<60 beats/min) than what is physiologically classified as normal, this falls into the definition of cardiac arrhythmia


Normal cardiac rhythm can be occasionally interrupted by a beat that occurs before the regular time of the next sinus beat, and this is described as a premature beat or premature contraction. The premature beat can be classified into two types depending on the location of the focus, which is different from the Sinus Node (SN):

• **Premature Atrial Contraction (PAC)** (also known as atrial premature beat (APB)) if its origin is in the atria or the AV node;

• **Premature Ventricular Contraction (PVC)** (also known as ventricular premature beat (VPB)) if its origin is in the ventricles;


<p align="center">
<img src=https://user-images.githubusercontent.com/92247654/187536651-48b3200a-de17-4bf9-b7ac-5ff778aa94bd.png width="500" height="300">
</p>



## METHOD: HYBRID APPROACH
1. **Beat windowing**: When dealing with a deep learning approach, the feature extraction block is data driven, so performed by the neural network which receives as input the single beats.
The beats have been extracted from ECG signals by taking a window which spans from –2s to +2s starting from the R peak of each beat. The 2 leads were fed separately to the network. 
2. **Model**: hybrid approach has been developed, which consists in the definition of a deep learning network fed by windowed beats, whose last Dense layer receives as inputs the ECG temporal features manually extracted. 


![image](https://user-images.githubusercontent.com/92247654/187540272-8d6f9f88-8d30-4682-972c-5c4021b29e2f.png)
<br/>


## K-FOLD CROSS VALIDATION RESULTS
The performance metrics were computed comparing the true known labels with the predictions’ vector obtained as the concatenation of the outputs of the 13 models resulting from the 13 different train-test splits according to k-fold cross validation method.


<p align="center">
<img src=https://user-images.githubusercontent.com/92247654/187540973-43904134-4015-48d7-b5db-3745a98d043c.png width="400" height="350">
</p>


















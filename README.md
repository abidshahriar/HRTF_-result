#Update Oct , 2025: 
Please note I've been currently working towards finishing this research as a research article. There is a huge level of progress i have made for this reseearch which will address a gap : [1] Perpetual Benchmarking of HRTF [2] Benchmar

This framework provides both an objective and a perceptual assessment . The first benchmark is an objective spectral analysis, comparing key directional features and notch patterns against the distribution found in the ARI database . The second, more novel benchmark is a perceptual evaluation using a custom-trained machine learning model. This model effectively simulates an 'average listener' from the ARI database and answers the question: "If this average listener heard sounds filtered by the simulated HRTF, where would they perceive the sound to be coming from?" By comparing the model's prediction to the true location, we obtain a quantitative measure of the HRTF's perceptual plausibility and its deviation from a population average.

( Im completing this manuscript and I will soon post a preprint on this), I am happy to provide an pre-publication insights or results and methods upon proper request ) 

----------

Previously (last updated 2 years ago): 

# Measuring_HRTF
In this repository, I have shared some of the results that I have accumulated for the HRTF simulation. (Still Updating )
Human beings possess the natural ability to perceive binaural sound due to the presence of two ears. Reproducing three-dimensional sound in a virtual space through headphones necessitates complex calculations. These calculations have been simplified by the utilization of head-related transfer functions (HRTFs). Personalized HRTFs, which are computed using various mathematical techniques and methods, including numerical calculations and machine learning, are now widely accessible. In this research, I conducted research on calculating the HRTF of a person's scanned head, generated HRTF data, and explored the methodology behind it. Additionally, I investigated why personalized HRTF data can produce a more immersive sound experience compared to commercial analog ICs in the context of 3D binaural rendering.

Methodology:   HRTF Measurement is a bit complicated method that requires robust hardware and system to calculate and measure it. Moreover, HRTF varies from person to person due to the variation of Pinna Structure and face geometry. Also, the conventional HRTF measurement with hardware takes one person to sit steadily in a measurement lab for much time which could be a little discomforting from person to person. To make the calculation easier a computational-based method is now widely used. Basically, there are equations to calculate Pressure on the mesh structure.  
To get a mesh of the head at first, I scanned a person’s face with the Help of an iPhone’s depth-sensing camera at first and then these cloud points were transformed to construct a Mesh of a head-on which I will conduct the calculation. The process of capturing this Mesh of a head is not an easy process. After taking Mesh cloud point data I have processed this Mesh with the help of MeshLab and Blender for different types of post-processing and so on. Next, I took this mesh for Mesh Grading for checking and fixing any disrupted mesh structure which would rather create issues while performing HRTF calculations. These Mesh are then made structure ready for calculations and so on. After this mesh is made ready, I perform an HRTF calculation on the Mesh using a Python script. 

And finally, I have got results from this calculation that are ready for evaluation. 

# HRTF Result Obtained:
![HRIR_ARI_44100_3D (1)](https://github.com/abidshahriar/HRTF_-result/assets/64680295/32980442-b6a6-4cf2-8913-1f8c2191d661)
# Time- and frequency-domain Response
![Picture3](https://github.com/abidshahriar/HRTF_-result/assets/64680295/11e29a0b-b487-49b5-832e-6e2224a92f5e)


Result and Analysis: 

Time- and frequency-domain characteristics of Measured HRTF: 

HRIR and HRTF are more likely to vary from person to person when measured although some common characteristics can be observed and these common characteristics have been also seen in our measurement of HRTF. For the front (azimuth 0.0 degree and elevation 0.0 degree) the measurement for the first few samples of the HRIR magnitude is approximately zero, corresponding to the propagation delay from sound source to ears. In practice, a time window is usually applied to raw HRIRs, and thus the initial delay only has relative significance. The time domain curve of the HRTF shows a peak in amplitude in the front (az. 0.0, el. 0.0 deg.) range of 1.3 to -0.9. This is because the sound wave reaches the listener's ear canal directly in this direction, resulting in a louder SPL (Sound Pressure Level) or Amplitude. The main body of the HRIRs reflects the complicated interactions between incident sound waves and anatomical structures causing sudden impulses of Amplitude. Subsequently, the HRIR magnitude returns to nearly zero. When the sound source moves away from directly facing the front or back positions, the initial time delay variation between the left and right ear HRIRs indicates the difference in sound propagation time to the left and right ears from the source. The impulse response for the back direction is lower than the impulse response for the front direction. This is because the sound waves have to travel around the head to reach the ears from the back direction. The head and ears act as a sound barrier to sound waves, so the sound waves are attenuated (reduced in amplitude) as travel around the head. Localization of sound source coming from the back direction is a bit more complex due to this than doing it for the front source. When a sound source is on the left of the anatomical structure there is always a non-zero value of HRIR magnitude because the sound source is already located near the left ear and as time passes sound travels to the ear canal directly creating a high impulse magnitude in the HRTF graph plot. Subsequently, the right ear receives a small magnitude response a significant time later than the left ear because the sound wave has to propagate all through the head and reach the right ear canal, e.g. ITD. Also, the impulse is much loIr as this happens because of the head shadow effect and pinna structure of the ear as the sound wave gets reflected by the anatomy of the subject causing an attenuation of SPL. A Vice-Versa scenario is also seen in the case of the right-side analysis but a short distinction can be seen in the case of left and right-side analysis. The impulse of the right side is much less in amplitude than the impulse of the left side. This attenuation indicates the complex structure of the anatomy in terms of size or ridges of pinna structure and causes slight attenuation of HRIR magnitude. This is significant in terms of sound localization technique. 


The frequency domain analysis plays a key role in localizing sound sources in Virtual Three-Dimensional Sound production through Headphones or Speaker Systems. This HRTF information is used to create unique filters in Digital Sound Processing and thus can also be a significant measure. 
The HRTF measurement varies from person to person for the unique anatomy of our ear and head shape. For the front (az. 0.0, el. 0.0 deg.) the frequency response curve for both ears is asymmetrical. This asymmetry in anatomy causes different sound waves in terms of frequency to be reflected off of the head and ears in different ways, resulting in a non-symmetrical HRTF. In lower frequencies above the level of under 600Hz, the magnitude of HRTF tends to lie at zero level as these frequencies are merely affected by the Head and Ear Structure. It is observed a peak in 1KHz of the HRTF measurement. The pinnae act as a natural filter for sound, and they amplify sound at certain frequencies and attenuate sound at other frequencies. The peak at 1 kHz is caused by the way the pinnae reflects sound waves that are coming from the front.

|Ungraded Left Mesh |Ungraded Right Mesh |
|------------|-----------|
|      ![left mesh left org ](https://github.com/abidshahriar/HRTF_-result/assets/64680295/f3505174-6f6c-4a20-aa99-f8fe2f314b76)|  ![right mesh righ org ](https://github.com/abidshahriar/HRTF_-result/assets/64680295/58b3e677-ec4c-48d3-b275-dc94229b0b4e)|

# Complete processed Mesh :

![ear method](https://github.com/abidshahriar/HRTF_-result/assets/64680295/3bf87dcc-9932-48dc-9924-7d0c4d354279)

# ARI Grid used in calculation (Reference: Mesh2HRTF )
![ARI GRID](https://github.com/abidshahriar/HRTF_-result/assets/64680295/de8202b0-150c-4444-9e09-42962193707d)


# HRTF Measurements of a KEMAR Dummy-Head Microphone data visualization for further comparision:

![WP](https://github.com/abidshahriar/HRTF_-result/assets/64680295/ac040751-8cd6-4f95-b0a6-a298ee5d6f13)
![WP2](https://github.com/abidshahriar/HRTF_-result/assets/64680295/092eda7d-9248-4083-873e-1d631ea13d7d)

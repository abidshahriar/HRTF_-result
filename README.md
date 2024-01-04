# HRTF-result
In this repository i have shared some of the results that i have accumulated for the HRTF Simulatuion. (Still Updating )

# HRTF Result Obtained:
![HRIR_ARI_44100_3D (1)](https://github.com/abidshahriar/HRTF_-result/assets/64680295/32980442-b6a6-4cf2-8913-1f8c2191d661)
# Frequency Response
![Picture1](https://github.com/abidshahriar/HRTF_-result/assets/64680295/c9596e4e-f3d7-4ead-a8c9-7838177025f0)

Result and Analysis: 

Time- and frequency-domain characteristics of Measured HRTF: 

HRIR and HRTF is more likely to vary person to person when measured however some common characteristics can be observed and these common characteristics has been also seen in our measurement of HRTF. For front (azimuth 0.0 degree and elevation 0.0 degree) the measurement for the first few samples of the he HRIR magnitude is approximately zero, corresponding to the propagation delay from sound source to ears. In practice, a time window is usually applied to raw HRIRs, and thus the initial delay only has relative significance. The time domain curve of the HRTF shows a peak in amplitude in the front (az. 0.0, el. 0.0 deg.) range of 1.3 to -0.9. This is because the sound wave reaches the listener's ear canal directly in this direction, resulting in a louder SPL (Sound Pressure Level) or Amplitude. The main body of the HRIRs, which reflects the complicated interactions between incident sound waves and anatomical structures causing sudden impulse of the Amplitude. Subsequently, the HRIR magnitude returns to nearly zero. When the sound source moves away from directly facing the front or back positions, the initial time delay variation between the left and right ear HRIRs indicates the difference in sound propagation time to the left and right ears from the source. The impulse response for the back direction is lower than the impulse response for the front direction. This is because the sound waves have to travel around the head to reach the ears from the back direction. The head and ears act as a sound barrier to sound waves, so the sound waves are attenuated (reduced in amplitude) as travelled around the head. For localization of sound source coming from back direction is a bit complex due to this than for doing it for the front source. When sound source is on the left of the anatomical structure there is always a non-zero value of HRIR magnitude as because the sound source is already located near the left ear and as time passes sound travels to the ear canal directly creating a high impulse magnitude in the HRTF graph plot. Subsequently, the right ear receives a small in magnitude response significant time later than the left ear because the sound wave has to propagate all through the head and reach to the right ear canal, e.g. ITD . Also the impulse is much lower as this happens because of head shadow effect and pinna structure of ear as sound wave gets reflected by the anatomy of the subject causing an attenuation of SPL. Vice-Versa scenario is also seen in case of the right-side analysis however a short distinction can be seen in case of left and right-side analysis. The impulse of the right side is much less in amplitude than the impulse of the left side. This attenuation indicates complex structure of the anatomy in terms of size or ridges of pinna structure and causes slight attenuation of HRIR magnitude. This is significant in terms of sound localization technique. 

|Ungraded Left Mesh |Ungraded Right Mesh |
|------------|-----------|
|      ![left mesh left org ](https://github.com/abidshahriar/HRTF_-result/assets/64680295/f3505174-6f6c-4a20-aa99-f8fe2f314b76)|  ![right mesh righ org ](https://github.com/abidshahriar/HRTF_-result/assets/64680295/58b3e677-ec4c-48d3-b275-dc94229b0b4e)|

# Complete processed Mesh :

![ear method](https://github.com/abidshahriar/HRTF_-result/assets/64680295/3bf87dcc-9932-48dc-9924-7d0c4d354279)

ARI Grid used in calculation
![Figure_2022-04-13_225819](https://github.com/abidshahriar/HRTF_-result/assets/64680295/e3843ce8-6db2-486d-b70e-535ba2b6ef10)



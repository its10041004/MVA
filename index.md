# Mathematical Vocoder Algorithm for Efficient NeuralSpeech Synthesis

In this work, we propose a new mathematical vocoder algorithm that generatesa waveform from acoustic features without phase estimation.  The main benefitof using our proposed method is that it excludes the training stage of the neuralvocoder from the end-to-end speech synthesis model without sacrificing soundquality.   Moreover,  the vocoder no longer limits the synthesis speed or soundquality in inferencing. Our implementation can synthesize speech at 8.82 MHz onan AWS t4g ARM core instance. Since the proposed methodology is not a data-driven method, it is applicable to unseen voices and multiple languages withoutany additional work. The proposed method is expected to adapt for researchingon neural network models capable of synthesizing speech at the studio recordinglevel.



## Quality Comparision ( samples from Hifi-Audio) 


|                                       |    1 (LJ050-0270)   |   2 (LJ017-0033)    |   3 (LJ004-0233)    |   4 (LJ011-0009)    |   5 (LJ042-0161)    |
|---------------------------------------|---------------------|---------------------|---------------------|---------------------|---------------------|
| Ground Truth                          |                     |                     |                     |                     |                     |
| WaveNet (MoL)                         |                     |                     |                     |                     |                     |
| WaveGlow                              |                     |                     |                     |                     |                     |
| MelGAN                                |                     |                     |                     |                     |                     |
| HiFi-GAN V1                           |                     |                     |                     |                     |                     |
| HiFi-GAN V2                           |                     |                     |                     |                     |                     |
| HiFi-GAN V3                           |                     |                     |                     |                     |                     |
| Ours ( Algo1   half zeroclip 1024/64) |                     |                     |                     |                     |                     |
| Ours ( Algo2   full zeroclip 1024/64) |                     |                     |                     |                     |                     |
| Ours ( Algo2   full zeroclip 1024/64) |                     |                     |                     |                     |                     |
| Ours ( Algo3   full signed 512/510)   |                     |                     |                     |                     |                     |
| Ours ( Algo3   full signed 512/384)   |                     |                     |                     |                     |                     |


## artifacts


## denoising with zero clipping

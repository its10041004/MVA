# Mathematical Vocoder Algorithm for Efficient NeuralSpeech Synthesis

In this work, we propose a new mathematical vocoder algorithm that generatesa waveform from acoustic features without phase estimation.  The main benefitof using our proposed method is that it excludes the training stage of the neuralvocoder from the end-to-end speech synthesis model without sacrificing soundquality.   Moreover,  the vocoder no longer limits the synthesis speed or soundquality in inferencing. Our implementation can synthesize speech at 8.82 MHz onan AWS t4g ARM core instance. Since the proposed methodology is not a data-driven method, it is applicable to unseen voices and multiple languages withoutany additional work. The proposed method is expected to adapt for researchingon neural network models capable of synthesizing speech at the studio recordinglevel.



## Quality Comparision 

### LJSpeech samples from [Hifi-GAN](https://jik876.github.io/hifi-gan-demo/) 
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


### LJSpeech sampels from  [WaveFlow](https://waveflow-demo.github.io/)
|                                                  | 1 (LJ001-0001) | 2 (LJ001-0003) | 3 (LJ001-0005) | 4 (LJ001-0015) | 5 (LJ001-00016) |
|--------------------------------------------------|----------------|----------------|----------------|----------------|-----------------|
|  Ground-truth (recorded speech)                  |                |                |                |                |                 |
|  WaveNet (30-layer,  res. channels =   128)      |                |                |                |                |                 |
|  WaveGlow (96-layer,  res. channels =   256)     |                |                |                |                |                 |
| WaveGlow (96-layer,  res. channels =   128)      |                |                |                |                |                 |
| WaveGlow (96-layer,  res. channels = 64)         |                |                |                |                |                 |
|  WaveFlow (64-layer,  res. channels =   256)     |                |                |                |                |                 |
| WaveFlow (64-layer,  res. channels =   128)      |                |                |                |                |                 |
| WaveFlow (64-layer,  res. channels = 64)         |                |                |                |                |                 |
| ClariNet (60-layer,  res. channels = 64)         |                |                |                |                |                 |
| Ours ( Algo1   half zeroclip 1024/64)            |                |                |                |                |                 |
| Ours ( Algo2   full zeroclip 1024/64)            |                |                |                |                |                 |
| Ours ( Algo2   full zeroclip 1024/64)            |                |                |                |                |                 |
| Ours ( Algo3   full signed 512/510)              |                |                |                |                |                 |
| Ours ( Algo3   full signed 512/384)              |                |                |                |                |                 |


### LJSpeech sampels from [DiffWave](https://diffwave-demo.github.io/)
|                                       | 1 (LJ001-0001) | 2 (LJ001-0002) | 3 (LJ001-0003) | 4 (LJ001-0004) | 5 (LJ001-0005) |
|---------------------------------------|----------------|----------------|----------------|----------------|----------------|
| Ground-truth                          |                |                |                |                |                |
| WaveNet   (C = 128)                   |                |                |                |                |                |
| WaveFlow   (C = 128)                  |                |                |                |                |                |
| DiffWave   (C = 128, T = 200)         |                |                |                |                |                |
| WaveFlow   (C = 64)                   |                |                |                |                |                |
| DiffWave   (C = 64,  T = 50)          |                |                |                |                |                |
| ClariNet   (C = 64)                   |                |                |                |                |                |
| Ours ( Algo1   half zeroclip 1024/64) |                |                |                |                |                |
| Ours ( Algo2   full zeroclip 1024/64) |                |                |                |                |                |
| Ours ( Algo2   full zeroclip 1024/64) |                |                |                |                |                |
| Ours ( Algo3   full signed 512/510)   |                |                |                |                |                |
| Ours ( Algo3   full signed 512/384)   |                |                |                |                |                |


### LJSpeech sampels from [WaveGlow](https://nv-adlr.github.io/WaveGlow/) and [SqueezeWave](https://tianrengao.github.io/SqueezeWaveDemo/)

|                                       | 1 (LJ001-0015) | 2 (LJ001-0051) | 3 (LJ001-0063) | 4 (LJ001-0072) | 5 (LJ001-0079) | 6 (LJ001-0094) | 7 (LJ001-0096) | 8 (LJ001-0102) | 9  (LJ001-0153) | 10 (LJ001-0173) |
|---------------------------------------|----------------|----------------|----------------|----------------|----------------|----------------|----------------|----------------|-----------------|-----------------|
| Ground Truth                          |                |                |                |                |                |                |                |                |                 |                 |
| Griffin-Lim                           |                |                |                |                |                |                |                |                |                 |                 |
| WaveNet                               |                |                |                |                |                |                |                |                |                 |                 |
| WaveGlow                              |                |                |                |                |                |                |                |                |                 |                 |
| WaveGlow(SW)                          |                |                |                |                |                |                |                |                |                 |                 |
| SqueezeWave 128L                      |                |                |                |                |                |                |                |                |                 |                 |
| SqueezeWave 128S                      |                |                |                |                |                |                |                |                |                 |                 |
| SqueezeWave 64L                       |                |                |                |                |                |                |                |                |                 |                 |
| SqueezeWave 64S                       |                |                |                |                |                |                |                |                |                 |                 |
| Ours ( Algo1   half zeroclip 1024/64) |                |                |                |                |                |                |                |                |                 |                 |
| Ours ( Algo2   full zeroclip 1024/64) |                |                |                |                |                |                |                |                |                 |                 |
| Ours ( Algo2   full zeroclip 1024/64) |                |                |                |                |                |                |                |                |                 |                 |
| Ours ( Algo3   full signed 512/510)   |                |                |                |                |                |                |                |                |                 |                 |
| Ours ( Algo3   full signed 512/384)   |                |                |                |                |                |                |                |                |                 |                 |
<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-0pky{border-color:inherit;text-align:left;vertical-align:top}
</style>
<table class="tg">
<thead>
  <tr>
    <th class="tg-0pky"> </th>
    <th class="tg-0pky">LJ003-0307  </th>
    <th class="tg-0pky">LJ034-0083</th>
    <th class="tg-0pky">LJ005-0101  </th>
    <th class="tg-0pky">LJ036-0216</th>
    <th class="tg-0pky">LJ007-0217  </th>
    <th class="tg-0pky">LJ037-0219</th>
    <th class="tg-0pky">LJ008-0131  </th>
    <th class="tg-0pky">LJ037-0222</th>
    <th class="tg-0pky">LJ010-0262  </th>
    <th class="tg-0pky">LJ040-0161</th>
    <th class="tg-0pky">LJ010-0293  </th>
    <th class="tg-0pky">LJ043-0183</th>
    <th class="tg-0pky">LJ018-0119  </th>
    <th class="tg-0pky">LJ045-0081</th>
    <th class="tg-0pky">LJ021-0049  </th>
    <th class="tg-0pky">LJ045-0147</th>
    <th class="tg-0pky">LJ028-0134  </th>
    <th class="tg-0pky">LJ045-0204</th>
    <th class="tg-0pky">LJ032-0100  </th>
    <th class="tg-0pky">LJ050-0276</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0pky">Ground Truth</td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
  </tr>
  <tr>
    <td class="tg-0pky">HifiGAN</td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
  </tr>
  <tr>
    <td class="tg-0pky">HifiGAN(MultiRes)</td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
  </tr>
  <tr>
    <td class="tg-0pky">pWaveGAN</td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
  </tr>
  <tr>
    <td class="tg-0pky">uMelGAN</td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
  </tr>
  <tr>
    <td class="tg-0pky">VocGAN</td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
  </tr>
  <tr>
    <td class="tg-0pky">HifiGAN</td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
  </tr>
  <tr>
    <td class="tg-0pky">Ours ( Algo1   half zeroclip 1024/64)</td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
  </tr>
  <tr>
    <td class="tg-0pky">Ours ( Algo2   full zeroclip 1024/64)</td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
  </tr>
  <tr>
    <td class="tg-0pky">Ours ( Algo2   full zeroclip 1024/64)</td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
  </tr>
  <tr>
    <td class="tg-0pky">Ours ( Algo3   full signed 512/510)</td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
  </tr>
  <tr>
    <td class="tg-0pky">Ours ( Algo3   full signed 512/384)</td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
    <td class="tg-0pky"> </td>
  </tr>
</tbody>
</table>

## Ablation Studies

### Algorithm 1 Half Spectrum Bin 

### Algorithm 2 Full Spectrum Bin


## denoising with zero clipping

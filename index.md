# Mathematical Vocoder Algorithm for Efficient NeuralSpeech Synthesis

In this work, we propose a new mathematical vocoder algorithm that generatesa waveform from acoustic features without phase estimation.  The main benefitof using our proposed method is that it excludes the training stage of the neuralvocoder from the end-to-end speech synthesis model without sacrificing soundquality.   Moreover,  the vocoder no longer limits the synthesis speed or soundquality in inferencing. Our implementation can synthesize speech at 8.82 MHz onan AWS t4g ARM core instance. Since the proposed methodology is not a data-driven method, it is applicable to unseen voices and multiple languages withoutany additional work. The proposed method is expected to adapt for researchingon neural network models capable of synthesizing speech at the studio recordinglevel.



## Quality Comparision 

### LJSpeech samples from [Hifi-GAN](https://jik876.github.io/hifi-gan-demo/) 

<table class="tg">
<thead>
  <tr>
    <th class="tg-0lax"> </th>
    <th class="tg-0lax">1 (LJ050-0270)</th>
    <th class="tg-0lax">2 (LJ017-0033)</th>
    <th class="tg-0lax">3 (LJ004-0233)</th>
    <th class="tg-0lax">4 (LJ011-0009)</th>
    <th class="tg-0lax">5 (LJ042-0161)</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0lax">Ground Truth</td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">WaveNet (MoL)</td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">WaveGlow</td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">MelGAN</td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">HiFi-GAN V1</td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">HiFi-GAN V2</td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">HiFi-GAN V3</td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo1&nbsp;&nbsp;&nbsp;half zeroclip 1024/64)</td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo2&nbsp;&nbsp;&nbsp;full zeroclip 1024/64)</td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo2&nbsp;&nbsp;&nbsp;full zeroclip 1024/64)</td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo3&nbsp;&nbsp;&nbsp;full signed 512/510)</td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo3&nbsp;&nbsp;&nbsp;full signed 512/384)</td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
</tbody>
</table>

### LJSpeech sampels from  [GAN vocoder](https://moneybrain-research.github.io/gan-vocoder//)

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

### LJSpeech sampels from  [WaveFlow](https://waveflow-demo.github.io/)

<table class="tg">
<thead>
  <tr>
    <th class="tg-0lax"> </th>
    <th class="tg-0lax">1 (LJ001-0001)</th>
    <th class="tg-0lax">2 (LJ001-0003)</th>
    <th class="tg-0lax">3 (LJ001-0005)</th>
    <th class="tg-0lax">4 (LJ001-0015)</th>
    <th class="tg-0lax">5 (LJ001-00016)</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0lax"> Ground-truth (recorded speech)    </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax"> WaveNet (30-layer,  res. channels =&nbsp;&nbsp;&nbsp;128)    </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax"> WaveGlow (96-layer,  res. channels =&nbsp;&nbsp;&nbsp;256)    </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">WaveGlow (96-layer,  res. channels =&nbsp;&nbsp;&nbsp;128)    </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">WaveGlow (96-layer,  res. channels = 64) </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax"> WaveFlow (64-layer,  res. channels =&nbsp;&nbsp;&nbsp;256)    </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">WaveFlow (64-layer,  res. channels =&nbsp;&nbsp;&nbsp;128)    </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">WaveFlow (64-layer,  res. channels = 64) </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">ClariNet (60-layer,  res. channels = 64)  </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo1&nbsp;&nbsp;&nbsp;half zeroclip 1024/64)</td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo2&nbsp;&nbsp;&nbsp;full zeroclip 1024/64)</td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo2&nbsp;&nbsp;&nbsp;full zeroclip 1024/64)</td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo3&nbsp;&nbsp;&nbsp;full signed 512/510)</td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo3&nbsp;&nbsp;&nbsp;full signed 512/384)</td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
</tbody>
</table>


### LJSpeech sampels from  [DiffWave](https://diffwave-demo.github.io/)
<table class="tg">
<thead>
  <tr>
    <th class="tg-0lax"> </th>
    <th class="tg-0lax">1 (LJ001-0001)</th>
    <th class="tg-0lax">2 (LJ001-0002)</th>
    <th class="tg-0lax">3 (LJ001-0003)</th>
    <th class="tg-0lax">4 (LJ001-0004)</th>
    <th class="tg-0lax">5 (LJ001-0005)</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0lax">Ground-truth </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">WaveNet&nbsp;&nbsp;&nbsp;(C = 128)   </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">WaveFlow&nbsp;&nbsp;&nbsp;(C = 128)  </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">DiffWave&nbsp;&nbsp;&nbsp;(C = 128, T = 200)</td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">WaveFlow&nbsp;&nbsp;&nbsp;(C = 64)    </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">DiffWave&nbsp;&nbsp;&nbsp;(C = 64,  T = 50)   </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">ClariNet&nbsp;&nbsp;&nbsp;(C = 64) </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo1&nbsp;&nbsp;&nbsp;half zeroclip 1024/64)</td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo2&nbsp;&nbsp;&nbsp;full zeroclip 1024/64)</td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo2&nbsp;&nbsp;&nbsp;full zeroclip 1024/64)</td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo3&nbsp;&nbsp;&nbsp;full signed 512/510)</td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo3&nbsp;&nbsp;&nbsp;full signed 512/384)</td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
    <td class="tg-0lax"> </td>
  </tr>
</tbody>
</table> |

 

### LJSpeech sampels from [WaveGlow](https://nv-adlr.github.io/WaveGlow/) and [SqueezeWave](https://tianrengao.github.io/SqueezeWaveDemo/)
 
<table class="tg">
<thead>
  <tr>
    <th class="tg-lqy6"> </th>
    <th class="tg-lqy6">1 (LJ001-0015)</th>
    <th class="tg-lqy6">2 (LJ001-0051)</th>
    <th class="tg-lqy6">3 (LJ001-0063)</th>
    <th class="tg-lqy6">4 (LJ001-0072)</th>
    <th class="tg-lqy6">5 (LJ001-0079)</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-lqy6">Ground Truth</td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
  </tr>
  <tr>
    <td class="tg-lqy6">Griffin-Lim</td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
  </tr>
  <tr>
    <td class="tg-lqy6">WaveNet</td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
  </tr>
  <tr>
    <td class="tg-lqy6">WaveGlow</td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
  </tr>
  <tr>
    <td class="tg-lqy6">WaveGlow(SW)</td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
  </tr>
  <tr>
    <td class="tg-lqy6">SqueezeWave 128L</td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
  </tr>
  <tr>
    <td class="tg-lqy6">SqueezeWave 128S</td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
  </tr>
  <tr>
    <td class="tg-lqy6">SqueezeWave 64L</td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
  </tr>
  <tr>
    <td class="tg-lqy6">SqueezeWave 64S</td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
  </tr>
  <tr>
    <td class="tg-lqy6">Ours ( Algo1&nbsp;&nbsp;&nbsp;half zeroclip 1024/64)</td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
  </tr>
  <tr>
    <td class="tg-lqy6">Ours ( Algo2&nbsp;&nbsp;&nbsp;full zeroclip 1024/64)</td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
  </tr>
  <tr>
    <td class="tg-lqy6">Ours ( Algo2&nbsp;&nbsp;&nbsp;full zeroclip 1024/64)</td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
  </tr>
  <tr>
    <td class="tg-lqy6">Ours ( Algo3&nbsp;&nbsp;&nbsp;full signed 512/510)</td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
  </tr>
  <tr>
    <td class="tg-lqy6">Ours ( Algo3&nbsp;&nbsp;&nbsp;full signed 512/384)</td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
    <td class="tg-lqy6"> </td>
  </tr>
</tbody>
</table>
 

## Ablation Studies
R-MCD 

<table class="tg">
<thead>
  <tr>
    <th class="tg-0lax">GT</th>
    <th class="tg-0lax">22 Khz</th>
    <th class="tg-0lax">21 Khz</th>
    <th class="tg-0lax">20 Khz</th>
    <th class="tg-0lax">19 Khz</th>
    <th class="tg-0lax">18 Khz</th>
    <th class="tg-0lax">17 Khz</th>
    <th class="tg-0lax">16 Khz</th>
    <th class="tg-0lax">15 Khz</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0lax">5.4669</td>
    <td class="tg-0lax">5.485</td>
    <td class="tg-0lax">5.5063</td>
    <td class="tg-0lax">5.5274</td>
    <td class="tg-0lax">5.5645</td>
    <td class="tg-0lax">5.6011</td>
    <td class="tg-0lax">5.6807</td>
    <td class="tg-0lax">5.7639</td>
    <td class="tg-0lax">5.8701</td>
  </tr>
  <tr>
    <td class="tg-0lax">14 Khz</td>
    <td class="tg-0lax">13 Khz</td>
    <td class="tg-0lax">12 Khz</td>
    <td class="tg-0lax">11 Khz</td>
    <td class="tg-0lax">10 Khz</td>
    <td class="tg-0lax">9 Khz</td>
    <td class="tg-0lax">8 Khz</td>
    <td class="tg-0lax">7 Khz</td>
    <td class="tg-0lax">6 Khz</td>
  </tr>
  <tr>
    <td class="tg-0lax">5.9553</td>
    <td class="tg-0lax">6.0065</td>
    <td class="tg-0lax">6.0502</td>
    <td class="tg-0lax">6.0738</td>
    <td class="tg-0lax">6.0963</td>
    <td class="tg-0lax">6.1532</td>
    <td class="tg-0lax">6.2358</td>
    <td class="tg-0lax">6.3837</td>
    <td class="tg-0lax">6.5192</td>
  </tr>
</tbody>
</table>

### Algorithm 1 Half Spectrum Bin 
<table class="tg">
<thead>
  <tr>
    <th class="tg-lqy6"> </th>
    <th class="tg-lqy6">1024</th>
    <th class="tg-lqy6">768</th>
    <th class="tg-lqy6">512</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-lqy6">512</td>
    <td class="tg-lqy6">7.1201</td>
    <td class="tg-lqy6">-</td>
    <td class="tg-lqy6">-</td>
  </tr>
  <tr>
    <td class="tg-lqy6">384</td>
    <td class="tg-lqy6">7.0498</td>
    <td class="tg-lqy6">7.0842</td>
    <td class="tg-lqy6">-</td>
  </tr>
  <tr>
    <td class="tg-lqy6">256</td>
    <td class="tg-lqy6">6.9279</td>
    <td class="tg-lqy6">7.0039</td>
    <td class="tg-lqy6">7.0491</td>
  </tr>
  <tr>
    <td class="tg-lqy6">192</td>
    <td class="tg-lqy6">6.9282</td>
    <td class="tg-lqy6">7.0204</td>
    <td class="tg-lqy6">6.9884</td>
  </tr>
  <tr>
    <td class="tg-lqy6">128</td>
    <td class="tg-lqy6">6.6855</td>
    <td class="tg-lqy6">6.8673</td>
    <td class="tg-lqy6">6.9730</td>
  </tr>
  <tr>
    <td class="tg-lqy6">96</td>
    <td class="tg-lqy6">6.558</td>
    <td class="tg-lqy6">6.6353</td>
    <td class="tg-lqy6">6.7327</td>
  </tr>
  <tr>
    <td class="tg-lqy6">64</td>
    <td class="tg-lqy6">6.4737</td>
    <td class="tg-lqy6">6.7202</td>
    <td class="tg-lqy6">6.7075</td>
  </tr>
  <tr>
    <td class="tg-lqy6">32</td>
    <td class="tg-lqy6">6.203</td>
    <td class="tg-lqy6">6.2363</td>
    <td class="tg-lqy6">6.3246</td>
  </tr>
</tbody>
</table>

### Algorithm 2 Full Spectrum Bin
<table class="tg">
<thead>
  <tr>
    <th class="tg-0lax"> </th>
    <th class="tg-0lax">1024</th>
    <th class="tg-0lax">768</th>
    <th class="tg-0lax">512</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0lax">512</td>
    <td class="tg-0lax">6.3424</td>
    <td class="tg-0lax">-</td>
    <td class="tg-0lax">-</td>
  </tr>
  <tr>
    <td class="tg-0lax">384</td>
    <td class="tg-0lax">6.1896</td>
    <td class="tg-0lax">6.4334</td>
    <td class="tg-0lax">-</td>
  </tr>
  <tr>
    <td class="tg-0lax">256</td>
    <td class="tg-0lax">6.0609</td>
    <td class="tg-0lax">6.1309</td>
    <td class="tg-0lax">6.5778</td>
  </tr>
  <tr>
    <td class="tg-0lax">192</td>
    <td class="tg-0lax">6.0109</td>
    <td class="tg-0lax">6.022</td>
    <td class="tg-0lax">6.1632</td>
  </tr>
  <tr>
    <td class="tg-0lax">128</td>
    <td class="tg-0lax">5.9476</td>
    <td class="tg-0lax">5.9648</td>
    <td class="tg-0lax">6.0506</td>
  </tr>
  <tr>
    <td class="tg-0lax">96</td>
    <td class="tg-0lax">5.8248</td>
    <td class="tg-0lax">5.8564</td>
    <td class="tg-0lax">5.9512</td>
  </tr>
  <tr>
    <td class="tg-0lax">64</td>
    <td class="tg-0lax">5.7976</td>
    <td class="tg-0lax">5.8271</td>
    <td class="tg-0lax">5.8584</td>
  </tr>
  <tr>
    <td class="tg-0lax">32</td>
    <td class="tg-0lax">5.6499</td>
    <td class="tg-0lax">5.6692</td>
    <td class="tg-0lax">5.7065</td>
  </tr>
</tbody>
</table>

## denoising with zero clipping

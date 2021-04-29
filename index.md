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
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gt/HIFIGAN1_GT_LJ050-0270.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gt/HIFIGAN2_GT_LJ017-0033.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gt/HIFIGAN3_GT_LJ004-0233.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gt/HIFIGAN4_GT_LJ011-0009.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gt/HIFIGAN5_GT_LJ042-0161.wav" type="audio/wav"></audio> </td>
  </tr>
  <tr>
    <td class="tg-0lax">WaveNet (MoL)</td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_WaveNetMoL/ss_wn_1.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_WaveNetMoL/ss_wn_2.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_WaveNetMoL/ss_wn_3.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_WaveNetMoL/ss_wn_4.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_WaveNetMoL/ss_wn_5.wav" type="audio/wav"></audio> </td>
  </tr>
  <tr>
    <td class="tg-0lax">WaveGlow</td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_WaveGlow/ss_wg_1.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_WaveGlow/ss_wg_2.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_WaveGlow/ss_wg_3.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_WaveGlow/ss_wg_4.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_WaveGlow/ss_wg_5.wav" type="audio/wav"></audio> </td>
  </tr>
  <tr>
    <td class="tg-0lax">MelGAN</td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_MelGAN/ss_mg_1.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_MelGAN/ss_mg_2.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_MelGAN/ss_mg_3.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_MelGAN/ss_mg_4.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_MelGAN/ss_mg_5.wav" type="audio/wav"></audio>  </td>
  </tr>
  <tr>
    <td class="tg-0lax">HiFi-GAN V1</td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_HifiGAN_v1/ss_hgan_v1_1.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_HifiGAN_v1/ss_hgan_v1_2.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_HifiGAN_v1/ss_hgan_v1_3.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_HifiGAN_v1/ss_hgan_v1_4.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_HifiGAN_v1/ss_hgan_v1_5.wav" type="audio/wav"></audio> </td>
  </tr>
  <tr>
    <td class="tg-0lax">HiFi-GAN V2</td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_HifiGAN_v2/ss_hgan_v2_1.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_HifiGAN_v2/ss_hgan_v2_2.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_HifiGAN_v2/ss_hgan_v2_3.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_HifiGAN_v2/ss_hgan_v2_4.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_HifiGAN_v2/ss_hgan_v2_5.wav" type="audio/wav"></audio>  </td>
  </tr>
  <tr>
    <td class="tg-0lax">HiFi-GAN V3</td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_HifiGAN_v3/ss_hgan_v3_1.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_HifiGAN_v3/ss_hgan_v3_2.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_HifiGAN_v3/ss_hgan_v3_3.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_HifiGAN_v3/ss_hgan_v3_4.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_gtLJS_HifiGAN_v3/ss_hgan_v3_5.wav" type="audio/wav"></audio> </td>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo1&nbsp;&nbsp;&nbsp;half zeroclip 1024/64)</td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_ours/HIFIGAN1_GT_LJ050-0270_Ours_half_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_ours/HIFIGAN2_GT_LJ017-0033_Ours_half_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_ours/HIFIGAN3_GT_LJ004-0233_Ours_half_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_ours/HIFIGAN4_GT_LJ011-0009_Ours_half_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_ours/HIFIGAN5_GT_LJ042-0161_Ours_half_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo2&nbsp;&nbsp;&nbsp;full zeroclip 1024/64)</td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_ours/HIFIGAN1_GT_LJ050-0270_Ours_full_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_ours/HIFIGAN2_GT_LJ017-0033_Ours_full_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_ours/HIFIGAN3_GT_LJ004-0233_Ours_full_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_ours/HIFIGAN4_GT_LJ011-0009_Ours_full_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_ours/HIFIGAN5_GT_LJ042-0161_Ours_full_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-0lax">Ours ( Algo3&nbsp;&nbsp;&nbsp;full signed 512/510)</td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_ours/HIFIGAN1_GT_LJ050-0270_Ours_full_signed_512_510.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_ours/HIFIGAN2_GT_LJ017-0033_Ours_full_signed_512_510.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_ours/HIFIGAN3_GT_LJ004-0233_Ours_full_signed_512_510.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_ours/HIFIGAN4_GT_LJ011-0009_Ours_full_signed_512_510.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_ours/HIFIGAN5_GT_LJ042-0161_Ours_full_signed_512_510.wav" type="audio/wav"></audio> </td>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo3&nbsp;&nbsp;&nbsp;full signed 512/384)</td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_ours/HIFIGAN1_GT_LJ050-0270_Ours_full_full_signed_512_384.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_ours/HIFIGAN2_GT_LJ017-0033_Ours_full_full_signed_512_384.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_ours/HIFIGAN3_GT_LJ004-0233_Ours_full_full_signed_512_384.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_ours/HIFIGAN4_GT_LJ011-0009_Ours_full_full_signed_512_384.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_ours/HIFIGAN5_GT_LJ042-0161_Ours_full_full_signed_512_384.wav" type="audio/wav"></audio> </td>
  </tr>
  
</tbody>
</table>

### LJSpeech sampels from  [GAN vocoder](https://moneybrain-research.github.io/gan-vocoder//)
<table class="tg">
<thead>
  <tr>
    <th class="tg-0lax"> </th>
    <th class="tg-0lax">1&nbsp;&nbsp;&nbsp;(LJ003-0307  )</th>
    <th class="tg-0lax">2 (LJ034-0083)</th>
    <th class="tg-0lax">3(&nbsp;&nbsp;&nbsp;LJ005-0101  )</th>
    <th class="tg-0lax">4 (LJ036-0216)</th>
    <th class="tg-0lax">5 (LJ007-0217)</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0lax">Ground Truth</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-0lax">HifiGAN</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-0lax">HifiGAN(MultiRes)</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-0lax">pWaveGAN</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-0lax">uMelGAN</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-0lax">VocGAN</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-0lax">Ours ( Algo1&nbsp;&nbsp;&nbsp;half zeroclip 1024/64)</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-0lax">Ours ( Algo2&nbsp;&nbsp;&nbsp;full zeroclip 1024/64)</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-0lax">Ours ( Algo2&nbsp;&nbsp;&nbsp;full zeroclip 1024/64)</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-0lax">Ours ( Algo3&nbsp;&nbsp;&nbsp;full signed 512/510)</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo3&nbsp;&nbsp;&nbsp;full signed 512/384)</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
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
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-0lax"> WaveNet (30-layer,  res. channels =&nbsp;&nbsp;&nbsp;128)    </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-0lax"> WaveGlow (96-layer,  res. channels =&nbsp;&nbsp;&nbsp;256)    </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-0lax">WaveGlow (96-layer,  res. channels =&nbsp;&nbsp;&nbsp;128)    </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-0lax">WaveGlow (96-layer,  res. channels = 64) </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-0lax"> WaveFlow (64-layer,  res. channels =&nbsp;&nbsp;&nbsp;256)    </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-0lax">WaveFlow (64-layer,  res. channels =&nbsp;&nbsp;&nbsp;128)    </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-0lax">WaveFlow (64-layer,  res. channels = 64) </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-0lax">ClariNet (60-layer,  res. channels = 64)  </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo1&nbsp;&nbsp;&nbsp;half zeroclip 1024/64)</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo2&nbsp;&nbsp;&nbsp;full zeroclip 1024/64)</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo2&nbsp;&nbsp;&nbsp;full zeroclip 1024/64)</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo3&nbsp;&nbsp;&nbsp;full signed 512/510)</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo3&nbsp;&nbsp;&nbsp;full signed 512/384)</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
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
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-0lax">WaveNet&nbsp;&nbsp;&nbsp;(C = 128)   </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-0lax">WaveFlow&nbsp;&nbsp;&nbsp;(C = 128)  </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
    <td class="tg-0lax"> </td>
  </tr>
  <tr>
    <td class="tg-0lax">DiffWave&nbsp;&nbsp;&nbsp;(C = 128, T = 200)</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-0lax">WaveFlow&nbsp;&nbsp;&nbsp;(C = 64)    </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-0lax">DiffWave&nbsp;&nbsp;&nbsp;(C = 64,  T = 50)   </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-0lax">ClariNet&nbsp;&nbsp;&nbsp;(C = 64) </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo1&nbsp;&nbsp;&nbsp;half zeroclip 1024/64)</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo2&nbsp;&nbsp;&nbsp;full zeroclip 1024/64)</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo2&nbsp;&nbsp;&nbsp;full zeroclip 1024/64)</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo3&nbsp;&nbsp;&nbsp;full signed 512/510)</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-0lax">Ours ( Algo3&nbsp;&nbsp;&nbsp;full signed 512/384)</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
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
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-lqy6">Griffin-Lim</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-lqy6">WaveNet</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-lqy6">WaveGlow</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-lqy6">WaveGlow(SW)</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-lqy6">SqueezeWave 128L</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-lqy6">SqueezeWave 128S</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-lqy6">SqueezeWave 64L</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-lqy6">SqueezeWave 64S</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-lqy6">Ours ( Algo1&nbsp;&nbsp;&nbsp;half zeroclip 1024/64)</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-lqy6">Ours ( Algo2&nbsp;&nbsp;&nbsp;full zeroclip 1024/64)</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-lqy6">Ours ( Algo2&nbsp;&nbsp;&nbsp;full zeroclip 1024/64)</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-lqy6">Ours ( Algo3&nbsp;&nbsp;&nbsp;full signed 512/510)</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-lqy6">Ours ( Algo3&nbsp;&nbsp;&nbsp;full signed 512/384)</td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="" type="audio/wav"></audio> </td>
  </tr>
  </tr>
</tbody>
</table>
 

## Ablation Studies
R-MCD 

 

### Algorithm 1 Half Spectrum Bin 
 

### Algorithm 2 Full Spectrum Bin
 

## denoising with zero clipping

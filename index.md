# Mathematical Vocoder Algorithm for Efficient Neural Speech Synthesis

In this work, we propose a new mathematical vocoder algorithm that generates a waveform from acoustic features without phase estimation.  The main benefit of using our proposed method is that it excludes the training stage of the neural vocoder from the end-to-end speech synthesis model without sacrificing soundquality.   Moreover,  the vocoder no longer limits the synthesis speed or sound quality in inferencing. Our implementation can synthesize speech at 8.82 MHz onan AWS t4g ARM core instance. Since the proposed methodology is not a data-driven method, it is applicable to unseen voices and multiple languages withoutany additional work. The proposed method is expected to adapt for researchingon neural network models capable of synthesizing speech at the studio recording level.



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
    <td class="tg-0lax">Ours ( Algo3&nbsp;&nbsp;&nbsp;full signed 512/384)</td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_ours/HIFIGAN1_GT_LJ050-0270_Ours_full_signed_512_384.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_ours/HIFIGAN2_GT_LJ017-0033_Ours_full_signed_512_384.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_ours/HIFIGAN3_GT_LJ004-0233_Ours_full_signed_512_384.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_ours/HIFIGAN4_GT_LJ011-0009_Ours_full_signed_512_384.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="hifigan_ours/HIFIGAN5_GT_LJ042-0161_Ours_full_signed_512_384.wav" type="audio/wav"></audio> </td>
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
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt/assets_audio__gt_LJ003-0307.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt/assets_audio__gt_LJ005-0101.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt/assets_audio__gt_LJ007-0217.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt/assets_audio__gt_LJ008-0131.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt/assets_audio__gt_LJ010-0262.wav" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-0lax">HifiGAN</td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt_HifiGAN/assets_audio__hfg2-hfg2_gt_LJ003-0307.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt_HifiGAN/assets_audio__hfg2-hfg2_gt_LJ005-0101.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt_HifiGAN/assets_audio__hfg2-hfg2_gt_LJ007-0217.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt_HifiGAN/assets_audio__hfg2-hfg2_gt_LJ008-0131.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt_HifiGAN/assets_audio__hfg2-hfg2_gt_LJ010-0262.wav" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-0lax">HifiGAN(MultiRes)</td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt_HifiGANours/assets_audio__hfg2-custom_gt_LJ003-0307.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt_HifiGANours/assets_audio__hfg2-custom_gt_LJ005-0101.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt_HifiGANours/assets_audio__hfg2-custom_gt_LJ007-0217.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt_HifiGANours/assets_audio__hfg2-custom_gt_LJ008-0131.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt_HifiGANours/assets_audio__hfg2-custom_gt_LJ010-0262.wav" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-0lax">pWaveGAN</td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt_pWaveGAN/assets_audio__hfg2-pwg_gt_LJ003-0307.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt_pWaveGAN/assets_audio__hfg2-pwg_gt_LJ005-0101.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt_pWaveGAN/assets_audio__hfg2-pwg_gt_LJ007-0217.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt_pWaveGAN/assets_audio__hfg2-pwg_gt_LJ008-0131.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt_pWaveGAN/assets_audio__hfg2-pwg_gt_LJ010-0262.wav" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-0lax">uMelGAN</td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt_uMelGAN/assets_audio__hfg2-umg_gt_LJ003-0307.wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt_uMelGAN/assets_audio__hfg2-umg_gt_LJ005-0101.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt_uMelGAN/assets_audio__hfg2-umg_gt_LJ007-0217.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt_uMelGAN/assets_audio__hfg2-umg_gt_LJ008-0131.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt_uMelGAN/assets_audio__hfg2-umg_gt_LJ010-0262.wav" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-0lax">VocGAN</td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt_VocGAN/assets_audio__hfg2-vocgan_gt_LJ003-0307.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt_VocGAN/assets_audio__hfg2-vocgan_gt_LJ005-0101.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt_VocGAN/assets_audio__hfg2-vocgan_gt_LJ007-0217.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt_VocGAN/assets_audio__hfg2-vocgan_gt_LJ008-0131.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_gt_VocGAN/assets_audio__hfg2-vocgan_gt_LJ010-0262.wav" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-0lax">Ours ( Algo1&nbsp;&nbsp;&nbsp;half zeroclip 1024/64)</td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_ours/assets_audio__gt_LJ003-0307_Ours_half_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_ours/assets_audio__gt_LJ005-0101_Ours_half_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_ours/assets_audio__gt_LJ007-0217_Ours_half_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_ours/assets_audio__gt_LJ008-0131_Ours_half_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_ours/assets_audio__gt_LJ010-0262_Ours_half_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-0lax">Ours ( Algo2&nbsp;&nbsp;&nbsp;full zeroclip 1024/64)</td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_ours/assets_audio__gt_LJ003-0307_Ours_full_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_ours/assets_audio__gt_LJ005-0101_Ours_full_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_ours/assets_audio__gt_LJ007-0217_Ours_full_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_ours/assets_audio__gt_LJ008-0131_Ours_full_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_ours/assets_audio__gt_LJ010-0262_Ours_full_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-0lax">Ours ( Algo3&nbsp;&nbsp;&nbsp;full signed 512/384)</td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_ours/assets_audio__gt_LJ003-0307_Ours_full_signed_512_384.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_ours/assets_audio__gt_LJ005-0101_Ours_full_signed_512_384.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_ours/assets_audio__gt_LJ007-0217_Ours_full_signed_512_384.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="ganvocoder_ours/assets_audio__gt_LJ008-0131_Ours_full_signed_512_384.wav" type="audio/wav"></audio> </td>
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
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_gt/LJ001-0001.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_gt/LJ001-0003.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_gt/LJ001-0005.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_gt/LJ001-0015.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_gt/LJ001-0016.wav" type="audio/wav"></audio> </td>
  </tr>


  <tr>
    <td class="tg-0lax"> WaveGlow (96-layer,  res. channels =&nbsp;&nbsp;&nbsp;256)    </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_gt_WaveGlow_96_256/LJ001-0001_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_gt_WaveGlow_96_256/LJ001-0003_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_gt_WaveGlow_96_256/LJ001-0005_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_gt_WaveGlow_96_256/LJ001-0015_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_gt_WaveGlow_96_256/LJ001-0016_synthesis.wav" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-0lax"> WaveFlow (64-layer,  res. channels =&nbsp;&nbsp;&nbsp;256)    </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_gt_WaveFlow_64_256/LJ001-0001_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_gt_WaveFlow_64_256/LJ001-0003_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_gt_WaveFlow_64_256/LJ001-0005_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_gt_WaveFlow_64_256/LJ001-0015_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_gt_WaveFlow_64_256/LJ001-0016_synthesis.wav" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-0lax">Ours ( Algo1&nbsp;&nbsp;&nbsp;half zeroclip 1024/64)</td>
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_ours/LJ001-0001_Ours_half_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_ours/LJ001-0003_Ours_half_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_ours/LJ001-0005_Ours_half_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>    
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_ours/LJ001-0015_Ours_half_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_ours/LJ001-0016_Ours_half_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-0lax">Ours ( Algo2&nbsp;&nbsp;&nbsp;full zeroclip 1024/64)</td>
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_ours/LJ001-0001_Ours_full_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_ours/LJ001-0003_Ours_full_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_ours/LJ001-0005_Ours_full_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>    
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_ours/LJ001-0015_Ours_full_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_ours/LJ001-0016_Ours_full_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-0lax">Ours ( Algo3&nbsp;&nbsp;&nbsp;full signed 512/384)</td>
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_ours/LJ001-0001_Ours_full_signed_512_384.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_ours/LJ001-0003_Ours_full_signed_512_384.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_ours/LJ001-0005_Ours_full_signed_512_384.wav" type="audio/wav"></audio> </td>    
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_ours/LJ001-0015_Ours_full_signed_512_384.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveflow_ours/LJ001-0016_Ours_full_signed_512_384.wav" type="audio/wav"></audio> </td>
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
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt/LJ001-0001.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt/LJ001-0002.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt/LJ001-0003.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt/LJ001-0004.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt/LJ001-0005.wav" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-0lax">WaveNet&nbsp;&nbsp;&nbsp;(C = 128)   </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_WaveNet_128/teacher8_l30_k2-LJ001-0001.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_WaveNet_128/teacher8_l30_k2-LJ001-0002.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_WaveNet_128/teacher8_l30_k2-LJ001-0003.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_WaveNet_128/teacher8_l30_k2-LJ001-0004.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_WaveNet_128/teacher8_l30_k2-LJ001-0005.wav" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-0lax">WaveFlow&nbsp;&nbsp;&nbsp;(C = 128)  </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_WaveFlow_128/LJ001-0001_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_WaveFlow_128/LJ001-0002_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_WaveFlow_128/LJ001-0003_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_WaveFlow_128/LJ001-0004_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_WaveFlow_128/LJ001-0005_synthesis.wav" type="audio/wav"></audio> </td>
  </tr>
    <td class="tg-0lax"> </td>
  </tr>
  
  <tr>
    <td class="tg-0lax">DiffWave&nbsp;&nbsp;&nbsp;(C = 128, T = 200)</td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_DiffWave_128_200/wav_ch_128_T_200_iter_1000000_cond_1_0.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_DiffWave_128_200/wav_ch_128_T_200_iter_1000000_cond_2_0.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_DiffWave_128_200/wav_ch_128_T_200_iter_1000000_cond_3_0.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_DiffWave_128_200/wav_ch_128_T_200_iter_1000000_cond_4_0.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_DiffWave_128_200/wav_ch_128_T_200_iter_1000000_cond_5_0.wav" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-0lax">WaveFlow&nbsp;&nbsp;&nbsp;(C = 64)    </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_WaveFlow_64/LJ001-0001_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_WaveFlow_64/LJ001-0002_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_WaveFlow_64/LJ001-0003_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_WaveFlow_64/LJ001-0004_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_WaveFlow_64/LJ001-0005_synthesis.wav" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-0lax">DiffWave&nbsp;&nbsp;&nbsp;(C = 64,  T = 50)   </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_DiffWave_64_50/wav_ch_64_T_50_iter_1000000_cond_1_0.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_DiffWave_64_50/wav_ch_64_T_50_iter_1000000_cond_2_0.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_DiffWave_64_50/wav_ch_64_T_50_iter_1000000_cond_3_0.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_DiffWave_64_50/wav_ch_64_T_50_iter_1000000_cond_4_0.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_DiffWave_64_50/wav_ch_64_T_50_iter_1000000_cond_5_0.wav" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-0lax">ClariNet&nbsp;&nbsp;&nbsp;(C = 64) </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_ClariNet_64/LJ001-0001_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_ClariNet_64/LJ001-0002_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_ClariNet_64/LJ001-0003_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_ClariNet_64/LJ001-0004_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_gt_ClariNet_64/LJ001-0005_synthesis.wav" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-0lax">Ours ( Algo1&nbsp;&nbsp;&nbsp;half zeroclip 1024/64)</td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_ours/LJ001-0001_Ours_half_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_ours/LJ001-0002_Ours_half_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_ours/LJ001-0003_Ours_half_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_ours/LJ001-0004_Ours_half_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_ours/LJ001-0005_Ours_half_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-0lax">Ours ( Algo2&nbsp;&nbsp;&nbsp;full zeroclip 1024/64)</td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_ours/LJ001-0001_Ours_full_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_ours/LJ001-0002_Ours_full_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_ours/LJ001-0003_Ours_full_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_ours/LJ001-0004_Ours_full_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_ours/LJ001-0005_Ours_full_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-0lax">Ours ( Algo3&nbsp;&nbsp;&nbsp;full signed 512/384)</td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_ours/LJ001-0001_Ours_full_signed_512_384.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_ours/LJ001-0002_Ours_full_signed_512_384.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_ours/LJ001-0003_Ours_full_signed_512_384.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_ours/LJ001-0004_Ours_full_signed_512_384.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="diffwave_ours/LJ001-0005_Ours_full_signed_512_384.wav" type="audio/wav"></audio> </td>
  </tr>

</tbody>
</table> 

 
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
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_gt/LJ001-0015.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_gt/LJ001-0051.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_gt/LJ001-0063.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_gt/LJ001-0072.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_gt/LJ001-0079.wav" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-lqy6">Griffin-Lim(WG)</td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_gt_GriffinLim/LJ001-0015.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_gt_GriffinLim/LJ001-0051.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_gt_GriffinLim/LJ001-0063.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_gt_GriffinLim/LJ001-0072.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_gt_GriffinLim/LJ001-0079.wav" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-lqy6">WaveNet(WG)</td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_gt_WaveNet/LJ001-0015.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_gt_WaveNet/LJ001-0051.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_gt_WaveNet/LJ001-0063.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_gt_WaveNet/LJ001-0072.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_gt_WaveNet/LJ001-0079.wav" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-lqy6">WaveGlow</td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_gt_WaveGlow/LJ001-0015.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_gt_WaveGlow/LJ001-0051.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_gt_WaveGlow/LJ001-0063.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_gt_WaveGlow/LJ001-0072.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_gt_WaveGlow/LJ001-0079.wav" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-lqy6">WaveGlow(SW)</td>
    <td class="tg-0lax"> <audio controls=""><source src="squeezeWave_gt_baseline_WaveGlow/LJ001-0015.wav_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="squeezeWave_gt_baseline_WaveGlow/LJ001-0051.wav_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="squeezeWave_gt_baseline_WaveGlow/LJ001-0063.wav_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="squeezeWave_gt_baseline_WaveGlow/LJ001-0072.wav_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="squeezeWave_gt_baseline_WaveGlow/LJ001-0079.wav_synthesis.wav" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-lqy6">SqueezeWave 128L</td>
    <td class="tg-0lax"> <audio controls=""><source src="squeezeWave_gt_SqueezeWave_128L/LJ001-0015.wav_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="squeezeWave_gt_SqueezeWave_128L/LJ001-0051.wav_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="squeezeWave_gt_SqueezeWave_128L/LJ001-0063.wav_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="squeezeWave_gt_SqueezeWave_128L/LJ001-0072.wav_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="squeezeWave_gt_SqueezeWave_128L/LJ001-0079.wav_synthesis.wav" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-lqy6">SqueezeWave 128S</td>
    <td class="tg-0lax"> <audio controls=""><source src="squeezeWave_gt_SqueezeWave_128S/LJ001-0015.wav_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="squeezeWave_gt_SqueezeWave_128S/LJ001-0051.wav_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="squeezeWave_gt_SqueezeWave_128S/LJ001-0063.wav_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="squeezeWave_gt_SqueezeWave_128S/LJ001-0072.wav_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="squeezeWave_gt_SqueezeWave_128S/LJ001-0079.wav_synthesis.wav" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-lqy6">SqueezeWave 64L</td>
    <td class="tg-0lax"> <audio controls=""><source src="squeezeWave_gt_SqueezeWave_64_L/LJ001-0015.wav_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="squeezeWave_gt_SqueezeWave_64_L/LJ001-0051.wav_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="squeezeWave_gt_SqueezeWave_64_L/LJ001-0063.wav_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="squeezeWave_gt_SqueezeWave_64_L/LJ001-0072.wav_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="squeezeWave_gt_SqueezeWave_64_L/LJ001-0079.wav_synthesis.wav" type="audio/wav"></audio> </td>
  </tr>
  </tr>
  <tr>
    <td class="tg-lqy6">SqueezeWave 64S</td>
    <td class="tg-0lax"> <audio controls=""><source src="squeezeWave_gt_SqueezeWave_64S/LJ001-0015.wav_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="squeezeWave_gt_SqueezeWave_64S/LJ001-0051.wav_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="squeezeWave_gt_SqueezeWave_64S/LJ001-0063.wav_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="squeezeWave_gt_SqueezeWave_64S/LJ001-0072.wav_synthesis.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="squeezeWave_gt_SqueezeWave_64S/LJ001-0079.wav_synthesis.wav" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-lqy6">Ours ( Algo1&nbsp;&nbsp;&nbsp;half zeroclip 1024/64)</td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_ours/LJ001-0015_Ours_half_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_ours/LJ001-0051_Ours_half_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_ours/LJ001-0063_Ours_half_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_ours/LJ001-0072_Ours_half_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_ours/LJ001-0079_Ours_half_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
  </tr>


  <tr>
    <td class="tg-lqy6">Ours ( Algo2&nbsp;&nbsp;&nbsp;full zeroclip 1024/64)</td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_ours/LJ001-0015_Ours_full_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_ours/LJ001-0051_Ours_full_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_ours/LJ001-0063_Ours_full_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_ours/LJ001-0072_Ours_full_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_ours/LJ001-0079_Ours_full_zeroclip_1024_64.wav" type="audio/wav"></audio> </td>
  </tr>

  <tr>
    <td class="tg-lqy6">Ours ( Algo3&nbsp;&nbsp;&nbsp;full signed 512/384)</td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_ours/LJ001-0015_Ours_full_signed_512_384.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_ours/LJ001-0051_Ours_full_signed_512_384.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_ours/LJ001-0063_Ours_full_signed_512_384.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_ours/LJ001-0072_Ours_full_signed_512_384.wav" type="audio/wav"></audio> </td>
    <td class="tg-0lax"> <audio controls=""><source src="waveglow_ours/LJ001-0079_Ours_full_signed_512_384.wav" type="audio/wav"></audio> </td>
  </tr>

</tbody>
</table>
 

## Ablation Studies
 

### Algorithm 1 Half Spectrum Bin 
 

### Algorithm 2 Full Spectrum Bin
 

## denoising with zero clipping

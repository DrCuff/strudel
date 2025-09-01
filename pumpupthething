/*
  @title Repump the Jam v1.0
  @by ChromaMagic
  @details strudel demo
*/

let cpm = 135/4;
const pickRestart = register('pickRestart', 
      (arr, pat) => pat.pick(arr.map((x)=>x.restart(pat.collect().fmap(v=>v+1)))))

let synth_arpeggio = cat(
  "<c3 c4 eb5 c3 c4 d5 c3 bb4>*8",
  "<g2 g3 bb4 g2 g3 a4 g2 g4>*8",
  "<eb2 eb3 g4 eb2 eb3 f4 eb2 g4>*8",
  "<eb2 eb3 g4 eb2 eb3 f4 f2 g4>*8",
  "<c3 c4 eb5 c3 c4 d5 c3 bb4>*8",
  "<g2 g3 bb4 g2 bb4 c5 bb2 g4>*8",
  "<eb2 eb3 g4 eb2 eb3 f4 eb2 g4>*8",
  "<f2 f3 g4 f2 f3 a4 f2 a4>*8",
).note()
  .n(1).sound("gm_pad_poly")
  .decay(.95).lpf(5000).lpenv(-3).lpa(.2)
  .delay(".3:.225:.45")
  .room(.8).rsize(2);

let synth_lead = cat(
  "<- - eb5 - - d5 - bb4>*8",
  "<- - bb4 - - a4 - g4>*8",
  "<- - g4 - - f4 - g4>*8",
  "<- - g4 - - f4 - g4>*8",
  "<- - eb5 - - d5 - bb4>*8",
  "<- - bb4 - bb4 c5 - g4>*8",
  "<- - g4 - - f4 - g4>*8",
  "<- - g4 - - a4 - a4>*8",
).note()
  .n(1).sound("gm_pad_metallic")
  .decay(.5).delay(".3:.225:.45")
  .room(.4).rsize(1).gain(.6);

// pumpupthejambeat
let putj = cat("<0@4 [0,1]@12 [0,1,2]@4 [0,1,2,3]@4>".pickRestart(
 [stack(s("oh*16").pan(0.45).gain("[0.08 0.16]*4").release(0),s("hh*4").pan(0.7).gain(0.20))
 ,s("bd*4").lpf(150).gain(1)
 ,s("[~ cp]*2").gain(0.5).pan(0.25)
 ,s("[~ rd]*4").gain(0.15).release(0).hpf(1500).pan(0.75)
 ,s("[~ sd!3]!4 [sd*4]!4").slow(2).gain(run(32).slow(2).mul(1/31).add(0.1).mul(0.4))
 ,s("cr").gain(0.2)
 ,s("bd").gain(0.8)
 ]).bank("RolandTR909").color("yellow").velocity(0.7))

let intro = stack(putj, synth_lead)
let v1 = stack(putj, synth_arpeggio)

arrange (
  [4, intro],
  [4, v1],
).cpm(cpm);

// @version 1.0

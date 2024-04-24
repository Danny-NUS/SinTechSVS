# SinTechSVS: A Singing Technique Controllable Singing Voice Synthesis System
## Abstract of the paper

<div style="text-align: justify">
    The precise control of singing techniques is of utmost importance in achieving emotionally expressive vocal performances. To bridge the gap between current Singing Voice Synthesis (SVS) systems and human singers, our paper focuses on developing an SVS system that allows for control over singing techniques. 
    In this paper, we introduce SinTechSVS, a singing technique controllable SVS system composed of a singing technique annotator, a singing technique controllable synthesizer, and a singing technique recommender. Our approach leverages transfer learning for efficient singing technique annotation and adapts the DiffSinger framework with additional style encoders and an attention-based singing technique local score (STLS) module to enhance singing technique controllability. 
    We also propose a Seq2Seq singing technique recommender for the new task of Singing Technique Recommendation (STR). 
    Experimental results demonstrate that SinTechSVS significantly improves the quality and expressiveness of synthesized vocal performances, with comparable general synthesis capabilities to state-of-the-art SVS systems and enhanced control over singing techniques, as evidenced by objective and subjective evaluations. To the best of our knowledge, SinTechSVS is the first SVS capable of controlling singing techniques. 
</div>

<!-- ### 
We provide the annotation of the dataset and its detail on the appendix website (this site). https://yamathcy.github.io/ISMIR2022J-POP/ 
``` -->

### Overall Architecture

<div style="text-align: center;">
    <img src="overall-1.png" width="1000px">
</div>

<div style="text-align: justify">
    SinTechSVS consists of three key components: singing technique annotator (STA), singing voice synthesizer conditioned on singing techniques (SVS), and singing technique recommender (STR). The 'OR' symbol in this figure means that the input of SVS is either by a user-input singing technique sequence or the predicted singing technique sequence from the singing technique recommender. 
</div>

<br>
<div style="text-align: center;">
    <img src="tr_inf.png" width="1000px">
</div>

<div style="text-align: justify">
    The training process of SinTechSVS consists of three steps, with each step laying the foundation for the next. Modules depicted with full shadows remain unfixed during the training step, while those with half shadows are first fixed and then unfixed during training. (Top-left): Training of STA; (Bottom-left): Training of STA; (Bottom-right): Inference of SinTechSVS.
</div>

## Singing Technique Annotations
<div style="text-align: justify">
    In this section, we provide samples of singing techniques that we annotated on opencpop dataset. In sentence-level samples, bolded words are sung in the specific technique.
</div>
<br>
<table>
    <thead>
        <tr>
            <th colspan="4">Singing Voice Samples of Pitch Singing Techniques</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><center>Pitch Singing Techniques</center></td>
            <td><center>Word-level Sample 1</center></td>
            <td><center>Word-level Sample 2</center></td>
            <td><center>Sentence-level Sample</center></td>
        </tr>
        <tr>
            <td>Scooping</td>
            <td>
                <audio controls>
                  <source src="2002000053_7_scooping.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="2001000020_11_scooping.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <center>
                    <span style="text-decoration: underline; font-weight: bold; color: red;">具(ju)</span> 象(xiang)
                </center>
                <audio controls>
                  <source src="2031001168_ju_scooping.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Bend</td>
            <td>
                <audio controls>
                  <source src="2002000066_0_bend.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="2002000066_11_bend.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <center>
                    没(mei) 限(xian) <span style="text-decoration: underline; font-weight: bold; color: red;">期(qi)</span>
                </center>
                <audio controls>
                  <source src="2042001596_qi_bend.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Drop</td>
            <td>
                <audio controls>
                  <source src="2002000071_3_drop.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="2007000218_6_drop.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <center>
                    再(zai) <span style="text-decoration: underline; font-weight: bold; color: red;">给(gei)</span> 我(wo) 两(liang) 分(fen) 钟(zhong)
                </center>
                <audio controls>
                  <source src="2067002490_gei_drop.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Melisma</td>
            <td>
                <audio controls>
                  <source src="2057002127_3_melisma.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="2010000384_4_melisma.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <center>
                    <span style="text-decoration: underline; font-weight: bold; color: red;">双(shuang)</span> 眼(yan)
                </center>
                <audio controls>
                  <source src="2017000662_shuang_melisma.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
    </tbody>
    <thead>
        <tr>
            <th colspan="4">Singing Voice Samples of Timbre Singing Techniques</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Vocal Fry</td>
            <td>
                <audio controls>
                  <source src="2001000009_0_vf.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="2004000113_2_vf.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <center>
                    <span style="text-decoration: underline; font-weight: bold; color: red;">我(wo)</span> 们(men) 都(dou) 需(xu) 要(yao) 勇(yong) 气(qi)
                </center>
                <audio controls>
                  <source src="2028001094_wo_vf.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Falsetto</td>
            <td>
                <audio controls>
                  <source src="2047001800_5_fal.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="2047001802_6_fal.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <center>
                    没(mei) 
                    <span style="text-decoration: underline; font-weight: bold; color: red;">有(wo) 你(you) 根(gen) 本(ben)</span> 不(bu) 想(xiang) 逃(tao)
                </center>
                <audio controls>
                  <source src="falsetto_gt.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Breathy</td>
            <td>
                <audio controls>
                  <source src="2050001901_5_breathy.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="2053001995_0_breathy.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <center>
                    我(wo) 
                    <span style="text-decoration: underline; font-weight: bold; color: red;">不(bu) 会(hui) 发(fa) 现(xian) 我(wo) 难(nan) 受(shou)</span>
                </center>
                <audio controls>
                  <source src="2094003485_all_except_first_breathy.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Belting</td>
            <td>
                <audio controls>
                  <source src="2054002011_3_belting.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="2057002140_13_belting.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <center>
                    <span style="text-decoration: underline; font-weight: bold; color: red;">一(yi) 辈(bei) 子(zi) 暖(nuan) 暖(nuan) 的(de) 好(hao)</span>
                </center>
                <audio controls>
                  <source src="2093003482_all_belting.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
    </tbody>
</table>

## Data Acquirement
<div style="text-align: justify">
If you want the manual singing technique annotation file for opencpop dataset, access <a href="https://docs.google.com/spreadsheets/d/1p1BRTCmCrcLdBm28w3OfeZ6mK3E752rD/edit?usp=drive_link&ouid=109505594792565231495&rtpof=true&sd=true">here</a> and request a permission. The annotation is research purpose only.
</div>
<div style="text-align: justify">
The request should include the following. Otherwise it will be rejected.
<ul>
    <li>Name</li>
    <li>Affiliation</li>
    <li>Email Address</li>
    <li>Agree to the License</li>
</ul>
</div>
<div style="text-align: justify">
For Opencpop dataset: Please trictly follow the instructions of <a href="https://wenet.org.cn/opencpop/">Opencpop</a>. We have no right to give you the access to Opencpop.
</div>

## Annotated Data Statistics
<ul>
<li>Distribution of manually annotated portion of Opencpop dataset. (The singing techniques "whisper" and "hiccup" are removed due to the small amount of labels.) </li>
<div style="text-align: center;">
    <img src="dataset.png" width="450px">
</div>
<li>Distribution of duration of each singing technique.</li>
<div style="text-align: center;">
    <img src="violin.png" width="800px">
</div>
</ul>


## SinTechSVS Samples

### Singing Voice Synthesis with Singing Technique Control
<div style="text-align: justify">
    In this section, we provide synthesized samples of SinTechSVS conditioned on singing techniques. In <b>Word-level Lyric Sequence</b>, bolded words are sung in the specific technique. <b>Regular/Straight</b> denotes synthesized audio with no singing techniques, serving as a reference for comparison.
</div>
<br>
<table>
    <thead>
        <tr>
            <th colspan="4">SinTechSVS Synthesized Samples Conditioned on Pitch Singing Techniques</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><center>Pitch Singing Techniques</center></td>
            <td><center><div style="width: 170pt"> Word-level Lyric Sequence</div></center></td>
            <td><center>Regular/Straight</center></td>
            <td><center>SinTechSVS</center></td>
        </tr>
        <tr>
            <td>Scooping</td>
            <td>
                <center>
                    冰 刀 <span style="text-decoration: underline; font-weight: bold; color: red;"> 划 </span> 的 圈
                    <br>
                    bing dao <span style="text-decoration: underline; font-weight: bold; color: red;">hua</span> de quan
                </center>
            </td>
            <td>
                <audio controls>
                  <source src="scooping_regular.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="scooping.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Bend</td>
            <td>
                <center>
                    又 无 可 <span style="text-decoration: underline; font-weight: bold; color: red;">奈</span> 何
                    <br>
                    you wu ke <span style="text-decoration: underline; font-weight: bold; color: red;">nai</span> he
                </center>
            </td>
            <td>
                <audio controls>
                  <source src="bending_regular.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="bending.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Drop</td>
            <td>
                <center>
                    小 火 车  摆 <span style="text-decoration: underline; font-weight: bold; color: red;">动</span> 的 旋 律
                    <br>
                    xiao huo che  bai <span style="text-decoration: underline; font-weight: bold; color: red;">dong</span> de xuan lv
                </center>
            </td>
            <td>
                <audio controls>
                  <source src="drop_regular.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="drop.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Melisma</td>
            <td>
                <center>
                    你 在 世 俗 里 的 名 字 被 人 用 <span style="text-decoration: underline; font-weight: bold; color: red;">了</span>
                    <br>
                    ni zai shi su li de ming zi bei ren yong <span style="text-decoration: underline; font-weight: bold; color: red;">le</span>
                </center>
            </td>
            <td>
                <audio controls>
                  <source src="melisma_regular.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="melisma.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
    </tbody>
    <thead>
        <tr>
            <th colspan="4">SinTechSVS Synthesized Samples Conditioned on Timbre Singing Techniques</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Vocal Fry</td>
            <td>
                <center>
                    <span style="text-decoration: underline; font-weight: bold; color: red;">喔 喔</span>
                    <br>
                    <span style="text-decoration: underline; font-weight: bold; color: red;">wo wo</span>
                </center>
            </td>
            <td>
                <audio controls>
                  <source src="vocalfry_regular.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="vocalfry.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Falsetto</td>
            <td>
                <center>
                    <span style="text-decoration: underline; font-weight: bold; color: red;">我 恨 你</span>
                    <br>
                    <span style="text-decoration: underline; font-weight: bold; color: red;">wo hen ni</span>
                </center>
            </td>
            <td>
                <audio controls>
                  <source src="falsetto_regular.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="falsetto.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Breathy</td>
            <td>
                <center>
                    <span style="text-decoration: underline; font-weight: bold; color: red;">很 少 人 看 诗</span>
                    <br>
                    <span style="text-decoration: underline; font-weight: bold; color: red;">hen shao ren kan shi</span>
                </center>
            </td>
            <td>
                <audio controls>
                  <source src="breathy_regular.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="breathy.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>Belting</td>
            <td>
                <center>
                    <span style="text-decoration: underline; font-weight: bold; color: red;">你 好 吗</span>
                    <br>
                    <span style="text-decoration: underline; font-weight: bold; color: red;">ni hao ma</span>
                </center>
            </td>
            <td>
                <audio controls>
                  <source src="belting_regular.wav" type="audio/mpeg", style="display: inline;">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
               <audio controls>
                  <source src="belting.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
    </tbody>
</table>

### Singing Voice Synthesis with Singing Technique Recommendation
 <script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=AM_HTMLorMML-full"></script>
<div style="text-align: justify">
    In this section, we provide synthesized samples of SinTechSVS conditioned on singing techniques recommended from the music score. <b>STan</b> represents SinTechSVS with annotated singing technique labels. <b>SinTechSVS</b> use the STR to predict the singing techniques for input.
</div>
<br>
<table>
    <thead>
        <tr>
            <th colspan="3">SinTechSVS Synthesized Samples Conditioned on Recommended Singing Techniques</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><center>Ground Truth</center></td>
            <td><center>STan</center></td>
            <td><center>SinTechSVS</center></td>
        </tr>
        <tr>
            <td>
                <audio controls>
                  <source src="GT/2099003684.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="STan/2099003684.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="SinTechSVS_/2099003684.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>
                <audio controls>
                  <source src="GT/2086003182.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="STan/2086003182.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="SinTechSVS_/2086003182.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>
                <audio controls>
                  <source src="GT/2081002987.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="STan/2081002987.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="SinTechSVS_/2081002987.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>
                <audio controls>
                  <source src="GT/2072002678.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="STan/2072002678.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="SinTechSVS_/2072002678.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
        <tr>
            <td>
                <audio controls>
                  <source src="GT/2046001741.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="STan/2046001741.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
            <td>
                <audio controls>
                  <source src="SinTechSVS_/2046001741.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
            </td>
        </tr>
    </tbody>
</table>

### Singing Voice Synthesis with Singing Technique Recommendation (Unseen)

<div style="text-align: justify">
This section showcases singing technique recommendations through unseen music score samples and their corresponding synthesized audio demonstrations. For pitch singing techniques, the abbreviations are: (1) straight - <b>STR</b>; (2) scooping - <b>SCO</b>; (3) bend - <b>BEND</b>; (4) drop - <b>DROP</b>; (5) melisma - <b>MEL</b>. For timbre singing techniques, the abbreviations are: (1) regular - <b>REG</b>; (2) vocal fry - <b>FRY</b>; (3) falsetto - <b>FAL</b>; (4) breathy: <b>BRE</b>; (5) belting: <b>BEL</b>. The word-level pitch, lyric, slur, and singing technique will be separated by |.
</div>

<br>
<table>
    <thead>
        <tr>
            <th colspan="2">Unseen Sample 1</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>
                <center><div style="width: 100pt">Input Sequence</div></center>
            </td>
            <td>
                <div style="width: 630pt"> <center>Lyrics: 但(dan) | 我(wo) | 早(zao) | 已(yi) | 学(xue) | 会(hui) | 一(yi) | 个(ge) | 人(ren) | 想(xiang) | 你(ni) </center>
                <center>Pitch: A3 | F#4/Gb4 E4 D4 | F#4/Gb4 | B4 | C#5/Db5 | B4 | A4 | F#4/Gb4 | E4 | D4 | F#4/Gb4 E4 D4</center>
                <center>Slur: 0 | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 0 | 0 | 1
                </center>
                </div>
            </td>
        </tr>
        <tr>
            <td>
                <center>Output Pitch Singing Techniques</center>
            </td>
            <td>
                <center>STR | MEL | REG | REG | SCO | REG | REG | DROP | REG | REG | MEL </center>
            </td>
        </tr>
        <tr>
            <td>
                <center>Output Timber Singing Techniques</center>
            </td>
            <td>
                <center>REG | BEL | BEL | FAL | FAL | FAL | FAL | BRE | BRE | REG | BRE</center>
            </td>
        </tr>
        <tr>
            <td>
                <center>Synthesized Audio</center>
            </td>
            <td>
                <center>
                <audio controls>
                  <source src="unseen1.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
                </center>
            </td>
        </tr>
    </tbody>
</table>

<table>
    <thead>
        <tr>
            <th colspan="2">Unseen Sample 2</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>
                <center><div style="width: 100pt">Input Sequence</div></center>
            </td>
            <td>
                <div style="width: 630pt"> <center>Lyrics: 看(kan) | 着(zhe) | 我(wo) | 的(de) | 脚(jiao) | 印(yin) | 一(yi) | 个(ge) | 人(ren) | 一(yi) | 步(bu) | 步(bu) | 好(hao) | 寂(ji) | 寞(mo)
                </center>
                <center>Pitch: F4 | G4 | E4 | D4 | C4 | D4 C4 A4 | E4 | F4 | C5 | E4 | F4 | C5 | E4 | F4 | F4
                </center>
                <center>Slur: 0 | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 0 | 0 | 1
                </center>
                </div>
            </td>
        </tr>
        <tr>
            <td>
                <center>Output Pitch Singing Techniques</center>
            </td>
            <td>
                <center>STR | STR | SCO | STR | REG | MEL | STR | STR | SCO | STR | STR | SCO | STR | STR | SCO
                </center>
            </td>
        </tr>
        <tr>
            <td>
                <center>Output Timber Singing Techniques</center>
            </td>
            <td>
                <center>BEL | BEL | BEL | BEL | BEL | REG | REG | REG | FAL | REG | REG | FAL | REG | REG | BEL
                </center>
            </td>
        </tr>
        <tr>
            <td>
                <center>Synthesized Audio</center>
            </td>
            <td>
                <center>
                <audio controls>
                  <source src="unseen2.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
                </center>
            </td>
        </tr>
    </tbody>
</table>

<table>
    <thead>
        <tr>
            <th colspan="2">Unseen Sample 3</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>
                <center><div style="width: 100pt">Input Sequence</div></center>
            </td>
            <td>
                <div style="width: 630pt"> <center>Lyrics: 有(you) | 什(shen) | 么(me) | 方(fang) | 法(fa) | 让(rang) | 自(zi) | 己(ji) | 真(zhen) | 的(de) | 忘(wang) | 记 (ji) | ha | ha
                 </center>
                <center>Pitch: G4 | A4 | A#4/Bb4 | A4 F4 | C4 | A#4/Bb4 | A4 | F4 | A#4/Bb4 | A4 | A#4/Bb4 | C5 | A#4/Bb4 A4 | A4 G4 F4
                </center>
                <center>Slur: 0 | 0 | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 1
                </center>
                </div>
            </td>
        </tr>
        <tr>
            <td>
                <center>Output Pitch Singing Techniques</center>
            </td>
            <td>
                <center>STR | STR | SCO | BEND | BEND | STR | STR | STR | BEND | STR | STR | SCO | DROP | MEL
                </center>
            </td>
        </tr>
        <tr>
            <td>
                <center>Output Timber Singing Techniques</center>
            </td>
            <td>
                <center>REG | REG | REG | BRE | BRE | BEL | BEL | BEL | BRE | BRE | BRE | FAL | BRE | BRE
                </center>
            </td>
        </tr>
        <tr>
            <td>
                <center>Synthesized Audio</center>
            </td>
            <td>
                <center>
                <audio controls>
                  <source src="unseen3.wav" type="audio/mpeg">
                  Your browser does not support the audio tag.
                </audio>
                </center>
            </td>
        </tr>
    </tbody>
</table>

## Contact
If you have any questions about the paper, please contact the first author Junchuan by junchuan@comp.nus.edu.sg.

## License
<ul>
<li><div style="text-align: justify">
The singing technique annotation for Opencpop is available to download for non-commercial purposes under the <a href="https://wenet.org.cn/opencpop/liscense/">Opencpop license</a>. 
</div>
</li>
<li>
<div style="text-align: justify">
This annotation may not be sold, leased, published or distributed to any third party without written permission from the administrator.
</div>
</li>
<li>
<div style="text-align: justify">
The National University of Singapore is not responsible for errors in the annotation's content or any damages resulting from its use. The administrator may update these conditions of use at any time.
</div>
</li>
</ul>

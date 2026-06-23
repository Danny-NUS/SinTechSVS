# SinTechSVS Demo Page

This repository contains the static supplementary demo page for **SinTechSVS: A Singing Technique Controllable Singing Voice Synthesis System**.

SinTechSVS is a singing voice synthesis system designed to control and recommend expressive singing techniques, including pitch techniques such as scooping, bend, drop, and melisma, and timbre techniques such as vocal fry, falsetto, breathy voice, and belting.

## Contents

- `index.html` - the complete static demo website.
- `assets/img/` - architecture and dataset statistic figures.
- `assets/audio/annotations/` - ground-truth singing technique annotation examples.
- `assets/audio/control/` - regular-vs-technique-conditioned synthesis examples.
- `assets/audio/recommendation/` - ground truth, STan, and SinTechSVS recommendation comparisons.
- `assets/audio/unseen/` - synthesized examples for unseen music score inputs.

## Local Preview

Open `index.html` directly in a browser, or run a small local server from this directory:

```bash
python3 -m http.server 8124
```

Then visit:

```text
http://127.0.0.1:8124/index.html
```

## Demo Structure

The page includes:

- Abstract and project summary
- Overall architecture and training/inference figures
- Annotated pitch and timbre singing technique examples
- Singing technique controllable synthesis samples
- Singing technique recommendation samples
- Unseen score recommendation examples
- Dataset/resource links
- BibTeX citation
- License and contact information

## Paper

**SinTechSVS: A Singing Technique Controllable Singing Voice Synthesis System**

Junchuan Zhao, Low Qi Hong Chetwin, Ye Wang

IEEE/ACM Transactions on Audio, Speech, and Language Processing, 2024

DOI: [10.1109/TASLP.2024.3394769](https://doi.org/10.1109/TASLP.2024.3394769)

## Citation

```bibtex
@article{zhao2024sintechsvs,
  title={Sintechsvs: A singing technique controllable singing voice synthesis system},
  author={Zhao, Junchuan and Chetwin, Low Qi Hong and Wang, Ye},
  journal={IEEE/ACM Transactions on Audio, Speech, and Language Processing},
  volume={32},
  pages={2641--2653},
  year={2024},
  publisher={IEEE}
}
```

## Contact

For questions about the paper or demo materials, please contact Junchuan Zhao at `junchuan@comp.nus.edu.sg`.

# FSIR: Few Shots Text to Image Retrieval

> **Paper:** *Few Shots Text to Image Retrieval: New Benchmarking Dataset and Optimization Methods*
> Ofer Idan, Vladi Vexler, Gil Lederman, Dima Sivov, Aviad Cohen Zada, Shir Niego Komforti
> Huawei Tel-Aviv Research Center
> [arXiv link TODO]

> **🚧 Dataset & Code Coming Soon:** This repository currently serves as a placeholder. The annotation files (JSONs) and code will be released here upon publication. Please star/watch this repository to be notified when the data is available.

## Overview

Pre-trained vision-language models (VLMs) excel at multimodal tasks but struggle with compositional queries and out-of-distribution (OOD) image-text pairs. Inspired by how humans naturally learn from minimal examples, we address this gap through few-shot learning approaches specifically designed for image retrieval.

We introduce the **Few-Shot Text-to-Image Retrieval (FSIR)** task and its accompanying benchmark dataset, **FSIR-BD** — the first to explicitly target image retrieval by text accompanied by reference examples, focusing on challenging compositional and OOD queries. We also propose two novel retrieval optimization methods (**FSIR-PL** and **FSIR-CTR**) that leverage single-shot or few-shot reference examples to improve performance, compatible with any pre-trained image encoder.

## FSIR-BD Benchmark Dataset

FSIR-BD contains **38,353 images** and **303 queries**, with 82% comprising the test corpus (averaging 37 ground-truth matches per query with significant hard negatives) and 18% forming the few-shot reference corpus (FSR) of exemplar positive and hard negative images.

The dataset comprises three sub-datasets:

| Sub-dataset | Domain | Source | Queries | Images |
|---|---|---|---|---|
| FSIR-BD-Compositional-VG | Urban life | Visual Genome + Flickr30K | 50 | 9,073 |
| FSIR-BD-Compositional-INQUIRE | Natural world | INQUIRE (iNat2024) + Flickr30K | 97 | 20,230 |
| FSIR-BD-OOD | Out-of-distribution | FGVC-Aircraft, DTD, EuroSAT | 157 | 9,050 |

Each query includes multiple positive images and up to 3× as many hard negatives — properties absent from prior datasets and closer to real-world retrieval conditions. Evaluation uses mean Average Precision (mAP@K).

### What This Repository Contains (Planned)

This repository will contain the **annotation files (JSONs) and code/scripts** used to construct and work with the FSIR-BD dataset. **It will not contain any original images or files** — those must be obtained directly from the original dataset sources listed below.

```
FSIR/
├── README.md
├── LICENSE
├── annotations/          # JSON annotation files (our new labels)
│   ├── visual_genome/
│   ├── flickr30k/
│   ├── fgvc_aircraft/
│   ├── dtd/
│   └── eurosat/
├── scripts/              # Code for dataset construction and evaluation
│   ├── generate_inquire_annotations.py
│   └── ...
└── ...
```

*The above structure is preliminary and may change upon release.*

## Source Datasets

| Dataset | License | Images Included Here? |
|---|---|---|
| [Visual Genome](https://homes.cs.washington.edu/~ranjay/visualgenome/) | Apache License 2.0 | No — download from source |
| [Flickr30K Entities](https://bryanplummer.com/Flickr30kEntities/) | CC0 (Public Domain) | No — download from source |
| [FGVC-Aircraft](https://www.robots.ox.ac.uk/~vgg/data/fgvc-aircraft/) | CC BY-SA 4.0 | No — download from source |
| [DTD (Describable Textures Dataset)](https://www.robots.ox.ac.uk/~vgg/data/dtd/) | Apache License 2.0 | No — download from source |
| [EuroSAT](https://github.com/phelber/eurosat) | Apache License 2.0 | No — download from source |

> **Note on INQUIRE:** The INQUIRE dataset ([Vendrow et al., 2024](#source-dataset-citations)) uses a CC BY-NC 4.0 license which restricts commercial use. To avoid imposing that restriction on this dataset, we do **not** distribute INQUIRE annotations. However, we will provide scripts and instructions to reproduce the INQUIRE-based annotations independently — see [Generating INQUIRE Annotations](#generating-inquire-annotations) below. Users who generate these annotations are responsible for complying with INQUIRE's [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/) terms.

## Getting Started

*Detailed setup instructions will be provided when the dataset is released.* The general workflow will be:

1. **Download source images** from each original dataset (links in the table above)
2. **Clone this repository** for annotations and code
3. **Configure image paths** and install dependencies
4. **Run evaluation scripts** as described in the paper

## Generating INQUIRE Annotations

The FSIR-BD-Compositional-INQUIRE sub-dataset is constructed from the INQUIRE benchmark, selecting 97 queries with at least 50 positives each, along with 150 hard negative images (same species) per query.

We will provide a script to reproduce these annotations. **Using them requires you to separately agree to and comply with INQUIRE's [CC BY-NC 4.0 license](https://creativecommons.org/licenses/by-nc/4.0/)**, which prohibits commercial use.

*Script and detailed instructions will be available upon release.*

## License

### Annotations and Code (this repository)

The annotations and code in this repository are released under the **CC BY-SA 4.0** license. See [LICENSE](LICENSE) for the full text.

This means you are free to:
- **Share** — copy and redistribute the material in any medium or format
- **Adapt** — remix, transform, and build upon the material for any purpose

Under the following terms:
- **Attribution (BY)** — you must give appropriate credit, provide a link to the license, and indicate if changes were made
- **ShareAlike (SA)** — if you remix, transform, or build upon the material, you must distribute your contributions under the same license

### Why CC BY-SA?

The inclusion of FGVC-Aircraft data (CC BY-SA 4.0) requires that derivative works be shared under compatible terms. CC BY-SA satisfies this requirement while remaining compatible with the Apache 2.0 and CC0 licenses of the other source datasets.

### Source Dataset Licenses

The original images and data remain under their respective licenses. By using this dataset, you agree to comply with all original license terms:

| Dataset | License | Full License Text |
|---|---|---|
| Visual Genome | Apache 2.0 | [Link](https://www.apache.org/licenses/LICENSE-2.0) |
| Flickr30K | CC0 1.0 | [Link](https://creativecommons.org/publicdomain/zero/1.0/) |
| FGVC-Aircraft | CC BY-SA 4.0 | [Link](https://creativecommons.org/licenses/by-sa/4.0/) |
| DTD | Apache 2.0 | [Link](https://www.apache.org/licenses/LICENSE-2.0) |
| EuroSAT | Apache 2.0 | [Link](https://www.apache.org/licenses/LICENSE-2.0) |

### Disclaimer

Users are solely responsible for ensuring their use of this dataset complies with all applicable license terms of both this repository and the original source datasets. The creators of FSIR make no warranties regarding the dataset and disclaim all liability for any use that violates the applicable license terms.

## Citation

If you use FSIR-BD in your research, please cite our paper:

```bibtex
@inproceedings{idan2026fsir,
  title={Few Shots Text to Image Retrieval: New Benchmarking Dataset and Optimization Methods},
  author={Idan, Ofer and Vexler, Vladi and Lederman, Gil and Sivov, Dima and Cohen Zada, Aviad and Niego Komforti, Shir},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
  year={2026}
}
```

### Source Dataset Citations

If you use FSIR-BD, please also cite the original source datasets:

**Visual Genome:**
```bibtex
@article{krishna2016visual,
  title={Visual Genome: Connecting Language and Vision Using Crowdsourced Dense Image Annotations},
  author={Krishna, Ranjay and Zhu, Yuke and Yu, Tiffany and Bernstein, Michael and Fei-Fei, Li},
  journal={arXiv preprint arXiv:1602.07332},
  year={2016}
}
```

**Flickr30K Entities:**
```bibtex
@article{plummer2015flickr30k,
  title={Flickr30k Entities: Collecting Region-to-Phrase Correspondences for Richer Image-to-Sentence Models},
  author={Plummer, B. A. and Wang, L. and Cervantes, C. M. and Caicedo, J. C. and Hockenmaier, J. and Lazebnik, S.},
  journal={arXiv preprint arXiv:1505.04870},
  year={2015}
}
```

**FGVC-Aircraft:**
```bibtex
@techreport{maji13fine-grained,
  title={Fine-Grained Visual Classification of Aircraft},
  author={S. Maji and J. Kannala and E. Rahtu and M. Blaschko and A. Vedaldi},
  year={2013},
  archivePrefix={arXiv},
  eprint={1306.5151}
}
```

**DTD (Describable Textures Dataset):**
```bibtex
@inproceedings{cimpoi14describing,
  title={Describing Textures in the Wild},
  author={M. Cimpoi and S. Maji and I. Kokkinos and S. Mohamed and A. Vedaldi},
  booktitle={Proceedings of the IEEE Conf. on Computer Vision and Pattern Recognition (CVPR)},
  year={2014}
}
```

**EuroSAT:**
```bibtex
@article{helber2019eurosat,
  title={EuroSAT: A Novel Dataset and Deep Learning Benchmark for Land Use and Land Cover Classification},
  author={Helber, Patrick and Bischke, Benjamin and Dengel, Andreas and Borth, Damian},
  journal={IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing},
  year={2019},
  publisher={IEEE}
}
```

**INQUIRE** (if you generate and use the INQUIRE-based annotations):
```bibtex
@article{vendrow2024inquire,
  title={INQUIRE: A Natural World Text-to-Image Retrieval Benchmark},
  author={Vendrow, Edward and Pantazis, Omiros and Shepard, Alexander and Brostow, Gabriel and Jones, Kate E and Mac Aodha, Oisin and Beery, Sara and Van Horn, Grant},
  journal={NeurIPS},
  year={2024}
}
```

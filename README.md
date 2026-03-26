# FSIR Dataset

[//]: # (TODO: Add paper title, authors, and arXiv link once available)

> **Paper:** *[Paper Title]* — [arXiv link]

## Overview

FSIR is a curated benchmark dataset for [brief description of task/domain]. It provides new annotations built on top of existing public datasets, enabling [brief description of what it enables].

This repository contains the **annotation files (JSONs) and code/scripts** used to construct and work with the FSIR dataset. **It does not contain any original images or files** — those must be obtained directly from the original dataset sources listed below.

## Source Datasets

| Dataset | License | Images Included Here? |
|---|---|---|
| [Visual Genome](https://homes.cs.washington.edu/~ranjay/visualgenome/) | Apache License 2.0 | No — download from source |
| [Flickr30K](http://shannon.cs.illinois.edu/DenotationGraph/) | CC0 (Public Domain) | No — download from source |
| [FGVC-Aircraft](https://www.robots.ox.ac.uk/~vgg/data/fgvc-aircraft/) | CC BY-SA 4.0 | No — download from source |
| [DTD (Describable Textures Dataset)](https://www.robots.ox.ac.uk/~vgg/data/dtd/) | Apache License 2.0 | No — download from source |
| [EuroSAT](https://github.com/phelber/eurosat) | Apache License 2.0 | No — download from source |

> **Note on INQUIRE:** The INQUIRE dataset uses a CC BY-NC 4.0 license which restricts commercial use. To avoid imposing that restriction on this dataset, we do **not** distribute INQUIRE annotations. However, we provide scripts and instructions to reproduce the INQUIRE-based annotations independently — see [Generating INQUIRE Annotations](#generating-inquire-annotations) below. Users who generate these annotations are responsible for complying with INQUIRE's CC BY-NC 4.0 terms.

## Repository Contents

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

[//]: # (TODO: Update directory structure to match actual repo layout)

## Getting Started

### 1. Download Source Images

Since this repository contains only annotations, you must first download the images from each source dataset. Follow the links in the [Source Datasets](#source-datasets) table above.

### 2. Set Up Image Paths

[//]: # (TODO: Add instructions for configuring image paths — e.g., a config file or env variable)

```bash
# Example
export VG_IMAGES_DIR=/path/to/visual_genome/images
export FLICKR30K_IMAGES_DIR=/path/to/flickr30k/images
# ... etc.
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

[//]: # (TODO: Add requirements.txt or update install instructions)

## Generating INQUIRE Annotations

We provide a script to reproduce the INQUIRE-based subset of our annotations. **Using these annotations requires you to separately agree to and comply with INQUIRE's [CC BY-NC 4.0 license](https://creativecommons.org/licenses/by-nc/4.0/)**, which prohibits commercial use.

```bash
# 1. Download INQUIRE from its official source
# 2. Run our generation script
python scripts/generate_inquire_annotations.py --inquire_dir /path/to/inquire --output_dir annotations/inquire/
```

[//]: # (TODO: Update script name and arguments to match actual implementation)

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

### Attribution Requirements

When using FSIR, please cite both this dataset and the relevant original sources:

```bibtex
@article{fsir2026,
  title={TODO: Paper Title},
  author={TODO: Authors},
  journal={arXiv preprint arXiv:XXXX.XXXXX},
  year={2026}
}
```

[//]: # (TODO: Add BibTeX entries for each source dataset)

### Disclaimer

Users are solely responsible for ensuring their use of this dataset complies with all applicable license terms of both this repository and the original source datasets. The creators of FSIR make no warranties regarding the dataset and disclaim all liability for any use that violates the applicable license terms.

## Citation

If you use FSIR in your research, please cite our paper:

```bibtex
@article{fsir2026,
  title={TODO: Paper Title},
  author={TODO: Authors},
  journal={arXiv preprint arXiv:XXXX.XXXXX},
  year={2026}
}
```

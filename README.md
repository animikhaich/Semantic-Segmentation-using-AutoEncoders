[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]

<!-- PROJECT LOGO -->
<br />
<p align="center">
    <img src="assets/vision_icon.png" alt="Logo" width="150" height="150">

  <h2 align="center">Semantic Segmentation using Auto Encoders</h2>

  <p align="center">
    A Lightweight Human (Person) Segmentation Model built using Autoencoders, trained on COCO.
    <br />
    <a href="https://nbviewer.jupyter.org/github/animikhaich/Semantic-Segmentation-using-AutoEncoders/blob/main/Model.ipynb">Model Notebook</a>
    ·
    <a href="https://github.com/animikhaich/Semantic-Segmentation-using-AutoEncoders/issues/new">Report Bug</a>
  </p>
</p>
<p align="center">
  <img src="assets/segmentation.png" alt="Demo GIF">
</p>
<!-- TABLE OF CONTENTS -->

## Table of Contents

- [Table of Contents](#table-of-contents)
- [About The Project](#about-the-project)
- [Jupyter Notebooks - nbViewer](#jupyter-notebooks---nbviewer)
- [Dataset Information](#dataset-information)
- [Features](#features)
- [Results](#results)
- [How to Run](#how-to-run)
  - [Hardware Used for the Experiment](#hardware-used-for-the-experiment)
  - [Dataset Directory Structure (For Training)](#dataset-directory-structure-for-training)
  - [Built With](#built-with)
- [Changelog](#changelog)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)
    - [Animikh Aich](#animikh-aich)

<!-- ABOUT THE PROJECT -->

## About The Project

Inspired from UNet ([Paper](https://arxiv.org/abs/1505.04597)), which is a form of Autoencoder with Skip Connections, I wondered why can't a much shallower network create segmentation masks for a single object? Hence, the birth of this small project.

The primary goal of this is to determine if a shallow end-to-end CNN can learn complicated features like human beings. Hence, as a proof of concept, this notebook has been created.

The noteboks do not render properly on GitHub, hence please use the [nbviewer](https://nbviewer.jupyter.org/) links provided below to see the results.

## Jupyter Notebooks - nbViewer

- [Dataset Preparation - Extracting Masks for Person from COCO Dataset](https://nbviewer.jupyter.org/github/animikhaich/Semantic-Segmentation-using-AutoEncoders/blob/main/Dataset%20Preparation.ipynb)
- [Model - Main Notebook Containing the Dataset Loader and Model Architecture](https://nbviewer.jupyter.org/github/animikhaich/Semantic-Segmentation-using-AutoEncoders/blob/main/Model.ipynb)


## Dataset Information

- The Model is trained on [COCO 2017 Dataset](https://cocodataset.org/).
- Dataset Splits Used:
  - Train: COCO 2017 Train Images + Train Annotations - `instances_train2017.json`
  - Val: COCO 2017 Val Images + Val Annotations - `instances_val2017.json`
- Dataset Download: https://cocodataset.org/#download
- Dataset Format Information: https://cocodataset.org/#format-data
- API to parse COCO: https://github.com/philferriere/cocoapi

## Features

- **Pre Trained Weights** - The weights can directly be downloaded from here: [weights.h5](https://github.com/animikhaich/Semantic-Segmentation-using-AutoEncoders/blob/main/weights.h5) - It is stored using Git LFS.
- **Fast Inference** - Inference Time for batch of `32` images of `512x512` dimensions with an Nvidia RTX 2080Ti is just `10.3 µs`.

## Results

Images (Left to Right): `Input Image`, `Predicted Image`, `Thresholded Mask @ 0.5`, `Ground Truth Mask`

![Result 1](assets/result_1.png)
![Result 2](assets/result_2.png)
![Result 3](assets/result_3.png)
![Result 4](assets/result_4.png)
![Result 5](assets/result_5.png)
![Result 6](assets/result_6.png)
![Result 7](assets/result_7.png)
![Result 8](assets/result_8.png)
![Result 9](assets/result_9.png)
![Result 10](assets/result_10.png)
![Result 11](assets/result_11.png)
![Result 12](assets/result_12.png)

## How to Run

The experiment should be fairly reproducible. However, a GPU would be recommended for training. For Inference, a CPU System would suffice.

### Hardware Used for the Experiment

- CPU: AMD Ryzen 7 3700X - 8 Cores 16 Threads
- GPU: Nvidia GeForce RTX 2080 Ti 11 GB
- RAM: 32 GB DDR4 @ 3200 MHz
- Storage: 1 TB NVMe SSD (This is not important, even a normal SSD would suffice)
- OS: Ubuntu 20.10

Alternative Option: [Google Colaboratory - GPU Kernel](https://colab.research.google.com/)

### Dataset Directory Structure (For Training)

- Use the COCO API to extract the masks from the dataset. (Refer: [Dataset Preparation.ipynb Notebook](https://nbviewer.jupyter.org/github/animikhaich/Semantic-Segmentation-using-AutoEncoders/blob/main/Dataset%20Preparation.ipynb))
- Save the masks in a directory as `.jpg` images.
- Example Directory Structure:

```sh
.
├── images
│   ├── train
│   │   ├── *.jpg
│   └── val
│       └── *.jpg
└── masks
│   ├── train
│   │   ├── *.jpg
│   └── val
│       └── *.jpg
```

### Built With

Simple List of Deep Learning Libraries. The main Architecture/Model is developed with Keras, which comes as a part of Tensorflow 2.x

- [Tensorflow 2.4.1](https://www.tensorflow.org/)
- [OpenCV 4.5.1.48](https://opencv.org/)
- [Numpy 1.19.5](https://numpy.org/)
- [Matplotlib 3.3.4](https://matplotlib.org/)
- [PyCOCOTools 2.0.2](https://github.com/philferriere/cocoapi)


## Changelog

Since this is a Proof of Concept Project, I am not maintaining a CHANGELOG.md at the moment. However, the primary goal is to improve the architecture to make the predicted masks more accurate.


## Contributing

Contributions are what make the open source community such an amazing place to be learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

Distributed under the MIT License. See [LICENSE](LICENSE.md) for more information.

## Contact

#### Animikh Aich

- Website: [Animikh Aich - Website](http://www.animikh.me/)
- LinkedIn: [animikh-aich](https://www.linkedin.com/in/animikh-aich/)
- Email: [animikhaich@gmail.com](mailto:animikhaich@gmail.com)
- Twitter: [@AichAnimikh](https://twitter.com/AichAnimikh)

<!-- MARKDOWN LINKS & IMAGES -->

[contributors-shield]: https://img.shields.io/github/contributors/animikhaich/Semantic-Segmentation-using-AutoEncoders.svg?style=flat-square
[contributors-url]: https://github.com/animikhaich/Semantic-Segmentation-using-AutoEncoders/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/animikhaich/Semantic-Segmentation-using-AutoEncoders.svg?style=flat-square
[forks-url]: https://github.com/animikhaich/Semantic-Segmentation-using-AutoEncoders/network/members
[stars-shield]: https://img.shields.io/github/stars/animikhaich/Semantic-Segmentation-using-AutoEncoders.svg?style=flat-square
[stars-url]: https://github.com/animikhaich/Semantic-Segmentation-using-AutoEncoders/stargazers
[issues-shield]: https://img.shields.io/github/issues/animikhaich/Semantic-Segmentation-using-AutoEncoders.svg?style=flat-square
[issues-url]: https://github.com/animikhaich/Semantic-Segmentation-using-AutoEncoders/issues
[license-shield]: https://img.shields.io/github/license/animikhaich/Semantic-Segmentation-using-AutoEncoders.svg?style=flat-square
[license-url]: https://github.com/animikhaich/Semantic-Segmentation-using-AutoEncoders/blob/master/LICENSE.md
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=flat-square&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/animikh-aich/
[product-screenshot]: assets/face-blur-demo.gif

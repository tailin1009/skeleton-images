# Skeleton Images Representation (SkeleMotion and TSRJI)

This repository holds the skeleton image representation codes for the papers
 
> 
**SkeleMotion: A New Representation of Skeleton Joint Sequences Based on Motion Information for 3D Action Recognition**,
Carlos Caetano, Jessica Sena, François Brémond, Jefersson A. dos Santos, and William Robson Schwartz,
*AVSS 2019*, Taipei, Taiwan.
>
[[Arxiv Preprint](https://arxiv.org/abs/1907.13025)]

> 
**Skeleton Image Representation for 3D Action Recognition based on Tree Structure and Reference Joints**,
Carlos Caetano, François Brémond and William Robson Schwartz,
*SIBGRAPI 2019*, Rio de Janeiro, Brazil.
>
[[Arxiv Preprint](https://arxiv.org/abs/1909.05704)]

# Contents
* [Usage Guide](#usage-guide)
  * [Prerequisites](#prerequisites)
  * [Code & Data Preparation](#code--data-preparation)
    * [Get the code](#get-the-code)
    * [Get the Skeleton Data](#get-the-skeleton-data)
    * [Usage](#usage)
* [Other Info](#other-info)
  * [Citation](#citation)
  * [Contact](#contact)

----
# Usage Guide

## Prerequisites
[[back to top](#skeleton-images-representation-SkeleMotion-and-SRJI)]

The main dependencies to run the code are

- [OpenCV][opencv]
- [NumPy][numpy]

The codebase is written in Python 3.6. We recommend the [Anaconda][anaconda] Python distribution.

## Code & Data Preparation

### Get the code
[[back to top](#skeleton-images-representation-SkeleMotion-and-SRJI)]

Use git to clone this repository
```
git clone --recursive https://github.com/carloscaetano/skeleton-images
```

### Get the Skeleton Data
[[back to top](#skeleton-images-representation-SkeleMotion-and-SRJI)]

We experimented our skeleton images representation on two large-scale 3D action recognition datasets: [NTURGB+D 60][nturgb-d60] and [NTURGB+D 120][nturgb-d120]. For more information about accessing the "NTU RGB+D" and "NTU RGB+D 120" datasets, go to [ROSE website][rose].

### Usage
[[back to top](#skeleton-images-representation-SkeleMotion-and-SRJI)]

To extract the skeleton images on NTU dataset, run the GenerateSkeletonImages.py. It has four arguments:
- [--data_path] Directory containing the NTU skeleton data
- [--img_type] Image type to compute:
  - 1 - CaetanoMagnitude (SkeleMotion - AVSS2019);
  - 2 - CaetanoOrientation (SkeleMotion - AVSS2019);
  - 3 - CaetanoTSRJI (TSRJI - SIBGRAPI2019)
- [--temp_dist] Temporal distance between frames
- [--path_to_save] Directory to save the extracted skeleton images

#### Example
To extract the Magnitude skeleton image, with temporal distance = 10, from the NTU dataset located in the directory ./nturgb+d_skeletons/ and save the skeleton images to the folder ./CaetanoMagnitude, you can run
```
python GenerateSkeletonImages.py --data_path ./nturgb+d_skeletons/ --img_type 1 --temp_dist 10 --path_to_save ./CaetanoMagnitude
```

# Other Info
[[back to top](#skeleton-images-representation-SkeleMotion-and-SRJI))]

## Citation
Please cite the following papers if you feel this repository useful.
```
@inproceedings{Caetano:AVSS:2019,
  author    = {Carlos Caetano and
               Jessica Sena and
               François Brémond and
               Jefersson A. dos Santos and
               William Robson Schwartz},
  title     = {SkeleMotion: A New Representation of Skeleton Joint Sequences Based on Motion Information for 3D Action Recognition},
  booktitle   = {IEEE International Conference on Advanced Video and Signal-based Surveillance (AVSS)},
  year      = {2019},
}

@inproceedings{Caetano:SIBGRAPI:2019,
  author    = {Carlos Caetano and
               François Brémond and
               William Robson Schwartz},
  title     = {Skeleton Image Representation for 3D Action Recognition based on Tree Structure and Reference Joints},
  booktitle   = {Conference on Graphics, Patterns and Images (SIBGRAPI)},
  year      = {2019},
}
```

## Contact
For any question, please contact
```
Carlos Caetano: carlos.caetano@dcc.ufmg.br
```

[nturgb-d60]:https://github.com/shahroudy/NTURGB-D
[nturgb-d120]:https://github.com/shahroudy/NTURGB-D
[rose]:http://rose1.ntu.edu.sg/Datasets/actionRecognition.asp
[anaconda]:https://www.continuum.io/downloads
[opencv]:https://opencv.org/
[numpy]:https://numpy.org/

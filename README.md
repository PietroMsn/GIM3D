# GIM3D: A 3D dataset for garment segmentation

GIM3D (Garments In Motion 3D) is a synthetic dataset of clothed 3D human characters in different poses. The over 4000 3D models in this dataset are produced by a physical simulation of clothes with different fabrics, sizes, and tightness, using animated human avatars having a large variety of shapes. Our dataset is composed of single meshes created to simulate 3D scans, with labels for the separate clothes and the visible body parts. See the original paper for more info.

<p align="center">
<img src="teaser_def.png"
</p>

Musoni, P. and Melzi, S. and Castellani, U., GIM3D: A 3D dataset for garment segmentation, STAG 2022 

Musoni, P. and Melzi, S. and Castellani, U., GIM3D plus: A labeled 3D dataset to design data-driven solutions for dressed humans, Graphical Models 2023

## Download and Papers

To download the dataset: [Download Dataset](https://univr-my.sharepoint.com/:f:/g/personal/pietro_musoni_univr_it/Es41qfco4zBKqx6ovPfcg5MB17zDTK9HbyAYjOkExq6Www?e=LkmbRQ)

The conference paper: [GIM3D](https://diglib.eg.org/bitstream/handle/10.2312/stag20221252/021-028.pdf)

The journal paper: [GIM3Dplus](https://www.sciencedirect.com/science/article/pii/S1524070323000176)
## Contents
* [Data](https://github.com/PietroMsn/GIM3D#Data)
* [Quick-start](https://github.com/PietroMsn/GIM3D#Quick-start)
* [Requirements](https://github.com/PietroMsn/GIM3D#requirements)
* [License](https://github.com/PietroMsn/GIM3D#license)
* [Acknowledgements](https://github.com/PietroMsn/GIM3D#acknowledgements)

 
 
## Data
```
Root_dir
  |_______Outfit Category
                |_________subject number
                                |___________ *_merged_manifold_decimated.ply
                                |___________ *_segmentation_data.txt
                                |___________ *_segmentation_labels.mat
```

For each subject directory there are three files:
- *_merged_manifold_decimated.ply that is the triangular mesh of the 3D model
- *_segmentation_data.txt that contains for each line the 7 numbers that we will explain below
- *_segmentation_labels.mat that is a matlab data file (radable through python by using scipy.io) containing the bin and the tri labels as explained in the paper

Each line of the "*_segmentation_data.txt" file has 7 numbers, for each vertex of the model.
Example:
```
0.482615 1.230420 0.026307 -0.953433 -0.173879 -0.246437 0.000000
...
0.711867 1.658515 1.071912 0.065284 0.972992 0.221414 1.000000
0.722283 1.660060 1.061142 0.055423 0.981116 0.185309 1.000000
```
The first three numbers are the three coordinates for each vertex of the model, the second three numbers specifies the normal for each vertex, the last number is the label for the vertex. The label is 0 for the body and 1 for the clothes. This format is compatible for the implementation of pointnet and pointnet++ (e.g. with the pytorch [PointNet and PointNet++ Code](https://github.com/yanx27/Pointnet_Pointnet2_pytorch)). Other formats (DiffusionNet, Point-Transformer) are available on request (email: pietro.musoni@univr.it).

In each category the directory "labels_tri"  contains the .txt files formatted as explained above but the lables indicates 0 for the body, 1 for the upper clothes and 2 for the lower clothes (e.g. in tshirts_trousers/labels_tri 1 stands for the tshirt vertices and 2 for the trousers).

## Quick-start  

The code for the creation of new poses will be available soon...
  
## Requirements

  
  
## License
Please check the license terms (also of third parts software) before downloading and/or using the code, the models and the data. 
All code and results obtained from it not already covered by other licenses has to be intendend only for non-commercial scientific research purposes.
Any other use, in particular any use for commercial purposes, is prohibited. This includes, without limitation, incorporation in a commercial product, use in a commercial service, or production of other artefacts for commercial purposes including, for example, 3D models, movies, or video games. 

## Acknowledgements
  
This work is partially supported by the project of the Italian Ministry of Education, Universities and Research (MIUR) ”Dipartimenti di Eccellenza 2018-2022” of the Department of Computer Science of Verona University

If you use this code and/or data, please cite:
```
@article{musoni2023gim3dplus,
title = {GIM3D plus: A labeled 3D dataset to design data-driven solutions for dressed humans},
journal = {Graphical Models},
volume = {129},
pages = {101187},
year = {2023},
issn = {1524-0703},
doi = {https://doi.org/10.1016/j.gmod.2023.101187},
url = {https://www.sciencedirect.com/science/article/pii/S1524070323000176},
author = {Pietro Musoni and Simone Melzi and Umberto Castellani},
}
```
and
```
@inproceedings {musoni2022gim3d,
booktitle = {Smart Tools and Applications in Graphics - Eurographics Italian Chapter Conference},
editor = {Cabiddu, Daniela and Schneider, Teseo and Allegra, Dario and Catalano, Chiara Eva and Cherchi, Gianmarco and Scateni, Riccardo},
title = {{GIM3D: A 3D Dataset for Garment Segmentation}},
author = {Musoni, Pietro and Melzi, Simone and Castellani, Umberto},
year = {2022},
publisher = {The Eurographics Association},
ISSN = {2617-4855},
ISBN = {978-3-03868-191-5},
DOI = {10.2312/stag.20221252}
}
```

The original unmerged 3D models come from the [CLOTH3D](https://chalearnlap.cvc.uab.cat/dataset/38/description/) dataset:
```
@inproceedings{bertiche2020cloth3d,
  title={CLOTH3D: Clothed 3D Humans},
  author={Bertiche, Hugo and Madadi, Meysam and Escalera, Sergio},
  booktitle={European Conference on Computer Vision},
  pages={344--359},
  year={2020},
  organization={Springer}
}
```

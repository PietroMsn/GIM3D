# Scanned GIM3D

GIM3D (Garments In Motion 3D) is a synthetic dataset of clothed 3D human characters in different poses. The over 4000 3D models in this dataset are produced by a physical simulation of clothes with different fabrics, sizes, and tightness, using animated human avatars having a large variety of shapes. Our dataset is composed of single meshes created to simulate 3D scans, with labels for the separate clothes and the visible body parts. See the original paper for more info.

<p align="center">
<img src="pipeline_dataset2.png"
</p>

Garavaso, D., and Masi, F., and Musoni, P. , S. and Castellani, U., Point Cloud Segmentation for 3d Clothed Human Layering, 3DOR 2025



## Download and Papers

To download the dataset: [Download Dataset](https://univr-my.sharepoint.com/:f:/g/personal/pietro_musoni_univr_it/EjZ0-1KtCn1NhqmtcdkuDngBK5l3gXg5kc-_8AZ3N0sBZA?e=AU90nM)

Pre-print paper: [Point Cloud Segmentation for 3d Clothed Human Layering](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5258952)

## Contents
* [Data](https://github.com/PietroMsn/GIM3D#Data)
* [Quick-start](https://github.com/PietroMsn/GIM3D#Quick-start)
* [Requirements](https://github.com/PietroMsn/GIM3D#requirements)
* [License](https://github.com/PietroMsn/GIM3D#license)
* [Acknowledgements](https://github.com/PietroMsn/GIM3D#acknowledgements)

 
 
## Data
```
Root_dir
|_________subject folder
                |___________ coord.npy (6000, 3) array
                |___________ normal.npy: (6000, 3) array
                |___________ segment.npy: (6000) array
                |___________ coord_smpl.npy (6000, 3) array
                |___________ normal_smpl.npy: (6000, 3)
                |___________ smpl.npy (6000, 3) array
```

For each subject directory there are six .npy files:
- coord.npy: (6000, 3) array containing the points of the scanned mesh
- normal.npy: (6000, 3) array containing the normals of the scanned mesh
- segment.npy: (6000) array containing the groundtruth labels of the segmented scanned mesh
- coord_smpl.npy: (6000, 3) array containing the ground truth coordinates of the underlying smpl model
- normal_smpl.npy (6000, 3) array containing the normals of the underlying smpl model
- smpl.npy: (6000) array containing the ground truth labels (body/no-body) of the scanned point-cloud (see the paper for more details)


## Segmentation-code  

To reproduce the segmentation results in the paper refer to [Multilayer Code](https://github.com/PietroMsn/Extended-Pointcept-Multilayer-Segmentation). This is a fork of the original code of PointCept (https://github.com/Pointcept/Pointcept) adapted to multilayer clothed human segmentation.
  
## License
Please check the license terms (also of third parts software) before downloading and/or using the code, the models and the data. 
All code and results obtained from it not already covered by other licenses has to be intendend only for non-commercial scientific research purposes.
Any other use, in particular any use for commercial purposes, is prohibited. This includes, without limitation, incorporation in a commercial product, use in a commercial service, or production of other artefacts for commercial purposes including, for example, 3D models, movies, or video games. 

## Acknowledgements
  
This work is partially supported by the project of the Italian Ministry of Education, Universities and Research (MIUR) ”Dipartimenti di Eccellenza 2018-2022” of the Department of Computer Science of Verona University

If you use this code and/or data, please cite:
'''
@article{garavaso5258952point,
  title={Point Cloud Segmentation for 3d Clothed Human Layering},
  author={Garavaso, Davide and Masi, Federico and Musoni, Pietro and Castellani, Umberto},
  journal={Available at SSRN 5258952}
}
'''
and
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

The original 3D models come from the [CLOTH3D](https://chalearnlap.cvc.uab.cat/dataset/38/description/) dataset:
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

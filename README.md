# ReadMVS : a tool for exporting dense point cloud data

The goal of this work is to add a tool to the OpenMVS library (original description below) that enables storing, for each 3D point of a dense point cloud, the list of images that enabled computing the position of this point in the 3D space thanks to triangulation, and the confidence on the accuracy of this position.
The data is read and extracted from one output of OpenMVS, the *sfm_data_dense.mvs* file which is written in a compressed binary format.  

## Introduction

[OpenMVS (Multi-View Stereo)](http://cdcseacave.github.io/openMVS) is a library for computer-vision scientists and especially targeted to the Multi-View Stereo reconstruction community. While there are mature and complete open-source projects targeting Structure-from-Motion pipelines (like [OpenMVG](https://github.com/openMVG/openMVG)) which recover camera poses and a sparse 3D point-cloud from an input set of images, there are none addressing the last part of the photogrammetry chain-flow. *OpenMVS* aims at filling that gap by providing a complete set of algorithms to recover the full surface of the scene to be reconstructed. The input is a set of camera poses plus the sparse point-cloud and the output is a textured mesh. The main topics covered by this project are:

- **dense point-cloud reconstruction** for obtaining a complete and accurate as possible point-cloud
- **mesh reconstruction** for estimating a mesh surface that explains the best the input point-cloud
- **mesh refinement** for recovering all fine details
- **mesh texturing** for computing a sharp and accurate texture to color the mesh

See the complete [documentation](https://github.com/cdcseacave/openMVS/wiki) on wiki.

## Build

See the [building](https://github.com/cdcseacave/openMVS/wiki/Building) wiki page.

Continuous integration:
 - linux 64 bits/GCC: [![Build Status](https://travis-ci.org/cdcseacave/openMVS.svg?branch=master)](https://travis-ci.org/cdcseacave/openMVS)

## Example

See the usage [example](https://github.com/cdcseacave/openMVS/wiki/Usage) wiki page.

## License

See the [copyright](https://github.com/cdcseacave/openMVS/blob/master/COPYRIGHT.md) file.

## Contact

openmvs[AT]googlegroups.com

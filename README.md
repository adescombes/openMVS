# ReadMVS : a tool for exporting dense point cloud data

The goal of this work is to add a tool to the [OpenMVS library](http://cdcseacave.github.io/openMVS) that enables storing, for each 3D point of a dense point cloud, the list of images that enabled computing the position of this point in the 3D space thanks to triangulation, and the confidence on the accuracy of this position.
The data is read and extracted from one output of OpenMVS, the *sfm_data_dense.mvs* file which is written in a compressed binary format.  
The output of ReadMVS is a file called *sfm_data_dense.bin*, at the same location as *sfm_data_dense.mvs*. Its structure is the following: 

```
[x][y][z][n][view_id_0][confidence_0][0][view_id_1][confidence_1][0]...[view_id_n][confidence_n][0][x][y][z][n][view_id_0][confidence_0][0][view_id_1][confidence_1][0]...
```
with the following format characters:
- x, y and z : floats. 3D coordinates of each point
- n : long long. Number of views that see one 3D point
- view_id_k : int. Index of the view (image) 
- confidence_k : float. Confidence with which the 3D point has been placed by view_id_k
- 4 empty bytes are left after each ```[view_id_k][confidence_k]```

#### Usage

```
./ReadMVS sfm_data_dense.mvs 
```
or 
```
./ReadMVS -i sfm_data_dense.mvs -o sfm_data_dense.bin
```
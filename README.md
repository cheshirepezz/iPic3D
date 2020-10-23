# iPic3D instruction guide

Particle-in-Cell code using the implicit moment method.

Please find the instructions to compile 
    1) mpich
    2) hdf5
    3) H5hut
    
Things between "..." are instructions to type in the terminal (without " "). You have to substitute things between <...> with your path (e.g., the whole address of the folder; this can be found in the terminal typing "pwd" from the folder).
Before doing anything, create mpich, hdf5 and H5hut directories in the folder prod/opt, following these instructions:
a) open terminal
b) type "cd ~/prod/opt"
e) type "mkdir -p compilers/mpich/3.2.1"
f) type "mkdir -p libraries/hdf5/1.8.12/mpich-3.2.1"
g) type "mkdir -p libraries/H5hut/1.99.13/hdf5-1.8.12/mpich-3.2.1"
h) type "mkdir -p applications/cmake/3.14.4"

Now compile mpich, hdf5, H5hut and cmake following these instructions in this correct order:

### [mpich](https://www.mpich.org/downloads/) (mpi distribution)
1) download mpich-3.2.1 (usually in the Downloads folder)
2) untar the folder (in the Downloads folder from the terminal type: "tar -xvf <mpich_folder_name>")
3) type "cd <mpich_folder_name>"
4) type "./configure --prefix=<path_of_the_folder_created_at_point_e> --enable-static CC=gcc CXX=g++ --disable-fortran"
(the path_of_the_folder_created_at_point_e should be somethiing like ~/prod/opt/compilers/mpich/3.2.1)
5) type "make"
6) type "make install"

### [hdf5](https://support.hdfgroup.org/ftp/HDF5/releases/hdf5-1.8/hdf5-1.8.12/obtain51812.html)

1) download hdf5-1.8.12.tar.gz (source code for all platforms)
2) untar the folder (in the Downloads folder from the terminal type: "tar -xvf <hdf5_folder_name>")
3) type "cd <hdf5_folder_name>"
4) type "./configure --prefix=<path_of_the_folder_created_at_point_f>  --enable-parallel --enable-hl --enable-shared CC=<path_of_the_folder_created_at_point_e>/bin/mpicc" CXX=<path_of_the_folder_created_at_point_e>/bin/mpicxx"
(the path_of_the_folder_created_at_point_e should be somethiing like ~/prod/opt/compilers/mpich/3.2.1; the path_of_the_folder_created_at_point_f should be somethiing like ~/prod/opt/libraries/hdf5/1.8.12/mpich-3.2.1)
5) type "make"
6) type "make install"

### [H5hut](https://gitlab.psi.ch/H5hut/src/tree/1.99.13)

1) download H5hut.tar.gz
2) untar the folder (in the Downloads folder from the terminal type: "tar -xvf <H5hut_folder_name>")
3) type "cd <H5hut_folder_name>"
4) type "./autogen.sh"
5) type "./configure --prefix=<path_of_the_folder_created_at_point_g> --with-hdf5=<path_of_the_folder_created_at_point_f>  --enable-shared CC=<path_of_the_folder_created_at_point_e>/bin/mpicc" CXX=<path_of_the_folder_created_at_point_e>/bin/mpicxx"
(the path_of_the_folder_created_at_point_e should be somethiing like ~/prod/opt/compilers/mpich/3.2.1; the path_of_the_folder_created_at_point_f should be somethiing like ~/prod/opt/libraries/hdf5/1.8.12/mpich-3.2.1;
the path_of_the_folder_created_at_point_g should be somethiing like ~/prod/opt/libraries/H5hut/1.99.13/hdf5-1.8.12/mpich-3.2.1)
6) type "make"
7) type "make install"

It is also convenient to install [hdfview](https://www.hdfgroup.org/downloads/hdfview/).

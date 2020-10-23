# iPic3D
Particle-in-Cell code using the implicit moment method


Open a terminal and write the command below to clone in your PC Plasma-Recipes repo:

```
git clone https://github.com/cheshirepezz/CEM.git
cd CEM
```

Instructions to compile 
   1) mpich
   2) hdf5
   3) H5hut
   
Things between "..." are instructions to type in the terminal (without " "). You have to substitute things between <...> with your path (e.g., the whole address of the folder; this can be found in the terminal typing "pwd" from the folder).
Before doing anything, create mpich, hdf5 and H5hut directories in the folder prod/opt, following these instructions:
open terminal

```
cd ~/prod/opt
mkdir -p compilers/mpich/3.2.1
mkdir -p libraries/hdf5/1.8.12/mpich-3.2.1
mkdir -p libraries/H5hut/1.99.13/hdf5-1.8.12/mpich-3.2.1
mkdir -p applications/cmake/3.14.4
```

Now compile mpich, hdf5, H5hut and cmake following these instructions in this correct order:
### mpich (mpi distribution)https://www.mpich.org/downloads/
1) download mpich-3.2.1 (usually in the Downloads folder)
2) untar the folder (in the Downloads folder from the terminal type: "tar -xvf <mpich_folder_name>")
```
cd <mpich_folder_name>"
./configure --prefix=<path_of_the_folder_created_at_point_e> --enable-static CC=gcc CXX=g++ --disable-fortran
```
the path_of_the_folder_created_at_point_e should be somethiing like ~/prod/opt/compilers/mpich/3.2.1
```
make
make install
```

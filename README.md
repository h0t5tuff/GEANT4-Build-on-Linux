1. move the two scripts in this repo to your home directory.

2. open .zshrc/.bashrc file in your home directory and comment out any Geant4 related lines.

3. now excute the build/uninstall script:

>chmod +x file_name.sh

4. finally run the build/uninstall script:

>./file_name.sh

5. Discard of this README.md












## Build an example

Copy an example from src to my geant4 folder

>cd geant4
>
>cp -R /Users/tensor/geant4/src/examples/basic/B1 ~/geant4/B1_Tensor
>
>cd ~/geant4examples/B1_tensor

Build

>mkdir build && cd build


on linux

>cmake .. -DCMAKE_BUILD_TYPE=Release -DGeant4_DIR=/home/bacon/geant4/geant4_install/lib/cmake/Geant4 -DCMAKE_PREFIX_PATH="/usr/local/Cellar/root/6.36.01;/home/bacon/geant4/geant4_install/lib/Geant4-11.3.1/cmake"
>
>make -j$(nproc)

Check what was enabled during build
>cat /Users/tensor/geant4/build/CMakeCache.txt | grep GEANT4_USE

Confirm Geant4 Build Has Qt, OpenGL, GDML, CADMesh, etc
>$HOME/geant4/install/bin/geant4-config --features

run Interactive session
>./exampleB1

In Geant4 prompt
>/control/execute vis.mac

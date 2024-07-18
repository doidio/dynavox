# DynaVox

dynamic volume rendering from static CT images

## User Guide

TODO

## Developer Guide

### How to pip install CUDA wheel

#### build non-CUDA .whl

```shell
git clone https://github.com/doidio/dynavox.git
cd SPlisHSPlasH
python setup.py bdist_wheel -DCMAKE_TOOLCHAIN_FILE=<vcpkg>/scripts/buildsystems/vcpkg.cmake
```

then check `pySPlisHSPlasH-xxx.whl` file in `build/dist`

#### install [CUDA Tookit](https://developer.nvidia.com/cuda-toolkit)

#### build CUDA .pyd

CLion Settings/CMake/Release

```
Generator=
non-Ninja Generator
```

```
CMakeOptions=
-DCMAKE_TOOLCHAIN_FILE=-DCMAKE_TOOLCHAIN_FILE=<vcpkg>/scripts/buildsystems/vcpkg.cmake
-DPYTHON_EXECUTABLE=<python.exe>
-DUSE_GPU_NEIGHBORHOOD_SEARCH=ON
-DBuild_FoamGenerator=OFF
-DBuild_MeshSkinning=OFF
-DBuild_VolumeSampling=OFF
```

build then check `pysplishsplash.xxx.pyd` file in `<cmake-build-release>/lib/Release`

#### replace .pyd

use [7-Zip](https://www.7-zip.org/download.html) open `pySPlisHSPlasH-xxx.whl`
and replace `pysplishsplash.xxx.pyd` then

#### pip install

```shell
pip install pySPlisHSPlasH-xxx.whl
```

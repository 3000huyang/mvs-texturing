#  MVS-Texturing windows 配置

------------------------------------------------------------

修正了在windows下由于MSVC只支持openmp 2.0引起的bug
增加内置依赖的MVE库，通过CMake即可编译

在VS2017 上测试通过，推荐使用VCPKG来安装tbb库。

如果使用VS2017，那么可以直接打开CMake工程，并修改CMakeSettings.json文件来配置


 VCPKG 使用请参见[https://github.com/Microsoft/vcpkg](https://github.com/Microsoft/vcpkg)

(Update: GN now has its new home at https://gn.googlesource.com/. And it can now be built using a single python build script.)

Stand Alone GN
This repo has a patch to make GN run as standalone binary with [build] setup folder placed anywhere/ or fixed in your system. This flexibility is made possible with a custom BUILD_CONFIG_ROOT in your project .gn file. With this patch, GN can run as a standalone setup for any small to medium size projects and you do not need to always copy [build] setup folder in every project folder.)
(Note: this repository has only tracked up to April 2018.)

# gn-standalone-mirror
Google GN Build Tool mirror++.

GN is a meta build system from Google Chrome/Chromium development team. It implements clean tooling language and good set of features. For more information, follow the links:
1) Google GN project https://chromium.googlesource.com/chromium/src/tools/gn/
2) GN doc at 2015 https://docs.google.com/presentation/d/15Zwb53JcncHfEwHpnG_PoIbbzQ3GQi_cpujYwbpcbZo/edit#slide=id.g119d702868_0_12 (By Brett Wilson)

As integral part of the Chromium source three, the GN source relies heavily on the underlying Chromium source tree for its base code. To build GN, the best approach is to checking out the Gigabytes of Chromium code in hours and build the GN tools in few minutes. To save the long checkout time, there have been scripts to checkout the required source that is sufficient to build the GN binary using the built-in bootstrap script.

Since the GN boostrap script is not maintained regularlily, the bootstrap build often fails for mostly irrelevant changes in the supporting Chromium code. This repo aims to maintain a Point Release that builds out of box for Windows/Linux/MacOS X with and only with the bootstrap script.

Dependency:
1) Ninja Build 
GN generates low-level "ninja" build files and uses ninja to do the real building job. You will need to have ninja binary included in the system environemnt PATH. 

2) msvcrt64.bat for Windows build

    a) Use the Windows SDK menus from Windows Startup Menu. Or

    b) Use the following link at https://gist.github.com/DanCraft99/3a99be44e26a1cd878b8578863cfcef6 for setup.



Build Steps:
1) To pull the code with submodules:

    git clone --recursive https://github.com/DanCraft99/gn-standalone-mirror

2) To pull in the latest code:

    git submodule update --init --recursive (for missing out the --recursive flag at initial check out)
    git submodule update (for subsequent check out)

3) Apply the latest patch:

    cd gn-standalone-mirror/gn-standalone/tools/gn/bootstrap
    patch -p2 < ../../../../patch/gn_bootstrap_patch.diff

4) Build

    (optional) python bootstrap.py --help
    
    python bootstrap.py -s --no-clean

Links:
1) Basic //build directory for use with Chromium's GN https://github.com/timniederhausen/gn-build
2) GN Group https://groups.google.com/a/chromium.org/forum/#!forum/gn-dev
3) Search for "gn standalone"
4) gist at https://gist.github.com/mohamed/4fa7eb75807463d4dfa3 for script to check out standalone gn code and its dependencies. 
5) Ninja build system at https://github.com/ninja-build/ninja
6) Other ninja generators, esp CMake and Meson, at https://github.com/ninja-build/ninja/wiki/List-of-generators-producing-ninja-build-files.

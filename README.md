# gn-standalone-mirror
Google GN Build Tool mirror.

GN is a meta build system from Google Chrome/Chromium development team. It implements clean tooling language and good set of features. For more information, follow the links:
1) Google GN project https://chromium.googlesource.com/chromium/src/tools/gn/
2) GN doc at 2015 https://docs.google.com/presentation/d/15Zwb53JcncHfEwHpnG_PoIbbzQ3GQi_cpujYwbpcbZo/edit#slide=id.g119d702868_0_12

As integral part of the Chromium source three, the GN source relies heavily on the underlying Chromium source tree for its base code. To build GN, the best approach is to checking out the Gigabytes of Chromium code in hours and build the GN tools in few minutes. To save the long checkout time, there have been scripts to checkout the required source that is sufficient to build the GN binary using the built-in bootstrap script. Follow https://gist.github.com/mohamed/4fa7eb75807463d4dfa3 For the link. 

Since the GN boostrap script is not maintained regularlily, the bootstrap build often fails for mostly irrelevant changes in the supporting Chromium code. This repo aims to maintain a Point Release that builds out of box for Windows/Linux/MacOS X.

Links:
1) Basic //build directory for use with Chromium's GN https://github.com/timniederhausen/gn-build
2) GN Group https://groups.google.com/a/chromium.org/forum/#!forum/gn-dev
3) Search for "gn standalone"

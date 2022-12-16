prerequisites: doxygen, python3, doxygen2docset (https://github.com/chinmaygarde/doxygen2docset/releases)

meson build
cd build && ninja doc

in build/doc/api/doxy-api.conf
GENERATE_DOCSET   = YES
DISABLE_INDEX     = YES
GENERATE_TREEVIEW = NO
DOCSET_BUNDLE_ID   = dpdk
DOCSET_PUBLISHER_ID = org.ilkondr
DOCSET_PUBLISHER_NAME= ilkondr

doxygen2docset --doxygen doc/api/{api/html} --docset ${target}

dpdk icon:
https://pbs.twimg.com/profile_images/847934144243945473/Hpd83-Cr_400x400.jpg

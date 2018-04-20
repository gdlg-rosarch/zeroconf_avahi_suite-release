# Script generated with Bloom
pkgdesc="ROS - Provides zeroconf services on avahi for ros systems. This is a c++ implementation."
url='http://wiki.ros.org/zeroconf_avahi'

pkgname='ros-kinetic-zeroconf-avahi'
pkgver='0.2.3_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('avahi'
'ros-kinetic-catkin'
'ros-kinetic-rosconsole'
'ros-kinetic-roscpp'
'ros-kinetic-zeroconf-msgs'
)

depends=('avahi'
'ros-kinetic-rosconsole'
'ros-kinetic-roscpp'
'ros-kinetic-zeroconf-msgs'
)

conflicts=()
replaces=()

_dir=zeroconf_avahi
source=()
md5sums=()

prepare() {
    cp -R $startdir/zeroconf_avahi $srcdir/zeroconf_avahi
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}


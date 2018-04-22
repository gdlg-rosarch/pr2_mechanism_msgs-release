# Script generated with Bloom
pkgdesc="ROS - This package defines services that are used to communicate with the realtime control loop. It also defines messages that represent the state of the realtime controllers, the joints and the actuators."
url='http://ros.org/wiki/pr2_mechanism_msgs'

pkgname='ros-kinetic-pr2-mechanism-msgs'
pkgver='1.8.2_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-actionlib-msgs'
'ros-kinetic-catkin'
'ros-kinetic-message-generation'
'ros-kinetic-std-msgs'
)

depends=('ros-kinetic-actionlib-msgs'
'ros-kinetic-message-runtime'
'ros-kinetic-std-msgs'
)

conflicts=()
replaces=()

_dir=pr2_mechanism_msgs
source=()
md5sums=()

prepare() {
    cp -R $startdir/pr2_mechanism_msgs $srcdir/pr2_mechanism_msgs
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


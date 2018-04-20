# Script generated with Bloom
pkgdesc="ROS - ROS package to use YOLO in ROS."
url='https://bitbucket.org/leggedrobotics/darknet_ros'

pkgname='ros-kinetic-darknet-ros'
pkgver='1.1.2_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('boost'
'ros-kinetic-actionlib'
'ros-kinetic-catkin'
'ros-kinetic-cv-bridge'
'ros-kinetic-darknet-ros-msgs'
'ros-kinetic-image-transport'
'ros-kinetic-message-generation'
'ros-kinetic-roscpp'
'ros-kinetic-rospy'
'ros-kinetic-rostest'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
)

depends=('boost'
'ros-kinetic-actionlib'
'ros-kinetic-cv-bridge'
'ros-kinetic-darknet-ros-msgs'
'ros-kinetic-image-transport'
'ros-kinetic-message-generation'
'ros-kinetic-roscpp'
'ros-kinetic-rospy'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
)

conflicts=()
replaces=()

_dir=darknet_ros
source=()
md5sums=()

prepare() {
    cp -R $startdir/darknet_ros $srcdir/darknet_ros
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


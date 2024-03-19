# Script generated with import_catkin_packages.py.
# For more information: https://github.com/bchretien/arch-ros-stacks.
pkgdesc="ROS - rqt_bag provides a GUI plugin for displaying and replaying ROS bag files."
url='https://wiki.ros.org/rqt_bag'

pkgname='ros-noetic-rqt-bag-plugins'
pkgver='0.5.1'
_pkgver_patch=0
arch=('any')
pkgrel=2
license=('BSD')

ros_makedepends=(
	ros-noetic-catkin
)

makedepends=(
	'cmake'
	'ros-build-tools'
	${ros_makedepends[@]}
)

ros_depends=(
	ros-noetic-rqt-plot
	ros-noetic-rqt-gui-py
	ros-noetic-geometry-msgs
	ros-noetic-rosbag
	ros-noetic-rospy
	ros-noetic-std-msgs
	ros-noetic-rqt-gui
	ros-noetic-sensor-msgs
	ros-noetic-rqt-bag
	ros-noetic-roslib
)

depends=(
	${ros_depends[@]}
	python-pillow
	python-cairo
)

_commit="2f6fbd558baa8e8038f4d11bb20e27c75537d39c"
_dir="rqt_bag-${_commit}/rqt_bag_plugins"
source=("${pkgname}-${pkgver}.tar.gz"::"https://github.com/ros-visualization/rqt_bag/archive/${_commit}.tar.gz")
sha256sums=('2ca91b332de127ca208d113146e9fbf5e04dfaf886b90eefc147a6aec7e1a997')

build() {
	# Use ROS environment variables.
	source /usr/share/ros-build-tools/clear-ros-env.sh
	[ -f /opt/ros/noetic/setup.bash ] && source /opt/ros/noetic/setup.bash

	# Create the build directory.
	[ -d ${srcdir}/build ] || mkdir ${srcdir}/build
	cd ${srcdir}/build

	# Build the project.
	cmake ${srcdir}/${_dir} \
		-DCATKIN_BUILD_BINARY_PACKAGE=ON \
		-DCMAKE_INSTALL_PREFIX=/opt/ros/noetic \
		-DPYTHON_EXECUTABLE=/usr/bin/python \
		-DSETUPTOOLS_DEB_LAYOUT=OFF
	make
}

package() {
	cd "${srcdir}/build"
	make DESTDIR="${pkgdir}/" install
}

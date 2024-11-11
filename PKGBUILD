# Script generated with import_catkin_packages.py.
# For more information: https://github.com/bchretien/arch-ros-stacks.
pkgdesc="ROS - tf2 is the second generation of the transform library, which lets the user keep track of multiple coordinate frames over time."
url='https://wiki.ros.org/tf2'

pkgname='ros-noetic-tf2'
pkgver='08b4cc720bf95428a30a54d9e9a8257849a93c61'
arch=('i686' 'x86_64' 'aarch64' 'armv7h' 'armv6h')
pkgrel=2
license=('BSD')

ros_makedepends=(
	ros-noetic-rostime
	ros-noetic-tf2-msgs
	ros-noetic-catkin
	ros-noetic-geometry-msgs
)

makedepends=(
	'cmake'
	'ros-build-tools'
	${ros_makedepends[@]}
	console-bridge
)

ros_depends=(
	ros-noetic-rostime
	ros-noetic-tf2-msgs
	ros-noetic-geometry-msgs
)

depends=(
	${ros_depends[@]}
	console-bridge
)

_dir="geometry2-${pkgver}/tf2"
source=("${pkgname}-${pkgver}.tar.gz"::"https://github.com/ros/geometry2/archive/${pkgver}.tar.gz")
sha256sums=('680bd01681279f14e2e3e123845e0007ba270b3fcdd727d10e8384dab05549e0')

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

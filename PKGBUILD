# Contributor: Tibor Bamhor <tiborb95 at gmail.com>

pkgname=gimp-plugin-aumask
pkgver=0.9.2
pkgrel=2
pkgdesc="Advanced unsharp mask - sharpening tool. Normal and selective blur mask. Sharpness equalizer and more." 
url="http://code.google.com/p/aumask/"
license="GPL-3"
arch=('i686' 'x86_64')
depends=(gimp)
makedepends=()
source=(http://aumask.googlecode.com/files/aumask-$pkgver.tgz)


build() {

	#defining variables
	work_dir=$srcdir/aumask/
	
	#building
	cd $work_dir
	
	#to fix problem: undefined reference to symbol 'pow@@GLIBC_2.0'
	export LDFLAGS="$LDFLAGS -lm"
	
	gimptool-2.0  --build aumask.c || exit 1
}

package() {
	#copying file into pkgdir to be packed
	mkdir -p ${pkgdir}/usr/lib/gimp/2.0/plug-ins/
   ls -al
	install -m 755 ${srcdir}/aumask/aumask ${pkgdir}/usr/lib/gimp/2.0/plug-ins/ 
	
}

sha1sums=('667916816ea10d5cf1c4204af6737cfcd42646f4') 


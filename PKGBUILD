# vim:set ts=2 sw=2 et:
# Maintainer: Ruben Van Boxem <vanboxem.ruben@gmail.com>
# Maintainer: Sergej Pupykin <pupykin.s+arch@gmail.com>
# Maintainer: BlackIkeEagle < ike DOT devolder AT gmail DOT com >
# Contributor: graysky <graysky AT archlinux DOT us>
# Contributor: DonVla <donvla@users.sourceforge.net>
# Contributor: Ulf Winkelvos <ulf [at] winkelvos [dot] de>
# Contributor: Ralf Barth <archlinux dot org at haggy dot org>
# Contributor: B & monty - Thanks for your hints :)
# Contributor: marzoul
# Contributor: Sergej Pupykin <pupykin.s+arch@gmail.com>
# Contributor: Brad Fanella <bradfanella@archlinux.us>
# Contributor: [vEX] <niechift.dot.vex.at.gmail.dot.com>
# Contributor: Zeqadious <zeqadious.at.gmail.dot.com>
# Contributor: Bartłomiej Piotrowski <bpiotrowski@archlinux.org>
# Contributor: Maxime Gauduin <alucryd@gmail.com>
#
# Original credits go to Edgar Hucek <gimli at dark-green dot com>
# for his xbmc-vdpau-vdr PKGBUILD at https://archvdr.svn.sourceforge.net/svnroot/archvdr/trunk/archvdr/xbmc-vdpau-vdr/PKGBUILD

pkgbase=kodi
pkgname=(
  'kodi-common' 'kodi-gbm' #'kodi-x11' 'kodi-wayland' 'kodi-gbm'
  'kodi-eventclients' 'kodi-tools-texturepacker' 'kodi-dev'
)
pkgver=21.2
pkgrel=4
arch=('x86_64' 'aarch64' 'armv7h')
url="https://kodi.tv"
license=('GPL2')
makedepends=(
  'afpfs-ng' 'bluez-libs' 'cmake' 'curl' 'dav1d' 'git' 'glew'
  'gperf' 'hicolor-icon-theme' 'java-environment<21' 'fmt' 'libaacs' 'libass'
  'libbluray' 'libcdio' 'libcec' 'libgl' 'mariadb-libs' 'libmicrohttpd'
  'libmodplug' 'libmpeg2' 'libnfs' 'libplist' 'libpulse' 'libva'
  'libxrandr' 'libxslt' 'lirc' 'lzo' 'mesa' 'nasm'
  'python-pycryptodomex' 'python-pillow' 'python-pybluez'
  'python-simplejson' 'shairplay' 'smbclient' 'sndio' 'spdlog' 'taglib'
  'tinyxml' 'swig' 'upower' 'giflib' 'rapidjson' 'meson' 'gtest'
  'pcre' 'libdisplay-info' 'tinyxml2'
  # 'doxygen' 'pipewire' 'graphviz' 'ghostscript'
  # wayland
  #'wayland-protocols' 'waylandpp' 'libxkbcommon'
  # gbm
  'libinput'
)

_codename=Omega
_commit=979dbf5fe5d0b42daf633434afc3986651c8646a

_sse_workaround=1

_libdvdcss_version="1.4.3-Next-Nexus-Alpha2-2"
_libdvdnav_version="6.1.1-Next-Nexus-Alpha2-2"
_libdvdread_version="6.1.3-Next-Nexus-Alpha2-2"
_ffmpeg_version="6.0" # matches LibreELEC version
#_ffmpeg_version="4.4.1-Nexus-Alpha1" # this is the ArchLinux package version, but it's out of date
#_ffmpeg_version="5.1.2"
#_ffmpeg_version="v4l2-request-hwaccel-4.4" #"v4l2-request-hwaccel-4.3.2" #"v4l2-request-hwaccel-4.2.2-rkvdec" #"v4l2-request-hwaccel-4.3.1-stable" # "v4l2-request-hwaccel-4.3-rkvdec" #"4.3.2-$_codename-19.1"
_crossguid_version="ca1bf4b810e2d188d04cb6286f957008ee1b7681"
_fstrcmp_version="0.7.D001"
_flatbuffers_version="23.3.3"
_libudfread_version="1.1.2"

source=(
  #"$pkgbase-$pkgver-$_codename.tar.gz::https://github.com/xbmc/xbmc/archive/$_commit.tar.gz"
  "$pkgbase-$pkgver-$_codename.tar.gz::https://github.com/xbmc/xbmc/archive/refs/tags/$pkgver-$_codename.tar.gz"
  "$pkgbase-libdvdcss-$_libdvdcss_version.tar.gz::https://github.com/xbmc/libdvdcss/archive/$_libdvdcss_version.tar.gz"
  "$pkgbase-libdvdnav-$_libdvdnav_version.tar.gz::https://github.com/xbmc/libdvdnav/archive/$_libdvdnav_version.tar.gz"
  "$pkgbase-libdvdread-$_libdvdread_version.tar.gz::https://github.com/xbmc/libdvdread/archive/$_libdvdread_version.tar.gz"
  #"$pkgbase-ffmpeg-$_ffmpeg_version.tar.gz::https://github.com/xbmc/FFmpeg/archive/$_ffmpeg_version.tar.gz"
  #"$pkgbase-ffmpeg-$_ffmpeg_version.tar.gz::https://ffmpeg.org/releases/ffmpeg-$_ffmpeg_version.tar.gz"
  #"$pkgbase-ffmpeg-$_ffmpeg_version.tar.gz::https://github.com/Kwiboo/FFmpeg/archive/$_ffmpeg_version.tar.gz"
  #"$pkgbase-ffmpeg-$_ffmpeg_version.tar.gz::https://github.com/jernejsk/FFmpeg/archive/$_ffmpeg_version.tar.gz"
  "$pkgbase-crossguid-$_crossguid_version.tar.gz::http://mirrors.kodi.tv/build-deps/sources/crossguid-$_crossguid_version.tar.gz"
  "$pkgbase-fstrcmp-$_fstrcmp_version.tar.gz::http://mirrors.kodi.tv/build-deps/sources/fstrcmp-$_fstrcmp_version.tar.gz"
  "$pkgbase-flatbuffers-$_flatbuffers_version.tar.gz::http://mirrors.kodi.tv/build-deps/sources/flatbuffers-$_flatbuffers_version.tar.gz"
  "$pkgbase-libudfread-$_libudfread_version.tar.gz::http://mirrors.kodi.tv/build-deps/sources/libudfread-$_libudfread_version.tar.gz"
  'https://github.com/xbmc/xbmc/commit/d2022ce1.patch'
  'https://github.com/xbmc/xbmc/commit/6f5dff4b.patch'
  'https://patch-diff.githubusercontent.com/raw/xbmc/xbmc/pull/24577.patch'
  "0001-WIP-DVDVideoCodecDRMPRIME-add-support-for-filters.patch"
  "0002-WIP-DRMPRIME-deinterlace-filter.patch"
  "0003-DVDVideoCodecDRMPRIME-Avoid-exception-with-AV_PIX_FM.patch"
  "0004-DVDVideoCodecDRMPRIME-Leave-deinterlace-filter-activ.patch"
  "0005-SetVideoInterlaced-Set-and-unset-deinterlace-method-.patch"
  "0006-DVDVideoCodecDRMPRIME-Close-deinterlace-filter-on-er.patch"
  "0007-DVDVideoCodecDRMPRIME-Fix-missing-flush-after-eof.patch"
  #"0010-kodi-ffmpeg-7.1.patch"
  "000-temp-revert-fences.patch"
  #"000-actual-flickering-fix.patch"
  "fix-libnfs-6-compatibility.patch"
  "fix-build-with-pipewire-1.4.patch"
)
noextract=(
  "$pkgbase-libdvdcss-$_libdvdcss_version.tar.gz"
  "$pkgbase-libdvdnav-$_libdvdnav_version.tar.gz"
  "$pkgbase-libdvdread-$_libdvdread_version.tar.gz"
  #"$pkgbase-ffmpeg-$_ffmpeg_version.tar.gz"
  "$pkgbase-crossguid-$_crossguid_version.tar.gz"
  "$pkgbase-fstrcmp-$_fstrcmp_version.tar.gz"
  "$pkgbase-flatbuffers-$_flatbuffers_version.tar.gz"
  "$pkgbase-libudfread-$_libudfread_version.tar.gz"
)

md5sums=('ba191fcbd49e19af50e5c56786bc9bf4'
         '42dc3770ae928103e8033a18b007e79d'
         '2349cde54d950af21fa4936371ad3349'
         '0d24c950abfef9dc02e231dda56912ac'
         'd4a8d62f3f8d6d946be75cf5bfa92687'
         '9c440bbdfcad9fd22e38f2388715b0cc'
         'a379be2558d12c02acdb062ad7c8969c'
         'e53c37085c3bf01d5c6623021563dcae'
         '45fd5496fab6d987bbc1951f9047da49'
         '9026df86ebf7611154f7e86cf60218dd'
         '1e333cda758c7d47f999d14c16a7cc9e'
         '3c49381d06ab377094fa3d124fc46cb5'
         'cfc38a9994fb9e55ede7fca1791d286d'
         '8d91e24de0783deb186df5f33390ae09'
         '82c2f86aa9da925eff8a12e046d1678f'
         '395e4211760a01fc9d788ef79b80dbe1'
         '50c8538297808b11a8c38807bbc4576e'
         '969ee726ef461a0258bfc372c00a8449'
         '495f85b357f1f675f995c8db828ff2c7'
         '3d120378e598659e6c918b3882d261ff'
         'd09af8cb649eed7a66c2a26e2c03749e')

prepare() {
  [[ -d kodi-build ]] && rm -rf kodi-build
  mkdir "$srcdir/kodi-build"

  ln -s "$srcdir/xbmc-$_commit" "$srcdir/xbmc-$pkgver-$_codename" 
  cd "xbmc-$pkgver-$_codename"

  # Fix build with taglib 2
  #patch -p1 -i ../d2022ce1.patch
  #patch -p1 -i ../6f5dff4b.patch
  #patch -p1 -i ../24577.patch

  patch -p1 -i $srcdir/0001-WIP-DVDVideoCodecDRMPRIME-add-support-for-filters.patch
  patch -p1 -i $srcdir/0002-WIP-DRMPRIME-deinterlace-filter.patch
  patch -p1 -i $srcdir/0003-DVDVideoCodecDRMPRIME-Avoid-exception-with-AV_PIX_FM.patch
  patch -p1 -i $srcdir/0004-DVDVideoCodecDRMPRIME-Leave-deinterlace-filter-activ.patch
  patch -p1 -i $srcdir/0005-SetVideoInterlaced-Set-and-unset-deinterlace-method-.patch
  patch -p1 -i $srcdir/0006-DVDVideoCodecDRMPRIME-Close-deinterlace-filter-on-er.patch
  patch -p1 -i $srcdir/0007-DVDVideoCodecDRMPRIME-Fix-missing-flush-after-eof.patch
  #patch -p1 -i $srcdir/0010-kodi-ffmpeg-7.1.patch
  patch -p1 -i $srcdir/000-temp-revert-fences.patch
#  patch -p1 -i $srcdir/000-actual-flickering-fix.patch
  patch -p1 -i $srcdir/fix-libnfs-6-compatibility.patch
  patch -p1 -i $srcdir/fix-build-with-pipewire-1.4.patch
}

build() {
  cd "$srcdir/kodi-build"

  # -march= defined in /etc/makepkg.conf will override the value for -mcpu we
  # uses here so unset them and redefine below
  unset CFLAGS CXXFLAGS

  CFLAGS="-O2 -pipe -fstack-protector-strong -fno-plt"
  CXXFLAGS="${CFLAGS}"

  _cmake_common_args=(
    -DCMAKE_INSTALL_PREFIX=/usr
    -DCMAKE_INSTALL_LIBDIR=/usr/lib
    -DUSE_LTO=ON
    -DENABLE_GOLD=OFF
    -DENABLE_AIRTUNES=ON
    -DENABLE_AVAHI=ON
    -DENABLE_CEC=ON
    -DENABLE_EVENTCLIENTS=ON
    -DENABLE_NEON=ON
    -DENABLE_UDEV=ON
    -DENABLE_UPNP=ON
    -DENABLE_LIRCCLIENT=ON
    -DENABLE_OPTICAL=OFF
    -DENABLE_INTERNAL_FFMPEG=OFF
    -DENABLE_INTERNAL_RapidJSON=OFF
    -DENABLE_INTERNAL_CROSSGUID=ON
    -DENABLE_INTERNAL_FSTRCMP=ON
    -DENABLE_INTERNAL_FLATBUFFERS=ON
    -DENABLE_INTERNAL_UDFREAD=ON
    -DENABLE_MYSQLCLIENT=ON
    -Dlibdvdcss_URL="$srcdir/$pkgbase-libdvdcss-$_libdvdcss_version.tar.gz"
    -Dlibdvdnav_URL="$srcdir/$pkgbase-libdvdnav-$_libdvdnav_version.tar.gz"
    -Dlibdvdread_URL="$srcdir/$pkgbase-libdvdread-$_libdvdread_version.tar.gz"
    #-DFFMPEG_URL="$srcdir/$pkgbase-ffmpeg-$_ffmpeg_version.tar.gz"
    -DCROSSGUID_URL="$srcdir/$pkgbase-crossguid-$_crossguid_version.tar.gz"
    -DFSTRCMP_URL="$srcdir/$pkgbase-fstrcmp-$_fstrcmp_version.tar.gz"
    -DFLATBUFFERS_URL="$srcdir/$pkgbase-flatbuffers-$_flatbuffers_version.tar.gz"
    -DUDFREAD_URL="$srcdir/$pkgbase-libudfread-$_libudfread_version.tar.gz"
    -DAPP_RENDER_SYSTEM=gles
    -DENABLE_VAAPI=OFF
    -DENABLE_VDPAU=OFF
  )

  #echo "building kodi-wayland"
  #cmake \
  #  ${_cmake_common_args[@]} \
  #  -DCORE_PLATFORM_NAME=wayland \
  #  ../"xbmc-$pkgver-$_codename"
  #make

  echo "building kodi-gbm"
  cmake \
    ${_cmake_common_args[@]} \
    -DCORE_PLATFORM_NAME=gbm \
    ../"xbmc-$pkgver-$_codename"
  #make VERBOSE=1 ffmpeg > $srcdir/ffmpeg.log 2>&1
  make

  # build x11 version last that will make it fallback in the launcher script
  #echo "building kodi-x11"
  #cmake \
  #  ${_cmake_common_args[@]} \
  #  -DCORE_PLATFORM_NAME=x11 \
  #  ../"xbmc-$pkgver-$_codename"
  #make
}

# kodi
# components: kodi
package_kodi-common() {
  pkgdesc="A software media player and entertainment hub for digital media"
  depends=(
    'bluez-libs' 'curl' 'dav1d' 'desktop-file-utils' 'hicolor-icon-theme'
    'lcms2' 'libass' 'libbluray' 'libcdio' 'libcec' 'libmicrohttpd' 'libnfs'
    'libplist' 'libpulse' 'libva' 'libxslt' 'lirc' 'mariadb-libs' 'mesa'
    'python-pillow' 'python-pycryptodomex' 'python-simplejson'
    'shairplay' 'smbclient' 'sqlite' 'taglib' 'tinyxml'
    'ffmpeg' 'libdisplay-info' 'flatbuffers'
  )
  optdepends=(
    'afpfs-ng: Apple shares support'
    'bluez: Blutooth support'
    'python-pybluez: Bluetooth support'
    'pulseaudio: PulseAudio support'
    'upower: Display battery level'
  )

  _components=(
    'kodi'
    'kodi-bin'
  )

  cd kodi-build
  for _cmp in ${_components[@]}; do
  DESTDIR="$pkgdir" /usr/bin/cmake \
    -DCMAKE_INSTALL_COMPONENT="$_cmp" \
     -P cmake_install.cmake
  done

  # remove windowing specific binaries
  rm -f "$pkgdir/usr/lib/kodi/"{kodi-x11,kodi-xrandr,kodi-wayland,kodi-gbm}
}

# kodi-x11
# components: kodi-bin
#package_kodi-x11() {
#  pkgdesc="x11 kodi binary"
#  provides=('kodi')
#  replaces=('kodi')
#  depends=(
#    'kodi-common' 'libxrandr'
#  )
#
#  cd kodi-build
#  install -Dm755 kodi-x11 "$pkgdir/usr/lib/kodi/kodi-x11"
#  install -Dm755 kodi-xrandr "$pkgdir/usr/lib/kodi/kodi-xrandr"
#}

# kodi-wayland
# components: kodi-bin
#package_kodi-wayland() {
#  pkgdesc="wayland kodi binary"
#  provides=('kodi')
#  replaces=('kodi')
#  depends=(
#    'kodi-common' 'libxkbcommon' 'waylandpp'
#  )
#
#  cd kodi-build
#  install -Dm755 kodi-wayland "$pkgdir/usr/lib/kodi/kodi-wayland"
#}

# kodi-gbm
# components: kodi-bin
package_kodi-gbm() {
  pkgdesc="gbm kodi binary"
  provides=('kodi')
  replaces=('kodi')
  depends=(
    'kodi-common' 'libxkbcommon' 'libinput'
  )

  cd kodi-build
  install -Dm755 kodi-gbm "$pkgdir/usr/lib/kodi/kodi-gbm"
}

# kodi-eventclients
# components: kodi-eventclients-common kodi-eventclients-ps3 kodi-eventclients-kodi-send
package_kodi-eventclients() {
  pkgdesc="Kodi Event Clients"
  optdepends=(
    'kodi: local machine eventclient use'
    'python: most eventclients are implemented in python'
  )

  _components=(
    'kodi-eventclients-common'
    'kodi-eventclients-ps3'
    'kodi-eventclients-kodi-send'
  )

  cd kodi-build
  for _cmp in ${_components[@]}; do
    DESTDIR="$pkgdir" /usr/bin/cmake \
      -DCMAKE_INSTALL_COMPONENT="$_cmp" \
      -P cmake_install.cmake
  done
}

# kodi-tools-texturepacker
# components: kodi-tools-texturepacker
package_kodi-tools-texturepacker() {
  pkgdesc="Kodi Texturepacker tool"
  depends=('libpng' 'giflib' 'libjpeg-turbo' 'lzo')

  _components=(
    'kodi-tools-texturepacker'
  )

  cd kodi-build
  for _cmp in ${_components[@]}; do
    DESTDIR="$pkgdir" /usr/bin/cmake \
      -DCMAKE_INSTALL_COMPONENT="$_cmp" \
      -P cmake_install.cmake
  done
}

# kodi-dev
# components: kodi-addon-dev kodi-eventclients-dev
package_kodi-dev() {
  pkgdesc="Kodi dev files"
  depends=('kodi-common')

  _components=(
    'kodi-addon-dev'
    'kodi-eventclients-dev'
  )

  cd kodi-build
  for _cmp in ${_components[@]}; do
    DESTDIR="$pkgdir" /usr/bin/cmake \
      -DCMAKE_INSTALL_COMPONENT="$_cmp" \
      -P cmake_install.cmake
  done
}

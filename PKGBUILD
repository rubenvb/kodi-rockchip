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
pkgver=20.0
pkgrel=1
arch=('x86_64' 'aarch64' 'armv7h')
url="https://kodi.tv"
license=('GPL2')
makedepends=(
  'afpfs-ng' 'bluez-libs' 'cmake' 'curl' 'dav1d' 'doxygen' 'git' 'glew'
  'gperf' 'hicolor-icon-theme' 'java-runtime' 'fmt' 'libaacs' 'libass'
  'libbluray' 'libcdio' 'libcec' 'libgl' 'mariadb-libs' 'libmicrohttpd'
  'libmodplug' 'libmpeg2' 'libnfs' 'libplist' 'libpulse' 'libva'
  'libxrandr' 'libxslt' 'lirc' 'lzo' 'mesa' 'nasm'
  'pipewire' 'python-pycryptodomex' 'python-pillow' 'python-pybluez'
  'python-simplejson' 'shairplay' 'smbclient' 'sndio' 'spdlog' 'taglib'
  'tinyxml' 'swig' 'upower' 'giflib' 'rapidjson' 'ghostscript' 'meson' 'gtest'
  'graphviz'
  # wayland
  #'wayland-protocols' 'waylandpp' 'libxkbcommon'
  # gbm
  'libinput'
)

_codename=Nexus

_sse_workaround=1

_libdvdcss_version="1.4.3-Next-Nexus-Alpha2-2"
_libdvdnav_version="6.1.1-Next-Nexus-Alpha2-2"
_libdvdread_version="6.1.3-Next-Nexus-Alpha2-2"
#_ffmpeg_version="4.4.1" # matches LibreELEC version
_ffmpeg_version="4.4.1-Nexus-Alpha1" # this is the ArchLinux package version, but it's out of date
#_ffmpeg_version="v4l2-request-hwaccel-4.4" #"v4l2-request-hwaccel-4.3.2" #"v4l2-request-hwaccel-4.2.2-rkvdec" #"v4l2-request-hwaccel-4.3.1-stable" # "v4l2-request-hwaccel-4.3-rkvdec" #"4.3.2-$_codename-19.1"
_crossguid_version="ca1bf4b810e2d188d04cb6286f957008ee1b7681"
_fstrcmp_version="0.7.D001"
_flatbuffers_version="2.0.0"
_libudfread_version="1.1.2"

source=(
  "$pkgbase-$pkgver-$_codename.tar.gz::https://github.com/xbmc/xbmc/archive/refs/tags/$pkgver-$_codename.tar.gz"
  "$pkgbase-libdvdcss-$_libdvdcss_version.tar.gz::https://github.com/xbmc/libdvdcss/archive/$_libdvdcss_version.tar.gz"
  "$pkgbase-libdvdnav-$_libdvdnav_version.tar.gz::https://github.com/xbmc/libdvdnav/archive/$_libdvdnav_version.tar.gz"
  "$pkgbase-libdvdread-$_libdvdread_version.tar.gz::https://github.com/xbmc/libdvdread/archive/$_libdvdread_version.tar.gz"
  "$pkgbase-ffmpeg-$_ffmpeg_version.tar.gz::https://github.com/xbmc/FFmpeg/archive/$_ffmpeg_version.tar.gz"
  #"$pkgbase-ffmpeg-$_ffmpeg_version.tar.gz::https://ffmpeg.org/releases/ffmpeg-$_ffmpeg_version.tar.gz"
  #"$pkgbase-ffmpeg-$_ffmpeg_version.tar.gz::https://github.com/Kwiboo/FFmpeg/archive/$_ffmpeg_version.tar.gz"
  #"$pkgbase-ffmpeg-$_ffmpeg_version.tar.gz::https://github.com/jernejsk/FFmpeg/archive/$_ffmpeg_version.tar.gz"
  "$pkgbase-crossguid-$_crossguid_version.tar.gz::http://mirrors.kodi.tv/build-deps/sources/crossguid-$_crossguid_version.tar.gz"
  "$pkgbase-fstrcmp-$_fstrcmp_version.tar.gz::http://mirrors.kodi.tv/build-deps/sources/fstrcmp-$_fstrcmp_version.tar.gz"
  "$pkgbase-flatbuffers-$_flatbuffers_version.tar.gz::http://mirrors.kodi.tv/build-deps/sources/flatbuffers-$_flatbuffers_version.tar.gz"
  "$pkgbase-libudfread-$_libudfread_version.tar.gz::http://mirrors.kodi.tv/build-deps/sources/libudfread-$_libudfread_version.tar.gz"
  "001-v4l2-request.patch"
  #"0001-enable-v4l2-request.patch"
  #"0002-java9.patch"
  #"0003-java9.patch"
)
noextract=(
  "$pkgbase-libdvdcss-$_libdvdcss_version.tar.gz"
  "$pkgbase-libdvdnav-$_libdvdnav_version.tar.gz"
  "$pkgbase-libdvdread-$_libdvdread_version.tar.gz"
  "$pkgbase-ffmpeg-$_ffmpeg_version.tar.gz"
  "$pkgbase-crossguid-$_crossguid_version.tar.gz"
  "$pkgbase-fstrcmp-$_fstrcmp_version.tar.gz"
  "$pkgbase-flatbuffers-$_flatbuffers_version.tar.gz"
  "$pkgbase-libudfread-$_libudfread_version.tar.gz"
)

md5sums=('2de29eef1e6eedff27487931b91d18bf'
         '42dc3770ae928103e8033a18b007e79d'
         '2349cde54d950af21fa4936371ad3349'
         '0d24c950abfef9dc02e231dda56912ac'
         '9f84fff2a7ddbaa83e6e85e3a12a5f91'
         'd4a8d62f3f8d6d946be75cf5bfa92687'
         '9c440bbdfcad9fd22e38f2388715b0cc'
         'a27992324c3cbf86dd888268a23d17bd'
         'e53c37085c3bf01d5c6623021563dcae'
         'a46d85745243617fd7d22b93be1a0c44')

prepare() {
  [[ -d kodi-build ]] && rm -rf kodi-build
  mkdir "$srcdir/kodi-build"

  cd "xbmc-$pkgver-$_codename"

  #patch -p1 < $srcdir/0001-enable-v4l2-request.patch
  patch -p1 < $srcdir/001-v4l2-request.patch
}

build() {
  cd "$srcdir/kodi-build"

  # -march= defined in /etc/makepkg.conf will override the value for -mcpu we
  # uses here so unset them and redefine below
  unset CFLAGS CXXFLAGS

  CFLAGS="-O2 -pipe -fstack-protector-strong -fno-plt"
  CXXFLAGS="${CFLAGS}"

  if [[ $CARCH = "armv7h" ]]; then
    # we use -mcpu=cortex-a53 rather than cortex-a72 to maximize RPi 3B and RPi 4B/400 compatibility
    # in a single package which is consistent with how LibreELEC is currently built, see:
    # https://github.com/LibreELEC/LibreELEC.tv/commit/8e6605f6da56f25a00272b1cbacb93d40200153f#commitcomment-46341034
    export CFLAGS+=" -mcpu=cortex-a53 -mfpu=neon-fp-armv8 -mfloat-abi=hard"
    export CXXFLAGS="${CFLAGS}"
  elif [[ $CARCH = "aarch64" ]]; then
    # note that linux-raspberrypi4 for aarch64 will currently NOT boot on RPi3 so we can use
    # a value of cortex-a72 here although the ffmpeg patch is using cortex-a53
    export CFLAGS+=" -mcpu=cortex-a72+crc"
    export CXXFLAGS="${CFLAGS}"
  fi

  _cmake_common_args=(
    -DCMAKE_INSTALL_PREFIX=/usr
    -DCMAKE_INSTALL_LIBDIR=/usr/lib
    -DUSE_LTO=OFF
    -DENABLE_GOLD=ON
    -DENABLE_EVENTCLIENTS=ON
    -DENABLE_INTERNAL_FFMPEG=ON
    -DENABLE_INTERNAL_CROSSGUID=ON
    -DENABLE_INTERNAL_FSTRCMP=ON
    -DENABLE_INTERNAL_FLATBUFFERS=ON
    -DENABLE_INTERNAL_UDFREAD=ON
    -DENABLE_MYSQLCLIENT=ON
    -Dlibdvdcss_URL="$srcdir/$pkgbase-libdvdcss-$_libdvdcss_version.tar.gz"
    -Dlibdvdnav_URL="$srcdir/$pkgbase-libdvdnav-$_libdvdnav_version.tar.gz"
    -Dlibdvdread_URL="$srcdir/$pkgbase-libdvdread-$_libdvdread_version.tar.gz"
    -DFFMPEG_URL="$srcdir/$pkgbase-ffmpeg-$_ffmpeg_version.tar.gz"
    -DFMT_URL="$srcdir/$pkgbase-fmt-$_fmt_version.tar.gz"
    -DSPDLOG_URL="$srcdir/$pkgbase-spdlog-$_spdlog_version.tar.gz"
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
  make VERBOSE=1 ffmpeg > $srcdir/ffmpeg.log 2>&1
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

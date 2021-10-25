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
pkgver=19.1
pkgrel=3
arch=('x86_64' 'aarch64' 'armv7h')
url="https://kodi.tv"
license=('GPL2')
makedepends=(
  'afpfs-ng' 'bluez-libs' 'cmake' 'curl' 'dav1d' 'doxygen' 'git' 'glew'
  'gperf' 'hicolor-icon-theme' 'java-runtime' 'libaacs' 'libass'
  'libbluray' 'libcdio' 'libcec' 'libgl' 'mariadb-libs' 'libmicrohttpd'
  'libmodplug' 'libmpeg2' 'libnfs' 'libplist' 'libpulse' 'libva'
  'libxrandr' 'libxslt' 'lirc' 'lzo' 'mesa' 'nasm'
  'python-pycryptodomex' 'python-pillow' 'python-pybluez'
  'python-simplejson' 'shairplay' 'smbclient' 'taglib' 'tinyxml' 'swig'
  'upower' 'giflib' 'rapidjson' 'ghostscript' 'meson' 'gtest' 'graphviz'
  # wayland
  'wayland-protocols' 'waylandpp' 'libxkbcommon'
  # gbm
  'libinput'
)

_codename=Matrix

_sse_workaround=1

_libdvdcss_version="1.4.2-Leia-Beta-5"
_libdvdnav_version="6.0.0-Leia-Alpha-3"
_libdvdread_version="6.0.0-Leia-Alpha-3"
_ffmpeg_version="v4l2-request-hwaccel-4.3.2" #"v4l2-request-hwaccel-4.2.2-rkvdec" #"v4l2-request-hwaccel-4.3.1-stable" # "v4l2-request-hwaccel-4.3-rkvdec" #"4.3.2-$_codename-19.1"
_fmt_version="6.1.2"
_spdlog_version="1.5.0"
_crossguid_version="8f399e8bd4"
_fstrcmp_version="0.7.D001"
_flatbuffers_version="1.12.0"
_libudfread_version="1.1.0"

source=(
  "$pkgbase-$pkgver-$_codename.tar.gz::https://github.com/xbmc/xbmc/archive/refs/tags/$pkgver-$_codename.tar.gz"
  "$pkgbase-libdvdcss-$_libdvdcss_version.tar.gz::https://github.com/xbmc/libdvdcss/archive/$_libdvdcss_version.tar.gz"
  "$pkgbase-libdvdnav-$_libdvdnav_version.tar.gz::https://github.com/xbmc/libdvdnav/archive/$_libdvdnav_version.tar.gz"
  "$pkgbase-libdvdread-$_libdvdread_version.tar.gz::https://github.com/xbmc/libdvdread/archive/$_libdvdread_version.tar.gz"
  #"$pkgbase-ffmpeg-$_ffmpeg_version.tar.gz::https://github.com/Kwiboo/FFmpeg/archive/$_ffmpeg_version.tar.gz"
  "$pkgbase-ffmpeg-$_ffmpeg_version.tar.gz::https://github.com/jernejsk/FFmpeg/archive/$_ffmpeg_version.tar.gz"
  "$pkgbase-fmt-$_fmt_version.tar.gz::http://mirrors.kodi.tv/build-deps/sources/fmt-$_fmt_version.tar.gz"
  "$pkgbase-spdlog-$_spdlog_version.tar.gz::http://mirrors.kodi.tv/build-deps/sources/spdlog-$_spdlog_version.tar.gz"
  "$pkgbase-crossguid-$_crossguid_version.tar.gz::http://mirrors.kodi.tv/build-deps/sources/crossguid-$_crossguid_version.tar.gz"
  "$pkgbase-fstrcmp-$_fstrcmp_version.tar.gz::http://mirrors.kodi.tv/build-deps/sources/fstrcmp-$_fstrcmp_version.tar.gz"
  "$pkgbase-flatbuffers-$_flatbuffers_version.tar.gz::http://mirrors.kodi.tv/build-deps/sources/flatbuffers-$_flatbuffers_version.tar.gz"
  "$pkgbase-libudfread-$_libudfread_version.tar.gz::http://mirrors.kodi.tv/build-deps/sources/libudfread-$_libudfread_version.tar.gz"
  "0001-enable-v4l2-request.patch"
  "0002-java9.patch"
  "0003-java9.patch"
)
noextract=(
  "$pkgbase-libdvdcss-$_libdvdcss_version.tar.gz"
  "$pkgbase-libdvdnav-$_libdvdnav_version.tar.gz"
  "$pkgbase-libdvdread-$_libdvdread_version.tar.gz"
  "$pkgbase-ffmpeg-$_ffmpeg_version.tar.gz"
  "$pkgbase-fmt-$_fmt_version.tar.gz"
  "$pkgbase-spdlog-$_spdlog_version.tar.gz"
  "$pkgbase-crossguid-$_crossguid_version.tar.gz"
  "$pkgbase-fstrcmp-$_fstrcmp_version.tar.gz"
  "$pkgbase-flatbuffers-$_flatbuffers_version.tar.gz"
  "$pkgbase-libudfread-$_libudfread_version.tar.gz"
)
sha512sums=('e9725a61828fa59502fdbb42d689c4948af792522049dadae136b5e90f53ee6fff570e6adb818dcce2ce54e957b0a31796b59aefd87fc55356531e2379ac6289'
            '5185dbdbeb1bd13ea9d8723f1f4ab599d6f3102f5ba1096cd085aa1cda252c045f327c719227bba8e1b742352ade5e335106c8d0c1637a5a6b93ce661620dd7e'
            '11c93eaacd156f8fd7dec7c43d366438b201f31ad55b2870463a9e286912b6ada08882319a021fb7992190f87b909a49f2b83e0321cc17aedc29f7fe5898fa72'
            'b3419ba0a1a2dd70f1bb6236afdfe1c6e88c9ad4264198b289e3bba9375e077cecf7f89848c7b09debaa445327f3507101f3d157e692f7a7163b2bb52643e1e7'
            '759aaa4d123b84e37a1d35d28c31420455eef960cfecd58fe5d17f73f41d883f4df2ba306325b2d3909b6d4e034c6b8760ca7b95901ca438f0e0bc53fe1b9484'
            '8770bf4bd2bb6d938e75e0cf1e665c41930dbd9d2a6825274a5a43cd1d85b9c9ca621bb040ed099429f0e16bddbc3399361c453eb1bf3fc01376e6ad9dd875b7'
            '78991c943dd95af563c4b29545b9b5d635caf1af5031262dde734ecf70c0b4ae866d954ee77b050f9f0cc089a3bc57ee9583895e51cb00dd1cc6c10ff905ca34'
            '2682d63609d3dcdfcd8136be632e45df26ad88ce93b9c49745cf728bbd2e6254a7b05c8b059ab581d532372e504206a525a52564b64d076dfdae9c965a09fd16'
            'aaeb0227afd5ada5955cbe6a565254ff88d2028d677d199c00e03b7cb5de1f2c69b18e6e8b032e452350a8eda7081807b01765adbeb8476eaf803d9de6e5509c'
            '8a0b88d739fa4694a69d3630140fe89fdd70d50bba4dadd1758d9aa2920cda16700bcafb8d89fe2a09ac907d3f378240c3cb4abc7106318136799836aba4b063'
            '340a03fe90d26a8a5c78e1e4f558a0b448a14332a661494f44af7de3e6c98cd219125e19f69d2a611ecb4870648a5d5b55d794e665eb8ec4192c0b499a0701ed'
            '484fe6a8c4c6f8a5265af8038b786d7e1af36680077b7ec5016e2864a5f715027c614dbae1f2342e3764feed75428859e25cdd1196be13ca857b3a96493416a6'
            '831f1f0500211d721b8deb7692f09d38de256cabb238a66ba305af03678a21ef11d0b5f06693beab0fe6d6aca65285a411590018fed3804d99a28db249f767d6'
            '78380202fb794cb9b1e950ede7e9bea733b708c40b01fad220fdc6a73eaa86af33adef50647393f3932de099d1007060621bf956ee41f111eed5bccb2a12fccf')
prepare() {
  [[ -d kodi-build ]] && rm -rf kodi-build
  mkdir "$srcdir/kodi-build"

  cd "xbmc-$pkgver-$_codename"

  patch -p1 < $srcdir/0001-enable-v4l2-request.patch
  patch -p1 < $srcdir/0003-java9.patch
#  patch -p1 < $srcdir/0002-java9.patch
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
    -DENABLE_LDGOLD=ON
    -DENABLE_EVENTCLIENTS=ON
    -DENABLE_INTERNAL_FFMPEG=ON
    -DENABLE_INTERNAL_FMT=ON
    -DENABLE_INTERNAL_SPDLOG=ON
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

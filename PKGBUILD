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
pkgver=20.1
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
_ffmpeg_version="4.4.1" # matches LibreELEC version
#_ffmpeg_version="4.4.1-Nexus-Alpha1" # this is the ArchLinux package version, but it's out of date
#_ffmpeg_version="5.1.2"
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
  #"$pkgbase-ffmpeg-$_ffmpeg_version.tar.gz::https://github.com/xbmc/FFmpeg/archive/$_ffmpeg_version.tar.gz"
  "$pkgbase-ffmpeg-$_ffmpeg_version.tar.gz::https://ffmpeg.org/releases/ffmpeg-$_ffmpeg_version.tar.gz"
  #"$pkgbase-ffmpeg-$_ffmpeg_version.tar.gz::https://github.com/Kwiboo/FFmpeg/archive/$_ffmpeg_version.tar.gz"
  #"$pkgbase-ffmpeg-$_ffmpeg_version.tar.gz::https://github.com/jernejsk/FFmpeg/archive/$_ffmpeg_version.tar.gz"
  "$pkgbase-crossguid-$_crossguid_version.tar.gz::http://mirrors.kodi.tv/build-deps/sources/crossguid-$_crossguid_version.tar.gz"
  "$pkgbase-fstrcmp-$_fstrcmp_version.tar.gz::http://mirrors.kodi.tv/build-deps/sources/fstrcmp-$_fstrcmp_version.tar.gz"
  "$pkgbase-flatbuffers-$_flatbuffers_version.tar.gz::http://mirrors.kodi.tv/build-deps/sources/flatbuffers-$_flatbuffers_version.tar.gz"
  "$pkgbase-libudfread-$_libudfread_version.tar.gz::http://mirrors.kodi.tv/build-deps/sources/libudfread-$_libudfread_version.tar.gz"
  "001-v4l2-request.patch"
  "0001-WIP-DVDVideoCodecDRMPRIME-add-support-for-filters.patch"
  "0002-WIP-DRMPRIME-deinterlace-filter.patch"
  "0003-DVDVideoCodecDRMPRIME-Avoid-exception-with-AV_PIX_FM.patch"
  "0004-DVDVideoCodecDRMPRIME-Leave-deinterlace-filter-activ.patch"
  "0005-SetVideoInterlaced-Set-and-unset-deinterlace-method-.patch"
  "0006-DVDVideoCodecDRMPRIME-Close-deinterlace-filter-on-er.patch"

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

sha512sums=('648df0649a0443d884b9414f43be4253764f1aaf9072aa8111e5a8a217c8291024ce1f27c2f7f673ac24005b32cc7dd25d86e99fc68166e3d5a637ae36b20f02'
            'd3be3bfc13c5ea56d8db745c2aab090c99760684fe4c8f62a13d266feb319e9180ceeecf8116bfd2ed90d9accba2c11dbbf93b61ad00f69a40812ebf4eabcdda'
            '51e6fc033121241354a5f0b3fc9a430577ae3ff6bb7f31445aa548ef4893037fb80eea3b2c6774c81e9ebaf9c45e9b490c98c2c65eb38f9f7daba84b236f7e1d'
            '629a41157d07b8ec0ea1fe89ae5ec48f63047472a862782b805c531ae31a0376fc4dc15175f8280c3ef91d7fa977bacebb1b51232640034a34bab2293210fc5e'
            '010db909d0769080b222b13a1b2d7fde5b0b093ce4691539cfcc3b46444c80be98112fae828d894bb3c8f097600d5e06bd1b41970ec87e7c1424ba637738b797'
            'f0a80d8e99b10473bcfdfde3d1c5fd7b766959819f0d1c0595ac84ce46db9007a5fbfde9a55aca60530c46cb7f8ef4c7e472c6191559ded92f868589c141ccaf'
            'aaeb0227afd5ada5955cbe6a565254ff88d2028d677d199c00e03b7cb5de1f2c69b18e6e8b032e452350a8eda7081807b01765adbeb8476eaf803d9de6e5509c'
            '26a06b572c0e4c9685743bd2d2162ac7dcd74b9324624cc3f3ef5b154c0cee7c52a04b77cdc184245d2d6ae38dfdcc4fd66001c318aa8ca001d2bf1d85d66a89'
            '3069feb5db40288beb5b112b285186162a704f0fdd3cf67a17fd4eeea015f2cfcfbb455b7aa7c3d79d00fd095a3fd11cffc7b121dce94d99c3b06a509a8977d2'
            '5b5caf78daa2baa4cbec8d2a49bab0029c038af316cc1f622cfe5a640a01039a27a75fbf04453829da75a2ca476e7d42fe3d74bc383fd5a37eceea9f3c5140e9'
            'f0670d4ddc9f358c2fbe7b4f2297f0681bbc33ae089c3fa86a5e590384a84617dbe34becbb60d5650fa6a42407a698fe02eb03e1a037a57b0c9ac5ceb6df90d7'
            'da7f921d7983c9a60933ee77c84fe0a5d139d443bd080e8d6eaec24f4ec1886f0a589ec69312f8f45ad967a5cbb890b0a7f53c78f13f328140fd3574575f30dc'
            '5b4c9ac1bb21aec58da977ec80234fc0fab595f57170e6a0bbff52d9f5c9a956f9afe84ac673566c424ad10163b458b042299f9458d4cbae732883156b44d302'
            '2213c9ca54f3db5a0fbed4d9ef6f9a3629c8a86d68e1d17d8815613d5ff4d482c3e5caa90f0acf739562cc85b55d18e5f4ada90ab2738c6e85e0958d1c8f2ba0'
            '32b3285dcf478fec5fce7b4dbde1fa34f4549e5ed07e7f8bb33a1034da5ee9daf89c5a2c7156985c07723c60ad7ab523b5d8865103b8d997400e540da6111c2c'
            'a01c07e525dd24b6f931857ee9e39b3193d65109b72a9d1a74d41d49e83204b3ada1b593b0697a568246d7ba41469b1f507ca64e81ba1aa7f67d0e9115ba7410')

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

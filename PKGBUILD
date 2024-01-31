# vim:set ts=2 sw=2 et:
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
pkgname=('kodi' 'kodi-gles' 'kodi-eventclients' 'kodi-tools-texturepacker' 'kodi-dev')
pkgver=20.3
pkgrel=6
arch=('x86_64')
url="https://kodi.tv"
license=('GPL2')
makedepends=(
  'afpfs-ng' 'bluez-libs' 'cmake' 'curl' 'dav1d' 'doxygen' 'git' 'glew'
  'gperf' 'hicolor-icon-theme' 'java-runtime<21' 'fmt' 'libaacs' 'libass'
  'libbluray' 'libcdio' 'libcec' 'libgl' 'mariadb-libs' 'libmicrohttpd'
  'libmodplug' 'libmpeg2' 'libnfs' 'libplist' 'libpulse' 'libva'
  'libva-vdpau-driver' 'libxrandr' 'libxslt' 'lirc' 'lzo' 'mesa' 'nasm'
  'pipewire' 'python-pycryptodomex' 'python-pillow' 'python-pybluez'
  'python-simplejson' 'shairplay' 'smbclient' 'sndio' 'spdlog' 'taglib'
  'tinyxml' 'swig' 'upower' 'giflib' 'rapidjson' 'ghostscript' 'meson' 'gtest'
  'graphviz' 'pcre'
  # wayland
  'wayland-protocols' 'waylandpp' 'libxkbcommon'
  # gbm
  'libinput'
)
options=(!lto)

_codename=Nexus

_libdvdcss_version="1.4.3-Next-Nexus-Alpha2-2"
_libdvdnav_version="6.1.1-Next-Nexus-Alpha2-2"
_libdvdread_version="6.1.3-Next-Nexus-Alpha2-2"
_ffmpeg_version="4.4.1-Nexus-Alpha1"
_crossguid_version="ca1bf4b810e2d188d04cb6286f957008ee1b7681"
_fstrcmp_version="0.7.D001"
_flatbuffers_version="23.3.3"
_libudfread_version="1.1.2"

source=(
  "$pkgbase-$pkgver-$_codename.tar.gz::https://github.com/xbmc/xbmc/archive/$pkgver-$_codename.tar.gz"
  "$pkgbase-libdvdcss-$_libdvdcss_version.tar.gz::https://github.com/xbmc/libdvdcss/archive/$_libdvdcss_version.tar.gz"
  "$pkgbase-libdvdnav-$_libdvdnav_version.tar.gz::https://github.com/xbmc/libdvdnav/archive/$_libdvdnav_version.tar.gz"
  "$pkgbase-libdvdread-$_libdvdread_version.tar.gz::https://github.com/xbmc/libdvdread/archive/$_libdvdread_version.tar.gz"
  "$pkgbase-ffmpeg-$_ffmpeg_version.tar.gz::https://github.com/xbmc/FFmpeg/archive/$_ffmpeg_version.tar.gz"
  "$pkgbase-crossguid-$_crossguid_version.tar.gz::https://mirrors.kodi.tv/build-deps/sources/crossguid-$_crossguid_version.tar.gz"
  "$pkgbase-fstrcmp-$_fstrcmp_version.tar.gz::https://mirrors.kodi.tv/build-deps/sources/fstrcmp-$_fstrcmp_version.tar.gz"
  "$pkgbase-flatbuffers-$_flatbuffers_version.tar.gz::https://mirrors.kodi.tv/build-deps/sources/flatbuffers-$_flatbuffers_version.tar.gz"
  "$pkgbase-libudfread-$_libudfread_version.tar.gz::https://mirrors.kodi.tv/build-deps/sources/libudfread-$_libudfread_version.tar.gz"
  'https://github.com/xbmc/xbmc/commit/35be40daa39965a9ea5b3569eb7d515e6a14da5d.patch'  # flatbuffers 23.3.3
  '0001-ffmpeg-fix-build-with-binutils-update.patch'  # binutils >=2.41
  'https://github.com/xbmc/xbmc/pull/23227.patch'  # thread priority crash
  'https://github.com/xbmc/xbmc/commit/d2022ce1.patch'
  'https://github.com/xbmc/xbmc/commit/6f5dff4b.patch'
  'https://patch-diff.githubusercontent.com/raw/xbmc/xbmc/pull/24577.patch'
  '0002-CWinSystemGbm-add-colourspace-connector-property.patch'
  '0003-video_clear.patch'
  '9999-hack-to-force-pvr-server-based-play-status.patch'
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
sha512sums=('cdec1383d33f421828f0249ac2929980c6eaa39e345a8a364d9f3479f873029a15f3f6e6d40707fd2df2067a71bdaa3c6a1e26277074c31c631c71afe7465cb4'
            'd3be3bfc13c5ea56d8db745c2aab090c99760684fe4c8f62a13d266feb319e9180ceeecf8116bfd2ed90d9accba2c11dbbf93b61ad00f69a40812ebf4eabcdda'
            '51e6fc033121241354a5f0b3fc9a430577ae3ff6bb7f31445aa548ef4893037fb80eea3b2c6774c81e9ebaf9c45e9b490c98c2c65eb38f9f7daba84b236f7e1d'
            '629a41157d07b8ec0ea1fe89ae5ec48f63047472a862782b805c531ae31a0376fc4dc15175f8280c3ef91d7fa977bacebb1b51232640034a34bab2293210fc5e'
            '8beb04d577b5251e74b0d52f4d130997a8ba94bbd488c7c8309e6b45095c27807e150212888ce3a384b23dff52f8df1a7bde5407bae924ddc363f8125c0616c5'
            'f0a80d8e99b10473bcfdfde3d1c5fd7b766959819f0d1c0595ac84ce46db9007a5fbfde9a55aca60530c46cb7f8ef4c7e472c6191559ded92f868589c141ccaf'
            'aaeb0227afd5ada5955cbe6a565254ff88d2028d677d199c00e03b7cb5de1f2c69b18e6e8b032e452350a8eda7081807b01765adbeb8476eaf803d9de6e5509c'
            '4066c94f2473c7ea16917d29a613e16f840a329089c88e0bdbdb999aef3442ba00abfd2aa92266fa9c067e399dc88e6f0ccac40dc151378857e665638e78bbf0'
            '3069feb5db40288beb5b112b285186162a704f0fdd3cf67a17fd4eeea015f2cfcfbb455b7aa7c3d79d00fd095a3fd11cffc7b121dce94d99c3b06a509a8977d2'
            'c05888d1ad11f9a33a578ddd2fdb705ccd385178f93f68c6af66d9361a16664f2efec7e92c3bdc2c5c93a979e973e6448ffd2b26dab6d120e1ce8a5ceb2bd948'
            '6de9e7673022e74428a55ca1e761bdb70e0b6432faa3dae7a2306c197bc52616bffdc138073496c51aebee537079cfd768845f233d688eeea5440dfb5ba163ec'
            '8c0eeb8dbc1e644b39bcdc98a47c6dfb78c206d19db7bc9597f4046eed000d515ac986a6c6806dd8f83f28fdf7ed84cfb295ee0652c769496d603b1f7529578d'
            'f4401073756f20eacb7ee06f5d4a581d505cca3129f66e57fd6f05f135d3261b19503f86e9da303cfd12b12bec8a33896c3574b8813891ef2569a9bdb5397903'
            '4672c9f26f9934be7f3cf1bc3bb8f7fc5fb84cafde05541d2fc62df2355361da27cc0321905e183a90b7470d62c760dcd12d3668b99529afc185275a0c3df7f9'
            '5dcaf77a76a738f39b23a681c4f80cb808e26aff0484b6b4d645e437c1d71ba9e7beedc80abb3e9e4785efb8e0b8b1097f3e399a110ef20fabd6348fc7a23e0b'
            'c413c32fdb6c6184a70a43ed573a1757747b92cc798089f7dcaef617014eb6e1db6f5f3ce4ad23fdc7480ccd78f35d9594e360762ad34c8fbf0c2ca074f15eb2'
            'cdbf4d8f545623ed125b78b2e0074e1d42d5f6a58fe5f5ddfb6685ec7bbee336df021a62499c29caabab5e3ffc18d4829ec60d23f164fcca90c2bf6bed93ddf2'
            '5513c575b5d59372f378d7161713e1a3ed64e83a19894eb68ae5ecebd329409cd827cab2fd25f91a2fc2fdb13e560ebcc6cf757d625c8d98787d8711eea0bafd')

prepare() {
  [[ -d "$srcdir/kodi-build" ]] && rm -rf "$srcdir/kodi-build"
  mkdir "$srcdir/kodi-build"
  [[ -d "$srcdir/kodi-build-gles" ]] && rm -rf "$srcdir/kodi-build-gles"
  mkdir "$srcdir/kodi-build-gles"

  cd "xbmc-$pkgver-$_codename"

  rm -rf system/certs # remove not needed cacert

  # flatbuffers 23.3.3
  patch -p1 -i "$srcdir/35be40daa39965a9ea5b3569eb7d515e6a14da5d.patch"
  # fix build with binutils >=2.41
  patch -p1 -i "$srcdir/0001-ffmpeg-fix-build-with-binutils-update.patch"
  # potential fix for thread priority crash
  # https://gitlab.archlinux.org/archlinux/packaging/packages/kodi/-/issues/3
  patch -p1 -i "$srcdir/23227.patch"
  # Fix build with taglib 2
  patch -p1 -i ../d2022ce1.patch
  patch -p1 -i ../6f5dff4b.patch
  patch -p1 -i ../24577.patch

  patch -p1 -i "$srcdir/0002-CWinSystemGbm-add-colourspace-connector-property.patch"
  patch -p1 -i "$srcdir/0003-video_clear.patch"
  patch -p1 -i "$srcdir/9999-hack-to-force-pvr-server-based-play-status.patch"
}

build() {

  _cmake_common_args=(
    -DCMAKE_BUILD_TYPE=Release
    -DCMAKE_INSTALL_PREFIX=/usr
    -DCMAKE_INSTALL_LIBDIR=/usr/lib
    -DENABLE_SSE=ON
    -DENABLE_SSE2=ON
    -DENABLE_SSE3=ON
    -DENABLE_SSSE3=ON
    -DENABLE_SSE4_1=ON
    -DENABLE_SSE4_2=ON
    -DENABLE_AVX=ON
    -DENABLE_AVX2=ON
    -DUSE_LTO=ON
    -DENABLE_LDGOLD=OFF
    -DENABLE_AIRTUNES=ON
    -DENABLE_AVAHI=ON
    -DENABLE_BLURAY=ON
    -DENABLE_CEC=ON
    -DENABLE_DBUS=ON
    -DENABLE_DVDCSS=ON
    -DENABLE_EGL=ON
    -DENABLE_EVENTCLIENTS=ON
    -DENABLE_MICROHTTPD=ON
    -DENABLE_MYSQLCLIENT=ON
    -DENABLE_NFS=ON
    -DENABLE_OPTICAL=ON
    -DENABLE_SMBCLIENT=ON
    -DENABLE_UDEV=ON
    -DENABLE_UPNP=ON
    -DENABLE_VAAPI=ON
    -DENABLE_VDPAU=ON
    -DENABLE_XSLT=ON
    -DENABLE_LIRCCLIENT=ON
    -DENABLE_INTERNAL_RapidJSON=OFF
    -DENABLE_INTERNAL_FFMPEG=ON
    -DENABLE_INTERNAL_CROSSGUID=ON
    -DENABLE_INTERNAL_FSTRCMP=ON
    -DENABLE_INTERNAL_FLATBUFFERS=ON
    -DENABLE_INTERNAL_UDFREAD=ON
    -Dlibdvdcss_URL="$srcdir/$pkgbase-libdvdcss-$_libdvdcss_version.tar.gz"
    -Dlibdvdnav_URL="$srcdir/$pkgbase-libdvdnav-$_libdvdnav_version.tar.gz"
    -Dlibdvdread_URL="$srcdir/$pkgbase-libdvdread-$_libdvdread_version.tar.gz"
    -DFFMPEG_URL="$srcdir/$pkgbase-ffmpeg-$_ffmpeg_version.tar.gz"
    -DCROSSGUID_URL="$srcdir/$pkgbase-crossguid-$_crossguid_version.tar.gz"
    -DFSTRCMP_URL="$srcdir/$pkgbase-fstrcmp-$_fstrcmp_version.tar.gz"
    -DFLATBUFFERS_URL="$srcdir/$pkgbase-flatbuffers-$_flatbuffers_version.tar.gz"
    -DUDFREAD_URL="$srcdir/$pkgbase-libudfread-$_libudfread_version.tar.gz"
  )

  # https://github.com/google/flatbuffers/issues/7404
  CXXFLAGS+=' -Wno-error=restrict'

  echo "building kodi"
  cd "$srcdir/kodi-build"
  cmake \
    ${_cmake_common_args[@]} \
    -DAPP_RENDER_SYSTEM=gl \
    ../"xbmc-$pkgver-$_codename"
  make

  echo "building kodi-gles"
  cd "$srcdir/kodi-build-gles"
  cmake \
    ${_cmake_common_args[@]} \
    -DAPP_RENDER_SYSTEM=gles \
    ../"xbmc-$pkgver-$_codename"
  make
}

# kodi
# components: kodi
package_kodi() {
  pkgdesc="A software media player and entertainment hub for digital media (gl renderer)"
  depends=(
    'bluez-libs' 'curl' 'dav1d' 'desktop-file-utils' 'hicolor-icon-theme' 'fmt'
    'lcms2' 'libass' 'libbluray' 'libcdio' 'libcec' 'libmicrohttpd' 'libnfs'
    'libplist' 'libpulse' 'libva' 'libvdpau' 'libxslt' 'lirc' 'lzo'
    'mariadb-libs' 'mesa' 'libpipewire' 'python-pillow' 'python-pycryptodomex'
    'python-simplejson' 'shairplay' 'smbclient' 'sndio' 'spdlog' 'sqlite'
    'taglib' 'tinyxml' 'libxrandr' 'libxkbcommon' 'waylandpp' 'libinput'
    'pcre'
  )
  optdepends=(
    'afpfs-ng: Apple shares support'
    'bluez: Blutooth support'
    'python-pybluez: Bluetooth support'
    'pulseaudio: PulseAudio support'
    'pipewire: PipeWire support'
    'upower: Display battery level'
  )
  provides=('kodi-common' 'kodi-x11' 'kodi-wayland' 'kodi-gbm')
  replaces=('kodi-common' 'kodi-x11' 'kodi-wayland' 'kodi-gbm')
  conflicts=('kodi-gles')

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

  # make sure the addons directory for binary addons exists
  # https://bugs.archlinux.org/task/77366
  mkdir -p "$pkgdir"/usr/lib/kodi/addons

  # https://gitlab.archlinux.org/archlinux/packaging/packages/kodi/-/issues/2
  mkdir -p "$pkgdir"/usr/share/kodi/system/certs
  ln -s /etc/ssl/cert.pem "$pkgdir"/usr/share/kodi/system/certs/cacert.pem
}

# kodi-gles
# components: kodi
package_kodi-gles() {
  pkgdesc="A software media player and entertainment hub for digital media (gles renderer)"
  depends=(
    'bluez-libs' 'curl' 'dav1d' 'desktop-file-utils' 'hicolor-icon-theme' 'fmt'
    'lcms2' 'libass' 'libbluray' 'libcdio' 'libcec' 'libmicrohttpd' 'libnfs'
    'libplist' 'libpulse' 'libva' 'libvdpau' 'libxslt' 'lirc' 'lzo'
    'mariadb-libs' 'mesa' 'libpipewire' 'python-pillow' 'python-pycryptodomex'
    'python-simplejson' 'shairplay' 'smbclient' 'sndio' 'spdlog' 'sqlite'
    'taglib' 'tinyxml' 'libxrandr' 'libxkbcommon' 'waylandpp' 'libinput'
    'pcre'
  )
  optdepends=(
    'afpfs-ng: Apple shares support'
    'bluez: Blutooth support'
    'python-pybluez: Bluetooth support'
    'pulseaudio: PulseAudio support'
    'pipewire: PipeWire support'
    'upower: Display battery level'
  )
  provides=('kodi-common' 'kodi-x11' 'kodi-wayland' 'kodi-gbm' 'kodi')
  replaces=('kodi-common' 'kodi-x11' 'kodi-wayland' 'kodi-gbm')
  conflicts=('kodi')

  _components=(
    'kodi'
    'kodi-bin'
  )

  cd kodi-build-gles
  for _cmp in ${_components[@]}; do
  DESTDIR="$pkgdir" /usr/bin/cmake \
    -DCMAKE_INSTALL_COMPONENT="$_cmp" \
     -P cmake_install.cmake
  done

  # make sure the addons directory for binary addons exists
  # https://bugs.archlinux.org/task/77366
  mkdir -p "$pkgdir"/usr/lib/kodi/addons
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
  depends=('kodi')

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

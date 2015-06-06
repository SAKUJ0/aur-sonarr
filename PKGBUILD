# Maintainer: Daniel Egeberg <daniel.egeberg@gmail.com>
# Contributor: Justin Dray <justin@dray.be>
pkgname="sonarr"
pkgver="2.0.0.3212"
pkgrel=1
pkgdesc="PVR for newsgroup users. Formerly known as NZBDrone"
arch=(any)
url="http://www.sonarr.tv"
license=('GPL3')
depends=('mono' 'libmediainfo' 'sqlite')
optdepends=('sabnzbd: an NZB downloader'
            'nzbget: an NZB downloader'
            'transmission: a torrent downloader'
            'deluge: a torrent downloader')
install='sonarr.install'
provides=('nzbdrone' 'nzbdrone-torrents')
conflicts=('nzbdrone' 'nzbdrone-torrents')
replaces=('nzbdrone' 'nzbdrone-torrents')
source=("http://update.sonarr.tv/v2/master/mono/NzbDrone.master.${pkgver}.mono.tar.gz"
        "sonarr.sh"
        "sonarr.service"
        "sonarr.install")
noextract=()
md5sums=('57765205b3008f6dfd429ff8945cdf5f'
         'a7490c3f8d6c3a314b59f87f71086f1f'
         '8a34a7ef0b0425e1d33c8174a494b952'
         '57642d54d804102fd7e0b433bb9d646d')
sha1sums=('521cbead7931e45690e0e23e33dcfa2c3aa391b5'
          '839c58c88ea515441a3c976c658d7bf519cce705'
          'c3ea8665c795629c21a3a14162644799e2a0e405'
          '299fd0510a4f21ab2170577b00bbf72219a0ff5b')
sha256sums=('0ba572d90cc96295995d497795e34f14103ef5cffab926d589d54f5e7e038c2d'
            'c5a2335351a8b23ef3e5d4e01652ba3699eb86ea0d607f29b25dda0d2c0f2cb7'
            'cbe23b489277bf07bade68616c57d5624d9c89e98d8a76d448ab2c57e717b2c9'
            '7a114a5d5e57d321248325963c2c10be30d5b2f9c3cb6ffa7eb5b917d944e576')
sha512sums=('3a2c284e52de42ba4f31065893f83e77ec9de9ae1697fc4a1e5b5092f6dcc08c0b6e75ed4c2fa9938f864f8828b751908a2fd3251092fbfa7b45caf2c350e753'
            '84efa2eebd9afe6b74203aefdc3fdbd4088ecfad17dbe929396f1ffc639743b615a9b75566a0b45d6b7925bd5675368015047c6d65c1421ffe8712728f350695'
            '73c92da588044f2f35b75ca33d0d09ca0f0db93edff491cef316b5745a3b481c659b062e608044d07a0b1d2194240cecddfc2c2fcec6f879a3ffcd2b3b788993'
            'bfd8ce196b822c6332db2678e616e3aab2657b1d490d932c8632530268e56d1dc73f64f9076d12ce9ce33023684392ed142fa3d94f7e138036265da1ddf93d45')

package() {
    cd "$srcdir"

    install -d -m 755 "${pkgdir}/var/lib/sonarr/.config/NzbDrone"

    msg2 "Install Sonarr in /usr/lib"
    install -d -m 755 "${pkgdir}/usr/lib/sonarr"
    cp -dpr --no-preserve=ownership "${srcdir}/NzbDrone/"* "${pkgdir}/usr/lib/sonarr"

    msg2 "Install executable into /usr/bin"
    install -D -m755 "${srcdir}/sonarr.sh" "${pkgdir}/usr/bin/sonarr"

    msg2 "Install sonarr.service"
    install -D -m 644 "${srcdir}/sonarr.service" "${pkgdir}/usr/lib/systemd/system/sonarr.service"
}

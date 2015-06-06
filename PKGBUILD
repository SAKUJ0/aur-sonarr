# Maintainer: Daniel Egeberg <daniel.egeberg@gmail.com>
# Contributor: Justin Dray <justin@dray.be>
pkgname="sonarr"
pkgver="2.0.0.3154"
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
md5sums=('3b9493499dccde7acd259dcc6582cc9c'
         'a7490c3f8d6c3a314b59f87f71086f1f'
         '8a34a7ef0b0425e1d33c8174a494b952'
         'ac445f6bfaee8212dbecc1e719117398')
sha1sums=('2bc3aadff56065e4f0bcbbb56d1f2957072fed81'
          '839c58c88ea515441a3c976c658d7bf519cce705'
          'c3ea8665c795629c21a3a14162644799e2a0e405'
          '04970dd47a42a4c5d42f94331054f07514fce198')
sha256sums=('5b4ea2fe574cd6d48ef0f735828dd2eae6af622e89373e1fb8d388ada8674075'
            'c5a2335351a8b23ef3e5d4e01652ba3699eb86ea0d607f29b25dda0d2c0f2cb7'
            'cbe23b489277bf07bade68616c57d5624d9c89e98d8a76d448ab2c57e717b2c9'
            'aaef625973a6e8e6fb41d7463c7aaa1eb389808385c01352ba7c1f806232ffce')
sha512sums=('853734093df67b1a0da796632946454fcc9879c22abe7f9ab1946d6df7379e54ba123344896f10b367ab792e0828d8a703de21e0e503feb6c19e1354000a3697'
            '84efa2eebd9afe6b74203aefdc3fdbd4088ecfad17dbe929396f1ffc639743b615a9b75566a0b45d6b7925bd5675368015047c6d65c1421ffe8712728f350695'
            '73c92da588044f2f35b75ca33d0d09ca0f0db93edff491cef316b5745a3b481c659b062e608044d07a0b1d2194240cecddfc2c2fcec6f879a3ffcd2b3b788993'
            '7318c61a73399c113238c0038dd3a658bea7ec245a2c8c2bbe70f2796cd95e58491cfeaca50ed9de6a3290b59a7dbe0f401da49a53474c7b524a65ad83868975')

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

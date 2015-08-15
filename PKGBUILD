    # Contributor: stalker_exe <stalkerexe8@gmail.com>, fixed by mephisto
    pkgname=firefox-nightly-russian
    pkgdesc='Standalone web browser from mozilla.org, nightly build. Russian'
    url='http://www.mozilla.org/projects/firefox/prerelease.html'
    pkgver=16.0a1  
    pkgrel=1
    groups=('internet')
    arch=('i686' 'x86_64')
    license=('MPL' 'GPL' 'LGPL')
    source=(firefox-nightly.desktop)
    md5sums=('3ef8281dd6ea1246fe0f2501136d5780')
    depends=('desktop-file-utils' 'libxt' 'mime-types' 'nss' 'shared-mime-info')
    package() {
      FX_SRC="firefox-${pkgver}.ru.linux-${CARCH}.tar.bz2"
      FX_SRC_URI="http://ftp.mozilla.org/pub/mozilla.org/firefox/nightly/latest-mozilla-central-l10n/${FX_SRC}"
     
      msg "Скачивание ${FX_SRC_URI}..."
      wget -N ${FX_SRC_URI}
      msg "Распаковка ${FX_SRC}..."
      bsdtar -x -f ${FX_SRC}
     
     
    #   uncomment this line to remove these
    #   rm -rf firefox/{extensions,plugins,searchplugins}
     
      mkdir -p "${pkgdir}"/{usr/{bin,share/{applications,pixmaps}},opt}
      cp -r firefox "${pkgdir}/opt/firefox-nightly-russian"
     
      ln -s /opt/firefox-nightly-russian/firefox "${pkgdir}/usr/bin/firefox-nightly"
      install -m644 "${srcdir}"/firefox-nightly.desktop "${pkgdir}/usr/share/applications/"
      install -m644 "${srcdir}/firefox/icons/mozicon128.png" "${pkgdir}/usr/share/pixmaps/${pkgname}-icon.png"
    }

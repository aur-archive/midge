# Contributor: chimeracoder <dev@chimeracoder.net>
pkgname='midge'
pkgver='0.2.41'
pkgrel='1'
pkgdesc="Midi sequencing from the comfort of your text editor"
arch=('any')
license=('GPL')
depends=('perl')
url='http://www.undef.org.uk/code/midge/'
source=('http://www.undef.org.uk/code/midge/midge-0.2.41.tar.gz')
md5sums=('ffee418022a1d6481425a1bfcdac2b0f')
sha512sums=('2cc295cd15a8d2d35ba95ba89b7c769686226fb561a5de6eb6b73cc2fd73c44890aea1df8f8c36f4fe2e18af43a66efa3bb7bb982e81132fea8b6cc57634e6c0')

build() {
   export PERL_MM_USE_DEFAULT=1 PERL5LIB=""                 \
      PERL_AUTOINSTALL=--skipdeps                            \
      PERL_MM_OPT="INSTALLDIRS=vendor DESTDIR='$pkgdir'"     \
      PERL_MB_OPT="--installdirs vendor --destdir '$pkgdir'" \
      MODULEBUILDRC=/dev/null
    cd "${srcdir}/midge-0.2.41" && 
    echo $(ls);
    #Hacked together. The real configure file is/was horribly broken
    BINDIR="/usr/bin";
    MANDIR="/usr/share/man/man1"
    INCDIR="/usr/include/midge"
    echo -e "midge $BINDIR\n    chmod 755 $BINDIR/midge\n    cp midge.1 $MANDIR\n    chmod 644 $MANDIR/midge.1\n    cp midi2mg $BINDIR\n    chmod 755 $BINDIR/midi2mg\n    cp midi2mg.1 $MANDIR\n    chmod 644 $MANDIR/midi2mg.1\n    cp include/* $INCDIR\n    chmod 644 $INCDIR/*.mgh" > Makefile
   find "$pkgdir" -name .packlist -o -name perllocal.pod -delete 
}

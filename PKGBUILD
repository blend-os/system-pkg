# Maintainer: Rudra Saraswat <rs2009@ubuntu.com>

pkgname='system-git'
pkgver=r3.92ef8d5
pkgrel=1
pkgdesc="A utility to manage your system"
arch=('x86_64' 'i686')
url="https://github.com/blend-os/blend"
license=('GPL3')
source=('git+https://github.com/blend-os/system.git')
sha256sums=('SKIP')

depends=('akshara' 'bash' 'python' 'python-yaml' 'python-click' 'python-fasteners')
provides=("${pkgname%-git}")
conflicts=("${pkgname%-git}")

pkgver() {
    cd "${srcdir}/${pkgbase%-git}"
    printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
    cd "${srcdir}/${pkgbase%-git}"
    install -Dm755 \
        "${pkgname%-git}" \
        -t "${pkgdir}"/usr/bin/
    install -Dm755 user -t "${pkgdir}"/usr/lib/user/
    cp -r user_modules "${pkgdir}"/usr/lib/user/
    ln -s ../lib/user/user "${pkgdir}"/usr/bin/user
}

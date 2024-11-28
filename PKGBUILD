# Maintainer: Bouteiller a2n Alan <a2n.dev@pm.me>

_tag=afd1fc5a8e79f80be23952194d8ffd3c33d62ebf
_plasmoidName="a2n.archupdate.plasmoid"
_souceName="archupdate"

pkgname="plasma6-applets-arch-update-notifier"
pkgver=6.3.2.r0.gcb8f18e
pkgrel=1
pkgdesc="KDE plasmoid that lets you know when arch updates are required. Takes all repo's into account (core, extra, aur, ...)."
arch=("any")
url="https://github.com/bouteillerAlan/archupdate"
license=("GPL-3.0-or-later")
source=("git+${url}.git#tag=${_tag}?signed")
depends=("konsole" "pacman-contrib" "kdialog")
makedepends=("git")
optdepends=("paru: paru support" "yay: yay support - supported by default")
sha256sums=("SKIP")
validpgpkeys=(
  6A2ECC8A396F8A943A109A1E0F11C2A6BF79111E # Bouteiller a2n Alan <a2n.dev@pm.me>, retrieved from https://github.com/bouteillerAlan.gpg
)

pkgver() {
  cd "${_souceName}"
  git describe --long --abbrev=7 | sed 's/^v//;s/\([^-]*-g\)/r\1/;s/-/./g'
}

package() {
  cd "${_souceName}"
  install -Dm 644 LICENSE -t "${pkgdir}"/usr/share/licenses/"${pkgname}"/
  find "${_plasmoidName}" -type f -exec install -Dm 644 "{}" "${pkgdir}/usr/share/plasma/plasmoids/{}" \;
}


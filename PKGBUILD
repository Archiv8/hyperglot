#!/bin/bash

# Created from the original PKGBUILD by Caleb Maclennan <caleb@alerque.com>

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# ToDo: Add files: User documentation
# ToDo: Add files: Tooling
# FixMe: Namcap warnings and errors

# Maintainer: Ross Clark <https://github.com/Archiv8/hyperglot/discussions>
# Contributor: Ross Clark <https://github.com/Archiv8/hyperglot/discussions>

pkgname="hyperglot"
pkgver=0.3.8
pkgrel=1
pkgdesc="A database and tools for detecting language support in fonts"
arch=(any)
url="https://github.com/rosettatype/$pkgname"
license=(
  "GPL3"
)
depends=(
  "python"
  "python-click"
  "python-colorlog"
  "python-fonttools"
  "python-unicodedata2"
  "python-yaml"
)
makedepends=(
  "python-build"
  "python-installer"
  "python-setuptools"
  "python-wheel"
)
_tarname="$pkgname-$pkgver"
source=(
  "$_tarname.tar.gz::$url/archive/$pkgver.tar.gz"
)
sha512sums=(
  "32b8a08795fad10bfe909ddcab9578a53d1a0faf5a9ac79c2a129d2529d00166336560528f298ff8433fdc1149791da948fa2ef4f4d67780bd79b8f8126bdaf6"
)

build() {

  cd "$_tarname"

  python -m build -wn
}

package() {

  cd "$_tarname"

  python -m installer -d "$pkgdir" dist/*.whl
}

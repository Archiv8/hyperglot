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
pkgver=0.4.1
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
  "ba7508a96d5baa1f3a7dd861ec3a2b336ae7af724120f71d00a4f93f68f973464660964fcab5c06fcc7f21388035ca643338e6c6e0e0162a6f956c353ff05081"
)

build() {

  cd "$_tarname"

  python -m build -wn
}

package() {

  cd "$_tarname"

  python -m installer -d "$pkgdir" dist/*.whl
}

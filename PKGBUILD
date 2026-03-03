# SPDX-License-Identifier: AGPL-3.0

#    ----------------------------------------------------------------------
#    Copyright © 2023, 2024 2025, 2026  Pellegrino Prevete
#
#    All rights reserved
#    ----------------------------------------------------------------------
#
#    This program is free software: you can redistribute it and/or modify
#    it under the terms of the GNU Affero General Public License as
#    published by the Free Software Foundation, either version 3 of the
#    License, or (at your option) any later version.
#
#    This program is distributed in the hope that it will be useful,
#    but WITHOUT ANY WARRANTY; without even the implied warranty of
#    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#    GNU Affero General Public License for more details.
#
#    You should have received a copy of the GNU Affero General Public
#    License along with this program.
#    If not, see <https://www.gnu.org/licenses/>.

# Maintainers:
#   Truocolo
#     <truocolo@aol.com>
#     <truocolo@0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b>
#   Pellegrino Prevete (dvorak)
#     <pellegrinoprevete@gmail.com>
#     <dvorak@0x87003Bd6C074C713783df04f36517451fF34CBEf>

_os="$(
  uname \
    -o)"
_evmfs_available="$(
  command \
    -v \
    "evmfs" || \
    true)"
if [[ ! -v "_evmfs" ]]; then
  if [[ "${_evmfs_available}" != "" ]]; then
    _evmfs="true"
  elif [[ "${_evmfs_available}" == "" ]]; then
    _evmfs="false"
  fi
fi
_node="nodejs"
if [[ "${_os}" == "Android" ]]; then
  # This will have to be removed when we
  # will have non-termux missing-provides bugged
  # life and dogeos android nodejs and nodejs-lts
  # builds.
  _node_lts="$(
    ( pacman \
       -Q \
       "nodejs-lts" \
       2>"/dev/null" || \
      pacman \
        -Q \
        "nodejs" ) | \
      awk \
        '{print $1}' \
      2>/dev/null)"
  if [[ "${_node_lts}" != "" ]]; then
    _node="nodejs-lts"
  fi
fi
if [[ ! -v "_npm" ]]; then
  _npm="true"
fi
if [[ ! -v "_git" ]]; then
  _git="false"
fi
if [[ ! -v "_git_http" ]]; then
  _git_http="github"
fi
if [[ ! -v "_ns" ]]; then
  _ns="isaacs"
  if [[ "${_git_http}" == "gitlab" ]]; then
    _ns="themartiancompany"
  fi
fi
if [[ ! -v "_archive_format" ]]; then
  if [[ "${_npm}" == "true" ]]; then
    _archive_format="tgz"
  elif [[ "${_npm}" == "false" ]]; then
    if [[ "${_git_http}" == "github" ]]; then
      _archive_format="zip"
    elif [[ "${_git_http}" == "gitlab" ]]; then
      _archive_format="tar.xz"
    fi
  fi
fi
_node="nodejs"
_pkg=inherits
pkgbase="${_pkg}"
pkgname=(
  "${pkgbase}"
)
_pkgdesc=(
  'Browser-friendly inheritance fully compatible'
  'with standard node.js'
)
pkgdesc="${_pkgdesc[*]}"
_commit="9a2c29400c6d491e0b7beefe0c32efa3b462545d"
pkgver=2.0.4
pkgrel=3
arch=(
  'any'
)
_gh="https://github.com"
_ns="isaacs"
_http="${_gh}"
url="${_http}/${_ns}/${pkgbase}"
license=(
  'custom'
)
depends=(
  "${_node}"
)
makedepends=(
  'npm'
)
provides=(
  "${_node}-${pkgbase}=${pkgver}"
)
conflicts=(
  "${_node}-${pkgbase}"
)
if [[ "${_npm}" == "true" ]]; then
  _tag="${pkgver}"
  _tag_name="pkgver"
elif [[ "${_npm}" == "false" ]]; then
  _tag="${_commit}"
  _tag_name="commit"
fi
_tarname="${_pkg}-${_tag}"
_npm_tarname="${_tarname}"
_tarfile="${_tarname}.${_archive_format}"
_npm_tarfile="${_npm_tarname}.${_archive_format}"
_sum="fc02da8e097a6ac82263a68a5fa441a9b8d0cc8d7e34551341460fea7b4f0619"
_sig_sum="d1acb8207f47fefffd54765644ecaca08b760f58df5af0fcfcd052bded88d6a1"
_bundle_sum="SKIP"
_bundle_sig_sum="SKIP"
_npm_sum="d94dbc6c1bb3c5ac0fb12a73ade187108fc60de273a1b754f55044eb5e24afaf"
_npm_sig_sum="5b335bcaf5c84ff68ae782951b2e7ef61ac8c1b5afadc6f8d03bb4207a3862d7"
_npm_sha512_sum='93fbc6697e3f6256b75b3c8c0af4d039761e207bea38ab67a8176ecd31e9ce9419cc0b2428c859d8af849c189233dcc64a820578ca572b16b8758799210a9ec1'
# Truocolo
_evmfs_ns="0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b"
# Dvorak
_evmfs_ns="0x87003Bd6C074C713783df04f36517451fF34CBEf"
# Gnosis
_evmfs_network="100"
_evmfs_address="0x69470b18f8b8b5f92b48f6199dcb147b4be96571"
# Harmony
_evmfs_network="1666600000"
_evmfs_address="0x1f762a05cfab651d3d95778f9c89c46545913623"
if [[ "${_npm}" == "true" ]]; then
  _sum="${_npm_sum}"
  _sig_sum="${_npm_sig_sum}"
fi
_evmfs_dir="evmfs://${_evmfs_network}/${_evmfs_address}/${_evmfs_ns}"
_evmfs_uri="${_evmfs_dir}/${_sum}"
_evmfs_src="${_tarfile}::${_evmfs_uri}"
_bundle_uri="${_evmfs_dir}/${_bundle_sum}"
_bundle_src="${_tarfile}::${_bundle_uri}"
_evmfs_npm_uri="${_evmfs_dir}/${_npm_sum}"
_evmfs_npm_src="${_tarfile}::${_evmfs_npm_uri}"
_evmfs_sig_uri="${_evmfs_dir}/${_sig_sum}"
_evmfs_sig_src="${_tarfile}.sig::${_evmfs_sig_uri}"
_bundle_sig_uri="${_evmfs_dir}/${_bundle_sig_sum}"
_bundle_sig_src="${_tarfile}.sig::${_bundle_sig_uri}"
_npm_sig_uri="${_evmfs_dir}/${_npm_sig_sum}"
_npm_sig_src="${_tarfile}.sig::${_npm_sig_uri}"
_npm_http="http://registry.npmjs.org"
source=()
sha256sums=()
if [[ "${_evmfs}" == "true" ]]; then
  if [[ "${_npm}" == "true" ]]; then
    _uri="${_evmfs_npm_uri}"
    _sig_src="${_npm_sig_src}"
    _sig_sum="${_npm_sig_sum}"
  elif [[ "${_npm}" == "false" ]]; then
    if [[ "${_git}" == "true" ]]; then
      _uri="${_bundle_uri}"
      _sum="${_bundle_sum}"
      _sig_src="${_bundle_sig_src}"
      _sig_sum="${_bundle_sig_sum}"
    elif [[ "${_git}" == "false" ]]; then
      _uri="${_evmfs_uri}"
      _sig_src="${_evmfs_sig_src}"
    fi
  fi
  source+=(
    "${_sig_src}"
  )
  sha256sums+=(
    "${_sig_sum}"
  )
elif [[ "${_evmfs}" == "false" ]]; then
  if [[ "${_npm}" == "true" ]]; then
    sha512sums=(
      "${_npm_sha512_sum}"
    )
    _uri="${_npm_http}/${_pkg}/-/${_tarfile}"
  elif [[ "${_npm}" == "false" ]]; then
    if [[ "${_tag_name}" == 'pkgver' ]]; then
      if [[ "${_git_http}" == "gitlab" ]]; then
        _uri="${url}/archive/refs/tags/${_tag}.${_archive_format}"
      fi
    elif [[ "${_tag_name}" == "commit" ]]; then
      if [[ "${_git_http}" == "github" ]]; then
        _uri="${url}/archive/${_commit}.${_archive_format}"
      elif [[ "${_git_http}" == "gitlab" ]]; then
        _uri="${url}/-/archive/${_commit}/${_tarname}.${_archive_format}"
      fi
    fi
  fi
fi
if [[ "${_npm}" == "true" ]]; then
  _tarfile="${_npm_tarfile}"
fi
_src="${_tarfile}::${_uri}"
source+=(
  "${_src}"
)
sha256sums+=(
  "${_sum}"
)
if [[ "${_npm}" == "true" ]]; then
  noextract=(
    "${_tarfile}"
  )
fi
validpgpkeys=(
  # Truocolo
  #   <truocolo@aol.com>
  '97E989E6CF1D2C7F7A41FF9F95684DBE23D6A3E9'
  'DD6732B02E6C88E9E27E2E0D5FC6652B9D9A6C01'
  #   <truocolo@0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b>
  'F690CBC17BD1F53557290AF51FC17D540D0ADEED'
  # Pellegrino Prevete (dvorak)
  #   <dvorak@0x87003Bd6C074C713783df04f36517451fF34CBEf>
  '12D8E3D7888F741E89F86EE0FEC8567A644F1D16'
)

build() {
  cd \
    "${srcdir}"
  _sha="$( \
    sha512sum \
      "${pkgbase}-${pkgver}.tgz")"
  printf \
    "%s\n  %s\n  %s\n" \
    "SHA512 checksum of source file:" \
    "${pkgbase}-${pkgver}.tgz:" \
    "${_sha}"
}

package() {
  cd \
    "${pkgdir}"
  local \
    _npm_options=()
  _npm_options=(
    -g
    # --user
    #   root
    --prefix
      "${pkgdir}/usr"
  )
  npm \
    install \
      "${_npm_options[@]}" \
      "${srcdir}/${pkgbase}-${pkgver}.tgz"
  rm \
    -fr \
    "${pkgdir}/usr/etc"
  # Fix npm derp
  find \
    "${pkgdir}/usr" \
    -type \
      d \
    -exec \
      chmod \
        755 \
	'{}' \
	+
}

# vim:set sw=2 sts=-1 et:

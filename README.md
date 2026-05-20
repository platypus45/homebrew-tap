# platypus45/homebrew-tap

Homebrew tap for [Domestique](https://github.com/platypus45/domestique) — adaptive cycling training planner.

## Install

```bash
brew tap platypus45/tap
brew install --cask domestique
```

Homebrew Cask strips `com.apple.quarantine` on install, so the macOS "unidentified developer" Gatekeeper dialog is bypassed automatically. Open `Domestique.app` from `/Applications` after install.

## Upgrade

```bash
brew upgrade --cask domestique
```

## Uninstall

```bash
brew uninstall --cask domestique
brew untap platypus45/tap   # optional
```

The Cask's `zap` block removes `~/.domestique` on `brew uninstall --zap --cask domestique`.

## Maintainer notes

The canonical `Casks/domestique.rb` lives in [platypus45/domestique](https://github.com/platypus45/domestique) under `Casks/`. On every release:

```bash
VER=1.8.5
curl -sL https://github.com/platypus45/domestique/releases/download/v${VER}/Domestique-v${VER}.dmg -o /tmp/D.dmg
SHA=$(shasum -a 256 /tmp/D.dmg | awk '{print $1}')
# Bump version + sha256 in the source repo's Casks/domestique.rb
# Then copy the updated file into this tap's Casks/ and push.
```

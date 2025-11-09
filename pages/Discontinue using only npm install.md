---
title: "Discontinue using only npm install"
---


<img src='https://scrapbox.io/api/pages/nishio-en/GPT5/icon' alt='GPT5.icon' height="19.5"/>
sh

```
# 1) Place the directory for the wrapper installation at the top of the PATH.
mkdir -p ~/.bin
if ! grep -q 'export PATH="$HOME/.bin:$PATH"' ~/.bashrc 2>/dev/null; then
  echo 'export PATH="$HOME/.bin:$PATH"' >> ~/.bashrc
fi
if [ -n "$ZSH_VERSION" ] && ! grep -q 'export PATH="$HOME/.bin:$PATH"' ~/.zshrc 2>/dev/null; then
  echo 'export PATH="$HOME/.bin:$PATH"' >> ~/.zshrc
fi

# 2) Create wrapper body
cat > ~/.bin/npm <<'SH'
#!/usr/bin/env bash
# --- block only: npm install / i / ci ---
# Skip the leading option (--xx) and extract the first subcommand
sub=""
for a in "$@"; do
  case "$a" in --*) ;; *) sub="$a"; break ;; esac
done
case "$sub" in
  install|i|ci)
    echo "npm $sub is not allowed, use pnpm." >&2
    exit 127
    ;;
esac

# Search for "real npm" by excluding this wrapper's own directory from the PATH
SELF_DIR="$(cd "$(dirname "$0")" && pwd)"
CLEAN_PATH="$(printf "%s" "$PATH" | awk -v RS=: -v ORS=: -v d="$SELF_DIR" '$0!=d' | sed 's/:$//')"
REAL_NPM="$(PATH="$CLEAN_PATH" command -v npm)"
if [ -z "$REAL_NPM" ]; then
  echo "Real npm not found." >&2
  exit 127
fi
exec "$REAL_NPM" "$@"
SH
chmod +x ~/.bin/npm

# 3) Reload the shell
exec $SHELL -l

# Confirmation of operation
npm install # => rejected
npm i # => rejected
npm ci # => rejected
npm run dev # => pass
```



---
This page is auto-translated from [/nishio/npm installだけを使用中止](https://scrapbox.io/nishio/npm installだけを使用中止) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
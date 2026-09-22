# Keysmith

A password and passphrase generator that runs entirely in your browser.

**Live:** https://chrisbrady86.github.io/keysmith/

## How it works

- Randomness comes from the Web Crypto API (`crypto.getRandomValues`), with rejection sampling so every character or word is equally likely.
- **Random mode** draws from lowercase, uppercase, digits and a shell-safe symbol set (`!#%*+-.=?@^_~`). Quotes, backslash, `$`, `&` and backtick are left out because they break shell commands and config files.
- **Passphrase mode** draws words from the EFF long wordlist (7,776 words, about 12.9 bits of entropy per word).
- Strength is shown in bits of entropy, with an estimated offline crack time at 10^12 guesses per second.

## Privacy

- Everything happens in one self-contained `index.html`. There are no external scripts, fonts or network requests; a Content-Security-Policy blocks them.
- Generated passwords are never stored or transmitted. Only your settings (length, mode, character types) are remembered in your browser's localStorage.

## Credits

Wordlist: [EFF Large Wordlist for Passphrases](https://www.eff.org/dice), Electronic Frontier Foundation, licensed CC BY 3.0 US.

<p align="center"><img src="favicon.svg" width="96" alt="Bit by Bit logo: a chip with the number 1"></p>

# Bit by Bit

**Start with one bit. Find out what lies beyond the last byte.**

An incremental browser game about the history of computing: click the chip, buy components from punched cards to Dyson spheres, and climb the data units from bits to Quettabytes and past the end of the official scale, while an unknown signal on the bus slowly decodes itself.

**Play:** https://akanyane.github.io/bit-by-bit/

*Leia em português: [README.pt-BR.md](README.pt-BR.md)*

## Features

- **9 eras** and **29 components**, each era changing the chip, the circuit board and the music
- **Upgrades, contracts and a research tree** with three branches (clicks, production, network)
- **Compression** (prestige): restart from zero and turn everything you generated into permanent algorithms
- **Random events:** data packets, viruses, solar storms and maintenance calls with three minigames (logic gates, bus memory, decode the byte)
- **89 achievements**, including secret ones hinted at by the story
- **A hidden story** told through the Transmission log
- **Chiptune music and sound effects** synthesized live with the Web Audio API
- **Numbers with no ceiling**, using `BigInt`
- **7 languages:** English, Português, Español, 日本語, 한국어, Deutsch, Italiano. The game picks your browser's language and falls back to English; you can switch anytime from the header.
- Progress is saved in your browser, with offline earnings

## Running locally

No build step and no dependencies. Clone the repo and open `index.html` in a browser, or serve the folder:

```sh
git clone https://github.com/akanyane/bit-by-bit.git
cd bit-by-bit
python3 -m http.server 8000   # then open http://localhost:8000
```

Add `?debug` to the URL (for example `http://localhost:8000/?debug`) to show a debug panel that adds bits, research points and triggers events on demand. Records sent to the leaderboard after using it are flagged.

## Project layout

```
index.html          the whole game: markup, styles and logic
i18n/en.js          English strings (defines every key; other languages fall back to it)
i18n/<lang>.js      pt-BR, es, ja, ko, de, it
favicon.svg / .ico  icons
```

### Adding a language

1. Copy `i18n/en.js` to `i18n/<code>.js` and set `I18N['<code>']`, `name`, `locale` and `htmlLang`.
2. Translate the strings. Entries written as functions handle numbers and plurals, so keep their parameters.
3. Add `<script src="i18n/<code>.js"></script>` to `index.html` and the code to the `LANGS` list.

Keys you leave out fall back to English.

## License

[MIT](LICENSE) © Akanyane. You can use, modify and redistribute it, as long as you keep the copyright notice and a link back to this repository.

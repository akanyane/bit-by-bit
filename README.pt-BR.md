<p align="center"><img src="favicon.svg" width="96" alt="Logo do Bit by Bit: um chip com o número 1"></p>

# Bit by Bit

**Comece com um bit. Descubra o que existe depois do último byte.**

Um jogo incremental no navegador sobre a história da computação: clique no chip, compre componentes que vão do cartão perfurado à esfera de Dyson e suba pelas unidades de dados, de bits a Quettabytes e além do fim da escala oficial, enquanto um sinal desconhecido no barramento vai sendo decodificado aos poucos.

**Jogar:** https://akanyane.github.io/bit-by-bit/

*Read in English: [README.md](README.md)*

## O que tem no jogo

- **9 eras** e **29 componentes**, cada era muda o chip, a placa e a música
- **Melhorias, contratos e uma árvore de pesquisa** com três ramos (cliques, produção, rede)
- **Compressão** (prestígio): recomece do zero e transforme tudo o que gerou em algoritmos permanentes
- **Eventos aleatórios:** pacotes de dados, vírus, tempestades solares e chamados de manutenção com três minijogos (portas lógicas, memória de barramento, decodifique o byte)
- **89 conquistas**, incluindo secretas com pistas na história
- **Uma história escondida** contada pela Transmissão
- **Música chiptune e efeitos sonoros** sintetizados na hora com a Web Audio API
- **Números sem teto**, usando `BigInt`
- **7 idiomas:** English, Português, Español, 日本語, 한국어, Deutsch, Italiano. O jogo usa o idioma do navegador e cai para o inglês; dá para trocar a qualquer momento no topo da página.
- O progresso fica salvo no navegador, com ganhos offline

## Rodando localmente

Sem build e sem dependências. Clone o repositório e abra o `index.html` no navegador, ou sirva a pasta:

```sh
git clone https://github.com/akanyane/bit-by-bit.git
cd bit-by-bit
python3 -m http.server 8000   # depois abra http://localhost:8000
```

## Estrutura

```
index.html          o jogo inteiro: marcação, estilos e lógica
i18n/en.js          textos em inglês (define todas as chaves; os outros idiomas caem para ele)
i18n/<idioma>.js    pt-BR, es, ja, ko, de, it
favicon.svg / .ico  ícones
```

### Adicionando um idioma

1. Copie `i18n/en.js` para `i18n/<código>.js` e ajuste `I18N['<código>']`, `name`, `locale` e `htmlLang`.
2. Traduza os textos. As entradas que são funções tratam números e plurais, então mantenha os parâmetros.
3. Adicione `<script src="i18n/<código>.js"></script>` no `index.html` e o código na lista `LANGS`.

Chaves que você não traduzir caem para o inglês.

## Licença

[MIT](LICENSE) © Akanyane. Pode usar, modificar e redistribuir, desde que mantenha o aviso de copyright e o link para este repositório.

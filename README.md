# Relatório de Estágio - Template LaTeX UNIJUÍ

Este repositório é um *fork* do template original desenvolvido pelo
**Prof. Eldair F. Dornelles**, disponível em:
[https://github.com/dornelles/relatorio-de-estagio-template-latex](https://github.com/dornelles/relatorio-de-estagio-template-latex)

Neste fork, o template foi utilizado como base para o Relatório de Estágio
Supervisionado do curso de **Ciência da Computação** da UNIJUÍ, campus Santa Rosa,
desenvolvido por **Cristian dos Santos Siqueira** (2026).

O relatório documenta o desenvolvimento de um módulo de geração automatizada de
propostas comerciais em PDF, integrado ao sistema Django da empresa
BIOTECNO Indústria e Comércio Ltda., com suporte a layouts intercambiáveis
gerenciados via painel administrativo.

---

## Estrutura do Projeto

A organização dos arquivos no projeto foi pensada para facilitar a manutenção e leitura do código fonte do documento:

* **`main.tex`**: Arquivo principal. É nele que você deve preencher os dados do trabalho (título, autor, resumo, palavras-chave) e onde os demais arquivos são incluídos (via `\input`).
* **`unijui.sty`**: Arquivo de estilos (pacote LaTeX) contendo as customizações de capa, folha de rosto e adequações visuais específicas exigidas pela universidade.
* **`referencias.bib`**: Arquivo de bibliografia onde devem ser inseridas as referências no formato formato BibTeX.
* **`build-latex.sh`**: Script em bash para facilitar e automatizar a compilação do documento em ambientes Linux/macOS.
* **Diretórios**:
  * `capitulos/`: Contém os arquivos `.tex` referentes a cada capítulo (Introdução, Metodologia, Desenvolvimento, etc.).
  * `apendices/` e `anexos/`: Diretórios destinados a arquivos de apêndices e anexos do trabalho.
  * `figuras/`: Pasta para armazenar as imagens e ilustrações utilizadas no documento.

## Pré-requisitos (Compilação Local)

Para compilar este documento localmente, você precisará de uma distribuição LaTeX instalada no seu sistema.

**Linux (Ubuntu/Debian):**
```bash
sudo apt-get install texlive-full
```
*(Você também pode instalar distribuições mais enxutas e adicionar pacotes conforme a necessidade, como `texlive-latex-extra`, `texlive-lang-portuguese` e `texlive-science`)*.

**Windows/macOS:**
Recomenda-se a instalação do [MiKTeX](https://miktex.org/) ou [MacTeX](https://www.tug.org/mactex/).

**Alternativa Cloud:**
O projeto pode ser facilmente importado e editado diretamente no [Overleaf](https://www.overleaf.com/). Basta compactar os arquivos em um `.zip` e fazer o upload na plataforma.

## Como Compilar

### Usando o Script (Linux/macOS)

O projeto inclui um script que automatiza o processo de compilação (rodando o `pdflatex` e o `bibtex` a quantidade de vezes necessária e removendo os arquivos temporários em seguida).

Para compilar o PDF:
```bash
./build-latex.sh
```
*(Caso o script não tenha permissão de execução, rode antes: `chmod +x build-latex.sh`)*

Para apenas limpar os arquivos temporários sem compilar:
```bash
./build-latex.sh clean
```

### Compilação Manual

Caso não utilize o script ou esteja em outro ambiente, a sequência de comandos tradicional no terminal para gerar as referências cruzadas e citações corretamente é:
```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

## Contribuição

Sinta-se à vontade para realizar um *fork* deste repositório, propor *pull requests* ou abrir *issues* com dúvidas e sugestões.

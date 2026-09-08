# Processamento de Sinais I

Repositório contendo os códigos, os sinais de entrada e os resultados das aulas práticas da disciplina **Processamento de Sinais I** (GELE7317), do CEFET/RJ.

Cada aula prática corresponde a uma pasta deste repositório e a um relatório técnico em formato de artigo científico em duas colunas. Os resultados apresentados nos relatórios podem ser reproduzidos executando os notebooks aqui disponíveis, preferencialmente no Google Colab.

**Autores:** Luis Antonio Torres Tigrera, Clara Carolina da Rocha Cavalcante, Matheus da Silva da Mota

**Professor:** Rafael S. Chaves — [repositório da disciplina](https://github.com/rafaelschaves/gele7317-proc-sin)

---

## Conteúdo

| Aula | Atividade | Pasta |
|---|---|---|
| Aula 01 | Análise de processamento de sinais digitais: amostragem e convolução | [`Aula_01/`](Aula_01) |
| Aula 02 | Amostragem e análise espectral de sinais | [`Aula_02/`](Aula_02) |
| Aula 03 | Filtros digitais: resposta em frequência, filtros FIR e IIR | [`Aula_03/`](Aula_03) |

---

## Como executar (Google Colab)

Esta é a forma recomendada de reproduzir os experimentos. **Não é necessário instalar nada, clonar o repositório ou baixar arquivos manualmente.** O Colab já traz NumPy, SciPy, Matplotlib e IPython pré-instalados, e os notebooks baixam automaticamente os arquivos `.wav` que utilizam.

1. Abra a pasta da aula desejada aqui no GitHub e clique no notebook da questão.
2. Clique no badge **Open in Colab**, presente na primeira célula de cada notebook.
3. No Colab, execute `Ambiente de execução → Executar tudo` (`Runtime → Run all`).

Alternativamente, qualquer notebook pode ser aberto diretamente trocando o domínio na URL, ou seja, substituindo

```
https://github.com/LuisTT0903/Processamento-de-Sinais1/blob/main/...
```

por

```
https://colab.research.google.com/github/LuisTT0903/Processamento-de-Sinais1/blob/main/...
```

Cada notebook é independente e pode ser executado do início ao fim sem depender dos demais. Os gráficos e os áudios são gerados diretamente na saída das células, e os áudios podem ser ouvidos pelo player que aparece no próprio notebook.

### Observação sobre os arquivos gerados no Colab

O Colab utiliza um sistema de arquivos temporário: as figuras salvas com `plt.savefig(...)` ficam no diretório de trabalho da sessão e são apagadas quando a sessão é encerrada. Para guardá-las, use o painel **Arquivos**, na barra lateral esquerda, e baixe os `.png` antes de fechar o notebook.

---

## Alternativa: execução local com Jupyter

Caso se prefira executar na própria máquina, os notebooks também funcionam localmente.

### Requisitos

- Python 3.10 ou superior
- NumPy — operações numéricas e vetoriais
- SciPy — leitura de arquivos `.wav`, geração de chirps, reamostragem, convolução e projeto de filtros
- Matplotlib — geração dos gráficos
- IPython — reprodução sonora dos sinais dentro do notebook
- Jupyter Notebook — execução dos notebooks

### Instalação

Clone o repositório:

```bash
git clone https://github.com/LuisTT0903/Processamento-de-Sinais1.git
```

Entre na pasta:

```bash
cd Processamento-de-Sinais1
```

Instale as dependências:

```bash
pip install -r requirements.txt
```

### Execução

Inicie o Jupyter na raiz do repositório:

```bash
jupyter notebook
```

Navegue até a pasta da aula e abra o notebook da questão desejada.

Nos notebooks da Aula 02, a variável `usar_colab`, definida no início do código, controla a origem dos arquivos de áudio. Ao executar localmente, defina:

```python
usar_colab = False
```

para que os arquivos sejam lidos da pasta local em vez de baixados. Os notebooks das Aulas 01 e 03 obtêm os arquivos por download em qualquer ambiente e, por isso, exigem conexão com a internet mesmo na execução local.

---

## Organização das pastas

```
Processamento-de-Sinais1/
├── README.md
├── requirements.txt
│
├── Aula_01/
│   ├── aula20260814.ipynb        -> código da atividade
│   ├── sinais_usados/            -> arquivos de entrada (.wav)
│   ├── resultados_graficos/      -> figuras geradas (.png)
│   ├── resultados_audios/        -> áudios gerados (.wav)
│   └── relatorio/                -> relatório da aula (.pdf)
│
├── Aula_02/
│   ├── *.ipynb                   -> um notebook por questão
│   ├── Sinais_Usados/            -> arquivos de entrada (.wav)
│   ├── resultados_graficos/      -> figuras geradas (.png)
│   └── relatorio/                -> relatório da aula (.pdf)
│
└── Aula_03/
    ├── *.ipynb                   -> um notebook por questão
    └── Audios_Usados/            -> arquivos de entrada (.wav)
```

Os notebooks das Aulas 02 e 03 estão nomeados por questão, de modo que o arquivo correspondente a cada item da atividade é identificado pelo próprio nome. A Aula 01 concentra toda a atividade em um único notebook.

---

## Onde estão os resultados

As figuras apresentadas nos relatórios estão em `resultados_graficos/`, na pasta da respectiva aula. Os áudios gerados, quando existirem, estão em `resultados_audios/`. Todos podem ser regerados executando os notebooks.

---

## Reprodutibilidade

Os notebooks obtêm os arquivos `.wav` por download a partir deste próprio repositório, o que garante que sejam executáveis sem configuração prévia no Google Colab. Não são utilizados caminhos absolutos vinculados à máquina de nenhum dos autores.

Os notebooks da Aula 02 salvam suas figuras automaticamente via `plt.savefig(..., dpi=150)`. Nas Aulas 01 e 03, os gráficos são apenas exibidos na saída das células, e as figuras versionadas em `resultados_graficos/` foram exportadas manualmente a partir dessa saída.

As bibliotecas utilizadas estão listadas em `requirements.txt`. Nenhuma versão específica é exigida para reproduzir os resultados; as versões disponíveis por padrão no Google Colab são suficientes.

---

## Relatórios

Os relatórios das Aulas 01 e 02 estão em `relatorio/`, dentro da pasta de cada aula, em formato PDF. Cada figura apresentada nos relatórios é referenciada pelo arquivo correspondente em `resultados_graficos/`, e os códigos que a geraram estão nos notebooks da mesma pasta.

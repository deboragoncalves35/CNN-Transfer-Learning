# CNN and Transfer Learning

Projeto acadêmico de classificação de imagens utilizando Redes Neurais Convolucionais (CNN) e Transfer Learning com Python e PyTorch.

O objetivo é explorar diferentes abordagens de classificação de imagens, desde a implementação de uma CNN própria até a utilização de arquiteturas pré-treinadas.

## Tecnologias utilizadas

- Python
- PyTorch
- Torchvision
- FastAI
- ResNet18 e ResNet34
- NumPy
- Matplotlib
- Jupyter Notebook

## Etapas do projeto

### 1. Classificação de cães e gatos com FastAI

- Utilização do conjunto de imagens Oxford-IIIT Pet.
- Aplicação de Transfer Learning com a arquitetura ResNet34 pré-treinada.
- Treinamento e teste do modelo para distinguir imagens de cães e gatos.

### 2. Classificação binária com CNN

- Implementação de uma Rede Neural Convolucional própria utilizando PyTorch.
- Construção de camadas convolucionais, pooling e fully connected.
- Classificação de imagens em duas classes.
- Treinamento e avaliação do modelo por meio de métricas de desempenho.

### 3. Classificação de raças de cães com Transfer Learning

- Utilização da arquitetura ResNet18 pré-treinada.
- Congelamento dos parâmetros das camadas convolucionais.
- Adaptação da camada classificadora para 12 classes.
- Treinamento, teste e validação do modelo.
- Análise das curvas de perda e acurácia.

## Estrutura do projeto

```text
CNN-Transfer-Learning/
├── CNN_Transfer_Learning.ipynb
├── Data/
│   ├── Duas/
│   └── Multi/
├── Figures/
│   └── Figure1.png
├── requirements.txt
├── utils.py
└── README.md
```

## Como executar

### 1. Clone o repositório

```bash
git clone https://github.com/deboragoncalves35/CNN-Transfer-Learning.git
cd CNN-Transfer-Learning
```

### 2. Crie um ambiente virtual (opcional)

Windows:

```bash
python -m venv .venv
.venv\Scripts\activate
```

Linux/macOS:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Instale as dependências

```bash
pip install -r requirements.txt
pip install notebook
```

Para executar o treinamento com GPU, instale a versão do PyTorch compatível com seu hardware, seguindo as instruções da documentação oficial: https://pytorch.org/get-started/locally/

### 4. Execute o notebook

```bash
jupyter notebook
```

Abra o arquivo `CNN_Transfer_Learning.ipynb` e execute as células na ordem.

O notebook utiliza caminhos relativos para acessar os arquivos do projeto. Portanto, execute-o a partir da pasta principal do repositório.

## Organização dos dados

As etapas de classificação binária e classificação de raças utilizam os conjuntos de imagens armazenados em `Data/Duas` e `Data/Multi`.

Os dados são carregados com `torchvision.datasets.ImageFolder`, que organiza as imagens conforme as pastas de cada classe.

Na primeira etapa, o conjunto Oxford-IIIT Pet é obtido automaticamente por meio da função `untar_data` do FastAI.

## Resultados e avaliação

O notebook apresenta ferramentas para acompanhar o treinamento dos modelos, incluindo:

- Gráficos de perda (*training loss* e *test loss*).
- Evolução da acurácia ao longo das épocas.
- Avaliação do modelo com dados de validação.

Os resultados podem variar conforme os parâmetros utilizados e o ambiente de execução.

## Observações

- O treinamento pode exigir bastante processamento e memória.
- Recomenda-se utilizar GPU para reduzir o tempo de treinamento.
- O conjunto de imagens utilizado nas etapas 2 e 3 está incluído no repositório por meio do Git LFS.

---

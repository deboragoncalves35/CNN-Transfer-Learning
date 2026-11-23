# CNN and Transfer Learning

Projeto acadêmico de classificação de imagens utilizando redes neurais convolucionais (CNN) e Transfer Learning com Python, PyTorch, Torchvision e FastAI.

O notebook apresenta três etapas principais:

1. **Classificação de cães e gatos com FastAI:** utilização de uma ResNet34 pré-treinada e fine-tuning para distinguir imagens de cães e gatos. Nesta etapa, o FastAI baixa o conjunto de imagens Oxford-IIIT Pet por meio de `untar_data`.
2. **Classificação binária com uma CNN própria:** implementação e treinamento de uma rede convolucional com PyTorch para classificar as duas classes organizadas em `Data/Duas`.
3. **Classificação de raças com Transfer Learning:** utilização da arquitetura ResNet18 pré-treinada, com adaptação da camada final para o conjunto de classes organizado em `Data/Multi`.

## Tecnologias utilizadas

- Python
- PyTorch
- Torchvision
- FastAI
- NumPy
- Matplotlib
- IPywidgets
- Jupyter Notebook

## Estrutura do projeto

```text
CNN-Transfer-Learning/
├── CNN_Transfer_Learning.ipynb
├── requirements.txt
├── utils.py
├── Data/
│   ├── Duas/
│   └── Multi/
└── Figures/
```

O arquivo `utils.py` contém funções auxiliares utilizadas para desenhar a representação da arquitetura da CNN. A pasta `Figures` reúne material visual complementar do projeto.

## Requisitos

- Python 3.10 ou 3.11 recomendado.
- Jupyter Notebook ou JupyterLab.
- Para treinamento mais rápido, recomenda-se utilizar uma GPU compatível com PyTorch. O notebook também pode ser executado em CPU, mas o treinamento pode demorar mais.

## Instalação

1. Clone este repositório:

   ```bash
   git clone https://github.com/SEU-USUARIO/CNN-Transfer-Learning.git
   cd CNN-Transfer-Learning
   ```

2. (Opcional, mas recomendado) Crie e ative um ambiente virtual:

   **Windows**
   ```bash
   python -m venv .venv
   .venv\\Scripts\\activate
   ```

   **Linux/macOS**
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```

3. Instale as dependências:

   ```bash
   pip install -r requirements.txt
   ```

   Caso a instalação de `torch` ou `torchvision` apresente incompatibilidade com seu sistema ou GPU, consulte o seletor oficial de instalação do PyTorch: https://pytorch.org/get-started/locally/

4. Inicie o Jupyter:

   ```bash
   jupyter notebook
   ```

5. Abra `CNN_Transfer_Learning.ipynb` e execute as células na ordem.

## Organização dos dados

As etapas 2 e 3 utilizam os dados locais nas pastas `Data/Duas` e `Data/Multi`. O carregamento é feito com `torchvision.datasets.ImageFolder`, que espera uma subpasta para cada classe.

Organize os arquivos de imagem neste formato:

```text
Data/
├── Duas/
│   ├── classe_1/
│   │   ├── imagem_001.jpg
│   │   └── ...
│   └── classe_2/
│       ├── imagem_001.jpg
│       └── ...
└── Multi/
    ├── raca_1/
    │   ├── imagem_001.jpg
    │   └── ...
    ├── raca_2/
    │   └── ...
    └── ...
```

Mantenha os nomes e a organização das classes do conjunto de dados original. Não é necessário baixar manualmente o conjunto Oxford-IIIT Pet para a primeira etapa: o próprio notebook utiliza a função `fastai.untar_data` para obtê-lo.

## Observações

- Execute o notebook a partir da pasta raiz do projeto, para que os caminhos relativos `Data/` e `Figures/` sejam localizados corretamente.
- O notebook contém etapas de treinamento que podem consumir bastante memória e tempo de processamento.
- Os resultados dependem do ambiente, dos dados e dos parâmetros de treinamento utilizados.
- O dataset é necessário para executar as etapas que carregam `Data/Duas` e `Data/Multi`.

## Objetivo

Explorar a implementação de CNNs, o processamento de imagens, o treinamento e a avaliação de modelos, além da aplicação de Transfer Learning com arquiteturas pré-treinadas.

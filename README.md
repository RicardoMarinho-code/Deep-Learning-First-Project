# Deep Learning - First Project 🧠

Este repositório contém os projetos iniciais de introdução ao **Machine Learning** e **Deep Learning**, desenvolvidos em formato Jupyter Notebook (`.ipynb`). O objetivo principal é guiar o aprendizado desde a visualização de dados básicos até a construção, treinamento e validação de uma rede neural artificial profunda para visão computacional.

---

## 📂 Estrutura do Repositório

O projeto é dividido em dois notebooks principais:

1. **`EXEPLO 1 MATPLOTLIB.ipynb`**
   * **Objetivo:** Introdução à manipulação de conjuntos de dados sintéticos e visualização gráfica.
   * **Tecnologias:** `scikit-learn` (geração de dados) e `matplotlib` (plotagem gráfica).
   * **Conteúdo:** Geração de um dataset de regressão linear simples com ruído e plotagem dos pontos em um gráfico de dispersão (*scatter plot*).

2. **`deep_learning.ipynb`**
   * **Objetivo:** Implementação de uma Rede Neural Multicamadas (Multi-Layer Perceptron) para classificar dígitos manuscritos.
   * **Tecnologias:** `PyTorch` (framework de Deep Learning), `torchvision` (processamento de imagens) e `matplotlib` (visualização).
   * **Conteúdo:** Download do dataset clássico MNIST, visualização de amostras, criação da arquitetura da rede, loop de treinamento (Backpropagation) e avaliação da precisão (*accuracy*).

---

## 🧠 Detalhes Técnicos da Rede Neural (`deep_learning.ipynb`)

A arquitetura da rede neural foi projetada utilizando o framework **PyTorch** para classificar as imagens de dígitos de `0` a `9` do dataset MNIST (imagens em tons de cinza com dimensões de $28 \times 28$ pixels).

### 🏢 Arquitetura do Modelo (`Modelo` classe)

A rede neural é do tipo *Feedforward* (totalmente conectada / Fully Connected):

```
[Camada de Entrada: 784 neurônios] ──(Linear + ReLU)──> [Camada Oculta 1: 128 neurônios]
                                      ──(Linear + ReLU)──> [Camada Oculta 2: 64 neurônios]
                                      ──(Linear)─────────> [Camada de Saída: 10 neurônios] ──(Log Softmax)
```

* **Camada de Entrada:** 784 neurônios (achatamento da imagem de $28 \times 28$ pixels para um vetor unidimensional).
* **Camada Oculta 1:** 128 neurônios, com função de ativação **ReLU** ($f(x) = \max(0, x)$).
* **Camada Oculta 2:** 64 neurônios, com função de ativação **ReLU**.
* **Camada de Saída:** 10 neurônios (um para cada classe/dígito de 0 a 9) com ativação **Log Softmax** (para cálculo eficiente de perdas).

### ⚙️ Hiperparâmetros e Configurações de Treinamento

* **Otimizador:** SGD (*Stochastic Gradient Descent*) com taxa de aprendizado ($\eta$) de `0.01` e *momentum* de `0.5`.
* **Função de Perda:** `NLLLoss` (*Negative Log Likelihood Loss*), adequada para classificação multiclasse quando usada em conjunto com `LogSoftmax`.
* **Tamanho do Lote (Batch Size):** 64 imagens por iteração.
* **Épocas (Epochs):** 10 épocas de treinamento completo sobre todo o conjunto de dados.
* **Dispositivo:** Suporte a aceleração por hardware via **CUDA** (GPU) se disponível, caso contrário, utiliza a **CPU**.

---

## 🛠️ Pré-requisitos e Instalação

Para executar os notebooks localmente, é necessário ter o Python instalado (recomendado v3.8 ou superior) juntamente com as bibliotecas listadas abaixo.

### 1. Criar e ativar um ambiente virtual (Opcional, mas recomendado)
```bash
# No Windows:
python -m venv venv
venv\Scripts\activate
```

### 2. Instalar as dependências necessárias
Execute o comando a seguir para instalar todas as bibliotecas usadas nos projetos:

```bash
pip install torch torchvision numpy matplotlib scikit-learn notebook
```

*Nota: Caso tenha uma GPU NVIDIA compatível e queira utilizar aceleração CUDA, consulte as instruções oficiais do [PyTorch](https://pytorch.org/get-started/locally/) para instalar a versão correta do pacote.*

---

## 🚀 Como Executar o Projeto

1. Clone o repositório em sua máquina local:
   ```bash
   git clone https://github.com/RicardoMarinho-code/Deep-Learning-First-Project.git
   cd Deep-Learning-First-Project
   ```

2. Inicie o servidor do Jupyter Notebook:
   ```bash
   jupyter notebook
   ```

3. No navegador que se abrirá automaticamente, selecione um dos dois arquivos `.ipynb` e execute as células individualmente (`Shift + Enter`).

---

## 📄 Licença

Este projeto está licenciado sob a **Licença MIT** - consulte o arquivo [LICENSE](LICENSE) para obter mais detalhes.

---
*Desenvolvido com fins didáticos para introdução aos conceitos fundamentais de Inteligência Artificial.*

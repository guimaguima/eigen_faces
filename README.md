# 🧠 Exercício de Programação: PCA para Reconhecimento de Imagens

Este notebook é uma implementação de um exercício de programação para a disciplina de **Álgebra Linear Computacional** (DCC - UFMG, 2025.1).  
O objetivo é demonstrar a aplicação da **Análise de Componentes Principais (PCA)** em tarefas de **reconhecimento de padrões** e **classificação de imagens**.

## 📚 Estrutura do Projeto

O projeto está dividido em duas partes principais:

1. **Tutorial guiado** sobre reconhecimento facial usando o método de **Eigenfaces**.
2. **Exercício prático** de reconhecimento de dígitos manuscritos do dataset **MNIST**, aplicando a mesma metodologia.

---

## 👥 Autores

- Gabriel Guimarães dos Santos Ricardo  
- João Pedro Moreira Smolinski

---

## 🧑‍🏫 Parte 1: Tutorial de Reconhecimento Facial (Eigenfaces)

### 🎯 Objetivo

Demonstrar a construção de um sistema de reconhecimento facial capaz de identificar 15 indivíduos, representando cada rosto como uma **combinação linear de autofaces** (eigenfaces).

### 🗂 Dataset

- **Yale Faces**: 15 diretórios (um por indivíduo), cada um com 11 imagens com variações de iluminação, expressão e acessórios.
- Imagens em escala de cinza com dimensão **100x100 pixels**.

### 🧪 Metodologia

1. **Vetorização**: Imagens de 100x100 são achatadas em vetores de 10.000 dimensões.
2. **Face média**: Cálculo da imagem média do conjunto de treinamento.
3. **Centralização**: Subtração da face média para destacar características individuais.
4. **PCA**: Extração das **autofaces** (componentes principais) do conjunto centralizado.
5. **Projeção no Espaço de Faces**: Representação de cada rosto no novo espaço reduzido.
6. **Classificação**:
   - Para cada indivíduo, calcula-se o vetor médio de projeção.
   - A classificação é feita com base na **menor distância euclidiana** entre vetores.

---

## ✍️ Parte 2: Exercício de Reconhecimento de Dígitos (Eigen-digits)

### 🎯 Objetivo

Construir um classificador para dígitos manuscritos (0 a 9), avaliando como o número de componentes principais (**k**) afeta a precisão.

### 🗂 Dataset

- **Optical Recognition of Handwritten Digits (sklearn.datasets.load_digits)**
- 1797 imagens de **8x8 pixels**
- Dividido em:
  - **90% treino**
  - **10% teste**

### 🧪 Metodologia

1. **Vetorização e Centralização**:
   - Imagens são transformadas em vetores de 64 dimensões.
   - Subtração do dígito médio de cada imagem de treino.
2. **PCA**:
   - Extração dos **auto-dígitos** (eigen-digits).
3. **Análise para diferentes valores de k**: `k = 5, 10, 15, 20`
4. **Classificação**:
   - Projeção no espaço gerado pelas componentes principais.
   - Cálculo da menor distância euclidiana para os vetores médios de cada classe (0 a 9).
5. **Avaliação**:
   - Geração de matriz de confusão 10x10.
   - Cálculo de **acurácia média** e **revocação média**.

---

## ⚙️ Como Executar

### ✅ Pré-requisitos

Instale os pacotes necessários:

```bash
pip install numpy matplotlib Pillow scikit-learn

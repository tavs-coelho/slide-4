# Análise PCA + K-Means no Dataset MNIST 🔢

Análise completa de clustering aplicando PCA (Principal Component Analysis) e K-Means no dataset MNIST de dígitos manuscritos.

## 📋 Sobre o Projeto

Este projeto demonstra técnicas de aprendizado não supervisionado para agrupar dígitos manuscritos do dataset MNIST. Utilizamos redução dimensional com PCA e clustering com K-Means, comparando diferentes configurações e avaliando os resultados com múltiplas métricas. 

### Objetivos

- ✅ Aplicar PCA com diferentes números de componentes (2, 10, 30)
- ✅ Realizar clustering com K-Means (k=10 clusters)
- ✅ Avaliar qualidade dos clusters com Silhouette Score, ARI e NMI
- ✅ Comparar performance entre configurações
- ✅ Gerar 7 visualizações detalhadas para interpretação
- ✅ Identificar padrões e limitações do método

---

## 🚀 Como Rodar no Jupyter Notebook

### Pré-requisitos

- Python 3.8 ou superior
- pip (gerenciador de pacotes Python)
- Jupyter Notebook ou JupyterLab

### Passo 1: Clone ou Baixe o Repositório

**Opção A: Clonar via Git**
```bash
git clone https://github.com/tavs-coelho/slide-4.git
cd slide-4
```

**Opção B: Baixar ZIP**
1. Vá para https://github.com/tavs-coelho/slide-4
2. Clique em "Code" → "Download ZIP"
3. Extraia o arquivo e navegue até a pasta no terminal

### Passo 2: Criar Ambiente Virtual (Recomendado)

**No Windows:**
```bash
# Criar ambiente virtual
python -m venv venv

# Ativar ambiente virtual
venv\Scripts\activate
```

**No Linux/Mac:**
```bash
# Criar ambiente virtual
python3 -m venv venv

# Ativar ambiente virtual
source venv/bin/activate
```

Você verá `(venv)` no início da linha do terminal quando o ambiente estiver ativado.

### Passo 3: Instalar Dependências

Com o ambiente virtual ativado, instale todas as bibliotecas necessárias:

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

**Pacotes que serão instalados:**
- `scikit-learn` - Algoritmos de ML (PCA, K-Means, métricas)
- `matplotlib` - Visualizações
- `seaborn` - Gráficos estatísticos
- `pandas` - Manipulação de dados
- `numpy` - Operações numéricas
- `jupyter` - Ambiente de notebooks
- `notebook` - Interface Jupyter Notebook

⏱️ **Tempo estimado:** 2-5 minutos (dependendo da conexão)

### Passo 4: Iniciar o Jupyter Notebook

```bash
jupyter notebook
```

Isso irá:
1. Iniciar o servidor Jupyter
2. Abrir automaticamente seu navegador em `http://localhost:8888`
3. Mostrar a lista de arquivos do diretório

**Alternativa - JupyterLab (interface mais moderna):**
```bash
jupyter lab
```

### Passo 5: Abrir o Notebook de Análise

Na interface do Jupyter:
1. Clique em `mnist_analysis.ipynb`
2. O notebook será aberto em uma nova aba

### Passo 6: Executar o Notebook

**Opção A: Executar Todas as Células de Uma Vez**
1. No menu superior, clique em **Cell** → **Run All**
2. Aguarde a execução completa (⏱️ ~5-10 minutos)
3. Visualizações aparecerão inline e serão salvas em `results/`

**Opção B: Executar Célula por Célula (Recomendado para Primeira Execução)**
1. Clique na primeira célula
2. Pressione **Shift + Enter** para executar e avançar
3. Observe os outputs e gráficos
4. Leia as explicações em markdown entre as células
5. Continue até a última célula

**Atalhos Úteis:**
- `Shift + Enter` - Executar célula atual e avançar
- `Ctrl + Enter` - Executar célula atual (sem avançar)
- `Alt + Enter` - Executar célula e inserir nova abaixo
- `Esc` - Modo comando (navegar entre células)
- `Enter` - Modo edição (editar célula)

### Passo 7: Verificar Resultados

Após a execução completa:

**Visualizações Inline:**
- Gráficos aparecerão diretamente no notebook

**Arquivos Salvos:**
```bash
results/
├── mnist_samples.png              # Exemplos do dataset
├── variance_explained.png         # Variância explicada por PCA
├── clusters_2d_predicted.png      # Clusters preditos em 2D
├── clusters_2d_true.png           # Labels verdadeiros em 2D
├── confusion_matrices.png         # Matrizes de confusão (2, 10, 30 comp.)
├── metrics_comparison.png         # Comparação de métricas
├── cluster_samples.png            # Exemplos de dígitos por cluster
└── elbow_method.png               # Método do cotovelo para K
```

**Métricas no Notebook:**
- Tabela comparativa de Silhouette Score, ARI, NMI
- Análises textuais e interpretações

---

## 📂 Estrutura do Projeto

```
slide-4/
├── README.md                      # 📖 Este arquivo - Documentação completa
├── requirements.txt               # 📦 Dependências Python
├── mnist_analysis.ipynb           # 📓 Notebook principal com análise
├── .gitignore                     # 🚫 Arquivos ignorados pelo Git
└── results/                       # 📊 Pasta gerada com visualizações
    ├── mnist_samples.png
    ├── variance_explained.png
    ├── clusters_2d_predicted.png
    ├── clusters_2d_true.png
    ├── confusion_matrices.png
    ├── metrics_comparison.png
    ├── cluster_samples.png
    └── elbow_method.png
```

---

## 🔧 Solução de Problemas

### Problema: `ModuleNotFoundError: No module named 'sklearn'`

**Solução:**
```bash
pip install scikit-learn
```

### Problema: `Jupyter command not found`

**Solução:**
```bash
pip install jupyter notebook
```

### Problema: Kernel morto ou travado

**Solução:**
1. No menu: **Kernel** → **Restart & Clear Output**
2. Execute novamente: **Cell** → **Run All**

### Problema: Demora muito para baixar MNIST

**Solução:**
O dataset MNIST (~55MB) é baixado automaticamente na primeira execução. Se houver problemas:
```python
# Na célula de carregamento, adicione timeout:
mnist = fetch_openml('mnist_784', version=1, as_frame=False, 
                     parser='auto', timeout=120)
```

### Problema: Memória insuficiente

**Solução:**
O notebook usa um subset de 10.000 amostras por padrão. Se ainda assim houver problemas:
```python
# Reduza ainda mais o subset:
subset_size = 5000  # Em vez de 10000
```

### Problema: Visualizações não aparecem

**Solução:**
```python
# Adicione no início do notebook:
%matplotlib inline
```

---

## ⚙️ Configurações Opcionais

### Usar Dataset Completo (70k amostras)

No notebook, na seção "2. Carregamento e Preparação dos Dados", comente estas linhas:

```python
# Comentar para usar dataset completo:
# subset_size = 10000
# indices = np.random.RandomState(42).choice(len(X), subset_size, replace=False)
# X = X[indices]
# y = y[indices]
```

⚠️ **Atenção:** Execução levará ~30-60 minutos

### Ajustar Número de Componentes PCA

Na seção "4. PCA + K-Means", modifique:

```python
# Testar outras configurações:
n_components_list = [2, 5, 10, 20, 30, 50]
```

### Mudar Número de Clusters

```python
# Testar outros valores de k:
n_clusters = 15  # Em vez de 10
```

---

## 📊 Resultados Esperados

### Tabela de Métricas (valores aproximados)

| PCA Components | Silhouette Score | ARI   | NMI   | Variância Explicada |
|----------------|------------------|-------|-------|---------------------|
| 2              | ~0.25            | ~0.45 | ~0.50 | ~25%                |
| 10             | ~0.17            | ~0.58 | ~0.63 | ~60%                |
| 30             | ~0.15            | ~0.65 | ~0.68 | ~85%                |

### Principais Insights

✅ **PCA com 30 componentes** oferece melhor concordância com labels verdadeiros

✅ **PCA com 2 componentes** tem melhor Silhouette Score (clusters mais separados geometricamente)

⚠️ **Dígitos confundidos:** 4↔9, 3↔5, 7↔1 são frequentemente agrupados juntos

⚠️ **Limitação do K-Means:** Assume clusters esféricos, não ideal para formas complexas

---

## 📚 Explicação dos Conceitos

### O que é PCA?

**Principal Component Analysis (PCA)** é uma técnica de redução dimensional que:
- Transforma dados de alta dimensão (784 pixels) para baixa dimensão (2, 10, 30)
- Preserva a máxima variância possível
- Remove redundância e ruído

**Por que usar?**
- Reduz custo computacional
- Facilita visualização (2D, 3D)
- Remove features correlacionadas

### O que é K-Means?

**K-Means** é um algoritmo de clustering que:
- Agrupa dados em K clusters
- Minimiza a distância intra-cluster
- Atribui cada ponto ao centroide mais próximo

**Como funciona?**
1. Inicializa K centroides aleatórios
2. Atribui cada ponto ao centroide mais próximo
3. Recalcula centroides como média dos pontos
4. Repete 2-3 até convergência

### Métricas de Avaliação

#### Silhouette Score (-1 a 1)
- Mede coesão intra-cluster e separação inter-cluster
- **> 0.7**: Clustering excelente
- **0.5-0.7**: Clustering razoável
- **< 0.5**: Clustering fraco
- **< 0**: Pontos podem estar no cluster errado

#### Adjusted Rand Index (0 a 1)
- Compara clusters preditos vs labels verdadeiros
- **1.0**: Concordância perfeita
- **0.0**: Concordância ao acaso
- Ajustado por chance (melhor que Rand Index simples)

#### Normalized Mutual Information (0 a 1)
- Mede informação mútua entre clusters e labels
- **1.0**: Informação compartilhada perfeita
- **0.0**: Sem informação compartilhada
- Independente do número de clusters

---

## 🎯 Casos de Uso

Este projeto pode ser adaptado para:

- 📝 **Reconhecimento de caracteres manuscritos**
- 🏷️ **Segmentação de clientes** (substituir MNIST por dados de clientes)
- 🖼️ **Compressão de imagens** (PCA como autoencoder linear)
- 🔍 **Detecção de anomalias** (pontos distantes de todos os clusters)
- 📊 **Análise exploratória** de datasets de alta dimensão

---

## 🛠️ Tecnologias Utilizadas

| Tecnologia | Versão | Uso |
|------------|--------|-----|
| Python | 3.8+ | Linguagem principal |
| scikit-learn | 1.3.0+ | Algoritmos de ML (PCA, K-Means, métricas) |
| matplotlib | 3.7.0+ | Visualizações |
| seaborn | 0.12.0+ | Gráficos estatísticos |
| pandas | 2.0.0+ | Manipulação de dados |
| numpy | 1.24.0+ | Operações numéricas |
| jupyter | 1.0.0+ | Ambiente de notebooks |

---

## 📖 Referências e Leituras Recomendadas

### Papers Fundamentais
- **PCA:** Pearson, K. (1901). "On Lines and Planes of Closest Fit to Systems of Points in Space"
- **K-Means:** MacQueen, J. (1967). "Some methods for classification and analysis of multivariate observations"

### Tutoriais Online
- [Scikit-learn PCA Documentation](https://scikit-learn.org/stable/modules/decomposition.html#pca)
- [Scikit-learn K-Means Documentation](https://scikit-learn.org/stable/modules/clustering.html#k-means)
- [Understanding PCA - StatQuest](https://www.youtube.com/watch?v=FgakZw6K1QQ)
- [K-Means Clustering - StatQuest](https://www.youtube.com/watch?v=4b5d3muPQmA)

### Livros
- "Python Machine Learning" - Sebastian Raschka
- "Hands-On Machine Learning" - Aurélien Géron
- "Pattern Recognition and Machine Learning" - Christopher Bishop

---

## 🤝 Contribuindo

Contribuições são bem-vindas! Para contribuir:

1. Fork o repositório
2. Crie uma branch para sua feature (`git checkout -b feature/NovaFeature`)
3. Commit suas mudanças (`git commit -m 'Adiciona NovaFeature'`)
4. Push para a branch (`git push origin feature/NovaFeature`)
5. Abra um Pull Request

### Ideias para Contribuições

- 🔄 Adicionar outros algoritmos (DBSCAN, GMM, Hierarchical)
- 📊 Implementar t-SNE e UMAP para visualização
- 🧪 Experimentar com datasets diferentes (Fashion-MNIST, CIFAR-10)
- 📈 Adicionar análise de sensibilidade dos hiperparâmetros
- 🎨 Melhorar visualizações com Plotly interativo
- 📝 Adicionar testes unitários

---

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.

---

## 👤 Autor

**Tavs Coelho**

- GitHub: [@tavs-coelho](https://github.com/tavs-coelho)
- Repositório: [slide-4](https://github.com/tavs-coelho/slide-4)

---

## 🙏 Agradecimentos

- Dataset MNIST original: Yann LeCun, Corinna Cortes, Christopher J. C. Burges
- Scikit-learn contributors
- Jupyter Project
- Comunidade Python de Machine Learning

---

## ❓ FAQ (Perguntas Frequentes)

### P: Quanto tempo leva para executar o notebook completo?
**R:** Com subset de 10k amostras: ~5-10 minutos. Com dataset completo (70k): ~30-60 minutos.

### P: Preciso de GPU para rodar?
**R:** Não! Este projeto roda perfeitamente em CPU. PCA e K-Means do scikit-learn são otimizados para CPU.

### P: Posso usar este código comercialmente?
**R:** Sim, sob os termos da licença MIT. Atribuição é apreciada mas não obrigatória.

### P: Como salvo o notebook com os outputs?
**R:** File → Download as → Notebook (.ipynb) ou use `File → Save and Checkpoint`

### P: Posso rodar no Google Colab?
**R:** Sim! Faça upload do `.ipynb` para o Colab. As dependências já estão instaladas no Colab.

### P: O que fazer se o kernel morrer com dataset completo?
**R:** Reduza o subset ou aumente a RAM. Ou use Colab (oferece mais memória gratuitamente).

---

## 📞 Suporte

Encontrou algum problema?

1. **Verifique a seção "Solução de Problemas"** acima
2. **Abra uma Issue** no GitHub com detalhes:
   - Sistema operacional
   - Versão do Python
   - Mensagem de erro completa
   - Passos para reproduzir o problema

---

## 🎓 Para Estudantes

Este projeto é ideal para:
- 📚 Trabalhos acadêmicos de Machine Learning
- 🎯 Portfólio de Data Science
- 🔬 Aprendizado prático de clustering
- 📊 Compreensão de redução dimensional

**Sugestões de Extensões para TCC/Projetos:**
1. Comparar com redes neurais (CNN para classificação)
2. Implementar sistema de reconhecimento em tempo real
3. Analisar outros datasets (Fashion-MNIST, EMNIST)
4. Desenvolver aplicação web com Flask/Streamlit

---

<div align="center">

### ⭐ Se este projeto foi útil, considere dar uma estrela no GitHub!

**Feito com ❤️ e ☕ por Tavs Coelho**

📅 Última atualização: Dezembro 2025

</div>

# Transfer Learning: Pizzas vs Burgers 🍕🍔

![Curso](https://img.shields.io/badge/Curso-Forma%C3%A7%C3%A3o%20Machine%20Learning%20Specialist-blue)
![Linguagem](https://img.shields.io/badge/Linguagem-Python-yellow.svg)
![Framework](https://img.shields.io/badge/Framework-PyTorch-orange.svg)
![Ambiente](https://img.shields.io/badge/Ambiente-Google%20Colab-lightgrey.svg)

---

## 📖 Sobre o Projeto

O objetivo é aplicar a técnica de **Transfer Learning** para construir um classificador de imagens de alta performance. O modelo foi treinado para diferenciar duas classes de alimentos: pizzas e hambúrgueres, utilizando um dataset personalizado.

Este repositório é originado do projeto final do Módulo 2 da **[Formação Machine Learning Specialist](https://www.dio.me/curso-machine-learning)** da [Dio.me](https://www.dio.me/).

---

## 🚀 Tecnologias Utilizadas

Este projeto foi desenvolvido utilizando as seguintes tecnologias:

* **Linguagem:** Python 3
* **Ambiente de Execução:** Google Colab
* **Framework de Deep Learning:** PyTorch
* **Bibliotecas Principais:**
    * `torchvision`: para modelos pré-treinados e transformações de imagem.
    * `Pillow`: para manipulação de imagens.
    * `requests`: para carregar imagens da internet para predição.
    * `Matplotlib` (implícito): para visualização de dados.

---

## 🛠️ Metodologia

O projeto seguiu as etapas clássicas de um pipeline de Visão Computacional com Transfer Learning:

1.  **Preparação dos Dados:** Um dataset personalizado com imagens de pizzas e hambúrgueres foi coletado e organizado em uma estrutura de pastas para treino e validação. Foram aplicadas transformações (`transforms`) para redimensionar, cortar e normalizar as imagens.

2.  **Carregamento do Modelo:** Foi utilizado o modelo **ResNet18**, pré-treinado no gigantesco dataset ImageNet, aproveitando seu conhecimento prévio sobre características visuais universais.

3.  **Transfer Learning (Ajuste Fino):**
    * As camadas convolucionais (extratoras de características) do modelo foram "congeladas".
    * A camada de classificação final, originalmente projetada para 1000 classes, foi substituída por uma nova camada com apenas 2 saídas (pizza e hambúrguer).

4.  **Treinamento:** Apenas a nova camada de classificação foi treinada com o nosso dataset. Essa abordagem reduz drasticamente o custo computacional e o tempo de treinamento, além de evitar overfitting em datasets menores.

5.  **Validação e Predição:** O modelo foi validado a cada época para monitorar a acurácia e a perda em dados não vistos. Ao final, uma função de predição foi criada para classificar novas imagens da internet.

---

## 📈 Resultados

O modelo treinado alcançou uma acurácia final de **95.31%** no conjunto de validação, demonstrando alta capacidade de generalização para diferenciar as duas classes com sucesso.

**Exemplo de Predição em uma nova imagem:**

`Testing image from: https://i.imgur.com/eeDDFhu.jpeg`<BR>
`Prediction: The image is a: pizza`<BR>
`Probability: 99.87%`

---

## ⚙️ Como Executar o Projeto

1.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/grossitech/transfer-learning-pizzas-burgers.git](https://github.com/grossitech/transfer-learning-pizzas-burgers.git)
    ```

2.  **Prepare o Dataset:**
    * Crie seu próprio dataset ou utilize o [/dataset_pizza_burger](./dataset_pizza_burger) que deixei aqui no repositório.
    * Organize as imagens na seguinte estrutura de pastas e **faça o upload para o seu Google Drive**:
        ```
        /meu_dataset
            /treino
                /pizza
                /hamburguer
            /validacao
                /pizza
                /hamburguer
        ```

3.  **Execute no Google Colab:**
    * Abra o arquivo `transfer_learning_pizzas_burgers.ipynb` no Google Colab.
    * **Importante:** Altere as variáveis `train_path` e `validation_path` na Célula 2 para o caminho correto do seu dataset no **seu** Google Drive.
    * Certifique-se de que o ambiente de execução está configurado para usar **GPU** (`Ambiente de execução > Alterar o tipo de ambiente de execução`).
    * Execute as células em ordem.

---

## 👨‍💻 Autor

<img 
  align=left 
  margin=10 
  width=80 
  src="https://avatars.githubusercontent.com/u/188269406"
/>
<p>&nbsp&nbsp&nbsp&nbspLuciano Grossi<br/><br/>
    &nbsp&nbsp&nbsp
    <a href="https://github.com/grossitech"><img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"></a>
    <a href="https://twitter.com/lucianogrossi"><img src="https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white" alt="Twitter"></a>
    <a href="https://www.linkedin.com/in/lucianogrossi"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
</p>

---

## 📜 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.
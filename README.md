# Transfer Learning: Pizzas vs Burgers 🍕🍔

![Course](https://img.shields.io/badge/Course-Machine%20Learning%20Specialist%20Track-blue)
![Language](https://img.shields.io/badge/Language-Python-yellow.svg)
![Framework](https://img.shields.io/badge/Framework-PyTorch-orange.svg)
![Environment](https://img.shields.io/badge/Environment-Google%20Colab-lightgrey.svg)

---

## 📖 About the Project

The goal of this project is to apply the **Transfer Learning** technique to build a high-performance image classifier. The model was trained to differentiate between two classes of food: pizzas and burgers, using a custom dataset.

This repository originates from the final project of Module 2 of the **[Machine Learning Specialist Track](https://www.dio.me/curso-machine-learning)** from [Dio.me](https://www.dio.me/).

Para versão em Português: [clica aqui](./README.ptbr.md).

---

## 📂 Repository Contents

The project's file and folder structure is organized as follows:

* `📁 dataset_pizza_burger/`: The main folder containing the custom image dataset. Its internal structure, ready to be read by frameworks like PyTorch, is:
    * `📁 training/`: Contains the images for **training** the model.
        * `📁 burger/`
        * `📁 pizza/`
    * `📁 validation/`: Contains the images for **validating** the model during each epoch.
        * `📁 burger/`
        * `📁 pizza/`
* `📄 transfer_learning_pizzas_burgers.ipynb`: The main project notebook, developed for Google Colab. It contains all the code, from data preparation to training and prediction.
* `📄 transfer_learning_pizzas_hamburgueres.py`: A Python script, an exported version of the notebook, for execution in non-notebook environments.

---

## 🚀 Technologies Used

This project was developed using the following technologies:

* **Language:** Python 3
* **Execution Environment:** Google Colab
* **Deep Learning Framework:** PyTorch
* **Main Libraries:**
    * `torchvision`: for pre-trained models and image transformations.
    * `Pillow`: for image manipulation.
    * `requests`: to load images from the internet for prediction.
    * `Matplotlib` (implicit): for data visualization.

---

## 🛠️ Methodology

The project followed the classic steps of a Computer Vision pipeline with Transfer Learning:

1.  **Data Preparation:** A custom dataset with images of pizzas and burgers was collected and organized into a folder structure for training and validation. Transformations (`transforms`) were applied to resize, crop, and normalize the images.

2.  **Model Loading:** The **ResNet18** model, pre-trained on the massive ImageNet dataset, was used, leveraging its prior knowledge of universal visual features.

3.  **Transfer Learning (Fine-Tuning):**
    * The convolutional (feature-extracting) layers of the model were "frozen".
    * The final classification layer, originally designed for 1000 classes, was replaced with a new layer with only 2 outputs (pizza and burger).

4.  **Training:** Only the new classification layer was trained with our dataset. This approach drastically reduces computational cost and training time, in addition to preventing overfitting on smaller datasets.

5.  **Validation and Prediction:** The model was validated at each epoch to monitor accuracy and loss on unseen data. Finally, a prediction function was created to classify new images from the internet.

---

## 📈 Results

The trained model achieved a final accuracy of **95.31%** on the validation set, demonstrating a high generalization capability to successfully differentiate between the two classes.

**Example of a prediction on a new image:**

`Testing image from: https://i.imgur.com/eeDDFhu.jpeg`<BR>
`Prediction: The image is a: pizza`<BR>
`Probability: 99.87%`

---

## ⚙️ How to Run the Project

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/grossitech/transfer-learning-pizzas-burgers.git](https://github.com/grossitech/transfer-learning-pizzas-burgers.git)
    ```

2.  **Prepare the Dataset:**
    * Create your own dataset or use the one provided in [/dataset_pizza_burger](./dataset_pizza_burger) here in the repository.
    * Organize the images in the following folder structure and **upload it to your Google Drive**:
        ```
        /my_dataset
            /train
                /pizza
                /hamburger
            /validation
                /pizza
                /hamburger
        ```

3.  **Run in Google Colab:**
    * Open the `transfer_learning_pizzas_burgers.ipynb` file in Google Colab.
    * **Important:** Change the `train_path` and `validation_path` variables in Cell 2 to the correct path of the dataset on **your** Google Drive.
    * Ensure the runtime environment is configured to use a **GPU** (`Runtime > Change runtime type`).
    * Run the cells in order.

---

## 👨‍💻 Author

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

## 📜 License

This project is under the MIT License. See the [LICENSE](LICENSE) file for more details.
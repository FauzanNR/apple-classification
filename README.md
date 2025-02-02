# Apple Classification
This project deliberating YOLOv8 and OpenCV2 to classify apple color. The apple classified into 3 different color, Red, Yellow, and Green.

# Environment Setup

I am using conda 24.11.3 with Linux Mint 21.1 system and YOLOv8 [model](https://yolov8.com/).<br>
Before continuing the process I would like to setting up the environment with conda, but I also put some adjustment if you want to run the program from jupyter. Make suere you have already install the miniconda or anaconda in your machine. By following this step you will creating project environment:
1. Clone the project
    ```bash
    git clone https://github.com/FauzanNR/apple-classification.git
    ```
2. Create conda environment for Yolo detection in normal way

    ```bash
    conda create --name detection-with-yolov8 python=3.11 -y
    ```
    Due to my Linux's storage limit, I would like to make my conda env specific in my project folder. This line will create a hiden folder for the env
   
    ```bash
    conda create --prefix=.conda-detection-with-yolov8 python=3.11 -y
    ```

3. after that, activate the environment

    ```bash
    conda activate detection-with-yolov8
    ```
    Or if you are using Vscode or Jupyter:
    <br>
    install this
    ```bash
    conda install ipykernel
    ```
    from here you can already select the kernel in Vscode.
    <br>
    if you want to use jupyter notebook, install the package inside this environment
    ```bash
    conda install jupyter
    ```
    Then run jupyter with this line. But don't go to fast, we need to install the Ultralytics library first.
    ```bash
    jupyter notebook
    ```
    
4. Install the Ultralytics library with CUDA
    ```bash
    conda install -c pytorch -c nvidia -c conda-forge pytorch torchvision pytorch-cuda=11.8 ultralytics
    ```
    If you are only use CPU:
    ```bash
    conda install -c conda-forge ultralytics
    ```
    and then, in each ```ipynb``` file
    ```python
    model.train(data=data,
            epochs=10, 
            imgsz=640,
            batch=9,
            device=0) <---- REMOVE THE ARGUMENT AND PARAMETER
    ```

5. Move the ipynb files to the project folder ```apple-classification```. The file provide data gathering instruction in it.


<br>

# Dataset used in this project
[Apllecounting2 Computer Vision Project](https://universe.roboflow.com/uttam-ubpdc/apllecounting2-fppyk-obt8f) by [Uttam](https://universe.roboflow.com/uttam-ubpdc)

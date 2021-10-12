## 快速上手

### 环境依赖

> python == 3.8

- torch == 1.8.1
- transformers == 4.7.0
- opt-einsum == 3.3.0
- ujson
- deepke

### 克隆代码
```
git clone git@github.com:zjunlp/DeepKE.git
```
### 使用pip安装

首先创建python虚拟环境，再进入虚拟环境

- 安装依赖: ```pip install -r requirements.txt```

### 使用数据进行训练预测

- 存放数据：在 `data` 文件夹下存放训练数据。模型采用的数据集是[DocRED](https://github.com/thunlp/DocRED/tree/master/)。

- DocRED包含以下数据：

  - `dev.json`：验证集

  - `rel_info.json`：关系集

  - `rel2id.json`：关系标签到ID的映射

  - `test.json`：测试集

  - `train_annotated.json`：训练集

  - `train_distant.json`: 由于文件太大，请自行从[Google Drive](https://drive.google.com/drive/folders/1c5-0YwnoJx8NS6CV2f-NoTHR__BdkNqw)上下载到`data/`目录下

- 开始训练：模型加载和保存位置以及配置可以在conf的`.yaml`文件中修改
  
  - 在数据集DocRED中训练：`python run.py` 

  - 训练好的模型保存在根目录下

- 从上次训练的模型开始训练：设置`.yaml`中的train_from_saved_model为上次保存模型的路径

- 每次训练的日志保存路径默认保存在根目录，可以通过`.yaml`中的log_dir来配置

- 进行预测： `python predict.py`

  - 预测生成的`result.json`保存在根目录


## 模型内容
DocuNet

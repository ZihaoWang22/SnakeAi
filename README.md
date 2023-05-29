# SnakeAi

##### 文件及结构说明
```bash
├───main
│   ├───logs
│   ├───sounds
│   ├───trained_models_cnn
│   ├───trained_models_mlp
│   ├───scripts
│   └───models
├───utils
│   └───scripts
```

###### 模型部分 ./main
ppo_snake_4875000_steps_circle.zip  初始策略：转圈圈模型  
ppo_snake_final_mlp.zip  1.0策略：1亿次训练  
ppo_snake_final_cnn.zip  2.0策略：1亿次训练  
ppo_snake_constant_seed.zip  最终策略：固定随机种子-2亿次训练  

###### 创建 conda 环境，将其命名为 SnakeAI，Python 版本 3.8.16
```python
conda create -n SnakeAI python=3.8.16
conda activate SnakeAI
```
###### [可选] 使用 GPU 训练需要手动安装完整版 PyTorch
```python
conda install pytorch=2.0.0 torchvision pytorch-cuda=11.8 -c pytorch -c nvidia
```
###### [可选] 运行程序脚本测试 PyTorch 是否能成功调用 GPU
```python
python .\utils\check_gpu_status.py
```
###### 安装外部代码库
pip install -r requirements.txt

##### 模型训练命令
```cmd
cd ./main
```
2. mlp  一亿次
```python
python train_mlp.py
```
3. cnn  一亿次
```python
python train_cnn.py
```
4. constant seed 2亿次训练
```python
python train_cnn_conseed.py
```

##### 模型展示命令部分
```cmd
cd ./main
```
1. 转圈圈
```python
python test_circle.py
```
2. mlp  一亿次
```python
python test_mlp.py
```
3. cnn  一亿次
```python
python test_cnn.py
```
4. constant seed 2亿次训练
```python
python test_cnn_conseed.py
```

# Norm-Aware Embedding for Efﬁcient Person Search

This repository hosts our code for our paper [Norm-Aware Embedding for Efﬁcient Person Search](http://openaccess.thecvf.com/content_CVPR_2020/papers/Chen_Norm-Aware_Embedding_for_Efficient_Person_Search_CVPR_2020_paper.pdf). 



## Preparation

1. Clone this repo

   ```bash
   https://github.com/DeanChan/NAE4PS.git && cd NAE4PS
   ```

2. Build environment with [conda](https://docs.anaconda.com/anaconda/install/linux/)

   ```bash
   conda env create --prefix <your_conda_env_path> -f environment.yml
   ```



## Experiments

1.  Download [CUHK-SYSU](https://github.com/ShuangLI59/person_search) and [PRW](https://github.com/liangzheng06/PRW-baseline) to `data/`

2. Download the trained model
   ```bash
   mkdir logs && wget https://github.com/DeanChan/NAE4PS/releases/download/v0.0.0/logs.tar.gz -P logs/ 
   cd logs && tar xvzf logs.tar.gz
   ```

3. Test
   ```bash
   CUDA_VISIBLE_DEVICES=0 python scripts/test_NAE.py -p logs/prw/Dec12_18-53-12_xuyue-PC
   ```
   
4. Train
   ```bash
   CUDA_VISIBLE_DEVICES=0 python scripts/train_NAE.py --debug --lr_warm_up -p ./logs/prw/ --batch_size 3 --nw 5 --w_RCNN_loss_bbox 10.0 --epochs 22 --lr 0.003
   ```
python setup.py install [--cuda_ext] [--cpp_ext]


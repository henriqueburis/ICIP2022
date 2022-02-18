# MbDML - MIXUP-BASED DEEP METRIC LEARNING FOR WEAKLY SUPERVISED LEARNING

- https://github.com/LukeDitria/OpenGAN
- https://github.com/facebookresearch/mixup-cifar10
- https://kevinmusgrave.github.io/pytorch-metric-learning/

## Code organization

- `train_MbDML1-NNGK_Mixup.py`: Esta abordagem chamada $NNGK+Mixup$ é uma simples combinação entre as funções de perdas das abordagens originais (NNGK e Mixup para compor a função de perda final desta abordagem. Essa  combinação de funções de perdas é utilizada durante o processo de treinamento, calculando-se a perda de ambas abordagens originais em cada lote e a retropropagação do erro é realizado na arquitetura CNN levando-se em consideração a função final combinada definida pela soma dos valores das funções de perda. 
- `train_MbDML2_MixupNNGK.py` : trai.
- `train_MbDML3_MixupNNGK_NNGK.py` : train.
- `train_NNGK.py` : nngk original.


## Requirements and Installation
- Python version 3.6
- A [PyTorch installation](http://pytorch.org/)
- A [Pytorch-Metric-Learning installation](https://kevinmusgrave.github.io/pytorch-metric-learning/#installation)


## MbDML
you can now run the python scrypt with the following command:

```sh
python3 train_MbDML1-NNGK_Mixup.py --max_epochs=200 --name "CIFAR10-MbDML1-NNGK_Mixup" --scale_mixup 2 --alpha 1 --beta 1 --data_dir datasets/CIFAR100K10/train --test datasets/CIFAR100K10/Test --save_dir results/neighbour=200 --num_classes 100 --tsne_graph False --im_ext png --gpu_id 0 --input_size 32

```

```sh
python3 train_MbDML2_MixupNNGK.py --max_epochs=200 --name "CIFAR10-MbDML2_MixupNNGK" --scale_mixup 2 --alpha 1 --alpha 0 --data_dir datasets/CIFAR100K10/train --test datasets/CIFAR100K10/Test --save_dir results/neighbour=200 --num_classes 100 --tsne_graph False --im_ext png --gpu_id 0 --input_size 32

```

```sh
python3 train_MbDML3_MixupNNGK_NNGK.py --max_epochs=200 --name "CIFAR10-MbDML3_MixupNNGK_NNGK" --scale_mixup 2 --alpha 1 --beta 1 --data_dir datasets/CIFAR100K10/train --test datasets/CIFAR100K10/Test --save_dir results/neighbour=200 --num_classes 100 --tsne_graph False --im_ext png --gpu_id 0 --input_size 32

```

## Accuracy Test .....corrigindo.

CIFAR100 - Train    |  CIFAR100 - Test
:-------------------------:|:-------------------------:
![](https://github.com/henriqueburis/Weekly-Learning_DML-Mixup_GAN/blob/main/figure/CIFAR100%20-%20XL10%25%20ACC%20-%20accuracy.png) |  ![](https://github.com/henriqueburis/Weekly-Learning_DML-Mixup_GAN/blob/main/figure/CIFAR100%20-%20XL10%25%20ACC%20-%20test.png) 


## Comparison
![N|Solid](https://github.com/henriqueburis/ICIP2022/blob/main/fig/Mean%20accuracies.PNG?raw=true)

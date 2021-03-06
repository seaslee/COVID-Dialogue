# COVID-19 Dialogue Generation Model

## Introduction

This is a pytorch implementation of the Chinese COVID Dialogue Generation Model.

# Environment

The code is based on python 3.7.3 and pytorch 1.4.0. The code is tested on GeForce RTX 2080Ti.

## Run

In training:

`LOAD_DIR` is the directory that you store your trained model weights

`DECODER_PATH` is the file path of the trained model weight

Before running the code, download the pre-trained [encoder](https://drive.google.com/file/d/13GnYf6pj0wD7XNWrazMnoQXgUki4Tybp/view?usp=sharing) and [decoder](https://drive.google.com/file/d/1qaAUCV2alrYVrSUyM2PCmYdRuAip_DSP/view?usp=sharing) model weight.

> You can also directly download the final trained decoder model [here](https://drive.google.com/file/d/1PDEFawj3aPr-8bEA4DjhSDhqMqOuZslR/view?usp=sharing)



1. First preprocess the dataset and split the data to train, validate and test sets:

   ```shell
   $ python preprocess.py
   ```

2. Train the dialogue generation model:

   ``` shell
   $ python train.py --load_dir ${LOAD_DIR}
   ```

3. Evaluation the trained dialogue generation model:

   ```shell
   $ python calculate_perplexity.py --decoder_path ${DECODER_PATH}
   ```

4. Generate responses using the trained dialogue generation model:

   ```shell
   $ python sample_generate.py --decoder_path ${DECODER_PATH}
   ```

The details of the model are provided in this [paper draft](https://github.com/pengtaoxie/pengtaoxie.github.io/blob/master/coviddiag-model.pdf)

If you find the code useful, please cite:

      @article{zeng2020coviddialogmodel,
         title={Develop Medical Dialogue Systems for COVID-19},
         author={Zeng, Guangtao and Wu, Qingyang and Zhang, Yichen and Yu, Zhou and Xing, Eric and Xie, Pengtao},
         journal={ https://github.com/UCSD-AI4H/COVID-Dialogue}, 
         year={2020}
      }



Generative Adversarial Network in Tensorflow
============================================

Tensorflow implementation of [Generative Adversarial Network](https://arxiv.org/abs/1406.2661) MNIST handwritten digit dataset.

Prerequisites
-------------

This code requires [Tensorflow](https://www.tensorflow.org/). The MNIST dataset is stored in the 'MNIST_data' directory. The files will be automatically downloaded if the dataset does not exist.
    
If you want to use `--show_progress True` option, you need to install python package `progress`.

    $ pip install progress
    
Usage
-----

To train a GAN with z dimension 100, run the following command:

    $ python main.py --z_dim 100

To see all training options, run:

    $ python main.py --help

which will print:

    usage: main.py [-h] [--input_dim INPUT_DIM] [--z_dim Z_DIM]
               [--d_update D_UPDATE] [--batch_size BATCH_SIZE]
               [--nepoch NEPOCH] [--lr LR] [--max_grad_norm MAX_GRAD_NORM]
               [--checkpoint_dir CHECKPOINT_DIR] [--image_dir IMAGE_DIR]
               [--use_adam [USE_ADAM]] [--nouse_adam]
               [--show_progress [SHOW_PROGRESS]] [--noshow_progress]

    optional arguments:
      -h, --help            show this help message and exit
      --input_dim INPUT_DIM
                            dimension of the discriminator input placeholder [784]
      --z_dim Z_DIM         dimension of the generator input noise variable z
                            [100]
      --d_update D_UPDATE   update the discriminator weights [d_update] times per
                            generator update [5]
      --batch_size BATCH_SIZE
                            batch size to use during training [128]
      --nepoch NEPOCH       number of epochs to use during training [100]
      --lr LR               learning rate of the optimizer to use during training
                            [0.001]
      --max_grad_norm MAX_GRAD_NORM
                            clip L2-norm of gradients to this threshold [40]
      --checkpoint_dir CHECKPOINT_DIR
                            checkpoint directory [./checkpoints]
      --image_dir IMAGE_DIR
                            directory to save generated images to [./images]
      --use_adam [USE_ADAM]
                            if True, use Adam optimizer; otherwise, use SGD [True]
      --nouse_adam
      --show_progress [SHOW_PROGRESS]
                            print progress [False]
      --noshow_progress

(Optional) If you want to see a progress bar, install `progress` with `pip`:

    $ pip install progress
    $ python main.py --z_dim --show_progress True


Acknowledgements
----------------

Majority of the source code in GAN.py is from: Agustinus Kristiadi / [@wiseodd](http://wiseodd.github.io/).

This repo is a modular version of Agustinus Kristiadi's implementation of GAN.
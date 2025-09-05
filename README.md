<div align="center">

# The residual generator: An improved divergence minimization framework for GAN

<a href="https://pytorch.org/get-started/locally/"><img alt="PyTorch" src="https://img.shields.io/badge/PyTorch-ee4c2c?logo=pytorch&logoColor=white"></a>
<a href="https://pytorchlightning.ai/"><img alt="Lightning" src="https://img.shields.io/badge/-Lightning-792ee5?logo=pytorchlightning&logoColor=white"></a>
<a href="https://hydra.cc/"><img alt="Config: Hydra" src="https://img.shields.io/badge/Config-Hydra-89b8cd"></a>
<a href="https://github.com/ashleve/lightning-hydra-template"><img alt="Template" src="https://img.shields.io/badge/-Lightning--Hydra--Template-017F2F?style=flat&logo=github&labelColor=gray"></a><br>

</div>

## Abstract
>GAN is a generative modelling framework which has been proven as able to minimise various types of divergence measures under an optimal discriminator. However, there is a gap between the loss function of GAN used in theory and in practice. In theory, the proof of the Jensen divergence minimisation involves the min-max criterion, but in practice the non-saturating criterion is instead used to avoid gradient vanishing. We argue that the formulation of divergence minimization via GAN is biased and may yield a poor convergence of the algorithm. In this paper, we propose the Residual Generator for GAN (Rg-GAN), which is inspired by the closed-loop control theory, to bridge the gap between theory and practice. Rg-GAN minimizes the residual between the loss of the generated data to be real and the loss of the generated data to be fake from the perspective of the discriminator. In this setting, the loss terms of the generator depend only on the generated data and therefore contribute to the optimisation of the model. We formulate the residual generator for standard GAN and least-squares GAN and show that they are equivalent to the minimisation of reverse-KL divergence and a novel instance of f-divergence, respectively. Furthermore, we prove that Rg-GAN can be reduced to Integral Probability Metrics (IPMs) GANs (e.g., Wasserstein GAN) and bridge the gap between IPMs and f-divergence. Additionally, we further improve on Rg-GAN by proposing a loss function for the discriminator that has a better discrimination ability. Experiments on synthetic and natural images data sets show that Rg-GAN is robust to mode collapse, and improves the generation quality of GAN in terms of FID and IS scores.

## Getting started
After cloning this repo, install dependencies
```yaml
# [OPTIONAL] create conda environment
conda create --name Rg-GAN-py38 python=3.8
conda activate abGAN-py38

# install requirements
pip install -r requirements.txt
```

Train model with experiment configuration
```yaml
# default
python run.py experiment=train_cifar10_gan.yaml

# train on CPU
python run.py experiment=train_cifar10_gan.yaml trainer.gpus=0

# train on GPU
python run.py experiment=train_cifar10_gan.yaml trainer.gpus=1
```

You can override any parameter from command line like this.
```yaml
python run.py experiment=train_cifar10_gan.yaml trainer.max_epochs=200 datamodule.batch_size=32
```
## 📜  License

This project is licensed under the Apache 2.0 License – see the [LICENSE](LICENSE) file for details. You are free to use, modify, and distribute Rg-GAN in either commercial or academic projects under the terms of this license.

## 📚 Citation

If you use **Rg-GAN** in your research or applications, please consider citing our paper:

```bibtex
@article{GNANHA2022108222,
title = {The residual generator: An improved divergence minimization framework for GAN},
journal = {Pattern Recognition},
volume = {121},
pages = {108222},
year = {2022},
issn = {0031-3203},
doi = {https://doi.org/10.1016/j.patcog.2021.108222},
url = {https://www.sciencedirect.com/science/article/pii/S0031320321004039},
author = {Aurele Tohokantche Gnanha and Wenming Cao and Xudong Mao and Si Wu and Hau-San Wong and Qing Li},
keywords = {Generative adversarial networks, Image synthesis, Deep learning}
}
```

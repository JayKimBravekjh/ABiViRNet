# ABiViRNet: Attention Bidirectional Video Recurrent Net for video captioning


This repository contains the code for building a system similar to the
one from the work [Video Description using Bidirectional Recurrent Neural Networks](https://arxiv.org/abs/1604.03390), 
presented at the [International Conference of Artificial Neural Networks (ICANN'16)](http://icann2016.org/). 
With this module, you can replicate our experiments and easily deploy new models. ABiViRNet is built upon our fork of 
[Keras](https://github.com/MarcBS/keras) framework and tested for the [Theano](http://deeplearning.net/software/theano) and [Tensorflow](https://www.tensorflow.org/) backends.

## Features: 

 * Attention model over the input sequence of frames
 * Peeked decoder LSTM: The previously generated word is an input of the current LSTM timestep
 * MLPs for initializing the LSTM hidden and memory state
 * Beam search decoding

## Architecture

![ICANN_model](./docs/model.png)

## Requirements

ABiViRNet requires the following libraries:

 - [Our version of Keras](https://github.com/MarcBS/keras) v1.2.1
 - [Multimodal Keras Wrapper](https://github.com/MarcBS/multimodal_keras_wrapper) v0.7 
 - [Coco-caption evaluation package](https://github.com/lvapeab/coco-caption/tree/master/pycocoevalcap/)

## Instructions:

Assuming you have a dataset and features extracted from the video frames:
 
 1) Prepare data:
 
   ``
 python data_engine/subsample_frames_features.py
 ``
 
  ``
 python data_engine/generate_features_lists.py
 ``
 
  ``
 python data_engine/generate_descriptions_lists.py
 ``

See [data_engine/README.md](data_engine/README.md) for detailed information.

2) Prepare the inputs/outputs of your model in `data_engine/prepare_data.py`
  
3) Set a model configuration in  `config.py` 
 
4) Train!:

  ``
 python main.py
 ``

## Citation

If you use this code for any purpose, please, do not forget to cite the following paper:
```
Peris, Á., Bolanos, M., Radeva, P., & Casacuberta, F. (2016, September). Video description using bidirectional recurrent neural networks. In International Conference on Artificial Neural Networks (pp. 3-11). Springer International Publishing.
```
Bibtex version:

```
@inproceedings{peris2016video,
  title={Video description using bidirectional recurrent neural networks},
  author={Peris, {\'A}lvaro and Bolanos, Marc and Radeva, Petia and Casacuberta, Francisco},
  booktitle={International Conference on Artificial Neural Networks},
  pages={3--11},
  year={2016},
  organization={Springer}
}
```

## About

Joint collaboration between the [Computer Vision at the University of Barcelona (CVUB)](http://www.ub.edu/cvub/) group at [Universitat de Barcelona](www.ub.edu)-[CVC](http://www.cvc.uab.es) and the [PRHLT Research Center](https://www.prhlt.upv.es) at [Universitat Politècnica de València](https://www.upv.es).


## Contact

Álvaro Peris ([web page](http://lvapeab.github.io/)): lvapeab@prhlt.upv.es 

Marc Bolaños ([web page](http://www.ub.edu/cvub/marcbolanos/)): marc.bolanos@ub.edu

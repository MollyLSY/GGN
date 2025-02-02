# Graph‐generative neural network for EEG‐based epileptic seizure detection via discovery of dynamic brain functional connectivity

GGN is a generative deep learning model for epilepsy seizure classification and detecting the abnormal functional connectivities when seizure attacks.

If any code or the datasets are useful in your research, please cite the following paper:

```
@article{li2022graph,
  title={Graph-generative neural network for EEG-based epileptic seizure detection via discovery of dynamic brain functional connectivity},
  author={Li, Zhengdao and Hwang, Kai and Li, Keqin and Wu, Jie and Ji, Tongkai},
  journal={Scientific Reports},
  volume={12},
  number={1},
  pages={18998},
  year={2022},
  publisher={Nature Publishing Group UK London}
}


```

or 

```
Li, Z., Hwang, K., Li, K. et al. Graph-generative neural network for EEG-based epileptic seizure detection via discovery of dynamic brain functional connectivity. Sci Rep 12, 18998 (2022).
```

--- 

## Preparation for dataset. 


1. According to the Policy from TUH, you must apply dataset TUSZ v1.5.2 from https://isip.piconepress.com/projects/tuh_eeg/
  (If you cannot download, you can email me.)
2. Preprocess the raw data following the benchmark setting from IBM: https://github.com/IBM/seizure-type-classification-tuh
3. Composite features from different frequencies following our paper (Supplementary).

---



## Testing via trained model.

the shuffled_index.npy stored the indices of training samples and testing samples of the best_model.pth (reported in the paper).

1. config the data path and trained model path in the file testing.sh.
1. `sh testing.sh`
1. use `sh testing.sh kill`, to kill the running process.

## Training GGN

1. config the data path and trained model path in the file training.sh
2. `sh training.sh`
3. or you could reset the hyperparameters in training.sh or just set in args, e.g.,`
sh training.sh data_path=xxx lr=0.00005`
1. use `sh training.sh kill`, to kill the running process.

## Training compared models

To train compared models, chanage the `--task=ggn` to following settings:


1. `sh training.sh --task=cnnnet`, training CNN based model.
1. `sh training.sh --task=gnnnet`, training GNN based model.
1. `sh training.sh --task=transformer`, training Transformer based model.


## Turn on debug log mode
to print more logs, set `--debug` in the command args.

## Q&A

**Message me if you have any questions: zhengdaoli (at) link (dot) cuhk (dot) edu.cn**

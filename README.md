


# Requirement
- python 3.4+
- pytorch 0.2.0
- tqdm
- numpy


# Usage

### 0) Download the data.
Link to all Datasets Coming Soon (most are from http://mulan.sourceforge.net/datasets-mlc.html)

### 1) Preprocess the data for a specific dataset
```bash
python preprocess.py -train_src data/reuters/train_inputs.txt -train_tgt data/reuters/train_labels.txt -valid_src data/reuters/valid_inputs.txt -valid_tgt data/reuters/valid_labels.txt -test_src data/reuters/test_inputs.txt -test_tgt data/reuters/test_labels.txt -save_data data/reuters/train_valid_test.pt -max_seq_len 300
```

### 2) Train and Test the model (training script contains the validation and testing code)
```bash
python train.py -dataset reuters -batch_size 32 -d_model 512 -d_inner_hid 512 -n_layers_enc 2 -n_layers_dec 2 -n_head 4 -epoch 50 -dropout 0.2 -dec_dropout 0.2 -lr 0.0002 -encoder 'graph' -decoder 'graph' -label_mask 'prior'
```


# Acknowledgement
Much of this code was adapted from @jadore801120

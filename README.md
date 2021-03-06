# BERT4Rec_pytorch

BERT4Rec in Pytorch   
https://arxiv.org/abs/1904.06690

### Model structure
```sh
BERT4REC(
  (model): BERT(
    (embedding): BERTEmbeddings(
      (token_embeddings): Embedding(3708, 256, padding_idx=0)
      (position_embeddings): Embedding(100, 256)
      (segment_embeddings): Embedding(3, 256, padding_idx=0)
      (layer_norm): LayerNorm((256,), eps=1e-06, elementwise_affine=True)
      (dropout): Dropout(p=0.1, inplace=False)
    )
    (transformer_encoders): ModuleList(
      (0): TransformerEncoder(
        (attention): MultiHeadedAttention(
          (query_linear): Linear(in_features=256, out_features=256, bias=True)
          (key_linear): Linear(in_features=256, out_features=256, bias=True)
          (value_linear): Linear(in_features=256, out_features=256, bias=True)
          (dropout): Dropout(p=0.1, inplace=False)
          (output_linear): Linear(in_features=256, out_features=256, bias=True)
        )
        (input_sublayer): SublayerConnection(
          (layer_norm): LayerNorm((256,), eps=1e-06, elementwise_affine=True)
          (dropout): Dropout(p=0.1, inplace=False)
        )
        (feed_forward): PositionwiseFeedForward(
          (feed_forward_1): Linear(in_features=256, out_features=1024, bias=True)
          (feed_forward_2): Linear(in_features=1024, out_features=256, bias=True)
          (dropout): Dropout(p=0.1, inplace=False)
          (activation): GELU()
        )
        (output_sublayer): SublayerConnection(
          (layer_norm): LayerNorm((256,), eps=1e-06, elementwise_affine=True)
          (dropout): Dropout(p=0.1, inplace=False)
        )
      )
      (1): TransformerEncoder(
        (attention): MultiHeadedAttention(
          (query_linear): Linear(in_features=256, out_features=256, bias=True)
          (key_linear): Linear(in_features=256, out_features=256, bias=True)
          (value_linear): Linear(in_features=256, out_features=256, bias=True)
          (dropout): Dropout(p=0.1, inplace=False)
          (output_linear): Linear(in_features=256, out_features=256, bias=True)
        )
        (input_sublayer): SublayerConnection(
          (layer_norm): LayerNorm((256,), eps=1e-06, elementwise_affine=True)
          (dropout): Dropout(p=0.1, inplace=False)
        )
        (feed_forward): PositionwiseFeedForward(
          (feed_forward_1): Linear(in_features=256, out_features=1024, bias=True)
          (feed_forward_2): Linear(in_features=1024, out_features=256, bias=True)
          (dropout): Dropout(p=0.1, inplace=False)
          (activation): GELU()
        )
        (output_sublayer): SublayerConnection(
          (layer_norm): LayerNorm((256,), eps=1e-06, elementwise_affine=True)
          (dropout): Dropout(p=0.1, inplace=False)
        )
      )
    )
  )
  (out): Linear(in_features=256, out_features=3708, bias=True)
```

### Project structure
```sh
????????? data
???   ????????? dataset.py
???   ????????? __init__.py
???   ????????? ml-1m
???       ????????? movies.dat
???       ????????? ratings.dat
???       ????????? README
???       ????????? users.dat
????????? datamodule.py
????????? lit_model.py
????????? model
???   ????????? bert.py
???   ????????? __init__.py
????????? README.md
????????? requirements.txt
????????? trainer.py
```

- dataset.py : ????????? ?????????, Dataset ??????

- datamodule.py : DataModule ??????, DataLoader ??????

- bert.py : BERT ?????? ??????

- lit_model.py : ?????? ??? ????????? ????????? Module ??????

- trainer.py : Trainer ??????

### Requirements
```
numpy==1.22.4
pandas==1.4.2
pytorch_lightning==1.6.4
torch==1.11.0+cu113
torchmetrics==0.9.1
```


### How to run
```
python trainer.py
```
### Check log data
```
tensorboard --logdir=training
```
### Update   


- 2022-05-31 : ?????? ?????? ??????
- 2022-06-03 : ?????? ????????????
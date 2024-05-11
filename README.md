Training and evaluation
Training

```
# Singview SwinT
python train.py --data-dir your-data-directory --data data_configs/ddsm2.yaml -b 4 -j 16 --epochs 41 --eval-frequent 2 -opt adam --lr 1e-5 --model fasterrcnn_swint_fpn_sigmoid --imgsz 1000 1500 --loss mix  --name your-output-directory

# Singview Resnet50
python train.py --data-dir your-data-directory --data data_configs/ddsm2.yaml -b 4 -j 16 --epochs 41 --eval-frequent 2 -opt adam --lr 1e-5 --model fasterrcnn_resnet50_fpn_sigmoid --imgsz 1000 1500 --loss mix  --name your-output-directory

# Multiview SwinT
python train_multi.py --data data_configs/vindr_mamo_2.yaml --data-dir your-data-directory -b 4  -j 16 -opt adam --lr 1e-5  --eval-frequent 2 --epochs 41 --model multiview_detector_swint   --imgsz 500 1200 --loss mix  --name your-output-directory

# Multiview Resnet50
python train_multi.py --data data_configs/vindr_mamo_2.yaml --data-dir your-data-directory -b 4  -j 16 -opt adam --lr 1e-5  --eval-frequent 2 --epochs 41 --model multiview_detector   --imgsz 500 1200 --loss mix  --name your-output-directory

```
### Evaluation

```
# Singview SwinT
python eval.py --data-dir your-data-directory --data data_configs/ddsm2.yaml  -b 1 -w 16  --imgsz 1000 1500 -m fasterrcnn_swint_fpn_sigmoid -mw model-weight

# Singview Resnet50
python eval.py --data-dir your-data-directory --data data_configs/ddsm2.yaml  -b 1 -w 16  --imgsz 1000 1500 -m fasterrcnn_resnet50_fpn_sigmoid -mw model-weight

# Multiview SwinT
python eval_multi.py --data data_configs/vindr_mamo_2.yaml --data-dir your-data-directory -b 1  -w 16 --imgsz 500 1200 -m multiview_detector_swint -mw model-weight

# Multiview Resnet50
python eval_multi.py --data data_configs/vindr_mamo_2.yaml --data-dir your-data-directory -b 1  -w 16 --imgsz 500 1200 -m multiview_detector -mw model-weight

```

 

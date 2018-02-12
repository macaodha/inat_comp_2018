# iNaturalist Competition Training Code  
This code finetunes an Inception V3 model on the iNaturalist 2018 competition [dataset](https://github.com/visipedia/inat_comp).


### Training
The network was trained on Ubuntu 16.04 using PyTorch 0.3.0. Each training epoch took about 1.5 hours using a GTX Titan X.  
The links for the raw data are available [here](https://github.com/visipedia/inat_comp).
We also provide a pretrained model that can be downloaded from [here](http://vision.caltech.edu/~macaodha/inat2018/iNat_2018_InceptionV3.pth.tar).
Every epoch the code will save a checkpoint and also save the current best model according to validation accuracy.


### Results
Training for about 75 epochs results in a top one accuracy of 60.20% and top three of 77.91% on the validation set.



### Submission File
By setting the following flags it's possible to generate a submission file for the competition.
```python
    evaluate = True
    save_preds = True
    resume = 'model_path/iNat_2018_InceptionV3.pth.tar'  # path to trained model
    val_file = 'ann_path/test2018.json'                  # path to test file
    data_root = 'data_path/inat2018/images/'             # path to test images
    op_file_name = 'inat2018_test_preds.csv'             # submission filename
```

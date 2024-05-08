# YOLOv9_training

### Training log
                 from  n    params  module                                  arguments                     
          0                -1  1      1856  models.common.Conv                      [3, 64, 3, 2]                 
          1                -1  1     73984  models.common.Conv                      [64, 128, 3, 2]               
          2                -1  1    212864  models.common.RepNCSPELAN4              [128, 256, 128, 64, 1]        
          3                -1  1    164352  models.common.ADown                     [256, 256]                    
          4                -1  1    847616  models.common.RepNCSPELAN4              [256, 512, 256, 128, 1]       
          5                -1  1    656384  models.common.ADown                     [512, 512]                    
          6                -1  1   2857472  models.common.RepNCSPELAN4              [512, 512, 512, 256, 1]       
          7                -1  1    656384  models.common.ADown                     [512, 512]                    
          8                -1  1   2857472  models.common.RepNCSPELAN4              [512, 512, 512, 256, 1]       
          9                -1  1    656896  models.common.SPPELAN                   [512, 512, 256]               
         10                -1  1         0  torch.nn.modules.upsampling.Upsample    [None, 2, 'nearest']          
         11           [-1, 6]  1         0  models.common.Concat                    [1]                           
         12                -1  1   3119616  models.common.RepNCSPELAN4              [1024, 512, 512, 256, 1]      
         13                -1  1         0  torch.nn.modules.upsampling.Upsample    [None, 2, 'nearest']          
         14           [-1, 4]  1         0  models.common.Concat                    [1]                           
         15                -1  1    912640  models.common.RepNCSPELAN4              [1024, 256, 256, 128, 1]      
         16                -1  1    164352  models.common.ADown                     [256, 256]                    
         17          [-1, 12]  1         0  models.common.Concat                    [1]                           
         18                -1  1   2988544  models.common.RepNCSPELAN4              [768, 512, 512, 256, 1]       
         19                -1  1    656384  models.common.ADown                     [512, 512]                    
         20           [-1, 9]  1         0  models.common.Concat                    [1]                           
         21                -1  1   3119616  models.common.RepNCSPELAN4              [1024, 512, 512, 256, 1]      
         22      [15, 18, 21]  1   5491411  models.yolo.DDetect                     [1, [256, 512, 512]]          
        gelan-c summary: 621 layers, 25437843 parameters, 25437827 gradients, 103.2 GFLOPs

      Transferred 931/937 items from /content/weights/gelan-c.pt
      AMP: checks passed ✅
      optimizer: SGD(lr=0.01) with parameter groups 154 weight(decay=0.0), 161 weight(decay=0.0005), 160 bias
      albumentations: Blur(p=0.01, blur_limit=(3, 7)), MedianBlur(p=0.01, blur_limit=(3, 7)), ToGray(p=0.01), CLAHE(p=0.01, clip_limit=(1, 4.0), tile_grid_size=(8, 8))
      train: Scanning /content/yolov9/data/numberplate/custom.cache... 120 images, 3 backgrounds, 0 corrupt: 100% 120/120 [00:00<?, ?it/s]
      Plotting labels to runs/train/exp5/labels.jpg... 
      Image sizes 640 train, 640 val
      Using 2 dataloader workers
      Logging results to runs/train/exp5
      Starting training for 25 epochs...
      /usr/lib/python3.10/multiprocessing/popen_fork.py:66: RuntimeWarning: os.fork() was called. os.fork() is incompatible with multithreaded code, and JAX is multithreaded, so this will likely lead to a deadlock.
        self.pid = os.fork()

      Epoch    GPU_mem   box_loss   cls_loss   dfl_loss  Instances       Size
       0/24      11.2G      2.061      5.557       1.72         29        640: 100% 8/8 [02:12<00:00, 16.62s/it]
                 Class     Images  Instances          P          R      mAP50   mAP50-95: 100% 1/1 [00:02<00:00,  2.29s/it]
                   all         15         35   0.000222     0.0286   0.000115   1.15e-05

      Epoch    GPU_mem   box_loss   cls_loss   dfl_loss  Instances       Size
       1/24      11.2G      1.561      3.744      1.339         43        640: 100% 8/8 [02:00<00:00, 15.01s/it]
                 Class     Images  Instances          P          R      mAP50   mAP50-95: 100% 1/1 [00:00<00:00,  5.52it/s]
                   all         15         35      0.651      0.514      0.514      0.346

      Epoch    GPU_mem   box_loss   cls_loss   dfl_loss  Instances       Size
       2/24      11.2G      1.236      1.551      1.073         38        640: 100% 8/8 [01:48<00:00, 13.53s/it]
                 Class     Images  Instances          P          R      mAP50   mAP50-95: 100% 1/1 [00:00<00:00,  5.58it/s]
                   all         15         35      0.928      0.629      0.716      0.468

      Epoch    GPU_mem   box_loss   cls_loss   dfl_loss  Instances       Size
       3/24      11.2G      1.292      1.386      1.073         37        640: 100% 8/8 [02:02<00:00, 15.33s/it]
                 Class     Images  Instances          P          R      mAP50   mAP50-95: 100% 1/1 [00:00<00:00,  3.84it/s]
                   all         15         35      0.894      0.686      0.757      0.487

      Epoch    GPU_mem   box_loss   cls_loss   dfl_loss  Instances       Size
       4/24      11.2G       1.34      1.119      1.065         42        640: 100% 8/8 [01:57<00:00, 14.71s/it]
                 Class     Images  Instances          P          R      mAP50   mAP50-95: 100% 1/1 [00:00<00:00,  5.22it/s]
                   all         15         35      0.951      0.686      0.723      0.465

      Epoch    GPU_mem   box_loss   cls_loss   dfl_loss  Instances       Size
       5/24      11.2G      1.239      1.041      1.084         36        640: 100% 8/8 [01:49<00:00, 13.69s/it]
                 Class     Images  Instances          P          R      mAP50   mAP50-95: 100% 1/1 [00:00<00:00,  4.09it/s]
                   all         15         35      0.922      0.676      0.756      0.499

      Epoch    GPU_mem   box_loss   cls_loss   dfl_loss  Instances       Size
       6/24      11.2G      1.269     0.9554       1.03         49        640: 100% 8/8 [02:02<00:00, 15.27s/it]
                 Class     Images  Instances          P          R      mAP50   mAP50-95: 100% 1/1 [00:00<00:00,  3.38it/s]
                   all         15         35      0.955      0.771      0.777       0.48

      Epoch    GPU_mem   box_loss   cls_loss   dfl_loss  Instances       Size
       7/24      11.2G      1.326     0.8924      1.025         35        640: 100% 8/8 [01:55<00:00, 14.40s/it]
                 Class     Images  Instances          P          R      mAP50   mAP50-95: 100% 1/1 [00:00<00:00,  5.52it/s]
                   all         15         35      0.988      0.771      0.788      0.474

      Epoch    GPU_mem   box_loss   cls_loss   dfl_loss  Instances       Size
       8/24      11.2G      1.326     0.8287      1.065         33        640: 100% 8/8 [02:00<00:00, 15.01s/it]
                 Class     Images  Instances          P          R      mAP50   mAP50-95: 100% 1/1 [00:00<00:00,  5.76it/s]
                   all         15         35      0.958      0.743      0.779      0.505

      Epoch    GPU_mem   box_loss   cls_loss   dfl_loss  Instances       Size
       9/24      11.2G      1.248     0.8834      1.038         33        640: 100% 8/8 [01:47<00:00, 13.49s/it]
                 Class     Images  Instances          P          R      mAP50   mAP50-95: 100% 1/1 [00:00<00:00,  5.87it/s]
                   all         15         35      0.922      0.743      0.774      0.509
      Closing dataloader mosaic

      Epoch    GPU_mem   box_loss   cls_loss   dfl_loss  Instances       Size
      10/24      11.3G      1.193     0.6491      1.056         17        640: 100% 8/8 [00:26<00:00,  3.33s/it]
                 Class     Images  Instances          P          R      mAP50   mAP50-95: 100% 1/1 [00:00<00:00,  5.84it/s]
                   all         15         35      0.989      0.714      0.769      0.474

      Epoch    GPU_mem   box_loss   cls_loss   dfl_loss  Instances       Size
      11/24      11.3G      1.155     0.8175      1.023         15        640: 100% 8/8 [00:28<00:00,  3.55s/it]
                 Class     Images  Instances          P          R      mAP50   mAP50-95: 100% 1/1 [00:00<00:00,  5.17it/s]
                   all         15         35      0.842      0.771      0.795      0.493

      Epoch    GPU_mem   box_loss   cls_loss   dfl_loss  Instances       Size
      12/24      11.3G      1.162     0.7347      1.049         16        640: 100% 8/8 [00:31<00:00,  4.00s/it]
                 Class     Images  Instances          P          R      mAP50   mAP50-95: 100% 1/1 [00:00<00:00,  5.42it/s]
                   all         15         35      0.915      0.743      0.812      0.488

      Epoch    GPU_mem   box_loss   cls_loss   dfl_loss  Instances       Size
      13/24      11.3G      1.137     0.7881      1.029         17        640: 100% 8/8 [00:29<00:00,  3.68s/it]
                 Class     Images  Instances          P          R      mAP50   mAP50-95: 100% 1/1 [00:00<00:00,  5.76it/s]
                   all         15         35        0.8      0.743      0.762      0.454

      Epoch    GPU_mem   box_loss   cls_loss   dfl_loss  Instances       Size
      14/24      11.3G      1.142     0.7448       1.04         16        640: 100% 8/8 [00:31<00:00,  3.88s/it]
                 Class     Images  Instances          P          R      mAP50   mAP50-95: 100% 1/1 [00:00<00:00,  5.45it/s]
                   all         15         35      0.884      0.743      0.795      0.474

      Epoch    GPU_mem   box_loss   cls_loss   dfl_loss  Instances       Size
      15/24      11.3G      1.141     0.6513     0.9982         11        640: 100% 8/8 [00:30<00:00,  3.79s/it]
                 Class     Images  Instances          P          R      mAP50   mAP50-95: 100% 1/1 [00:00<00:00,  5.73it/s]
                   all         15         35      0.928      0.739      0.801      0.499

      Epoch    GPU_mem   box_loss   cls_loss   dfl_loss  Instances       Size
      16/24      11.3G      1.173     0.6446       1.02         11        640: 100% 8/8 [00:28<00:00,  3.54s/it]
                 Class     Images  Instances          P          R      mAP50   mAP50-95: 100% 1/1 [00:00<00:00,  5.76it/s]
                   all         15         35          1      0.764      0.836      0.489

      Epoch    GPU_mem   box_loss   cls_loss   dfl_loss  Instances       Size
      17/24      11.3G      1.137     0.6186     0.9558         12        640: 100% 8/8 [00:28<00:00,  3.61s/it]
                 Class     Images  Instances          P          R      mAP50   mAP50-95: 100% 1/1 [00:00<00:00,  5.76it/s]
                   all         15         35      0.874      0.796      0.831      0.521

      Epoch    GPU_mem   box_loss   cls_loss   dfl_loss  Instances       Size
      18/24      11.3G      1.096     0.5647     0.9941         14        640: 100% 8/8 [00:28<00:00,  3.51s/it]
                 Class     Images  Instances          P          R      mAP50   mAP50-95: 100% 1/1 [00:00<00:00,  3.91it/s]
                   all         15         35      0.863      0.771      0.797      0.491

      Epoch    GPU_mem   box_loss   cls_loss   dfl_loss  Instances       Size
      19/24      11.3G      1.075     0.5747     0.9667          9        640: 100% 8/8 [00:28<00:00,  3.55s/it]
                 Class     Images  Instances          P          R      mAP50   mAP50-95: 100% 1/1 [00:00<00:00,  5.57it/s]
                   all         15         35      0.925      0.707      0.771      0.501

      Epoch    GPU_mem   box_loss   cls_loss   dfl_loss  Instances       Size
      20/24      11.3G      1.104     0.5918     0.9688         15        640: 100% 8/8 [00:30<00:00,  3.76s/it]
                 Class     Images  Instances          P          R      mAP50   mAP50-95: 100% 1/1 [00:00<00:00,  5.66it/s]
                   all         15         35          1      0.703      0.838      0.499

      Epoch    GPU_mem   box_loss   cls_loss   dfl_loss  Instances       Size
      21/24      11.3G      1.115     0.5541      1.006         21        640: 100% 8/8 [00:28<00:00,  3.59s/it]
                 Class     Images  Instances          P          R      mAP50   mAP50-95: 100% 1/1 [00:00<00:00,  5.47it/s]
                   all         15         35      0.893      0.771      0.827      0.521

      Epoch    GPU_mem   box_loss   cls_loss   dfl_loss  Instances       Size
      22/24      11.3G      1.023     0.5411     0.9272         11        640: 100% 8/8 [00:27<00:00,  3.50s/it]
                 Class     Images  Instances          P          R      mAP50   mAP50-95: 100% 1/1 [00:00<00:00,  4.23it/s]
                   all         15         35      0.961      0.771      0.825      0.518

      Epoch    GPU_mem   box_loss   cls_loss   dfl_loss  Instances       Size
      23/24      11.3G      1.021     0.5229     0.9769         19        640: 100% 8/8 [00:30<00:00,  3.85s/it]
                 Class     Images  Instances          P          R      mAP50   mAP50-95: 100% 1/1 [00:00<00:00,  5.53it/s]
                   all         15         35      0.872      0.829       0.85      0.527

      Epoch    GPU_mem   box_loss   cls_loss   dfl_loss  Instances       Size
      24/24      11.3G      1.056     0.5282     0.9511         14        640: 100% 8/8 [00:26<00:00,  3.36s/it]
                 Class     Images  Instances          P          R      mAP50   mAP50-95: 100% 1/1 [00:00<00:00,  5.59it/s]
                   all         15         35      0.905      0.812      0.851      0.521

![image](https://github.com/ChintanShahDS/YOLOv9_training/assets/94432132/52509ec4-f7d2-45b9-a552-8cd3046328d2)

## Outputs

### Training graphs
![image](https://github.com/ChintanShahDS/YOLOv9_training/assets/94432132/67001bfb-72ab-4795-a004-4883f9cdbb31)

### Confusion graph
![image](https://github.com/ChintanShahDS/YOLOv9_training/assets/94432132/228b9493-6a7a-4e38-8fba-177d524cc0d9)

### Output samples
![image](https://github.com/ChintanShahDS/YOLOv9_training/assets/94432132/eca161f2-acd3-45f4-9846-65cff781dc30)



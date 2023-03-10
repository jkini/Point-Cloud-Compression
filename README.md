# Point-Cloud-Compression

## Installations
```
cuda-11.0
cmake-3.7.2-gcc-6.2.0
pytorch==1.7.1 
torchvision==0.8.2 
torchaudio==0.7.2 
numpy==1.20.3 
open3d==0.9.0.0 
einops==0.3.2 
scikit-learn==1.0.1 
compressai 
argparse
tensorboard
```

## Data Preparation
Download the ShapeNetCore v1 dataset
```
cd ./dataset
git clone https://github.com/hjwdzh/Manifold
cd Manifold && mkdir build
cd build 
cmake .. -DCMAKE_BUILD_TYPE=Release
make 
cd ..
```
```
python prepare_shapenet.py --data_root path_to_dataset
```
.pkl files will be created in /data directory

## Training
```
python train.py --dataset shapenet
```

## Testing
```
python test.py --dataset shapenet --model_path output/../ckpt/ckpt-best.pth
```

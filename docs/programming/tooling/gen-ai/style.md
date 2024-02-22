# Style transfer


## Facial Editing

Best Free AI Hairstyles Online & App for Free Hairstyle Try-On [web](https://www.perfectcorp.com/consumer/blog/hair/best-AI-hairstyle-app-virtual-hairstyles)

**FOSS apps**:
- core:
  [`scikit-image`](https://scikit-image.org/)
- generic: [STIT](https://github.com/rotemtzaban/STIT)
  [StyleGAN](https://en.wikipedia.org/wiki/StyleGAN) ([github](https://github.com/NVlabs/stylegan))
- hairstyles: [^wiki:hairstyle] <!-- [hairstyle-try-on](https://github.com/sanviiz/hairstyle-try-on) -->
  [StyleGANSalon](https://stylegan-salon.github.io/) [^foss:StyleGANSalon]
  [**Style-Your-Hair**](https://github.com/garlicbreadai/Hair) [^foss:Style-Your-Hair] [^note:hairstyle-experience]
  [Barbershop]https://github.com/ZPdesu/Barbershop [^foss:Barbershop]

[^foss:StyleGANSalon] Sasikarn Khwanmuang (2023) `StyleGAN` Salon: Multi-View Latent Optimization for Pose-Invariant Hairstyle Transfer (CVPR) [io](https://stylegan-salon.github.io/)

[^foss:Barbershop]: [Peihao Zhu](https://github.com/ZPdesu) (2021) `Barbershop`: GAN-based Image Compositing using Segmentation Masks (SIGGRAPH Asia) [github](https://github.com/ZPdesu/Barbershop)

[^foss:Style-Your-Hair] [Taewoo Kim](https://github.com/Taeu) (2022) "Style Your Hair": Latent Optimization for Pose-Invariant Hairstyle Transfer via Local-Style-Aware Hair Alignment (ECCV) [github](https://github.com/Taeu/Style-Your-Hair) <details><summary>Style-Your-Hair deployment</summary>

Deployment with [conda](https://docs.anaconda.com/free/anaconda/install/linux/)
```bash
sudo apt-get install libgl1-mesa-glx libegl1-mesa libxrandr2 libxrandr2 libxss1 libxcursor1 libxcomposite1 libasound2 libxi6 libxtst6
curl -O https://repo.anaconda.com/archive/Anaconda3-2023-09-0-Linux-x86_64.sh # firefox
shasum -a 256 ./Anaconda3-2023-09-0-Linux-x86_64.sh 
bash ~/Downloads/Anaconda3-2023.09-0-Linux-x86_64.sh 
. ~/anaconda3/bin/activate 
conda init    

git clone https://github.com/Taeu/Style-Your-Hair.git
cd Style-Your-Hair
conda create -n style_your_hair python=3.7.9
conda activate style_your_hair
conda install pytorch==1.8.0 torchvision==0.9.0 torchaudio==0.8.0 cudatoolkit=11.1 -c pytorch -c conda-forge
pip install face_alignment==1.3.3 face-recognition gdown ipython matplotlib

# Undocumented
conda install scikit-image
pip install face_alignment face-recognition gdown ipython matplotlib
```

Test with [images](https://drive.google.com/drive/folders/1RxzbNcKb3bPDKccyo300YXCJ8EvZSaIL)
```bash
mkdir ~/workspace/research/Style-Your-Hair/ffhq_image
cd ~/workspace/research/Style-Your-Hair/ffhq_image
unzip ../new_input_ffhq-20240202T164205Z-001.zip

convert -resize 1024X1024 ./sg.png ./sgogo.png
mv /sgogo.png ~/workspace/research/Style-Your-Hair/ffhq_image

python main.py --input_dir ./ffhq_image/ --im_path1 source.png --im_path2 target.png \
    --output_dir ./style_your_hair_output/ \
    --warp_loss_with_prev_list delta_w style_hair_slic_large \
    --save_all --version final --flip_check
```

<details><summary>Troubleshooting</summary>

- Use `pillow==6.0.0` that [fixes](https://github.com/python-pillow/Pillow/issues/3557) issue 
  `'PngStream' object has no attribute 'chunk_eXIf'`

</details>

</details>

[^wiki:hairstyle]: For the list of hairstyles see https://en.wikipedia.org/wiki/List_of_hairstyles .
    E.g., compare [bob](https://en.wikipedia.org/wiki/Bob_cut) vs [lob](https://en.wikipedia.org/wiki/Lob_(haircut))

[^note:hairstyle-experience]: From my personal experience, this tool generalizes badly, namely, overfitted to the training set
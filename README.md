## Global_Diffusion_Model


### Key features

- Docker for training condition diffusion model


### News

- 2024/09: Internal testing starting.



### Data preparation

1. Put the images into `traindata` folder (both png and jpeg formats are fine).

```
├──traindata
    ├──1.jpg
    ├──2.jpg
    ├──3.jpg
``` 

2. Generate a `metadata.csv` file including the metadata.

| Image  | Ethnicity        | Sex |    Age|  DR|
| ------------- | ------------------ |-------------|------------|-----|
| 1.jpg      | British     |     female  |    62        |  mild diabetic retinopathy   |
| 2.jpg        | Chinese  |     female        |    71        |  moderate diabetic retinopathy   |
| 3.jpg        |       Indian        |     male        |       52     |  no diabetic retinopathy   |



### Install Docker

If you have not installed Docker on your machine. Please follow [official instructions](https://docs.docker.com/engine/install/).



### Run the docker

To fine tune RETFound on your own data, follow these steps:


1. Download the docker

```
docker pull yukunzhou/diffuser_docker
``` 

2. Run it

Please substitute the `{Absolute_path}` with the path to `traindata` folder
```
docker run --gpus all -it -v {Absolute_path}:/app/diffusers/Global_DM -v {Absolute_path}/diffusion1.5:/app/diffusers/examples/text_to_image/diffusion1.5 yukunzhou/diffuser_docker
```

The process will generate a `diffusion1.5` folder in `{Absolute_path}` path. The model weights will be saved there.


### Citation

TBC



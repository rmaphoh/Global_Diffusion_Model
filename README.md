## Global_Diffusion_Model


### Key features

- Docker for training condition diffusion model


### News

- 2024/09: Internal testing starting.
- 2025/03: Metadata update.


### Hardware requirements

- A consumer-grade GPU (~16GB) is essential for model training. We have tested the docker with [multiple GPUs](https://docs.google.com/spreadsheets/d/1PIajcnnW9xhQ85XJVHh3sgvDcdrGk6AYFYzsXcJiC3k/edit?usp=sharing). 


### Data requirements

- Please include around 1k-20k images. The docker running will take around 1-2 days. 



### Data preparation

1. Put the images into `traindata` folder (both png and jpeg formats are fine).

```
├──traindata
    ├──1.jpg
    ├──2.jpg
    ├──3.jpg
``` 

2. Generate a `metadata.csv` file including the metadata.

- If a variable is missing / not known, then leave that cell BLANK.

- If you don’t have ANY metadata for that image, then only the ‘Image’ column would be filled in.

- Save the metadata.csv in the same path as “traindata” folder

```
├──traindata
    ├──1.jpg
    ├──2.jpg
    ├──3.jpg
├──metadata.csv   
``` 

An example and column dictionary can be found [here](https://docs.google.com/spreadsheets/d/1wJPJfBJxTCCVcGCEbWiC5m3EjxeQLSIn/edit?usp=sharing&ouid=115097033631735657188&rtpof=true&sd=true).



### Install Docker

If you have not installed Docker on your machine. Please follow [official instructions](https://docs.docker.com/engine/install/).



### Run the docker


1. Download the docker

```
docker pull yukunzhou/diffuser_docker
``` 

2. Run it

Please substitute the `{Absolute_path}` with the path to `traindata` folder.
```
docker run --gpus all -it -v {Absolute_path}:/app/diffusers/Global_DM yukunzhou/diffuser_docker
```
e.g.`docker run --gpus all -it -v /home/yukun:/app/diffusers/Global_DM yukunzhou/diffuser_docker`

The process will generate a `diffusion1.5`,`diffusion2`, and `sdxl` folder in `{Absolute_path}` path. The model weights will be saved there.



### Citation

TBC



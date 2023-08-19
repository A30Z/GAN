# Face Generation GAN:

for this example we using DCGAN tutorial of pytorch.org

we will use the Celeb-A Faces dataset which can be downloaded at the 
[linked site](http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html),
or in 
[Google Drive](https://drive.google.com/drive/folders/0B7EVK8r0v71pTUZsaXdaSnZBZzg).
The dataset will download as a file named img_align_celeba.zip. Once downloaded, create a directory named celeba and extract the zip file into that directory. Then, set the dataroot input for this notebook to the celeba directory you just created. The resulting directory structure should be:
  /path/to/celeba
    -> img_align_celeba
        -> 188242.jpg
        -> 173822.jpg
        -> 284702.jpg
        -> 537394.jpg
           ...

so in this example real data is pictures of celebrity faces and generator learning to generate pictures similar to real faces from noise

this is **generator** architectur:

![generator](https://github.com/A30Z/GAN/assets/121484376/6fc02246-8a23-44b6-a68a-d55a8bd89c1d)


this is **discriminator** architecture:

![discriminator](https://github.com/A30Z/GAN/assets/121484376/997f91a6-1c0b-4d99-9742-7b4c83a8fcc8)


training example:

![training](https://github.com/A30Z/GAN/assets/121484376/433efb54-e66c-40bc-9e22-ce01ace90777)


first generator output:

![output1](https://github.com/A30Z/GAN/assets/121484376/5a54f555-d25b-4f29-bb17-f313c0671b6c)


last generator output:

![output2](https://github.com/A30Z/GAN/assets/121484376/577cccc3-eebb-434f-9edc-7e0702517c9e)


real data vs generator output:

![output3](https://github.com/A30Z/GAN/assets/121484376/687716df-3247-4528-861e-39135191fe71)

you can see details in notebook

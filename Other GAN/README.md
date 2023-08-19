# Cycle GAN
it contains 2 generators and 2 discriminators to transfer images from one domain to another.
there are some examples of cycle GAN like (summer2winter) , (picture2paint) , (horse2zebra).

The model architecture is comprised of two generator models: one generator (Generator-A) for generating images for the first domain (Domain-A) and the second generator (Generator-B) for generating images for the second domain (Domain-B).

  Domain-B -> Generator-A -> Domain-A
  Domain-A -> Generator-B -> Domain-B

Each generator has a corresponding discriminator model (Discriminator-A and Discriminator-B). The discriminator model takes real images from Domain and generated images from Generator to predict whether they are real or fake.

  Domain-A -> Discriminator-A -> [Real/Fake]
  Domain-B -> Generator-A -> Discriminator-A -> [Real/Fake]

  Domain-B -> Discriminator-B -> [Real/Fake]
  Domain-A -> Generator-B -> Discriminator-B -> [Real/Fake]

in this kind of GAN we have 3 **losses**:
1)**Adversarial Loss**: We apply Adversarial Loss to both the Generators, where the Generator tries to generate the images of it's domain, while its corresponding discriminator distinguishes between the translated samples and real samples. Generator aims to minimize this loss against its corresponding Discriminator that tries to maximize it.

2)**Cycle Consistency Loss**: It captures the intuition that if we translate the image from one domain to the other and back again we should arrive at where we started. Hence, it calculates the L1 loss between the original image and the final generated image, which should look same as original image. It is calculated in two directions:
Domain-B -> Generator-A -> Domain-A -> Generator-B -> Domain-B
Domain-A -> Generator-B -> Domain-B -> Generator-A -> Domain-A

3)**Identity Loss**: It encourages the generator to preserve the color composition between input and output. This is done by providing the generator an image of its target domain as an input and calculating the L1 loss between input and the generated images.

As all of these loss functions play critical roles in arriving at high-quality results. Hence, both the generator models are optimized via combination of all of these loss functions.

we pick (horse2zebra) for example 
one discriminator classify real horse image from fake horse image and another dicriminator classify real zebra from fake zebra.
one generator try to genereate horse image from real zebra image and another generator generete zebra image from real horse image.

![architecture](https://github.com/A30Z/GAN/assets/121484376/50eb6cd4-45f5-4851-8c55-912b4d582454)

we have the same thing for zebra discriminator.

this is **generators architecture**:

![generator](https://github.com/A30Z/GAN/assets/121484376/7bc2a501-3c05-4be3-a8ce-62f459252d26)

this is **discriminator architecture**:

![Discriminator](https://github.com/A30Z/GAN/assets/121484376/5d46ef4f-8b84-4710-a891-4ea7cd9ea835)

this is **resault**:

![resault](https://github.com/A30Z/GAN/assets/121484376/1a892de6-46a5-4a94-afa7-40d550c63b9c)

you can find details and code and model in this link:

[pytorch_implementation](https://www.kaggle.com/code/balraj98/cyclegan-translating-horses-zebras-pytorch)



# text to image GAN
the goal is to generate an image that corresponds to a given textual description. This involves converting the text input into a meaningful representation, such as a feature vector, and then using this representation to generate an image that matches the description.

the diffrent part of this type of GAN is converting text to semantic features to pass to generators.
everything else is really similar to other kind of GANs

![architecture](https://github.com/A30Z/GAN/assets/121484376/b94a1385-620a-4f68-8270-1e7b93ec7a70)

**generator** and **discriminator** architecture:

![architrcture](https://github.com/A30Z/GAN/assets/121484376/6f86266f-c7bd-4bc7-a6f4-4a8fea21bfe0)

this is **resault**:

![output](https://github.com/A30Z/GAN/assets/121484376/b7f04a8d-39c2-4b9e-a9a3-7055fa1c9007)

you can find details and code and model in this link:

[pytorch implementation](https://www.kaggle.com/code/avikbanik/text-to-image-xlnet-pytorch)

# Super-resolution GAN(SRGAN)
Super-resolution GAN applies a deep network in combination with an adversary network to produce higher resolution images. As shown above, SRGAN is more appealing to a human with more details compared with the similar design without GAN (SRResNet). During the training, A high-resolution image (HR) is downsampled to a low-resolution image (LR). A GAN generator upsamples LR images to super-resolution images (SR). We use a discriminator to distinguish the HR images and backpropagate the GAN loss to train the discriminator and the generator.

this is **architecture of SRGAN**:

![SRGAN](https://github.com/A30Z/GAN/assets/121484376/b22c2008-0676-4c7b-8775-184cce7c3493)

this is **generator architecture**:

![srgen](https://github.com/A30Z/GAN/assets/121484376/5f7e70b2-6dc8-4156-a9d7-3fc865740384)

this is **discriminator architecture**:

![srdis](https://github.com/A30Z/GAN/assets/121484376/e0786f40-53f1-41b0-8623-a43f4841d36c)

in this kind of GAN we have 2 **losses**:

1)**Content Loss**: We use two types of content loss in the paper : pixelwise MSE loss for the SRResnet architecture, which is most common MSE loss for image Super Resolution. However MSE loss does not able to deal with high frequency content in the image that resulted in producing overly smooth images. Therefore the authors of the paper decided to  use loss of different VGG layers. This VGG loss is based on the ReLU activation layers of the pre-trained 19 layer VGG network. This loss is defined as follows:
**simple content loss**:

![l1](https://github.com/A30Z/GAN/assets/121484376/e9886b64-9ed3-4477-ba0f-c9fa5b127e15)

**VGG contents loss**:

![l2](https://github.com/A30Z/GAN/assets/121484376/c5845b26-072c-4261-8684-193cafb5971a)

2)**Adversarial Loss**: The Adversarial loss is the loss function that forces the generator to image more similar to high resolution image by using a discriminator that is trained to differentiate between high resolution and super resolution images.

![l3](https://github.com/A30Z/GAN/assets/121484376/beb8086d-0552-4514-b8fb-3f593f3ed161)

**total loss**:

![l4](https://github.com/A30Z/GAN/assets/121484376/d3e603ba-9d30-46a2-9bec-b6c7b1f941a2)



this is a **resault**:

![example](https://github.com/A30Z/GAN/assets/121484376/2e163892-d3bc-4eaa-a7ec-1d2712a12f1a)

you can find details and code and model:

[pytorch implementation](https://www.kaggle.com/code/balraj98/single-image-super-resolution-gan-srgan-pytorch)

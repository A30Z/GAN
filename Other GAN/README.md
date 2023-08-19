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

in this kind of GAN we have 3 **losses for generator**:
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

you can find code and model and details in this link:

[pytorch_implementation](https://www.kaggle.com/code/balraj98/cyclegan-translating-horses-zebras-pytorch)



# text to image GAN
the goal is to generate an image that corresponds to a given textual description. This involves converting the text input into a meaningful representation, such as a feature vector, and then using this representation to generate an image that matches the description.

![architecture](https://github.com/A30Z/GAN/assets/121484376/b94a1385-620a-4f68-8270-1e7b93ec7a70)

**generator** and **discriminator** architecture:

![architrcture](https://github.com/A30Z/GAN/assets/121484376/6f86266f-c7bd-4bc7-a6f4-4a8fea21bfe0)

this is resault:

![output](https://github.com/A30Z/GAN/assets/121484376/b7f04a8d-39c2-4b9e-a9a3-7055fa1c9007)

you can find code and model in this link:

[pytorch implementation](https://www.kaggle.com/code/avikbanik/text-to-image-xlnet-pytorch)



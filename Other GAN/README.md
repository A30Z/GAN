# Cycle GAN
it contains 2 generators and 2 discriminators to transfer images from one dimension to another
there are some examples of cycle GAN like (summer2winter) , (picture2paint) , (horse2zebra)
we pick (horse2zebra) for example 
one discriminator classify real horse image from fake horse image and another dicriminator classify real zebra from fake zebra.
one generator try to genereate horse image from real zebra image and another generator generete zebra image from real horse image.

![architecture](https://github.com/A30Z/GAN/assets/121484376/50eb6cd4-45f5-4851-8c55-912b4d582454)

we have the same thing for zebra discriminator 

this is **generators architecture**:

![generator](https://github.com/A30Z/GAN/assets/121484376/7bc2a501-3c05-4be3-a8ce-62f459252d26)

this is **discriminator architecture**:

![Discriminator](https://github.com/A30Z/GAN/assets/121484376/5d46ef4f-8b84-4710-a891-4ea7cd9ea835)

this is **resault**:

![resault](https://github.com/A30Z/GAN/assets/121484376/1a892de6-46a5-4a94-afa7-40d550c63b9c)

you can find code and model in this link:

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



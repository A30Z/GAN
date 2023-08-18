# Cycle GAN
it contains 2 generators and 2 discriminators to transfer images from one dimension to another
there are some examples of cycle GAN like (summer2winter) , (picture2paint) , (horse2zebra)
we pick (horse2zebra) for example 
one discriminator classify real horse image from fake horse image and another dicriminator classify real zebra from fake zebra.
one generator try to genereate horse image from real zebra image and another generator generete zebra image from real horse image.

![cyclegan-BA](https://github.com/A30Z/GAN/assets/121484376/50eb6cd4-45f5-4851-8c55-912b4d582454)

we have the same thing for zebra discriminator 

this is **generators architecture**:

![generator](https://github.com/A30Z/GAN/assets/121484376/7bc2a501-3c05-4be3-a8ce-62f459252d26)

this is **discriminator architecture**:

![Discriminator](https://github.com/A30Z/GAN/assets/121484376/5d46ef4f-8b84-4710-a891-4ea7cd9ea835)

this is **resault**:

![resault](https://github.com/A30Z/GAN/assets/121484376/1a892de6-46a5-4a94-afa7-40d550c63b9c)

you can find code and model in this link:

[pytorch_implementation](https://www.kaggle.com/code/balraj98/cyclegan-translating-horses-zebras-pytorch)





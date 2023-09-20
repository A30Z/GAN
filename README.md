# GAN
GAN is short of generative adversarial networks.
GANs are an exciting and rapidly changing field, delivering on the promise of generative models in their ability to generate realistic examples across a range of problem domains, most notably in image-to-image translation tasks such as translating photos of summer to winter or day to night, and in generating photorealistic photos of objects, scenes, and people that even humans cannot tell are fake.

Common use cases of GANs include the following:

    Filling in images from an outline.
    Generating a realistic image from text.
    Producing photorealistic depictions of product prototypes.
    Converting black and white imagery into color.

    Photo translations from image sketches or semantic images that are especially useful in the healthcare industry for diagnoses.

In video production, GANs can be used to perform the following:

    Model patterns of human behavior and movement within a frame.
    Predict subsequent video frames.
    Create a deepfake.

Other use cases of GANs include text-to-speech for the generation of realistic speech sounds. Furthermore, GAN-based generative AI models can generate text for blogs, articles and product descriptions. These AI-generated texts can be used for a variety of purposes, including advertising, social media content, research and communication.

a GAN has 2 parts:
The **generator** learns to generate plausible data.
The **discriminator** learns to distinguish the generator's fake data from real data.

architecture of a GAN:

![architecture](https://github.com/A30Z/GAN/assets/121484376/ba517345-494c-46d9-b9f4-20e6ec8aa77d)


Both the generator and the discriminator are neural networks.
these two neural networks compete with each other by using deep learning methods to become more accurate in their predictions

the generative model captures the distribution of data and is trained in such a manner that it tries to maximize the probability of the Discriminator making a mistake. The Discriminator, on the other hand, is based on a model that estimates the probability that the sample that it got is received from the training data and not from the Generator. The GANs are formulated as a minimax game, where the Discriminator is trying to minimize its reward V(D, G) and the Generator is trying to minimize the Discriminator’s reward or in other words, maximize its loss. It can be mathematically described by the formula below: 

![GANloss](https://github.com/A30Z/GAN/assets/121484376/a663c345-2b59-4fd5-b7ad-1e09960af296)

    where,

        G = Generator 
        D = Discriminator 
        Pdata(x) = distribution of real data 
        P(z) = distribution of generator 
        x = sample from Pdata(x) 
        z = sample from P(z) 
        D(x) = Discriminator network 
        G(z) = Generator network 

you can see diffrent kind of GAN in each folder

### References

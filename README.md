# Variational-Autoencoders


- The code was from this [repo](https://github.com/davidADSP/GDL_code).
- A good summary [medium post](https://towardsdatascience.com/understanding-variational-autoencoders-vaes-f70510919f73) of understanding VAE.
- A [Introduction course](https://www.youtube.com/watch?v=rZufA635dq4) about generative model from MIT.
- [Unsupervised Learning VAE course](https://www.bilibili.com/video/BV1JE411g7XF?p=58) and [notes](https://datawhalechina.github.io/leeml-notes/#/chapter27/chapter27) from Dr.Hongyi Li(Mandarin)

Before we explored VAEs, we need to __understand what is encoder,decoder, autoencoder__?![ ](https://github.com/syhwawa/Variational-Autoencoders/blob/main/images/autoencoder1.png)
Data encoding is to map (sensory) input data to a different (often lower dimensional, compressed) feature representation. And Data Decoding is to map the feature representation back into the input data.

Auto-encoder is a __complex mathematical model__ which trains on __unlabeled__ as well as unclassified data and is used to map the __input data__ to another compressed feature representation and from that feature representation __reconstructing back the input data__.

## Variational Autoencoders (VAEs). 
In a nutshell, a VAE is an autoencoder whose encodings distribution is regularised during the training in order to ensure that its latent space has good properties allowing us to generate some new data. Moreover, the term “variational” comes from the close relation there is between the regularisation and the variational inference method in statistics.

A variational autoencoder can be defined as being an autoencoder whose training is regularised to avoid overfitting and ensure that the latent space has good properties that enable generative process

![Key differences between VAEs and autoencoder:](https://github.com/syhwawa/Variational-Autoencoders/blob/main/images/differences%20between%20VAE%20and%20autoencoder.png)

Just as a standard autoencoder, a variational autoencoder is an architecture composed of both an encoder and a decoder and that is trained to minimise the reconstruction error between the encoded-decoded data and the initial data. However, in order to introduce some regularisation of the latent space, we proceed to a slight modification of the encoding-decoding process: instead of encoding an input as a single point, we encode it as a __distribution__ over the latent space. The model is then trained as follows:
1. the input is encoded as distribution over the latent space
2. a point from the latent space is sampled from that distribution
3. the sampled point is decoded and the reconstruction error can be computed
4. the reconstruction error is backpropagated through the network 


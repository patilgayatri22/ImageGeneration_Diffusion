# Fine-Tuning Diffusion Models for Image Generation

  Diffusion models are current State-Of-The-Art (SOTA) for high-quality text-to-image synthesis, but training the model from scratch is computationally expensive. Using LoRA, we can fine tune a small subset of parameters to capture stylistic anime faces and scenes and result in efficiency with faster convergence.

There are 3 main components in the architecture as shown in the image below:

**1. VAE (Encoder–Decoder pair)**: To compress and reconstruct images into a low-dim latent space.

**2. UNet Denoiser:** To iteratively remove noise from latent images, conditioned on text and timestep embeddings.

**3. Text Encoder (CLIP)**: To converts textual prompts into feature embeddings which will guide the UNet’s denoising process.

**LoRA (Low-Rank Adaptation)**
Fine-tuning with LoRA allowed us to to modify pre-trained models by adding low-rank trainable matrices to specific attention layers into the model’s layers while freezing the original weights. So now, instead of training the entire large weight matrices W, it will add a low-rank decomposition (product of two smaller matrices A and B). LoRA updates the weight by using :
**Wn = W0 + A ∗B**
where, A and B are the trainable matrices.

# Usage

**1. Clone the repository**

      git clone https://github.com/patilgayatri22/ImageGeneration_Diffusion.git
      cd ImageGeneration_Diffusion


**2. Launch the notebook**

Open image_generation_diffusion.ipynb in Jupyter or Colab to run training and image generation steps.

**3. Customize prompts**

Edit your text prompts to generate images in your desired style.

**4. Evaluate outputs**

Check generated images and results files to analyze performance.



# Contributing
Contributions welcome! Fork, create a feature branch, and submit a PR.

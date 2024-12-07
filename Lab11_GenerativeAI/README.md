# GenerativeAI

## Adversarial Image Generation using FGSM

 - Loads a grayscale image
 - Generates Gaussian noise
 - Creates an adversarial image by combining the original image with noise
 - Displays both the original and adversarial images side by side

 ## GAN

 The GAN consists of:

 - A Generator that transforms random noise into MNIST-like images
 - A Discriminator that tries to distinguish between real and generated images
 - Training loop with visualization capabilities

 Output: 

 - Generated images are saved in './fake_images/' directory
 - Model checkpoints are saved in './GAN_models/' directory
 - Training progress is printed every 500 batches

 ## Diffusion Model: Image Noise Addition and Denoising Demonstration

 - Loads and preprocesses a grayscale image
 - Progressively adds Gaussian noise in 5 steps
 - Applies Gaussian blur for denoising
 - Visualizes the entire process
 - Provides quantitative analysis of noise levels

# Additional Implementations

 ## Diffusion Model

 A lightweight implementation of a diffusion model using Multi-Layer Perceptron (MLP) for generating MNIST digits. 

• Core Concept
  - Diffusion models work by gradually adding noise to images and then learning to reverse this process
  - Uses a fixed number of timesteps (50 in this case) for the noise addition/removal process

• Forward Process (Noise Addition)
  - Starts with a clear image
  - Progressively adds Gaussian noise according to a fixed schedule

• Reverse Process (Denoising)
  - Starts with pure noise
  - Gradually denoises in reverse timesteps
  - Predicts and removes noise at each step
  - Uses the trained MLP to estimate noise at each timestep

• Key Components
  - Noise Schedule: Linear schedule from β₁=1e-4 to β₅₀=0.02
  - Network: Simple MLP with 3 layers (input→512→256→output)
  - Time Embedding: Adds timestep information to help network understand denoising level

• Training Approach
  - Batch size: 512 for efficiency
  - Loss: MSE between predicted and actual noise
  - Learning rate: 2e-3 with Adam optimizer
  - Samples generated after each epoch to monitor progress

 Output:
 - Model checkpoint is saved as './diffusion_models/fast_mlp_diffusion.pth'
 - Training progress is displayed using tqdm
 - Loss values are shown in real-time

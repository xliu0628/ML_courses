# Diffusion Models 
Main references: Weng, Lilian. (Jul 2021). What are diffusion models? Lil’Log. https://lilianweng.github.io/posts/2021-07-11-diffusion-models/.

## High-level understanding
- Diffusion models learn the probability distribution by slowly adding random noises to the data and then learning to reverse the process to recover the data from the noise.
- They define a Markov chain of diffusion steps to slowly add noises. 

## Details
### Forward diffusion process, e.g. Markov Chain process
<img width="709" alt="image" src="https://github.com/user-attachments/assets/3532c998-18f4-4903-9898-a3be696452db" />

### Connection with stochastic gradient Langevin dynamics
Stochastic gradient Langevin dynamics can produce samples from a probability density using only the gradients in a Markov chain of updates: 
<img width="710" alt="image" src="https://github.com/user-attachments/assets/7e9b6f9b-8ae3-4256-bdaf-d99db81ff532" />
Compared to standard SGD, stochastic gradient Langevin dynamics injects Gaussian noises into the parameter updates to avoid collapse into local minima. 

### Reverse Diffusion process
The reverse process is sample $X_{t-1}$ from ${X_{t}}$. $q(X_t|X_{t-1})$ is known (the Gaussian noise in the Markov process), but $q(X_{t-1}|X_{t})$ is unknown. It involves transforming Gaussian noise back into a sample of data. Ideally, we want to model this reverse process as a sequence of conditional probabilities. The challenge here is that the reverse process requires knowledge of the true distribution of $q(X_{t-1}|X_{t})$ which involves the entire dataset. We learn a model to approximate these conditional probabilities instead. 

### Loss function
#### KL distance

### Conditioned Generation
It refers to generating samples conditioned on class labels or a piece of descriptive text.
#### 1 Classifier Guided Diffusion
It refers to guiding the diffusion sampling process toward the conditioning information (e.g. a target class label) by altering the noise prediction. 
<img width="710" alt="image" src="https://github.com/user-attachments/assets/750b4707-bd24-4009-8d49-2db5774c68c5" />
This guided model achieves better results than SOTA GANs. 

### Speed Up Diffusion models
The Markov chain makes it really slow. How to speed up
- Strided sampling
- Parameterizing the model and therefore making it deterministic. Fewer samples can then be used.
- Progressive Distillation (Salimans & Ho, 2022) is a method for distilling trained deterministic samplers into new models of halved sampling steps.
- Consistency Models (Song et al. 2023) learns to map any intermediate noisy data points 
 on the diffusion sampling trajectory back to its origin 
 directly. It is named as consistency model because of its self-consistency property as any data points on the same trajectory is mapped to the same origin.
- Use latent variable space
- Decompose the data by trimming off redundancy, then run diffusion on the latent space,

### Model Architecture
- Unet
- Transformer






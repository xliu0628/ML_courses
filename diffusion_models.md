# Notes of https://lilianweng.github.io/posts/2021-07-11-diffusion-models/
## High-level understanding
- Diffusion models learn the probability distribution by slowly adding random noises to the data and then learning to reverse the process to recover the data from the noise.
- They define a Markov chain of diffusion steps to slowly add noises. 

## Details
### Forward diffusion process, e.g. Markov Chain process
<img width="709" alt="image" src="https://github.com/user-attachments/assets/3532c998-18f4-4903-9898-a3be696452db" />


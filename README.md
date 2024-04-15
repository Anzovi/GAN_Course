# Глубокие генеративные модели (Deep Generative Models)  
# Зозуля Андрей Витальевич  

# Ссылки   
Ссылка на Colab: https://colab.research.google.com/drive/1ZK3uWp11BAr_6mH1YTygchkzDPHN1hBF?usp=sharing  
обучение stable diffusion 1.5 через Dreambooth wandb: https://api.wandb.ai/links/anzovitte/xnrkzn8v  
обучение stable diffusion 1.5 с использованием LoRa (rank = 2) wandb: https://api.wandb.ai/links/anzovitte/ih28b5wk  
обучение stable diffusion 1.5 с использованием LoRa (rank = 8) wandb: https://api.wandb.ai/links/anzovitte/zvhzkabm  
обучение stable diffusion 1.5 с использованием LoRa (rank = 24) wandb: https://api.wandb.ai/links/anzovitte/tti5s4z2  

1. Собрать датасет от 15 изображений одного персонажа, кропнуть и заресайзить лица  
Кропнул и заресайзил, всего 27 изображений.

<p float="left">  
  <img src="https://github.com/Anzovi/GAN_Course/blob/homework_4/instance%20images/3_c66971e5.jpg" width="100" />
  <img src="https://github.com/Anzovi/GAN_Course/blob/homework_4/instance%20images/GettyImages.jpg" width="100" /> 
  <img src="https://github.com/Anzovi/GAN_Course/blob/homework_4/instance%20images/Margot-Robbi.jpg" width="100" />
  <img src="https://github.com/Anzovi/GAN_Course/blob/homework_4/instance%20images/Margot-Robbie.jpg" width="100" />
  <img src="https://github.com/Anzovi/GAN_Course/blob/homework_4/instance%20images/sd-aspect-1482916032-margotrobbiewhite.jpg" width="100" />
</p>  

2. Скачать предобученный чекпоинт SD1.5 с civitai.com и обучить Stable diffusion 1.5.  
Использовались промты:

--instance_prompt="a photo of sks woman face" токен на который мы хотим обучить персонажа  
--class_prompt="a photo of woman face" промт для регуляризации  

Desert   |  Forest  |  Kitchen |  Moon |  Street
:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:
![](https://github.com/Anzovi/GAN_Course/blob/homework_4/Dreambooth%20generated/desert-min.jpg)  |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/Dreambooth%20generated/forest-min.jpg)  |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/Dreambooth%20generated/kitchen-min.jpg) |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/Dreambooth%20generated/moon-min.jpg) |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/Dreambooth%20generated/street-min.jpg)

3. Обучить LoRA модель и сравнить лучший чекпоинт Unet и Lora  

4. Добавить в pipeline ControlNet  




![alt text](https://github.com/Anzovi/GAN_Course/blob/homework_3/imgs/StyleGAN_Preporations.png)

# Глубокие генеративные модели (Deep Generative Models)  
# Зозуля Андрей Витальевич  

# Ссылки   
Ссылка на Colab: https://colab.research.google.com/drive/1ZK3uWp11BAr_6mH1YTygchkzDPHN1hBF?usp=sharing  
обучение stable diffusion 1.5 через Dreambooth wandb: https://api.wandb.ai/links/anzovitte/xnrkzn8v  
обучение stable diffusion 1.5 с использованием LoRa (rank = 2) wandb: https://api.wandb.ai/links/anzovitte/ih28b5wk  
обучение stable diffusion 1.5 с использованием LoRa (rank = 8) wandb: https://api.wandb.ai/links/anzovitte/zvhzkabm  
обучение stable diffusion 1.5 с использованием LoRa (rank = 24) wandb: https://api.wandb.ai/links/anzovitte/tti5s4z2  

1. Собрать датасет от 15 изображений одного персонажа, кропнуть и заресайзить лица
:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:
![](https://github.com/Anzovi/GAN_Course/blob/homework_4/instance%20images/3_c66971e5.jpg)  |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/instance%20images/GettyImages.jpg)  |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/instance%20images/Margot-Robbi.jpg) |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/instance%20images/Margot-Robbie.jpg) |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/instance%20images/sd-aspect-1482916032-margotrobbiewhite.jpg)
2. Скачать предобученный чекпоинт SD1.5 с civitai.com
3. Обучить Stable diffusion 1.5.
4. Обучить LoRA модель и сравнить лучший чекпоинт Unet и Lora
5. Добавить в pipeline ControlNet

Solarized dark        |  Solarized Ocean  |  Solarized Ocean |  Solarized Ocean |  Solarized Ocean 
:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:
![](https://...Dark.png)  |  ![](https://...Ocean.png)  |  ![](https://...Ocean.png) |  ![](https://...Ocean.png) |  ![](https://...Ocean.png)


![alt text](https://github.com/Anzovi/GAN_Course/blob/homework_3/imgs/StyleGAN_Preporations.png)

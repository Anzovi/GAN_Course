# Глубокие генеративные модели (Deep Generative Models)  
# Зозуля Андрей Витальевич  

# Ссылки   
Ссылка на Colab: https://colab.research.google.com/drive/1ZK3uWp11BAr_6mH1YTygchkzDPHN1hBF?usp=sharing  
обучение stable diffusion 1.5 через Dreambooth wandb: https://api.wandb.ai/links/anzovitte/xnrkzn8v  
обучение stable diffusion 1.5 с использованием LoRa (rank = 2) wandb: https://api.wandb.ai/links/anzovitte/ih28b5wk  
обучение stable diffusion 1.5 с использованием LoRa (rank = 8) wandb: https://api.wandb.ai/links/anzovitte/zvhzkabm  
обучение stable diffusion 1.5 с использованием LoRa (rank = 24) wandb: https://api.wandb.ai/links/anzovitte/tti5s4z2  
# Выполнение работы
## 1. Собрать датасет от 15 изображений одного персонажа, кропнуть и заресайзить лица  
Кропнул и заресайзил, всего 27 изображений.

<p float="left">  
  <img src="https://github.com/Anzovi/GAN_Course/blob/homework_4/instance%20images/3_c66971e5.jpg" width="100" />
  <img src="https://github.com/Anzovi/GAN_Course/blob/homework_4/instance%20images/GettyImages.jpg" width="100" /> 
  <img src="https://github.com/Anzovi/GAN_Course/blob/homework_4/instance%20images/Margot-Robbi.jpg" width="100" />
  <img src="https://github.com/Anzovi/GAN_Course/blob/homework_4/instance%20images/Margot-Robbie.jpg" width="100" />
  <img src="https://github.com/Anzovi/GAN_Course/blob/homework_4/instance%20images/sd-aspect-1482916032-margotrobbiewhite.jpg" width="100" />
</p>  

## 2. Скачать предобученный чекпоинт SD1.5 с civitai.com и обучить Stable diffusion 1.5.  
Использовались промты:

--instance_prompt="a photo of sks woman face" токен на который мы хотим обучить персонажа  
--class_prompt="a photo of woman face" промт для регуляризации  

### Dreambooth обучение  

Desert   |  Forest  |  Kitchen |  Moon |  Street
:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:
![](https://github.com/Anzovi/GAN_Course/blob/homework_4/Dreambooth%20generated/desert-min.jpg)  |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/Dreambooth%20generated/forest-min.jpg)  |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/Dreambooth%20generated/kitchen-min.jpg) |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/Dreambooth%20generated/moon-min.jpg) |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/Dreambooth%20generated/street-min.jpg)

### Вывод: На обучение потребовалось 37 мин (class prompt уже был сгенерирован). Удобный способ генерации изображений через фаин тюн SD, собенно если есть готовые изображения для class prompt. Хуже сработало когда тело генерировалось в полный рост, нужно было добавить больше medium изображений.  

## 3. Обучить LoRA модель и сравнить лучший чекпоинт Unet и Lora  
### Rank 2  

Desert   |  Forest  |  Kitchen |  Moon |  Street
:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:
![](https://github.com/Anzovi/GAN_Course/blob/homework_4/LoRa%20rank%202%20generated/desert-min.jpg)  |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/LoRa%20rank%202%20generated/forest-min.jpg)  |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/LoRa%20rank%202%20generated/kitchen-min.jpg) |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/LoRa%20rank%202%20generated/moon-min.jpg) |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/LoRa%20rank%202%20generated/street-min.jpg)
### Время обучения 26m 35s  

### Rank 8  

Desert   |  Forest  |  Kitchen |  Moon |  Street
:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:
![](https://github.com/Anzovi/GAN_Course/blob/homework_4/LoRa%20rank%208%20generated/desert-min.jpg)  |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/LoRa%20rank%208%20generated/forest-min.jpg)  |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/LoRa%20rank%208%20generated/kitchen-min.jpg) |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/LoRa%20rank%208%20generated/moon-min.jpg) |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/LoRa%20rank%208%20generated/street-min.jpg)  
### Время обучения 26m 45s

### Rank 24  

Desert   |  Forest  |  Kitchen |  Moon |  Street
:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:
![](https://github.com/Anzovi/GAN_Course/blob/homework_4/LoRa%20rank%2024%20generated/desert-min.jpg)  |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/LoRa%20rank%2024%20generated/forest-min.jpg)  |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/LoRa%20rank%2024%20generated/kitchen-min.jpg) |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/LoRa%20rank%2024%20generated/moon-min.jpg) |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/LoRa%20rank%2024%20generated/street-min.jpg)  
### Время обучения 27m 18s

### Вывод: в отличии от Dreambooth способа обучения LoRa обучает только часть модели - адаптеры под нужную задачу, а веса основной модели замораживаются, поэтому качество генерации немного падает. Также можно заметить, что с повышением параметра размера Lora --rank качество генерации улучшается, за счет увелечения количества обучаемых параметров, но и увеличивается время обучения. Разница между рангом 2 и 8 ещё какая-то видна, но для 8 и 24 сложно сказать какая генерация лучше. 

### Сравнение Rank 24 и Dreambooth  

#### Dreambooth обучение  

Desert   |  Forest  |  Kitchen |  Moon |  Street
:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:
![](https://github.com/Anzovi/GAN_Course/blob/homework_4/Dreambooth%20generated/desert-min.jpg)  |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/Dreambooth%20generated/forest-min.jpg)  |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/Dreambooth%20generated/kitchen-min.jpg) |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/Dreambooth%20generated/moon-min.jpg) |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/Dreambooth%20generated/street-min.jpg)

#### Rank 24  

Desert   |  Forest  |  Kitchen |  Moon |  Street
:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:
![](https://github.com/Anzovi/GAN_Course/blob/homework_4/LoRa%20rank%2024%20generated/desert-min.jpg)  |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/LoRa%20rank%2024%20generated/forest-min.jpg)  |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/LoRa%20rank%2024%20generated/kitchen-min.jpg) |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/LoRa%20rank%2024%20generated/moon-min.jpg) |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/LoRa%20rank%2024%20generated/street-min.jpg) 

#### В целом если важно время обучения и размер хранимых весов модели то стоит использовать LoRa, качество генерации падает, но незначительно.

## 4. Добавить в pipeline ControlNet  

### Генерация положения частей тела под картину Моно Лизы  

Референс   |  Генерация  |
:-------------------------:|:-------------------------:
![](https://github.com/Anzovi/GAN_Course/blob/homework_4/ControlNet/Mona_ref.png)  |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/ControlNet/Mona.png) 

### Генерация положения частей тела под позы йоги  

Референс   |  Генерация  |
:-------------------------:|:-------------------------:
![](https://github.com/Anzovi/GAN_Course/blob/homework_4/ControlNet/Yoga_ref.png)  |  ![](https://github.com/Anzovi/GAN_Course/blob/homework_4/ControlNet/Yoga.png) 

### Вывод: нужно было загрузить в инстанс больше изображений с medium ракурсом, тогда изображения на расстоянии были бы лучше сгенерированы.

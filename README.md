# Глубокие генеративные модели (Deep Generative Models)
# Зозуля Андрей Витальевич
# Описание задачи Лр 2
1. Имплементирован CSPup блок
2. Имплементирован генератор по заданной архитектуре (без первого слоя 4x4x1024, тк в противном случае выкидывает CUDA out of memory)
3. Обучен имплементированный GAN
4. Вроде как некоторую сходимость получил (больше похоже на mode collapse)
<br />
<br />
# Ссылки
Весь код не отображается на гите, поэтому ссылка на DCGANmodded Colab: https://colab.research.google.com/drive/1kBS2nW1dYEVV8CVTWg2aI7mEsmekXrPa?authuser=1 <br />
<br />
Не уверен в правильности CSPup блока, поэтому решил переделать CSPblock и переименовал в ResGAN. <br />
ResConv_Try_1 :https://colab.research.google.com/drive/1dmPAMoKcW2OhCteyG-nu_sw4qolM1bTY?authuser=1 <br />
ResConv_Try_2 : https://colab.research.google.com/drive/1AT0QtyPTg6o82FhwsOyC9u-QVb6DdMvQ?authuser=1 <br />
ResConv_W_GAN_GP : https://colab.research.google.com/drive/1ELxgCOVlAJG9EQ-XxW62ogNlKVEXp2sS?authuser=1 <br />
<br />
# Первая архитектура CSPupblock
Сначала реализован DCGANmodded, получил результат в "DCGANmodded.ipynb", похоже что mode collapse, и предположил что реализовал CSPupBlock неправильно, поэтому переделал блок и сохранил в ResConv_Try_1. <br />
<br />
# Попытки с другой архитектурой CSPupblock
1. Попробовал clipping весов дискриминатора. Получил опять результат похожий mode collapse. <br />
2. Добавил разный learning rate при обучении в зависимости от лоссов генератора и дискриминатора, сохранил в "ResConv_Try_2.ipynb". Опять mode collapse. <br />
3. Попытался избавится от mode collapse за счет техник wasserstein GAN gradient penalty "ResConv_W_GAN_GP.ipynb", но уперся в ресурсы видеокарты. <br />
<br />
# Графики лоссов
В DCGANmodded много эксперементировал и не записывал лоссы. <br />
Ссылка на первую часть для DCGANmodded wandb: https://api.wandb.ai/links/anzovitte/6znowx8r <br />
Ссылка на вторую часть для ResGan wandb: https://api.wandb.ai/links/anzovitte/615o22sz <br />

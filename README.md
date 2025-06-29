# VISION_YOLO_BLIP
Проект распознавания предметов на столе. Запустить r requirements.txt. Данные надо распаковать в файте Video.v9i.yolov11.zip в корневую директрю и запустить файл *.ipynb.

Данные были размечены через систему Roboflow.
train: ../train/images
val: ../valid/images
test: ../test/images

nc: 13
names: ['basket', 'dish with food', 'fork', 'glass empty', 'glass plate', 'glass with tea', 'knife', 'paper', 'redpaper', 'spoon', 'sugar bag', 'table', 'tea pot']

roboflow:
  workspace: aalex11
  project: video-ytrrz
  version: 9
  license: CC BY 4.0
  url: https://universe.roboflow.com/aalex11/video-ytrrz/dataset/9
Код интегрирует метод YOLO и большую модель изображений и видео BLIP, которая генерирует подсказки к распознанным объектам на видео к каждому датафрему типа ("[Frame 200] YOLO: fork, glass plate, glass empty, dish with food, knife, table, tea pot, paper, redpaper, basket, glass with tea, spoon | BLIP: a person is sitting at a table with a plate of food")
Описание вывода:
Тренировочные метрики (обновляются каждый эпизод обучения):
box_loss — ошибка предсказания границ объектов (боксов). Чем меньше, тем лучше.

cls_loss — ошибка классификации объектов. Тоже должно снижаться.

dfl_loss — "Distribution Focal Loss", метрика точности по координатам бокса. Чем ниже, тем точнее.

GPU_mem — использованная видеопамять.

Instances — сколько объектов обрабатывалось в эпоху.

Size — размер входного изображения (например, 640×640).

Валидационные метрики (точность модели на проверочных данных):
Box(P) (Precision) — точность: сколько из предсказанных объектов — правильные.

R (Recall) — полнота: сколько из реальных объектов удалось найти.

mAP50 — средняя точность при IoU = 0.5. Основной показатель качества.

mAP50-95 — средняя точность при IoU от 0.5 до 0.95 (жёстче и объективнее)

В среднем метрики. 

Precision (mean): 0.808
Recall (mean): 0.836
mAP@0.5: 0.863
mAP@0.5:0.95: 0.690
F1-score: 0.821
Изображение Roboflow3.png - показывает изменения метрик по ходу обучения в Roboflow.
Обучать желательно не менее чем на 50 эпохах. По умоляанию 10.
Запуск альтернативной модели распознавания модели обученной на YOLO 11 разврнутая на сайте Roboflow https://app.roboflow.com/workflows/embed/eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ3b3JrZmxvd0lkIjoibFNxT2NkbDc5d2h6dHFqb242TEkiLCJ3b3Jrc3BhY2VJZCI6IkhsSzFwYWtDeUNYWHlLMHdUeHQ1aGhwdElnYTIiLCJ1c2VySWQiOiJIbEsxcGFrQ3lDWFh5SzB3VHh0NWhocHRJZ2EyIiwiaWF0IjoxNzUxMjEyNDAxfQ.G_JGtwYZU1f8EKTKeiszxSHpK39J2PGWxffmM5H95aM


На модели Roboflow YOLO 11
mAP@50 
88.3%
Precision 
76.4%
Recall 
79.6%

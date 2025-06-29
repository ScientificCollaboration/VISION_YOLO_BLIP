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

Запуск альтернативной модели распознавания модели обученной на YOLO 11 разврнутая на сайте Roboflow https://app.roboflow.com/workflows/embed/eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ3b3JrZmxvd0lkIjoibFNxT2NkbDc5d2h6dHFqb242TEkiLCJ3b3Jrc3BhY2VJZCI6IkhsSzFwYWtDeUNYWHlLMHdUeHQ1aGhwdElnYTIiLCJ1c2VySWQiOiJIbEsxcGFrQ3lDWFh5SzB3VHh0NWhocHRJZ2EyIiwiaWF0IjoxNzUxMjEyNDAxfQ.G_JGtwYZU1f8EKTKeiszxSHpK39J2PGWxffmM5H95aM

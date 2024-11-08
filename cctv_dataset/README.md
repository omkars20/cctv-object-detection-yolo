
-- data set struture --

cctv_dataset/
├── data.yaml
├── train/
├── valid/
└── test/


step1 : set up the env

pip install torch torchvision torchaudio numpy pandas matplotlib


step2 : clone the repo

git clone https://github.com/ultralytics/yolov5
cd yolov5
pip install -r requirements.txt


step3 : 

configure the data.yaml

train: /path/to/cctv-dataset/train
val: /path/to/cctv-dataset/valid
test: /path/to/cctv-dataset/test

nc: <number_of_classes>
names: ['class1', 'class2', 'class3']


step4: Train the model

python train.py --img 640 --batch 16 --epochs 50 --data /path/to/cctv-dataset/data.yaml --weights yolov5s.pt --project cctv-yolo-project --name custom-yolo


step5 : Evaluate the model

python detect.py --weights runs/train/custom-yolo/weights/best.pt --source /path/to/video.mp4 --img 640 --conf 0.4


step6 : run the inference on video

python detect.py --weights runs/train/custom-yolo/weights/best.pt --source /path/to/video.mp4 --img 640 --conf 0.4



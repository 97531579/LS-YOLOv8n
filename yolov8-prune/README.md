------------------ train base model ------------------
model = YOLO('ultralytics/cfg/models/v8/yolov8n.yaml')
model.load('yolov8n.pt') # loading pretrain weights
model.train(data='/root/data_ssd/dataset/data_exp.yaml',
            cache=True,
            imgsz=640,
            epochs=300,
            batch=32,
            close_mosaic=30,
            workers=8,
            device='0',
            optimizer='SGD', # using SGD
            # resume='', # last.pt path
            # amp=False # close amp
            # fraction=0.2,
            project='runs/train',
            name='yolov8n-visdrone',
            )
Note: Optional pruning algorithms are in ultralytics/models/yolo/detect/compress.py

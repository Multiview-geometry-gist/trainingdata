# trainingdata

huggingface에 올라와있는 training set  
https://huggingface.co/datasets/ccvl/SpatialReasonerTrain-RL  
| 항목 | 값 |
|------|-----|
| **question_index** | 2121 |
| **question** | “Consider the real-world 3D locations… Which side of the bird is facing the camera?” |
| **choices** | A: front / B: back / C: left / D: right |
| **bounding_box** | `{ bbox_3d: [0, 1, 2.9], label: "the bird" }` |
| **direction** | `{ front_dir: [0.1, -0.1, -1], left_dir: [-1, 0.2, -0.1] }` |
| **answer** | A |
| **answer_name** | front |
| **category** | orientation_viewpoint |
| **image_filename** | 0029d8bae76d9a79.jpg |  
<img width="1024" height="757" alt="image" src="https://github.com/user-attachments/assets/8964114a-0cd6-4fb8-90cc-03bb458aa86a" />  
https://s3.amazonaws.com/open-images-dataset/train/{image_id}.jpg => 이걸로 이미지 확인  




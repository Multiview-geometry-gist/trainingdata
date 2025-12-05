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
<img width="512" height="378" alt="image" src="https://github.com/user-attachments/assets/8964114a-0cd6-4fb8-90cc-03bb458aa86a" />  
https://s3.amazonaws.com/open-images-dataset/train/{image_id}.jpg => 이걸로 이미지 확인  

10도 로테이션 novel view   
<img width="553" height="415" alt="image" src="https://github.com/user-attachments/assets/a1edc4c7-ef21-44b0-80b3-1dc42ff07184" />  
dirction vector에 대해서 그냥 rotation matrix 곱해주기  
<img width="360" height="107" alt="image" src="https://github.com/user-attachments/assets/af019bb1-d3ca-4980-b3d4-b817e852439b" />  
front_dir_rot = [ 0.11584, -0.08112, -1     ]  
left_dir_rot  = [-1.01955,  0.02331, -0.1   ]  
너무 많이 회전하면 facing the camera 같은 QA가 틀릴수 있음  






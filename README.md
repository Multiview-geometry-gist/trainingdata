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
<img width="512" height="378" alt="image" src="https://github.com/user-attachments/assets/8964114a-0cd6-4fb8-90cc-03bb458aa86a" />  <br>
https://s3.amazonaws.com/open-images-dataset/train/{image_id}.jpg => 이걸로 이미지 확인  <br>
10도 로테이션 novel view   <br>
<img width="553" height="415" alt="image" src="https://github.com/user-attachments/assets/a1edc4c7-ef21-44b0-80b3-1dc42ff07184" />  <br>
dirction vector에 대해서 그냥 rotation matrix 곱해주기  <br>
<img width="360" height="107" alt="image" src="https://github.com/user-attachments/assets/af019bb1-d3ca-4980-b3d4-b817e852439b" />  <br>
front_dir_rot = [ 0.11584, -0.08112, -1     ]  <br>
left_dir_rot  = [-1.01955,  0.02331, -0.1   ]  <br>
너무 많이 회전하면 facing the camera 같은 QA가 틀릴수 있음  <br>
<img width="465" height="350" alt="image" src="https://github.com/user-attachments/assets/02822e01-4af1-4713-9272-eaa66035e788" />    <br>
<img width="453" height="101" alt="image" src="https://github.com/user-attachments/assets/6300629f-5d29-45da-be5a-a65c020c0db6" />  <br>
front_rot = (0.08412, -0.11596, -1)    <br>
left_rot  = (-0.95108, -0.37136, -0.1)  <br>  

3DSRBench orientation 카테고리 데이터 포맷 <br>  
## 3D Spatial Reasoning Samples

| index       | question                                                                                                                                                                                                 | A            | B            | C   | D   | answer | category                | image_source | image_url                                                             |
|-------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------|--------------|-----|-----|--------|--------------------------|---------------|------------------------------------------------------------------------|
| 01H3EK4T    | Consider the real-world 3D locations and orientations of the objects. If I stand at the dog's position facing where it is facing, is the man in front of me or behind me?                                | in front of  | behind       | null | null | B      | orientation_in_front_of | MS-COCO       | ![](http://images.cocodataset.org/train2017/000000560373.jpg)         |
| 0BGU2CVW    | Consider the real-world 3D locations and orientations of the objects. If I stand at the person in white sweater's position facing where it is facing, is the blue arrow sign on the left or right of me? | on the left  | on the right | null | null | B      | orientation_on_the_left | MS-COCO       | ![](http://images.cocodataset.org/train2017/000000412793.jpg)         |
| 0EI5G56U    | Consider the real-world 3D locations and orientations of the objects. Which side of the grey SUV in the back is facing the camera?                                                                       | front        | left         | back | right | A      | orientation_viewpoint   | MS-COCO       | ![](http://images.cocodataset.org/train2017/000000518850.jpg)         |







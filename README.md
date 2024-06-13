# Application-of-YOLOv8-in-Taiwan-Vehicle-Flow-Tracking-System
### 使用YOLOv8應用於臺灣車流追蹤系統 | Taiwan Vehicle Flow Tracking System

學生：蘇羿璇 Yi-Hsuan Su 

指導教授：黃承龍 Dr. Cheng-Lung Huang 

國立高雄科技大學資訊管理系碩士班  National Kaohsiung University of Science and Technology Information Management Master's Program

---

#### 摘要 | Abstract

臺灣車流追蹤系統可以實地捕捉道路上的車輛位置和移動情況。提供即時監測幫助應對交通擁堵、事故和其他交通事件，以提高道路安全性和流動性。

The Taiwan Vehicle Flow Tracking System captures real-time vehicle positions and movements on roads, aiding in monitoring traffic congestion, accidents, and other events to enhance road safety and mobility.

---

#### 使用情境說明(動機) | Contextual Description (Motivation)

我們置身於台灣一個繁忙的都會區，道路上充滿了車輛、行人和各種交通挑戰，尤其是在上下班高峰時段。我們意識到，有效的交通管理系統是必要的，以應對日益增長的車流量、減少擁堵和提高道路安全性。在這種情境下，我們想做一個屬於台灣的車流追蹤系統，能幫助交通單位制定更有效的交通政策，讓人們能夠減少通勤時間，提高生活品質。

We find ourselves in a bustling urban area of Taiwan, where roads are filled with vehicles, pedestrians, and various traffic challenges, especially during rush hours. Recognizing the necessity for effective traffic management systems to handle increasing traffic volume, reduce congestion, and enhance road safety, we aim to develop a Taiwan-specific vehicle flow tracking system. This system will assist transportation authorities in formulating more effective traffic policies, thereby reducing commute times and improving quality of life.

---

#### 使用的資料集介紹 | Introduction to Dataset Used

A. 參考連結：[Car-Counting Repository](https://github.com/redeagle17/Car-Counting)  
使用 YOLO 模型進行物體檢測，並使用 SORT 算法進行目標追蹤，同時計算穿越指定計數線的車輛數量。

A. Reference Link: [Car-Counting Repository](https://github.com/redeagle17/Car-Counting)  
Utilizes YOLO model for object detection, SORT algorithm for object tracking, and calculates vehicle counts crossing specified counting lines.

---

#### 使用畫面結果展示 | Visual Results Display

- 預測圖片 | Predicted Images
- 車流追蹤偵測的過程 | Vehicle Flow Tracking Detection Process

---

#### 系統建置之步驟 | System Setup Steps

A. 載入需要使用到的模組與套件，例如 YOLO、SORT、cv2。  
B. 選擇想要辨識的影片檔案，並寫入 VideoWriter 儲存辨識的影片。  
C. 定義 YOLO 模型預測結果中可能的類別名稱列表。  
D. 載入 yolov8n.pt 權重檔案。  
E. 從檔案讀取遮罩圖像 (mask.png)，用於指定計數區域。  
F. 使用 SORT 目標追蹤器。  
G. 使用 YOLO 模型檢測區域中的物體，如果檢測到的物體是車輛類別且信度大於 0.3，則進行累計的動作，並在影像上顯示計數值。

A. Load necessary modules and packages such as YOLO, SORT, and cv2.  
B. Choose the video file for recognition and write a VideoWriter to save the recognized video.  
C. Define the list of possible class names from YOLO model predictions.  
D. Load the yolov8n.pt weight file.  
E. Read a mask image (mask.png) from file for specifying counting regions.  
F. Utilize the SORT object tracker.  
G. Use YOLO model to detect objects in the specified region. Accumulate counts for objects identified as vehicles with confidence greater than 0.3 and display count values on the image.

---

#### 結論與心得 | Conclusion and Insights

- 執行 SORT 需搭配 sort.py 檔案，否則無法執行；目前僅完成單向部分的車流計算，未來將持續新增功能。
- 採用遮罩的技術在 YOLO 相關文獻中較少見，為一項有趣的實驗。
- 在取得目標類別時，不明原因地持續偵測到 "bus"，這部分仍須進一步釐清。
- 系統模型使用官方提供的 yolov8n.pt 模型，未來可透過建置自有資料集進行模型訓練。

- Execution of SORT requires inclusion of sort.py for proper functionality. Currently, only one-way traffic flow calculation has been implemented, with plans for continued feature expansion.
- The use of masking techniques in YOLO-related literature is less common, making it an interesting experiment.
- There's an ongoing issue with consistently detecting "bus" as the target class, which requires further investigation.
- The system model utilizes the official yolov8n.pt model, with future plans to train models using custom datasets.

---

#### 分工 | Division of Labor

組長  
學號：F111118107  
姓名：蘇羿璇  
負責工作：程式撰寫、報告彙整  

Team Leader  
Student ID: F111118107  
Name: 蘇羿璇  
Responsibilities: Program Coding, Report Compilation  

---

#### 參考資料 | References

A. 使用 YOLO 模型進行物體檢測，使用 SORT 算法進行目標追蹤，同時計算穿越指定計數線的車輛數量。  
參考連結：[Car-Counting Repository](https://github.com/redeagle17/Car-Counting)

B. 使用 Ultralytics YOLO 進行模型訓練  
參考連結：[Ultralytics YOLO Training Documentation](https://docs.ultralytics.com/modes/train/)

C. COCO123 資料集  
參考連結：[COCO128 Dataset](https://github.com/ultralytics/ultralytics/blob/main/ultralytics/cfg/datasets/coco128.yaml)

A. Utilizes YOLO model for object detection, SORT algorithm for object tracking, and calculates vehicle counts crossing specified counting lines.  
Reference Link: [Car-Counting Repository](https://github.com/redeagle17/Car-Counting)

B. Utilizes Ultralytics YOLO for model training.  
Reference Link: [Ultralytics YOLO Training Documentation](https://docs.ultralytics.com/modes/train/)

C. COCO123 Dataset  
Reference Link: [COCO128 Dataset](https://github.com/ultralytics/ultralytics/blob/main/ultralytics/cfg/datasets/coco128.yaml)

---

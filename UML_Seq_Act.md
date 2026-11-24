# 作業 4：UML 類別圖、循序圖與活動圖

# 1. UML 類別圖

<img width="1480" height="947" alt="image" src="https://github.com/user-attachments/assets/db3bf864-3dd5-48a1-96d6-54b78ed39b77" /><br>
<br>

## 說明

| 類別／模組 | 責任 |
| :--- | :--- |
| `CameraService`（`lib/server.py`） | 管理所有攝影機；提供上傳與監看的 WebSocket、MJPEG 串流（FR-2）、推論迴圈與廣播 |
| `CameraState`（`dataclass`） | 保存單一攝影機的最新影格、偵測結果、事件次數、在線數與監控端連線 |
| `YoloDetector`（`lib/yolo.py`） | 載入 YOLO 模型並提供 `detect(frame)`，輸出偵測結果（FR-1） |
| `Detection` | 單一偵測結果：類別、信心度與正規化（0~1）邊界框 |
| `WebRouter`（`lib/web.py`） | 回傳首頁、手機頁、上傳頁與監控頁（FR-3） |

> 為了讓圖清楚，只畫出主要類別與主要方法／欄位。`CameraService`、`YoloDetector`、`WebRouter` 在程式中是模組（函式與全域變數），圖中以 `«module»` 類別表示；`Detection` 在程式中是字典（`dict`），圖中以類別呈現其欄位。

<br>

______
# 2. 使用案例對應的循序圖與活動圖

以下三個使用案例對應 `hw3.md` 的使用案例圖：UC2、UC4、UC5。

## UC2：上傳即時影像（include UC3 YOLO 事故偵測）

### 循序圖
<img width="1789" height="1056" alt="image" src="https://github.com/user-attachments/assets/e8ebaccf-8fb0-47e9-b963-c26e82aea5e4" /><br>
<br>

### 活動圖
<img width="918" height="1859" alt="image" src="https://github.com/user-attachments/assets/7f640cd0-185a-4de8-b6ab-21b56df44af6" /><br>
<br>

## UC4：即時監看偵測結果

### 循序圖
<img width="1104" height="820" alt="image" src="https://github.com/user-attachments/assets/0f08c744-cee5-4c8c-89c2-e59ed38fb14b" /><br>
<br>

### 活動圖
<img width="822" height="1804" alt="image" src="https://github.com/user-attachments/assets/eebffe13-3949-476a-959b-c166562e581a" /><br>
<br>

## UC5：觀看 MJPEG 即時串流

### 循序圖
<img width="1446" height="879" alt="image" src="https://github.com/user-attachments/assets/d4f62134-9165-4f7d-a4a0-bed579eee840" /><br>
<br>

### 活動圖
<img width="858" height="1696" alt="image" src="https://github.com/user-attachments/assets/e9d2867e-b070-4dd7-a010-e43fe707e189" /><br>

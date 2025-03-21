# Plano Detection and Classification

## Project Description
This project is a computer vision-based plano detection and classification system designed to automatically count votes from ballot papers. It leverages YOLO (You Only Look Once) models to detect number boxes and black dots on ballot papers, then classifies the results into votes for three candidate pairs (paslon). The system includes image processing, data augmentation, and statistical calculations to evaluate prediction accuracy.

## Key Features
1. **Number Box Detection**: Identifies and crops boxes containing vote numbers from ballot images.
2. **Black Dot Detection**: Analyzes the position of black dots to determine votes on the ballot.
3. **Image Augmentation**: Generates image variations (rotation, blur, grayscale, resize) to enhance detection accuracy.
4. **Automatic Rotation**: Rotates images if detected upside-down based on the position of vote boxes.
5. **Vote Compilation**: Combines results from number and dot detection to calculate votes per candidate pair.
6. **Accuracy Evaluation**: Calculates error percentage by comparing predictions with ground truth data.

## Technologies Used
- **Programming Language**: Python
- **Main Libraries**:
  - Ultralytics YOLO (for object detection)
  - OpenCV (cv2) (for image processing)
  - NumPy (for numerical operations)
  - Matplotlib (for image visualization)
  - Pandas (for data processing)
- **YOLO Models**:
  - `box_number_model.pt`: Detects number boxes
  - `number_2.pt`: Classifies numbers
  - `circle_number_model.pt`: Detects dot boxes
  - `final_model.pt`: Detects black dots
  - `dot_boxes_detection.pt`: Detects dot boxes comprehensively

## How to Run
### Prerequisites
- Python 3.8 or higher
- Install dependencies:
  ```bash
  pip install ultralytics opencv-python numpy matplotlib pandas
  ```

### Steps
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/IvanSholana/C-Plano-Detection.git
   ```
2. **Prepare the Dataset**:
   - Place ballot images in the `./dataset/Test/` folder.
   - Ensure file names follow the format (e.g., `TPS_501.jpg`).
3. **Prepare Models**:
   - Place YOLO model files (`*.pt`) in the `./models/` folder.
4. **Run the Program**:
   ```bash
   python main.py
   ```
5. **Output**:
   - Vote prediction CSV: `Prediksi_Nama_Tim.csv`
   - Vote percentage CSV: `gammafest_results2.csv`

## Sample Results
Here are partial vote prediction results from 700 polling stations (TPS):
```
TPS_501.jpg: [77, 141, 18]
TPS_502.jpg: [122, 98, 10]
TPS_503.jpg: [41, 165, 23]
...
TPS_700.jpg: [62, 6, 0, 101, 1, 31, 3]
```
- Column 1: Votes for Paslon 1
- Column 2: Votes for Paslon 2
- Column 3: Votes for Paslon 3

**Error Percentage**: 0.0% (based on comparison with ground truth).

## Contribution
1. Fork this repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -m "Added feature X"`).
4. Push to your branch (`git push origin feature-branch`).
5. Create a Pull Request.

## License
This project is licensed under the [MIT License](LICENSE).

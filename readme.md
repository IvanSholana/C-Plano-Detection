Here’s the English version of the README tailored for your GitHub portfolio based on the document you provided:

---

# Plano Detection and Classification

**Date**: March 21, 2025  
**Created by**: [Your Name/Your Team]  
**Organization**: [Your Organization, if applicable]  

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

## Code Structure
1. **Model Definition** (`0.2`): Loads pre-trained YOLO models.
2. **Image Augmentation** (`0.3`): Creates image variations to improve model robustness.
3. **Image Rotation** (`0.4`): Rotates images if detected upside-down.
4. **Number Detection** (`0.5`):
   - Retrieves number boxes (`0.5.1`)
   - Classifies numbers from boxes (`0.5.2`)
5. **Dot Detection** (`0.6`):
   - Crops dot boxes (`0.6.1`)
   - Counts votes from dots (`0.6.2`)
   - Determines split count for dot boxes (`0.6.3`)
6. **Main Program** (`0.7`): Integrates all functions to process the dataset and generate vote predictions.

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
   git clone https://github.com/[username]/[repository-name].git
   cd [repository-name]
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

## Contact
For questions or suggestions, reach out to me at [your email] or open an [issue](https://github.com/[username]/[repository-name]/issues) in this repository.

---

**Notes**: 
- Replace `[username]`, `[repository-name]`, `[Your Name/Your Team]`, and `[your email]` with your own information.
- Adjust the "How to Run" section if you have a specific main file (e.g., `main.py`).
- Add a `LICENSE` file to your repository if you wish to include a license.

I hope this README enhances your GitHub portfolio! Let me know if you need any adjustments or additions.
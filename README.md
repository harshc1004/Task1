# Task1

# Train Video Processing Assignment (Side View):

## Overview:
This project implements a video processing system for a side-view train video, splitting it into smaller videos of each coach, counting the number of coaches, organizing the output into structured folders, extracting frames, detecting doors (open/closed), annotating images, and generating a PDF report with minimal images to identify the full wagon.

## How to Set Up the Project:
1. **Install Dependencies:**: Ensure you have Python 3.x installed. Install required libraries by running the following command in your terminal or Colab environment:
   
2. **Download Input Video:**: Obtain the raw video file (e.g., `DHN-side-view-lower-2025-08-31-11-24-27-47.mp4`) from the "Raw_video inside DHN-wagon" Google Drive folder.

3. **Run the Script:** Upload the video to your Colab environment, then run the script with: python main('/content/DHN-side-view-lower-2025-08-31-11-24-27-47.mp4', 'processed_output')

## Key Features Implemented:
**Video Splitting:** Uses OpenCV's background subtraction to detect gaps between coaches and splits the input video into individual coach segments.

**Coach Counting:** Reports the total number of coaches detected in the video.

**Frame Extraction:** Extracts every 10th frame from each coach video and saves them as images in respective folders.

**Component Detection:** Identifies doors (open or closed) using contour detection based on area, aspect ratio, and intensity, with annotations added to images.

**Coverage Report:** Generates a PDF report with one annotated image per coach to cover the full wagon length (nose to tail).

## Limitations or Assumptions Made:
**Assumptions:** The script assumes a fixed camera capturing a side-view train moving horizontally with clear gaps between coaches. The train number is hardcoded as '12309'; update if different.

**Limitations:** Background subtraction may fail if the background varies (e.g., due to lighting or shadows); tune gap_threshold and min_coach_frames if needed. Door detection relies on basic contour analysis, which may misclassify doors in complex scenes; adjust parameters (e.g., area range, intensity threshold) for accuracy. The solution is optimized for the provided video and may require tuning for other inputs.

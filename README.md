Pedestrian Interaction Analysis AI
A tool developed to analyze pedestrian interactions in natural environments, using Python, deep learning, and computer vision techniques. This tool automatically identifies and tracks pedestrians from uncalibrated RGB camera footage, making it ideal for use in urban planning, public spaces, and pedestrian behavior studies.

In crowded areas like city centers or parks, understanding how pedestrians avoid collisions is crucial for improving public safety and the design of shared spaces. I developed this AI-driven pedestrian interaction analysis tool, which processes real-time video streams to extract data on pedestrian behaviors such as path deviation, medial-lateral separation, and crowd dynamics.

Key Features:

Pedestrian Detection: Detects humans in the video frame using the FairMOT algorithm, which is based on YOLOv5 architecture.
Trajectory Analysis: Tracks walking trajectories and calculates distance and deviation between pedestrians in a frame.
Crowd Interaction: Identifies factors like crowd size, pedestrian distraction, and mobility constraints that influence collision avoidance behavior.
You can find more details in my post: Pedestrian Interaction Analysis AI


Requirements:
You will need the following to run this code:

Python 3.6+
OpenCV (CV2) 4.5.0+
numpy 1.18.5
argparse
FairMOT pre-trained models and YOLOv5 configurations
For pedestrian detection:
Download the FairMOT weights and configuration files from:
FairMOT Weights **Download**

System Requirements:
A good GPU is recommended for faster processing, although the code is optimized for CPU usage as well.

File Structure:

main.py: Detects and calculates pedestrian trajectories and interactions.
utils.py: Functions to compute distances and perspective transformations.
plot.py: Functions for rendering results, including bird’s-eye view visualizations.
models/: Contains the pre-trained models and configuration files.
data/: Sample videos for testing.
output/: Stores processed frames and interaction results.
output_vid/: Stores final output videos.
Usage: To run with the default directory structure:

bash
Copy code
python main.py
If the paths for models or input videos are different:

bash
Copy code
python main.py --model='model path' --video_path='video file path' --output_dir='output directory' --output_vid='output video directory'
How It Works:

Run the main script with the following command:
bash
Copy code
python main.py
A graphical interface will appear, allowing you to draw a region of interest (ROI) and set a distance scale using 8 reference points. Four points will define the area of analysis, while the others help measure distances between pedestrians.
The tool transforms the ROI into a bird’s-eye view to ensure accurate distance measurements and trajectory mapping.
FairMOT detects pedestrians in each frame, tracks their movements, and calculates the medial-lateral separation and deviation from their initial walking paths. These results are visualized both as a bird’s-eye view and on the original video frame.
Output:

Bird’s-eye View: Shows pedestrian trajectories and distance lines between them.
Processed Frames: Annotated video frames showing deviations and crowd dynamics.
Find more information on this project in my detailed post: Pedestrian Interaction Analysis AI




## Acknowledgements

This project is based on the original work by Deepak Birla. The original code can be found [here](link to the original repository).

## Modifications

- Refactored the codebase to improve readability and performance.
- Replaced YOLOv3 with YOLOv5 for human detection.
- Added new functionalities for enhanced user interaction.
- Updated dependencies to the latest versions.
- Fixed various bugs and improved error handling.
- Enhanced the user interface with a new design.

## Contact

Modified by Mohammadamin Nikmanesh  
Email: amin.nikmanesh@gmail.com  
Date: 2024-05-20

**##References**:

FairMOT: GitHub Link
Perspective Transformations with OpenCV: Documentation Link
License:
This project is open-source and licensed under the MIT License.

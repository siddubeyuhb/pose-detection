# pose-detection
Pose detection done for a physical therapy of the knee video using mediapipes library

Instructions:

- Run the jupyter notebook and change the video source accordingly to model and obtain 
the resultant video as 'output.mp4'

Notes:

- ML done on Pose Detection.ipynb for KneeBendVideo.mp4

- Model uses mediapipe library for object detection 

- Pose function from the library used to estimate the locations of the left hip, knee and ankles

- mediapipe.solutions.pose.Pose is used with the parameters set to (model_complexity=2, min_tracking_confidence = 0.9)

- Process the single image frame using mediapipe.solutions.pose.Pose.process and using .pose_landmarks find the 
coordinates of the locations of the required bodyparts

- After getting the locations, angle of the chord from the hip to the knee with respect to the horizontal
surface found using trignometry

- Similarly, angle of the chord from the ankle to the knee with respect to the horizontal surface found

- Finally, since the bent knee forms a triangle with the horizontal surface, traingle's angle sum property used
to find the angle (bendness) of the knee

- Now, as the model runs frame by frame, the angle of the knee is calculated and displayed on the screen

- A flag is set to display "Keep your knee bent" when the angle of the knee is less than 140 degrees

- A counter is also displayed for every successful bent of the knee lasting more than 8 seconds

- Program stops if last frame is empty and returns the output video file

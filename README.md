# open-web-cam
Let's capture a video from camera(in-built camera in laptop), and convert it into grayscale and then display it,just the initial way to start project in computer vision.
To capture a video, we need a video capture object.
cap = cv2.VideoCapture(0)
As i am using only one camera that is my web cam, so i simply pass 0.But if anyone is using 2 cameras at a time, then he/she can use both the cameras at the same time by passing 1.
cap.read() returns a bool (True/False). If frame is read correctly, it will be True. So Anyone can check end of the video by checking this return value.
Sometimes, cap may not have initialized the capture. In that case, this code shows error. Anyone can check whether it is initialized or not by the method cap.isOpened(). If it is True, OK. Otherwise open it using cap.open()
After reading a video file, we can display the video frame by frame. A frame of a video is simply an image and we display each frame the same way we display images, i.e., we use the function imshow().
As in the case of an image, we use the waitKey() after imshow() function to pause each frame in the video. In the case of an image, we pass ‘0’ to the waitKey() function, but for playing a video, we need to pass a number greater than ‘0’ to the waitKey() function. This is because ‘0’ would pause the frame in the video for an infinite amount of time and in a video we need each frame to be shown only for some finite interval of time, so we need to pass a number greater than ‘0’ to the waitKey() function. This number is equal to the time in milliseconds we want each frame to be displayed.
While reading the frames from a webcam, using waitKey(1) is appropriate because the display frame rate will be limited by the frame rate of the webcam even if we specify a delay of 1 ms in waitKey.
Once that's done, we use cv2.destroyAllWindows() to close everything.

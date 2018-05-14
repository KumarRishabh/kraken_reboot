# GaussianMixtureModel

It is a ROS based implementation of Gaussian Mixture Model(GMM) algorithm for object detection.

ROS WORKFLOW  :-

(input_image) ---(input)--->>  (object_detect) ---(state)--->> (print)

USAGE  :-

window 1:     
               rosrun </directory name/> pub_r -vid </location of video/>    
  
    **takes location of video as input and sends it to the node- object_detect via topic- input.
  
    
window 2:      
               rosrun </directory name/> gmm_r
  
    **subscribes to the topic- input, performs algorithms on the image and publishes it on the topic- state
  
  .
window 3:      
               rosrun </directory name/> sub_r
  
     **node print subcribes to the topic- state and prints the location of buoys in the video.

window 4:
			   rosrun </director name/> kalman_r

	 **Nodes runs a kalman instance to provide template to the KF-EBT code.
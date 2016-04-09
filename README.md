# DecaWave Localization ROS Node
Localization ROS node for the DecaWave EVK1000. This ROS node uses known
anchor positions to solve for the position of a tag. This approach uses
a non-linear optimization method to determine the position of the tag which
makes it more resilient to noise than naive geometric approaches. Also, I use
Kalman filter to reduce the noise in the position signal.

# Installation
    cd $CATKIN_WS
    git clone https://github.com/wallarelvo/decawave_localization.git
    cd decawave_localization
    pip install -r requirements.txt

# Running
1. Turn on three or more anchors and one tag
2. Record the locations of the anchors relative to a known origin in
`launch/localize.launch` or in `param/demo.yaml`
3. Run `roslaunch decawave_localization localize.launch` with the appropriate
parameters for your current setup
4. Open RViz or run `rostopic echo /radio_pose` to see the current pose of
your tag

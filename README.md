이 리포지토리는 (https://github.com/felixchenfy/ros_record_rgbd_images)를 포크한 것입니다.
최신 버전과 맞지 않는 부분이 많아서 그냥 다운 받아서 쓰면 에러 발생할 수 있습니다. 
코드부분은 최신 버전으로 업데이트해서 올렸으며, 나머지 부분은 가상환경을 써서 환경을 맞춰 사용했습니다.

# Press key to record color/depth images from ROS topics

Keys:
* `a`: Save a single pair of color/depth images to folder.
* `s`: Start continuous recording. (Continuously saving color/depth images to folder.)
* `d`: Stop continuous recording.

Example of usage:
```
rosrun ros_record_rgbd_images record_color_depth_images_to_disk.py \
    --depth_topic camera/aligned_depth_to_color/image_raw \
    --color_topic camera/color/image_raw \
    --dst_folder output \
    --max_frame_rate 10.0 \
    --save_to_separate_folder true
```

Test with local data:
```
bash run_unit_test.py
```

Test on Realsense:
```
roslaunch ros_record_rgbd_images run_realsense.launch 
roslaunch ros_record_rgbd_images run_record_images.launch 
```

# cppKinect
A very **user-friendly** and **fast** way to use *Microsoft Kinect* (first version) with **C++**.
*Microsoft SDK* is an extremely useful tool to create programmes with Kinect devices, but it is not so ready-to-use with C++ programming language. 
With **cppKinect** you can start programming and acquire RGB and depth images just in 5 minutes. Then, when you have time and desire, you could check the open source code to understand all the details about Microsoft device. 
You can consider cppKinect as a *wrapper* of *Microsoft SDK 1.8*! Enjoy!
Please, contact me for any suggestion or questions.

***

**Prerequisites:**
- OpenCV (tested with 2.4.13)
- Microsoft Kinect SDK (v1.8)

***

**How to use:**
* Import all files (.cpp, .h) in your project. _Acquisitionkinect2_ is the acquisition from Microsoft Kinect One, _frameset.h_ is the container for all data extracted from the device;
* Create a loop and call the method `getframe(frameset)`;
* Get the data from the frameset
* That's all!

***

**Code sample**
```
int main(){

 ...
 
 Acquisition *_pkinect = nullptr;
 FrameSet frame;

 _pkinect = new AcquisitionKinect1();

 while(1){
   _pkinect->getFrame(frame);
}
```

***
**Data inside frameset**:
* Kinect version (`int kinectVersion`)
* RGB (`cv::Mat RGB`)
* Depth with skeleton (`cv::Mat depth`)
* Depth without skeleton 3 channels (`cv::Mat depthWithoutSkeleton`)
* Depth without skeleton 1 channels (`cv::Mat depthWithoutSkeleton1ch`)
* Joint Real (`std::vector<tripletPoint> bodyJoint`)
* Joint RGB (`std::vector<tripletPoint> bodyJointRGB`)
* Joint Depth (`std::vector<tripletPoint> bodyJointDepth`)
* Head Pitch (`int pitch`)
* Head Roll (`int roll`)
* Head Yaw (`int yaw`)

***

**Skeleton Joint names:**
```
enum jointNames{
    FS_head,
    FS_neck,
    FS_shoulderCenter,
    FS_spineShoulder,
    FS_shoulderRight,
    FS_elbowRight,
    FS_wristRight,
    FS_handRight,
    FS_thumbRight,
    FS_shoulderLeft,
    FS_elbowLeft,
    FS_wristLeft,
    FS_handLeft,
    FS_thumbLeft,
    FS_spineMid,
    FS_spine,
    FS_spineBase,
    FS_hipCenter,
    FS_hipRight,
    FS_kneeRight,
    FS_ankleRight,
    FS_footRight,
    FS_hipLeft,
    FS_kneeLeft,
    FS_ankleLeft,
    FS_footLeft,
    FS_handTipRight,
    FS_handTipLeft
};
```



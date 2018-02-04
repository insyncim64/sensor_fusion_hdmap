As Active Safety Map & Cloud System Developer, you will be part of a team working with map data needs for a fused environmental perception, as well as a solution for probe sourcing sensor data for keeping a cloud based map continuously up to date and reliable enough to be used for autonomous driving.
Main responsibilities

One of your responsibilities will be to design the system solution as well as writing and releasing requirements and documentation, supporting the development in these areas. In this work, you need to have a close collaboration with the Function Owners within Active Safety as well as other stakeholders within Volvo Cars globally, such as the Infotainment/Navigation area, the team within Volvo Cars IT working with the cloud development and the Sensor Performance team.

-Further, as a Senior Developer, you will collaborate closely with our map suppliers, as well as our SW Partner Zenuity, in all phases of the Active Safety and Autonomous Drive projects. You will also work to define strategies and new technology steps / advanced engineering within the area together with the Map & Cloud Team Leader.


Basic:
What is sensor fusion?
- Many sensors are equipped in a car. Integrate different cameras, radars can help to achieve a acurate status of a car in the environment.
- https://static.leiphone.com/uploads/new/article/740_740/201708/59a669c009294.jpg?imageMogr2/format/jpg/quality/90
- However, every sensor has its pros and cons. e.g. take two sensors in a cellphone, accerometer is not accurate while error will not be accumulated. gyro is accurate in returning the changes, while errors will be accumulated.
- Kalman filter is a classic tool to do sensor fusion.
What is high defition map?
Why a high definition map is needed?
Why sensor fusion is needed?
What is the relationship between sensor fusion and HAD?
What have you done for sensor fusion and HAD?

What are sensors in a car?
- CMOS cameras will be blinded in a rainy and floggy whether
- Radars perform well in bad weather condition while their resolution is not that good.
- LiDAR ToF Technology using light. based on different reflection of signal it determines the surface. e.g. diffuse reflection, retro-reflection

One example for sensor fusion in a car?
- Back camera and ultrasonic range finder for parking
- Front camera and multi module radars for ADAS

Sensor fusion systems
- centralized
- distributed

Practical experience about Sensor Fusion, Map and Cloud:
- Apollo Cloud platform
    - HD Map: openDRIVE
    - OTA
    - Data Platform

Companies:
- Civil Maps
    - base map
    - camera view, voxel view
    - get feature points based on the base map(SLAM)
    - second car can reuse the based map and localizes itself
    - 80% - +/-5cm
    - How to use LiDAR
C/C++

HD Map
- The importance of HD Map in Autonoumous Driving
    - From cloud platform perspective, simulation system can not work without HD map. The goal of a simulation system is to reconstruct real roads, traffic and environment. And it is used for training algorithms. On the other hand, HD Map in the cloud can act as a data source for cars in the road. It supports autonomous driving mainling in four aspects, localization, perception, decision and planning.
    - Localization: it is known that in combination of GPS, IMU, current map is working perfectly for cars. However, current accuracy of localization can not meet the requirement for localization in autonomous driving. Different sensors are used for percept and localize a car. A quick solution is to have a map which contains crucial information for driving. And it should as detailed as possible. Then a low cost autonomous driving solution can be proposed. A single lens camera can be used to capture image. Lanes can be used to compare with the lane information in the HD map to determine the location horizontally. Traffic light, light and lighting pole can be used for localization vertically.
    - Perception: At first, sensors can percept the environment up to 1km away. HD Map can provide you information much more far away from it. Secondly, through comparison between the information which is captured actively from sensors and HD map, it helps to detect objects, like vehcile and pedestrian. To aggregate different regions which are needed by perception module, HD Map can provide region of interest(ROI). Moreover, information from HD map can provide semantic meaning. For example, different kinds of traffic light system have different number of lights. If it knows that how many lights it should detect and percept. It will help a lot to design perception algorithms. 
    - Decision and Planning: Including the realtime update of map, it helps to plan efficiently.
    - HD Map can help to reduce number of sensors. A feasible solution can be hardly proposed without HD map.
- Process to create an HD map
    - Data sourcing
        - Image, Point Cloud, GPS Track
    - Pre-Processing
        - Sensor fusion which combines information from GPS, IMU, LiDAR, and camera
        - Deep learning for segmentation and detection
    - Manual Verification
        - human being is needed to increase accuracy
    - Release
        - HD Map
        - ADAS Map
        - Infotainment map
    - Update
        - A update cycle exists between cloud of map provider and car. Here is the [update cylce](https://mp.weixin.qq.com/s?__biz=MzI1NjkxOTMyNQ==&mid=100000179&idx=1&sn=63bdf976825c2770ef974a7c11ed8f6e&chksm=6a1e13c15d699ad78c84170c8f447e456742b608efadca25cf37001027c6f7ba6a16179dd72b&scene=20&key=ffd6e7826d53df79f8fa0d6d3a605b69eab835c3a7f6e9b417f0e172bb307a57c80de27a35ff2d4a84893b42496a1c745c1526c69788e175961ee4e8a14030b50cf6cf25047043361bedc1b89ae458ba&ascene=0&uin=MTE2NjQzMjMyMA%3D%3D&devicetype=iMac+MacBookPro12%2C1+OSX+OSX+10.12.6+build(16G29)&version=12020110&nettype=WIFI&lang=zh_CN&fontScale=100&pass_ticket=IYK%2FI9o2lXOo4hCjSwjLG0LZNdIURijz4X9oUzAknRcwcU2FAcspk%2BmQy6fFfhp0## "update cycle") of ApolloAuto HDMap from Baidu.
![](MapUpdateCycle.png)
    
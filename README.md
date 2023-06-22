# Fight_Detection
A binary classification of frames that can tell us whether there is evidence of fight and violence.
## Proposed Methodology
The goal is to create a system that can detect violent behavior in real-time and 
provide an alarm to the proper authorities.
**Architecture:**
The frames that make up the security camera's footage. MobileNet v2 classifier 
is fed the frames in order to identify potentially violent scenes. Frames are 
eliminated if they contain no instances of violence. The frame with the violence 
identified is acquired, and then the image quality is improved.
![](https://production-media.paperswithcode.com/methods/Screen_Shot_2020-06-06_at_10.37.14_PM.png)

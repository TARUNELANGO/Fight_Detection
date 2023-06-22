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

![](Aspose.Words.6c1d07dc-7120-4b1a-af5b-29f7f4e8c982.005.png)

Figure 1: Methodology 

**Dataset:**  

There are a total of 1000 videos in the dataset, split evenly between violent and peaceful scenes. Most of the videos are from closed-circuit television, and their average length is about 5 seconds. During each epoch, 350 movies are selected at random from both the violent and non-violent groups for training purposes. 

![](Aspose.Words.6c1d07dc-7120-4b1a-af5b-29f7f4e8c982.006.jpeg)

Figure 2: Video clips from the violence dataset 

**MobileNet V2:**  

Using depth wise separable convolution as its foundation, MobileNet breaks down a standard convolution  into a depth wise convolution and a pointwise convolution. 

The module displays a resizing cell with a stride of 2 and a residual cell with a stride of 1 (the latter has a residual/identity relationship). Figure 3 shows four different  types  of  convolutions,  labelled  "conv"  for  a  standard  convolution, "dwese" for a depth-wise separable convolution, "Relu6" for a ReLu activation function with a magnitude constraint, and "Linear" for the application of the linear function. 

MobileNetV2 primarily made use of the linear bottleneck and inverted residual block  methods.  Information  loss  due  to  nonlinear  functions  like  ReLU  is mitigated by increasing the channel size of input in the linear bottleneck layer. The idea is based on the notion that even if some information is lost in one channel,  it  could  still  be  present  in  the  other  nine.  The  channel  dimension structure of a normal residual block is ("wide" - "narrow" - "wide"), whereas that of an inverted residual block is ("narrow" - "wide" - "narrow"). The memory footprint can be decreased by using skip links between skinny layers as opposed to thicker ones. 

![](Aspose.Words.6c1d07dc-7120-4b1a-af5b-29f7f4e8c982.007.png)

Figure 3: MobileNet v2 Architecture 

**Image Enhancement:**  

The resulting frames undergo Picture Enhancement processing. This is done with the help of the Python Imaging Library's built-in features (PIL). PIL has excellent support for a wide variety of file formats, a sleek interface, and respectable image processing chops. The Core Picture Library prioritises speed of access to data across  many popular pixel  formats. It's a great resource  for standard picture editing  software.  The  output  frames'  brightness  and  colour  saturation  are improved by a factor of 2. 

**Operating Environment:** 

Python - Python is utilised, which is a popular programming language that is well suited for Machine Learning and Deep Learning applications due to its extensive collection of pre-built libraries. We have made advantage of Python's library ecosystem,  which  includes  programmes  like  Tensorflow  and  Open-CV.  Its straightforward syntax means it's utilised all throughout the world for things like building websites. 

Google Colaboratory - To facilitate the development of Python-based projects, such  as  Machine  Learning  and  Deep  Learning  implementations,  Google  has created an environment called Google Colaboratory. When we need aid with jobs that need a lot of processing power, we may utilise Google's Graphics Processor Unit  (GPU)  or  Tensor  Processing  Unit  (TPU)  for  free.  A  fair  amount  of processing power is required for this task, and therefore it is employed here. 

**RESULTS AND DISCUSSION** 

The following graphical representation demonstrates the accuracy of testing and training in this section. When a dataset of 1000 videos with an average duration of 7 seconds is used as input, the training and testing accuracy and loss for the MobileNet v2 model are presented in Fig. 4.1. For each period, 350 movies from the violence class and 350 films from the non-violence class are trained. Training yielded  96%  accuracy,  whereas  testing  yielded  95%  accuracy  using  CCTV footage that was not included in the dataset. The resultant video frames are shown in Figure 4.3. 

![](Aspose.Words.6c1d07dc-7120-4b1a-af5b-29f7f4e8c982.008.jpeg)

Figure 4.1: Accuracy and Error of the training set 

Figure 4.1's accuracy and loss attain a stable level of increment and decrement after around 5 epochs. Figure 4.2 illustrates the calculated confusion matrix as well as additional rating criteria. 

As input, a violent video is sent into the system. Figure 4.3 illustrates a video clip classified as containing aggressive behaviour. Another video clip with no violent actions was provided as input.  Figure 4.4 shows a video clip that  is clearly labelled as deceptive or violent. 

![](Aspose.Words.6c1d07dc-7120-4b1a-af5b-29f7f4e8c982.009.jpeg)

Figure 4.2: Confusion matrix of the trained model 

![](Aspose.Words.6c1d07dc-7120-4b1a-af5b-29f7f4e8c982.010.jpeg)

Figure 4.3: Output frame that recognized violence 

![](Aspose.Words.6c1d07dc-7120-4b1a-af5b-29f7f4e8c982.011.jpeg)

Figure 4.4: Output frame that recognized violence 

![](Aspose.Words.6c1d07dc-7120-4b1a-af5b-29f7f4e8c982.012.jpeg)

Figure 4.5: Output frame that recognized violence 

![](Aspose.Words.6c1d07dc-7120-4b1a-af5b-29f7f4e8c982.013.jpeg)

Figure 4.6: Output frame that did not recognize violence 

**Comparison With CNN-LSTM Architecture:** 

![](Aspose.Words.6c1d07dc-7120-4b1a-af5b-29f7f4e8c982.014.png) ![](Aspose.Words.6c1d07dc-7120-4b1a-af5b-29f7f4e8c982.015.png)

Figure 4.7: Comparison of Training and Testing accuracy of MobileNet v2 and CNN**-**LSTM Models** 

![](Aspose.Words.6c1d07dc-7120-4b1a-af5b-29f7f4e8c982.016.png)

Figure 4.8: Performance Metrics of MobileNet v2 model 

As the comparison shown in the Fig 4.7, MobileNet v2 has shown improvement than CNN-LSTM in the violence detection task. The above graphs has shown that MobileNet v2 is capable of performing better than model trained using CNN- LSTM. This proves that MobileNet v2 too can become the state of the art model for Real-time Violence detection.

# Answers to Comments
First, we would like to thank the editor and the anonymous reviewers for their valuable and helpful comments. We will revise the submitted paper according to these comments. In this document, we summarize the answers to the comments and attempt to clarify the points addressed by each reviewer. 
## Reviewer #1:
OVERALL SCORE 7 Accept
### [General Comments]: 
I'm overall positive towards the paper. Likely to be of interest to a large proportion of the community. Significant.
Novel. Technically sound. Sufficient. Good. 
### [Questions]: 
1. More mathematical explanation is needed for the good performance on Image Compression.   
**Answer:**
   - In stationary scenes like surveillance camera, because images have a more relative distribution, it is convincing that 
   data-driven compress matrix is better than traditional constant matrix. latest data-driven researches like Numax and Adagio, they have shown a better result, and we realize a more effective way.  
   - Compress sensing (Cand` es, Romberg, and Tao 2006) has proven if satisfy the incoherence condition, one can reconstruct 
   the original image from sparse signal. We defined the coherence of Φ,Ψ, and use our regularization to train the compress matrix. Experiment shows our result are less coherent.   
     CCN | GAUSS 
      - | :-: |
     3.1e+3  | 1.17e+4


2. Why the CCN can beat all the baselines?  
**Answer:**We calculate the defined coherence of baselines and our method, our approach is remarkably better than baselines. 
     CCN | GAUSS 
      - | :-: |
     3.1e+3  | 1.17e+4

3. Also, why adding the regularization doesn't hurt the object detection performance.  
**Answer:**
   -	Because we use the proposed special L1 norm minimization replace the default L1 norm minimization in first convolutional layer. It is similar to normal L1 norm minimization, which is a common optimize way and has been used in many CNN model training(cite).
   -	Technically, we also use a two steps training strategy to compensate the accuracy loss as paper mentioned.  
   
## Reviewer #2:  
OVERALL SCORE 5 Marginally below threshold  
### [General Comments]:  
Moderately significant. Novel. Technically sound. Sufficient. Good.  
### [Questions]:  
1.	Using multi-task learning (object detection and image compression) or transfer learning (from object detection features to image compression) makes sense and is technically sound. However, my major concern is that the user cases are rare, and this paper does not list related applications to this problem. Without examples, the problem itself seems not critical and is very limited.  
**Answer:** Yes, you are right. Given space limitations, this article can’t fully introduce application scenarios and the importance of our method for applications.  Our method is to solve a realistic problem in image wireless transmission.  
For example, about applications:  Intelligent wireless monitoring camera, unmanned aerial vehicle and other embedded wireless devices all need to face wireless transmission consumption challenge. We will supply it in our new paper.  
![camera](https://github.com/sosaaaad2/Rebuttal/blob/master/images/wireless_camera.jpg)![unmanned](https://github.com/sosaaaad2/Rebuttal/blob/master/images/timg.jpg)  
                                     Fig1

2.	Beyond, the method used in this paper is not novel. Basically it follows the multi-task learning and transfer learning settings. The major novel of this paper lies in the problem, however, I am still skeptical about the importance of this problem. I have not found any convincing applications in the abstract and introduction.  
**Answer:** About the methodology innovation, transfer learning is not main scope of this article. The main contribution of this article is:  
     -	Propose a data-driven compress sensing method based on neural network training, which can use large dataset
     -	Propose a new regularization to improve incoherence, and then improve PSNR.
     -	First propose a method that use convolution operation to realize Linear mapping and image compression, improve the efficiency.  

3.	What's the applications of a system like Figure 2? Can you provide some concrete and critical examples
**Answer:** A concrete example(surveillance camera) ：  
 ![block]（https://github.com/sosaaaad2/Rebuttal/blob/master/images/APLVPASYS_BD.jpg）  
                                Fig2

## Reviewer #3:  
OVERALL SCORE 7 Accept  
### [General Comments]:    
Significant. Novel. Technically sound. Sufficient. Satisfactory. 
### [Questions]:   
1.	In the Abstract, the authors aim to address the challenge of designing an efficient framework for real-time object detection and image compression. However, the authors show that CCN doesn’t affect inference efficiency and almost no loss of detection accuracy, e.g., in table 5, Original YOLOv2 and CCN-YOLO is almost the same time. It is somehow a conflict with the target problem.  
**Answer:** CCN are realized based on YOLO model, the main innovation is in the training part. Our purpose is to find the parameters of convolution that can realize feature extraction and compress subsampling at same time., and replace parameters of YOLO models. So we doesn’t increase latency. In commutating time, proposed approach only add little IO time on compress image and random pooling, which is far less than detection time of YOLO. The extra operation can also be execute with detection at same time, so it doesn’t FPS of system.   

2.	In the second paragraph of Model Implementation, please introduce the function of YOLOv2 briefly.  
**Answer:** Thank you for your suggestion, we will revise the paper as suggested in further revision.

3.	The cost of CCN is not reduced compared with the original CNN model, which means the running time is limited by the current CNN model.
**Answer:** Yes, you are perfectly right. CCN is an improvement of CNN, it is limited by the speed of original CNN model. To further improve throughput, we can easily apply our strategy in a more efficient CNN model. For example, a small model,TINY-YOLO. or a quantization model. This is also an important aspect for our future work.   

4.	The dataset of BSD100 is small and it has no test set. The authors are suggested to provide explanations or choose other standard datasets.  
**Answer:** Because existing data-driven compress sensing methods, e.g, Numax, Adagio, cost high computation, those models can’t be trained in complete COCO and VOC dataset. To compare the performance with data-driven methods, we specially use a small dataset(BSD100) to compare the PSNR and training speed of image compressing.  

5.	The following are minor ones for further revisions:  
Occasionally, I noticed several typos, please correct them before the next submission. 
a) For example, in equation 4, the position of vector 0 and scalar 0 are strange. 
b) Spaces are required before the second and the third paragraph in Background and the third paragraph in Incoherence Regularization.
c) In table 4, the training set can be mentioned once, that will make the table more concise.
d) It is not professional to provide a code link in the abstract, and is better to put it as a URL reference or a footnote.
e) In equation (3), the dimensional of left value is N while the dimension of y is M. Please revise accordingly.
**Answer:** Thank you for your suggestion, we will revise the paper as suggested in further revision.

Download Link: https://assignmentchef.com/product/solved-cs276a-project2-human-face-detection-using-boosting
<br>
Boosting is a general method for improving the accuracy of any given learning algorithm. Specifically, one can use it to combine weak learners, each performing only slightly better than random guess, to form an arbitrarily good hypothesis. In this project, you are required to implement an AdaBoost and RealBoost algorithms for frontal human face detection.

<h1>2.     Data</h1>

<ul>

 <li><strong>Training data: </strong>Face and non-face images of the size of 16×16 pixels are given.</li>

 <li><strong>Testing data: </strong>Three photos taken at the class are used for testing.</li>

 <li><strong>Hard negatives: </strong>Three background images are taken without faces.</li>

</ul>

<h1>3.     Tasks</h1>

Perform the following tasks. Report your results in the given order and write a concise interpretation for each result:

<ol>

 <li><strong>Construct weak classifiers </strong>{<em>h<sub>j</sub></em>}<strong>: </strong>Load the predefined set of Haar filters. Compute the features {<em>f<sub>j</sub></em>} by applying each Haar filter to the integral images of the positive and negative populations. Determine the polarity <em>s<sub>j </sub></em>and threshold <em>θ<sub>j </sub></em>for each weak classifier <em>h<sub>j</sub></em>:</li>

</ol>

(

−<em>s<sub>j              </sub></em>if <em>f<sub>j </sub>&lt; θ<sub>j</sub>,</em>

<em>h<sub>j</sub></em>(<em>x</em>) = <em>s<sub>j       </sub></em>otherwise<em>.</em>

Write a function which returns the weak classifier with lowest weighted error. Note, as the samples change their weights over time, the histograms and threshold <em>θ </em>will change.

<ol start="2">

 <li><strong>Implement AdaBoost: </strong>Implement the AdaBoost algorithm to boost the weak classifiers. Construct the strong classifier <em>H</em>(<em>x</em>) as an weighted ensemble of <em>T </em>weak classifiers:</li>

</ol>

<em> .</em>

Two class photos are given. Note, you need to scale the image into a few scales so that the faces at the front and back are 16×16 pixels in one of the scaled image. Run your classifier on these images. Perform non-maximum suppression, i.e.

1

when two positive detections overlap significantly, choose the one that has higher score. Perform hard negatives mining. You are given background images without faces. Run your strong classifier on these images. Any “faces” detected by your classifier are called “hard negatives”. Add them to the negative population in the training set and re-train your model. Include the following in your report:

<ul>

 <li><strong>Haar filters: </strong>Display the top 20 Haar filters after boosting. Report the corresponding voting weights {<em>α<sub>t </sub></em>: <em>t </em>= 1<em>,…,</em>20}.</li>

 <li><strong>Training error of strong classifier: </strong>Plot the training error of the strong classifier over the number of steps <em>T</em>.</li>

 <li><strong>Training errors of weak classifiers: </strong>At steps <em>T </em>= 0<em>,</em>10<em>,</em>50<em>,</em>100, plot the curve for the training errors of the top 1<em>,</em>000 weak classifiers among the pool of weak classifiers in increasing order. Compare these four curves.</li>

 <li><strong>Histograms: </strong>Plot the histograms of the positive and negative populations over <em>F</em>(<em>x</em>), for <em>T </em>= 10<em>,</em>50<em>,</em>100, respectively.</li>

 <li><strong>ROC: </strong>Based on the histograms, plot their corresponding ROC curves for <em>T </em>= 10<em>,</em>50<em>,</em>100, respectively.</li>

 <li><strong>Detections: </strong>Display the detected faces in both of the provided images without hard negative mining.</li>

 <li><strong>Hard negative mining: </strong>Display the detected faces in both of the provided images with hard negative mining.</li>

</ul>

<ol start="3">

 <li><strong>Implement RealBoost: </strong>Implement the RealBoost algorithm using the top <em>T </em>= 10<em>,</em>50<em>,</em>100 features you chose in step (c). Compute the histograms of negative and positive populations and the corresponding ROC curves. Include the following in your report:</li>

</ol>

<ul>

 <li><strong>Histograms: </strong>Plot the histograms of the positive and negative populations over <em>F</em>(<em>x</em>), for <em>T </em>= 10<em>,</em>50<em>,</em>100, respectively.</li>

 <li><strong>ROC: </strong>Based on the histograms, plot their corresponding ROC curves. Compare them with the ROC curves in (e).</li>

</ul>
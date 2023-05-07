Download Link: https://assignmentchef.com/product/solved-ir-assignment-2
<br>



Information Retrieval in High Dimensional Data







Please hand in your solutions via Moodle as an IPYTHON (Jupyter) notebook.

Solutions must be handed in by groups. Please state the names of your group members at a prominent place in your submission. (For example, at the beginning of your provided notebook or in a separate text file.)

Principal Component Analysis

Task 1: [10 points] Let <strong>X </strong>∈ R<em><sup>p</sup></em><sup>×<em>N</em></sup>, <em>p &lt; N </em>be a centered matrix of <em>p N</em>-dimensional data samples with the full-size SVD <strong>X </strong>= <strong>UΣV</strong><sup>&gt;</sup>. Assume that the singular values are sorted in a descending manner, i.e. <em>σ</em><sub>1<em>,</em>1 </sub>≥ <em>… </em>≥ <em>σ<sub>p,p</sub></em>.

<ul>

 <li>Provide a normalized vector ˆ<strong>s</strong>∈R<em><sup>p</sup></em>, such that</li>

</ul>

ˆ<strong>s </strong>= arg max <strong>s</strong><sup>&gt;</sup><strong>ΣΣ</strong><sup>&gt;</sup><strong>s</strong><em>.</em>

<strong>s </strong>s.t. k<strong>s</strong>k=1

<ul>

 <li>Show that the empirical variance of the inner products of the columns of <strong>X </strong>with a normalized vector <strong>a</strong>,</li>

</ul>

<em>N</em>

<em>,</em>

<em>i</em>=1

is maximized when <strong>a </strong>is set to the first column of <strong>U</strong>, i.e. <strong>a </strong>= <strong>u</strong><sub>1 </sub>(note that k<strong>a</strong>k = 1).

Hint: Write <strong>a </strong>as a linear combination of the columns of <strong>U</strong>. Verify that such a representation does not affect the norm constraint.

Task 2: [15 points] For this task, download the modified version of the <em>Yale Face Database B </em>provided on Moodle (task2_data.zip). The Yale Face Database B consists of single light source images of 10 subjects, each seen in different poses and illumination conditions. In the provided form the database is divided into 5 subsets. In subset 0 the subject is illuminated by an almost frontal light source, while for subsets 1-4 the

light source is gradually moved along the horizon. Subset 0 will serve as the training set, while subsets 1-4 are used for testing.

<ul>

 <li>Write a function that takes as an input matrix <strong>T </strong>of vectorized images from subset 0. The output of this function are the 20 first singular vectors <strong>U</strong>[:<em>,</em>1]<em>,…,</em><strong>U</strong>[:<em>,</em>20]. Display the first 3 vectors as images, i.e., reshape them to size 50×50 and display them.</li>

 <li>Write a function that takes as an input the training set <strong>T </strong>(a matrix composed of vectorized pictures from subset 0), a vector containing the labels of the training set (i.e., if the the <em>i</em>-th sample belongs to class <em>j</em>, the <em>i</em>-th entry of the labels vector is <em>j</em>. In this exercise <em>j </em>is an integer between 1 and 10), the test samples <em>S </em>(a matrix composed of vectorized pictures from subsets 1-4) and the corresponding labels (in a separate vector), the 20 singular vectors from the first step, and the parameter <em>k </em>that denotes how many of the PCs are used. Use the Euclidean distance to classify each sample image based on its three nearest neighbors. (This is done by comparing the test samples with the training samples in the reduced space.) As an output give the fraction of images from <em>S </em>that were misclassified, i.e., the error rate. Repeat this for subsets 1 through 4 and for <em>k </em>= 1<em>,…,</em>20. Plot the error rate for each subset.</li>

 <li>Repeat the above experiment without using the first three singular vectors, i.e., use <em>k </em>= 1<em>,…,</em>17 singular vectors starting from the 4-th. Plot the error rate as before. How do you explain the difference in recognition rate?</li>

</ul>
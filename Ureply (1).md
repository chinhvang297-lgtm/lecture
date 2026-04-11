# **Ureply**

# Lecture 2 and 3

## 1. Types of data

**Can you name some types of data?**

Number, categorical, natural language, image, audio, video, text...

## 2. Types of machine learning problem

**Based on the description below, what is the type of the problem?** 

**You have a spreadsheet of records for the list of items that customer purchase. Each row is represent a binary vector for the purchased item. You are going to find some best salers.**

**A. Classification    B. Clustering    C. Regression    D. Reinforcement learning**

B

or A

## 3. Types of analytics

**You have the record of the purchase, and the record of the customer in a fast food shop. You are going to analyze what the best strategies are in order to make more money.**

**A. Predictive analytics    B. Descriptive analytics    C. Prescriptive analytics    D. Diagnostics analytics**

C

ABCD分别对应：将会发生什么？ 发生了什么？ 应该怎么做？ 为什么会发生？



# **Lecture 4 DataRepresentation II**

## 1. TF-IDF Calculation

**Consider two documents:**

**Document 1: "The cat sat on the mat"**

**Document 2: "The dog chased the cat"**

**Calculate the TF-IDF score for the word "dog" in Document 2**

- Count of dog in document 2: 1
- Total words in Document 2: 5
- TF(dog, Doc 2) = 0.2
- IDF(dog) = log(2/1) = 0.301
- TF-IDF(dog, Doc 2) = 0.0602

TF 词频 IDF 逆文档频率

## 2. One-Hot Encoding

**Suppose we have a feature gender having the value, {male, female, unknown}. Which is the correct representation for gender using one-hot encoding?**

**A. Male {1,0}, Female {0,1}, Unknown {0,0}**

**B. Male {1,0,0}, Female {0,1,0}, Unknown {0,0,1}**

**C. Male {0}, Female {1}, Unknown {2}**

B

独热编码会为每个类别创建一个独立的二进制列

## 3. Hotdeck Imputation

**Why is the Hotdeck imputation (random value from the same column) good for predicting missing value?**

- All the assigned values are valid in Hotdeck imputation.
- The assigned values can be any valid values from the existing data, instead of the median/mean/mode values.

Hotdeck 插补是从同一列已有的数据中随机选取一个真实值来填充缺失值，而不是用均值、中位数或众数。

它的好处是：

- 填充的值是真实存在的，不会像均值插补那样引入数据中原本没有的数值。
- 保留了数据的原始分布特性，不会人为压低或抬高某个特征的取值。

## 4. PCA vs LDA

**State a difference between PCA and LDA in dimension reduction**

Unlike PCA, which optimizes for variance regardless of class labels, LDA aims to find a linear combination of features that seperates different classes.

PCA (主成分分析) 无监督.

LDA (线性判别分析) 有监督.

## 5. Regression for Missing Value

**Can we use regression to predict the missing value in data preprocessing?**

Yes, imputation.



# Lecture 5 DataRepresentation III

## 1. Differences between word embeddings and TF-iDF

**Suggest two major differences between word embeddings and TF-iDF.**

i. Word embeddings is dense vector, TF-iDF is spare vector.

ii. TF-IDF captures term frequency-inverse document frequency, Word embeddings captures semantic similarity.

## 2. Evaluate the quality of the embeddings

**Suggest how you evaluate the quality of the embeddings.**

Intrinsic: Direct tasks like word similarity or analogy tests.

Extrinsic: Performance on downstream tasks like sentiment analysis or NER.

内在评估：直接的任务，例如词相似度或类比测试。

外在评估：在下游任务上的表现，例如情感分析或命名实体识别（NER）。

## 3. SIFT descriptor

**Why is SIFT descriptor invariant to rotation or scale?**

Invariant to scale: Multi-Scale Detection / Scale Normalization / Descriptor Scaling

Invariant to rotation: Orientation assignment / dominant direction / relative coordinates

## 4. Matcher in image processing

**Describe and explain how matcher compares two objects in image processing.**

(1) Area-Based (Template) Matching: 

Sum of Squared Differences of two objects / Normalized Cross-Correlation of two objects

(2) Feature-Based Matching: Distance between the descriptors

## 5. Bias for neural network

**What is bias for neural network?**

This is an extra parameter added to the weighted sum of inputs before applying the activation function. It helps the model shift the activation curve so that the network can learn patterns more flexibly.



# Lecture 6 Data Modeling I

## 1. Major components for autoencoder

**What are the major components for an autoencoder?**

Encoder, decoder, latent space.

## 2. Self-attension mechanism

**What is self-attension mechanism?**

Self-attention is a process where each word in a sequence considers every other word in the sequence to establish context. Similar to a neuron, the calculation includes attention score, weighted sum, scaling and normalization.

## 3. Machine learning problems

**What are the types of machine learning problems?**

Supervised, semi-supervised, unsupervised, reinforcement.

## 4. ML algorithms

**Which of the following ML algorithms can classify non-linear relations?**

**A. Decision Tree    B. Random Forest    C. SVM    D. KNN    E. Neural Network**

All of them.

## 5. Precision and Recall

**Suppose: y_actual = [0,1,0,1,1,1,0],   y_prediction = [0,0,0,0,1,1,1].  What is precision and recall?**

2/3 and 2/4

Precision is how many of the positively identified cases are actually positive.
Recall is how many data of a certain class can the model correctly identify.



# Lecture 7 Data Modeling II

## 1. Overfitting

**What is overfitting? How can you avoid it?**

Overfitting occurs when an algorithm fits too closely or even exactly to its training data, resulting in a model that can’t make accurate predictions or conclusions from any data other than the training data.

Early stopping
Train with more data
Data augmentation (adding noise to data)
Reasonable amount of parameters
Regularization (applying penalty for the number of features used)

## 2. Distance measurement vs Correlation measurement

**State two main differences between distance measurement and correlation measurement in the metrics for the evaluation of the model.**

Distance is the sum of the differences, while correlation is the average product.

Better distance has a smaller value, while better correlation has a large magnitude of the value.

Distance ranges [0, +inf), while correlation ranges [-1, 1].

## 3. Odds in regression

**In regression problem, what is odds? What is odds ratio?**

Odds are the probability of an event occurring divided by the probability of the event not occurring.

An odds ratio is the odds of the event in one group divided by the odds in another group not exposed.

## 4. K-means

**What is the stopping criterion of K-means algorithm?**

1. Centroids of newly formed clusters do not change.
2. Maximum number of iterations is reached.

## 5. Cluster 

**State the factors in determining the number of clusters, in clustering problem.**

Percentage of explained variance (elbow method)  

Within and between cluster distances (Silhouette score)  

Information criterion (AIC/BIC/DIC) (used in X-means clustering)

## 6. Delayed reward

**What is delayed reward in reinforcement learning?**

When an agent performs an action but does not receive the associated feedback (positive or negative) until many time steps later.



# Lecture 8 Data Visualization

## 1. Scatter plot

**What types of data work best in scatter plots?**

The sample from two variables, including both discrete and continuous.

## 2. Box-plots

**What type of data is box-plots usually used for?**

Numeric data of a variable with some categories (condition or hue) of another variable.

## 3. Outlier

**What is an outlier?**

An outlier is an extremely high or extremely low data point relative to the nearest data point and the rest of the neighboring co-existing values in a data graph or dataset you are working with. Mathematically (or in boxplot), outliers are data points lying more than 1.5 times the IQR above the 3rd quartile or below the 1st quartile.

## 4. Legend in a graph

**What is the purpose of a legend in a graph?**

A legend serves as a guide or explanation for the different data series or components displayed in the visualisation. It aids the viewer in comprehending the significance of the many hues, symbols, or lines used to represent various data categories, variables, or groupings in the chart or graph.

## 5. Good data visualization

**What makes a good data visualization?**

See advice at the end of slides. In short: 1. Data Accuracy 2. Clear and Relevant Title 3. Appropriate Visual Representation 4. Data Labels and Legends 5. Consistent Scale and Units. 6. ... etc

## 6. Data visualization parameter

**Explain what a parameter is in data visualization.**

A parameter is a placeholder value that isn part of the original dataset until you or the end-user choose it. 

E.g. user chooses to see top 5 / top 10 suggested friends in the friend recommendation system.



# Lecture 9 Case Studies (I) Business Problems

## 1. Business analyst

**What are the roles of a business analyst?**

Identify the business objectives. 
Work with the development team. 
Assess the functional and non-functional requirements, and perform user acceptance testing. 
Present and document the results.

## 2. Business analytics process

**Suppose you are a business analyst, when you are given a new project, what do you do first?**

Learn about the business domain, competitions, team, and customer.

## 3. Handle changes to requirement

**Suppose you are a business analyst, how do you handle changes to requirements?**

In theory, communication, negotiation and documentation. In practice, just inform the team to work on the changes.

## 4. Tools of Business analytics

**What tools do you usually use as a business analytics?**

Those tools should be designed for effective communication and visualization, e.g. Power BI, Tableau, Microsoft Visio.

## 5. Test cases of Recommender System (RS)

**How can you design the test cases for binary recommender system for internal testing?**

Keep some users or products away from training , and reserve them for final testing.

## 6. Evaluation metrics for RS

**What are the different evaluation metrics for Recommender System?**

Click-through rate (CTR)

Conversion rate

Retention rate

Net promoter score (NPS)

... etc

## 7. Implicit feedback vs Explicit feedback

**What are the major differences between implicit and explicit feedback in RS?**

The level of user engagement (explicit requires more engagement). The amount of information available (explicit collects more information).

## 8. Stock price 

**How is stock price determined in the market?**

Company performance (earnings, revenue growth) Market sentiment (investor confidence) Economic factors (inflation, interest rates) Industry trends (sector performance) News and events (government policies, global crises)

## 9. Correlation analysis vs Causality analysis

**State the main difference between correlation analysis and causality analysis. Name two computational methods to inferring causality.**

Correlation is a relationship where action A relates to action B. 
Causation means action A causes outcome B. 

Computational methods: algorithmic information theory models and noise models

## 10. Correlation versus Causation 

**Explain correlation versus causation in portfolio construction.** 

Correlation (The How): Measures how two assets move in relation to each other. A correlation of +1 means they move in sync, while -1 means they move in opposite directions. It describes a historical statistical association but does not explain why it exists.

Causation (The Why): Indicates a direct cause-and-effect relationship where a change in one variable (like an interest rate hike) directly results in a change in another (like a drop in bond prices)



# Lecture 10 Case Studies (II) Natural Language Problems

## 1. Common Pretraining Objectives for LLMs

**What are some common pretraining objectives for LLMs?**

1. Next Token Prediction: The model is given a sequence of words and must predict the most likely next token.
2. Masked Language Modeling (MLM): A certain percentage (often 15%) of tokens in a sentence are randomly hidden (masked), and the model must predict them based on the surrounding context.
3. Next Sentence Prediction (NSP): The model is given two sentences and must determine if the second sentence actually follows the first in the original text.
4. Sentence Order Prediction (SOP): SOP uses two consecutive sentences and swaps their order to force the model to learn sentence-level coherence by distinguishing the original order from the swapped order.

## 2. Handling Out-of-Vocabulary (OOV) Words

**How do LLMs handle out-of-vocabulary (OOV) words or tokens?**

1. Subword Tokenization: Rare or unseen words are broken into sub-units (prefixes, suffixes, or roots) that exist in the model's vocabulary.
2. Special Unknown Token: Some older or specialized models replace OOV words with a placeholder like `[UNK]`. However, this is generally avoided in modern LLMs because it causes significant information loss.
3. Character/Byte-Level Fallback: If a subword cannot be matched, tokenizers can break the text down to individual characters or UTF-8 bytes. Since all possible characters/bytes are in the base vocabulary, this technically eliminates OOV errors.

## 3. Embedding Layers in LLMs

**What are embedding layers in LLMs?**

The embedding layer is the first internal component of the Transformer architecture. Its primary role to act as a translator, converting discrete numerical token IDs into dense, high-dimensional vectors that the neural network can process mathematically.

## 4. Attention in LLMs

**Explain the concept of attention in LLMs.**

Attention is a mechanism that allows the model to dynamically focus on the most relevant parts of an input sequence when processing

## 5. Advantage of small kernel

**What is the advantage of using small kernels like 3×3 than using a few large ones.**

Smaller kernels let you use more filters so you can use a greater number of activations functions and let the CNN learn a more discriminative mapping function. Also, smaller kernels capture more spatial context and use fewer computations and parameters making them a better choice over large ones.

## 6. Receptive field

**In CNN, what is receptive field?**

The receptive field dictates which portions of the input volume contribute to the computation of a given activation.

## 7. VGG Net's major lesson

**What is the major lesson from VGG Net?**

VGG Net uses 3×3 with a stride of 1, showing large filters are unnecessary.

## 8. Bring balance when handling imbalanced datasets

**How do you bring balance to the force when handling imbalanced datasets in deep learning?**

1. Weight Balancing
2. Over and Under Sampling



# Lecture 11 Case Studies (III) Multimedia Problems

## 1. Deep Learning Models for Image Generation

**What are some famous deep learning models tailored for image generation?**

- Vision Transformers (or multimodal)
- GANs
- Diffusion based models

## 2. Transfer Learning in Image Generation

**What does transfer learning mean in terms of image generation?**

Transfer learning is the process of taking a deep learning model that has already been trained on a massive, general dataset and training it on a much smaller specialized dataset. Instead of starting from scratch with random mathematical values (weights), the model begins with a foundational understanding of visual elements like edges, textures, and shapes.

## 3. Detecting Real vs Fake Images

**(Open question) Technical speaking, how can we tell the image is a real one, or a fake one?**

- Frequency domain analysis
- Checking the digital metadata for the image (Best effort only)
- Detecting inconsistency and unnatural parts in the image
- Applying automated AI detection tools (Really working?)

## 4. Components of a Reinforcement Learning Agent

**What are the main components in a reinforcement learning agent?**

Policy, value function and model.

## 5. Q-function

What is Q-function?

- To quantify goodness/badness of states and actions.
- To aid selection among actions.

## 6. Steps in a Typical Reinforcement Learning Algorithm

**What are the steps involved in a typical Reinforcement Learning algorithm?**

Reinforcement learning is basically a trial-and-error learning process.

1. The agent interacts with the environment by performing an action.
2. The agent performs an action and moves from one state to another.
3. The agent receives a reward based on the action it performed.
4. Based on the reward, the agent knows whether the action is good or bad.
5. If the action is good (a positive reward), then the agent prefers performing that action. If the action is bad (a negative reward), then the agent tries performing other actions that can result in a positive reward.

## 7. Supervised Learning vs Reinforcement Learning

**What are the main difference between supervised learning and reinforcement learning?**

In supervised learning, the learning model is presented with an input and desired output. It learns by example. Reinforcement Learning has different tasks, such as exploitation or exploration, Markov decision processes, policy learning, deep learning, and value learning.

## 8. Self-Driving Car: Input and Output Devices

**You are working as a data engineer in the car industry. You are exploring the possibilities in manufacturing a self-driving car. A self-driving car is capable of travelling without human input. However, there are some difficulties in developing the self-driving car agent.**

**What are the compulsory input and output devices of a self-driving car?**

- Input devices: front cameras, rear camera
- Output devices: wheels, windows

## 9. Four Actions of a Self-Driving Car Agent

**Define four actions of a self-driving car agent.**

- Move forward
- Move backward
- Spin the wheel
- Open the windows
- Close the window
- ... etc.

## 10. Four Operations of a Self-Driving Car Agent

**Define four operations (e.g. car parking) of a self-driving car agent.**

- Stop in front of the red traffic light
- Drive along the road
- Stop in front of the zebra crossing when passer-by around it
- Close the window then get into the tunnel
- ... etc



# Lecture 12 Case Studies (IV) Game Problems

## 1. AI generated 3D model

**How do AI generated 3D models work?**

1. Understand the prompt, including object type, materials, style. 
2. Predict the underlying 3D structure, often a mesh. 
3. Use spatial intelligence to predict what the back of the object looks like 4. Apply Physically based rendering textures to tell the engine how the surface reacts to action, light.

## 2. Evaluate 3D model

**How can we evaluated the quality of a generated 3D model?**

1. Hausdorff Distance: Measures the maximum surface deviation between two models. 
2. Chamfer Distance (CD): Calculates the average distance between each point on the generated model and the nearest point on the reference. 
3. Manifold/Watertight Check: Ensures the mesh has no holes or non-manifold edges.

4. Triangle Uniformity: Evaluates if the polygons are evenly sized and shaped. 
5. Polygon Count: Balances detail against performance. 
6. ... etc

## 3. 3D object representing types

**Explain the difference between representing a 3D object as a point cloud, voxels, or a polygonal mesh. Which is most efficient for generative AI?**

1. Point Clouds: A collection of 3D points of the surface. 
2. Voxels: The 3D cubes arranged on a regular grid (similar to LEGO / Minecraft structure). 
3. Polygonal Mesh: A collection of vertices, edges, and faces (usually triangles or quads) that define a surface.
4. Most GenAI tools use polygonal mesh, as it is the most efficient for actual use. Unreal and Unity engines work better (more memory efficient) with mesh.
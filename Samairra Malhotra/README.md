![BeyondQuantum Banner for Research Projects](../BeyondQuantum_Banner_Research_Projects_2025.png)

# EXOPLANET DETECTION VIA KEPLER DATA: A COMPARATIVE STUDY OF QUANTUM AND CLASSICAL MACHINE LEARNING MODELS

Ever since I was a young girl admiring the glow-in-the-dark stars on my bedroom ceiling, I always wondered if we are all alone in this world, and if life exists beyond Earth. Exoplanets fascinate me; it's like being part of a giant cosmic family, and I can't help but wonder about the other members. My research is motivated by a deep hunger to explore the unknown. This project is my first step toward my goal of finding habitable exoplanets and improving our methods for detecting them. The intersection of astrophysics, which explores the unthinkably enormous, and quantum mechanics, which studies the infinitesimally small, is undeniably beautiful. I aim to unite the subjects that ignite my passion the most, and this work embodies that commitment.

## **INTRODUCTION**

### _What?_

Exploring exoplanets has emerged as a cornerstone of modern astrophysics in recent decades. My research is based on the comparison of the design and implementation of cutting-edge classical and quantum machine-learning techniques to detect exoplanets within the Kepler Objects of Interest Cumulatives Dataset from NASA Exoplanet Archive.

Since 2009, NASA has launched the Kepler and TESS missions to survey the depths of space in search of exoplanets, to discover what kinds of worlds exist outside of our solar system. My goal is to explore how deep learning algorithms can help in classifying the presence of exoplanets.

The main method used by Kepler to detect exoplanets is the transit method. Exoplanets may give themselves away when they pass in front of a star and dim some of its light. The passage of a planet between a star and Earth is called a "transit." If such a dimming is detected at regular intervals and lasts a fixed, repeated length of time, then it is very likely that another, dimmer object is orbiting the star. Machine learning models can learn to detect these subtle, repeating patterns even when the signal is weak or partly obscured by noise. By plotting stellar brightness as a function of time, one can observe a light curve with periodic dips, each corresponding to a planetary transit.

I have utilized the Lightkurve Python module to analyze light curves obtained by the satellites. After preprocessing the data, I worked with the transit light curve of a confirmed exoplanet, Pi Mensae. Given its initially uneven and complex structure, which made interpreting it hard, I applied further manipulation to smooth and clarify the signal (removing long term trends using a Savitzky–Golay filter, removing outliers using simple sigma clipping, removing infinite or NaN values, folding the data at a particular period (period=6.27, epoch_time=1325.504), and finally Reducing the time resolution of the array and taking the average value in each bin.), ultimately producing a more interpretable final graph. [(HowToFindAnExoplanet)](https://heasarc.gsfc.nasa.gov/docs/tess/HowToFindAnExoplanet-UserVersion.html)

![pimensae](https://github.com/user-attachments/assets/66066fce-90fc-4e68-b386-63edcdac03e1)

### _Why?_

Missions like Kepler and TESS observe hundreds of thousands of stars, generating terabytes of data which is quite noisy, with irregularities caused by instruments, starspots, or cosmic rays. Machine learning handles this scale far more efficiently than manual analysis or simple rule-based filters. Also, ML models don't need explicit equations to detect transit shapes—they learn from examples. Machine learning classifiers (like the ones used in my research) can learn to distinguish between real planets and imposters using labeled training data.

Classical machine learning still faces limitations when it comes to processing extremely high-dimensional, noisy, and entangled information. This is where Quantum Machine Learning becomes an exciting and valid frontier to explore. It introduces a fundamentally new approach and leverages the unique capabilities of quantum computing, which may process high-dimensional data more efficiently than classical methods. One of the primary objectives of my approach is to develop quantum algorithms for machine learning, encompassing both the adaptation of classical machine learning models and the creation of new models inspired by quantum computing principles.

## Classical Machine Learning Model

The code is referenced by [KDAG IIT KGP](https://kdagiit.medium.com/unveiling-the-cosmos-discovering-exoplanets-with-machine-learning-2b841ed40f85)

### Preprocessing of the data

I started off by data preprocessing, which involved dropping rows/columns with missing values, one-hot encoding categorical features, splitting data into train and test sets, and scaling data using StandardScaler(). I turned it into a binary classification problem and split the data into 70% training and 30% testing.

Now on the preprocessed data, I trained four ML algorithms, which include: Logistic Regression, Neural Network — MLP Classifier, Random Forest Classifier and Gradient Boosting Classifier.

I then evaluated these models based on accuracy, precision, F1-score, and recall metrics. After analyzing the performance metrics, it was concluded that the Gradient Boosting Classifier was the best choice.

To evaluate my model further, I visualized a confusion matrix of the Gradient Boosting Classifier as a heatmap, to show how many samples were correctly vs. incorrectly classified. The confusion matrix breaks down the predictions into correct and incorrect categories, helping one go beyond accuracy to evaluate how the model behaves per class.
![cml](https://github.com/user-attachments/assets/e4e82fcc-c584-4266-afa3-08fdd41bc255)


## Quantum Machine Learning Model

I built a hybrid quantum-classical neural network using PennyLane and PyTorch, structured for binary classification.

I started the preprocessing by dropping irrelevant columns, filtering the dataset to include only two target classes and encoded them to: 'CANDIDATE' → 0 and 'CONFIRMED' → 1, filling missing values using the mean for numerical columns and mode for categorical ones, one-hot encoding categorical features, standardizing all feature values to have zero mean and unit variance, padding or truncating the resulting feature vectors to length 64, which corresponds to 2<sup>6</sup> — the required size for amplitude embedding on 6 qubits and then normalizing each 64-D vector to unit length to satisfy quantum state requirements.

After this, I encoded classical data into a quantum state, allowing it to be trained with classical optimizers. My model consists of a quantum layer (the QNode wrapped by TorchLayer) which outputs 6 real values, a fully connected linear layer (nn.Linear) that maps these 6 values to a single logit. And a sigmoid activation function to output a probability score between 0 and 1, suitable for binary classification.

To avoid a shape mismatch error during training, I converted the NumPy arrays to PyTorch tensors and wrapped them into a TensorDataset for use with DataLoader. I then trained for 25 epochs using mini-batch gradient descent (batch size = 8). And for each batch, I first cleared previous gradients, then passed inputs through the hybrid model, computed binary cross-entropy loss between predictions and labels, performed backpropagation to compute gradients across both classical and quantum parameters and updated the model using the Adam optimizer with a learning rate of 0.01. After this, I logged the epoch-wise total loss, observing its decrease over time to monitor convergence.

![epoch](https://github.com/user-attachments/assets/fa35e766-9f8f-4244-bdbe-3b3dc82544e2)

Lastly, I evaluated my model based on accuracy, precision, F1-score, and recall metrics. And furthermore, visualized a confusion matrix as a heatmap to show how many confirmed exoplanets and candidates were correctly identified by the model and how many were not.
![qml](https://github.com/user-attachments/assets/ae9fa8e2-36ad-4635-9736-134c47ca4e87)


## Comparison between the performance metrics of the classical and quantum ML models


| Model               | Accuracy | Precision | F1 Score | Recall  |
|---------------------|----------|-----------|----------|---------|
| Classical ML Model  | 87.87%   | 88.22%    | 89.70%   | 91.23%  |
| Quantum ML Model    | 78.00%   | 76.65%    | 82.43%   | 89.16%  |

## Conclusion
After a thoroughly analyzing both the classical and hybrid quantum-classical machine learning models, I conclude that, based on the methods and implementation used in my project, the quantum approach <ins> does not </ins> demonstrate a clear advantage. While the quantum model successfully integrated amplitude embedding and variational circuits, its classification accuracy and learning dynamics did not significantly outperform the classical baseline. Further exploration with alternative quantum architectures, larger datasets, or more advanced encoding techniques may be necessary to fully assess the potential benefits of quantum machine learning in detecting exoplanets using Kepler’s Data.

## References
1. NASA Exoplanet Archive. [KOI Cumulative Dataset](https://exoplanetarchive.ipac.caltech.edu/cgi-bin/TblView/nph-tblView?app=ExoTbls&config=cumulative)
2. Hounsell, R. HowToFindAnExoplanet-UserVersion. [NASA TESS Science Support Center](https://heasarc.gsfc.nasa.gov/docs/tess/HowToFindAnExoplanet-UserVersion.html)
3. KDAG IIT KGP (2023). Unveiling the Cosmos: Discovering Exoplanets with Machine Learning [Medium](https://kdagiit.medium.com/unveiling-the-cosmos-discovering-exoplanets-with-machine-learning-2b841ed40f85)
4. Pennylane. AmplitudeEmbedding [Pennylane](https://docs.pennylane.ai/en/stable/code/api/pennylane.AmplitudeEmbedding.html)
5. Regadío, A. Exoplanet discovery with variational quantum circuits. Quantum Mach. Intell. 7, 11 (2025). [Springer Nature](https://doi.org/10.1007/s42484-024-00229-1)
6.  Nikoletos, K. (2025). Quantum-ML-Classification-with-PennyLane. [GitHub](https://github.com/Nikoletos-K/Quantum-ML-Classification-with-PennyLane)
7.  Gottlieb, J. (2023). Finding Exoplanets Using Machine Learning. [Medium](https://medium.com/@joshuadavidgottlieb/finding-exoplanets-using-machine-learning-e9d93b95c182)



   
> The research poster for this project can be found in the [BeyondQuantum Proceedings 2025](https://thinkingbeyond.education/beyondquantum_proceedings_2025/).


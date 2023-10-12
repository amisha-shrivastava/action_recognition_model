# Action Recognition Model
Action Recognition is a computer vision task that involves recognizing human actions in videos or images. The goal is to classify and categorize the actions being performed in the video or image into a predefined set of action classes.

## Why action recognition is useful?
Action recognition in videos is valuable for various reasons across different fields and applications:

1. **Automated Surveillance**: Recognizing atomic actions helps in identifying specific behaviors in surveillance footage. For instance, recognizing falling can trigger an alert for immediate assistance, ensuring timely help in case of accidents or emergencies.
2. **Elderly Behavior Monitoring**: Monitoring the activities of daily living is vital for the elderly, especially those living alone. By recognizing actions like walking or bending, caregivers or automated systems can ensure that the elderly are active and moving, which is essential for their health. Additionally, recognizing falling can enable quick response to prevent injuries.
3. **Human-Computer Interaction**: Understanding atomic actions like gestures or body movements is fundamental for natural human-computer interaction. For example, recognizing a gesture as "raising hand" or "pointing" can enhance communication in virtual environments or assistive technologies.
4. **Content-Based Video Retrieval**: Atomic action recognition aids in organizing and retrieving videos based on specific activities. For instance, if someone is looking for videos related to exercises involving bending for physical therapy, recognizing the action "bending" ensures accurate search results.
5. **Video Summarization**: In summarizing lengthy videos, recognizing atomic actions helps in identifying key moments. For example, in a video feed from an elderly person's home, summarizing moments of "falling" or "trouble walking" could provide useful insights for caregivers without them having to watch hours of footage.

## Long-term Recurrent Convolutional Networks (LRCN)
In 2015 a group of authors suggested end-to-end trainable class of architectures for visual recognition and description. The main idea is to use a combination of CNNs to learn visual features from video frames and LSTMs to transform a sequence of image embeddings into a class label, sentence, probabilities, or whatever you need. Thus, raw visual input is processed with a CNN, whose outputs are fed into a stack of recurrent sequence models.
<center>
<img src='https://drive.google.com/uc?export=download&id=1I-q5yLsIoNh2chfzT7JYvra17FsXvdme'>
</center>

### Fundamental properties of a Long-term Recurrent Convolutional Network (LRCN) model:

1. **Convolutional Layers (CNN)**: Extract spatial features from individual frames/images.
2. **Recurrent Layers (LSTM)**: Capture temporal dependencies across frames in videos or sequences.
3. **Time-Distributed Layers**: Ensures consistent input format across all time steps, applying the same set of weights to each frame's output.
4. **Pooling Layers**: Reduces spatial dimensions of features, enhancing computational efficiency and preventing overfitting.
5. **Dropout Regularization**: Prevents overfitting by randomly dropping out connections during training, enhancing model robustness.
5. **Loss Function**: Measures the difference between predicted and actual outputs, tailored to the specific task (e.g., classification, regression).
6. **Output Layer**: Tailored to the specific task, utilizes activation functions like softmax (for classification) or linear (for regression) for accurate predictions.

You can read the paper [Long-term Recurrent Convolutional Networks for Visual Recognition and Description](https://arxiv.org/abs/1411.4389?source=post_page---------------------------) by Jeff Donahue (CVPR 2015), to learn more about this architecture.

## Comparision with other Models

ConvLSTM, which combines convolutional layers with LSTM cells, and CNN-RNN are some of the models that can be used for recognizing actions performed in a video. But here, we will implement another approach known as the Long-term Recurrent Convolutional Network (LRCN) due to the following reasons:

1. **Unified Integration**: LRCN seamlessly integrates both spatial (via convolutional layers) and temporal (via recurrent layers) features, allowing it to learn complex patterns in both dimensions simultaneously.
2. **Simpler Architecture**: LRCN often has a simpler architecture compared to more complex models like ConvLSTM, making it easier to implement, train, and experiment with, especially in scenarios with limited computational resources.
3. **Ease of Implementation**: Due to its straightforward architecture, LRCN is easier to understand, implement, and troubleshoot, which can lead to faster development and iteration during the model-building process.
4. **Efficient Learning**: LRCN's design allows it to efficiently capture both short-term and long-term dependencies in sequential data, striking a balance between capturing intricate details and understanding broader contextual patterns.
5. **Enhanced Performance**: In tasks where understanding the interplay between spatial and temporal features is crucial, LRCN often outperforms models that address these aspects separately, leading to more accurate action recognition results.

## Process of creating model

- **`Step 1:` Visualize the Data with its Labels**

- **`Step 2:` Preprocess the Dataset**

- **`Step 3:` Split the Data into Train and Test Set**

- **`Step 4:` Implement the LRCN Approach**
 
    - **`Step 5.1:` Construct the Model**
    
    - **`Step 5.2:` Compile & Train the Model**
    
    - **`Step 5.3:` Plot Model’s Loss & Accuracy Curves**
    
- **`Step 6:` Test the model on YouTube videos**

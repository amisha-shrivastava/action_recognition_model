                              LRCN(Long Term Recurrent Convolutional Network)
Generally pre-trained CNN model like VGG, ResNet, or Inception as feature extractors can be used, that can be fine-tuned for the problem and the LSTM model can then use the features extracted by CNN, to predict the action being performed in the video.
But here, we will implement another approach known as the Long-term Recurrent Convolutional Network (LRCN), which combines CNN and LSTM layers in a single model. The Convolutional layers are used for spatial feature extraction from the frames, and the extracted spatial features are fed to LSTM layer(s) at each time-steps for temporal sequence modeling. 


Using a single integrated model (such as LRCN, which combines CNN and LSTM layers) instead of two separate models (for example, a CNN for spatial features and an LSTM for temporal sequences) offers several advantages:

**Reduced Complexity**: A single integrated model often has a simpler architecture compared to the combination of two separate models. This can lead to a reduction in computational complexity, making the training and inference processes more efficient and easier to manage.<br>

**End-to-End Learning**: A single integrated model can learn both spatial and temporal features in an end-to-end manner. This means the model can automatically learn to extract relevant spatial patterns and understand the temporal relationships within the data without the need for manual feature engineering or explicit separation of spatial and temporal processing stages.<br>

**Joint Optimization**: Training a single model allows for joint optimization of both spatial and temporal components. The model's parameters are optimized together, ensuring that spatial and temporal representations are learned in a way that complements each other, potentially leading to a more effective and coherent representation of the data.<br>

**Feature Integration**: An integrated model can effectively integrate spatial and temporal features. The model learns to correlate spatial patterns with their temporal evolution, capturing complex spatiotemporal patterns that might be missed when processing spatial and temporal features independently in two separate models.<br>

**Easier Deployment**: Deploying a single model is often more straightforward than managing the deployment of two separate models. Having a unified model simplifies the deployment process, making it easier to integrate the model into real-world applications.

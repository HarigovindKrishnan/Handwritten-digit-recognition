# Handwritten-digit-recognition

This project involves employing two models, with the first one being composed of three convolutional layers (conv2D), two maxPooling layers, a flatten layer followed by two dense layers. The final dense layer consists of 10 neurons with the softmax activation function. The final dense layer holds the output to our model which is 10 values ranging from 0 to 1 and these values add up to 1. Thus it can be considered as essentially giving us probabilities of the 10 digits to recognize from.

![Screenshot](./Screenshot%202025-03-22%20185658.png)

The second model created in this project is to recognize the operator used in the equation. The model is trained to recognize only the four basic mathematical operators i.e. +, -, *, /.

![Screenshot](./Screenshot%202025-03-22%20185713.png)

The dataset consists of around 4700 images of digits followed by close to 2300 images of operators. These images are classified into folders with each folder name being the digit or operator whose images are stored in it. Thus, while loading the data, the folder name is given as the target value for the first model as the array indices of the 10 output neurons happen to be from 0 to 9. In case of the operators, the operators are featurized into the vectors: [1,0,0,0], [0,1,0,0], [0,0,1,0], [0,0,0,1] for +, -, *, / respectively as the output of the model would be a 1x4 matrix.

To compute the result of the handwritten equation containing 2 operands and one operator, such as:

![Screenshot](./Screenshot%202025-03-22%20185938.png)

We make an assumption that the 1st operand, the operator and the 2nd operand are spaced equally, as our approach involved dividing te image into three equal sections containing operand 1, operator and operand 2 respectively. The two operand images are fed to the first model while the operator image is fed to the second model and the predictions of these models are stored and then the result is computed.

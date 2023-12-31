
# SOURCES #
	
The online book I used to learn can be found here: http://neuralnetworksanddeeplearning.com/index.html
	
# INPUT PARAMETERS #

The program will prompt you input the following(scroll down explanations):
01. File with training data and answers.
02. Hidden layer count.
03. Neurons in each hidden layer.
04. Value range.
05. Batch size.
06. Generation count.
07. Learning rate.
08. Learning rate decrease.
09. File with testing data and answers.

# SAMPLE PARAMETERS #

How well the neural network is trained is very dependent on the training parameters and the size of the dataset.
Here are some sample values for the parameters that work all right and may be a good starting point:
* Hidden layer count: 1 or 2.
* Neurons in each hidden layer: 20 to 100.
* Value range: -0.1 0.1
* Batch size: 10      // I haven't played with this all that much.
* Generation count: 10 to 40
* Learning rate: 1.0
* Learning rate decrease: 1.1 to 2.0

# EXPLANATIONS #
					
01. File with training data and answers: give a file path to the following file:
	* This is a file with 2 matrices in it. The first matrix(input matrix) in the file contains the inputs for the input neuron layer
	  and the second matrix(output matrix) contains the answers(for the corresponding input),(see class 'Matrix' for implementation
	  details). Every row in the input matrix is input an vector for the input neuron layer. Every row in the output matrix is the
	  vector which is the correct answer for the corresponding input vector(same row in input matrix). The number of rows in the two
	  matrices MUST be the same or the program throws an exception (obviously every input should have and output and vice versa).
	* The user doesn't directly set the number of input and output neurons. When given a training data file the program reads the
	  columns of the two matrices and sets the input and output layers accordingly.
	* The file extension doesn't matter.
	
02. Hidden layer count: choose how many hidden layers the network will have.
	* Positive integer, can be 0.
	* The more hidden layers the slower the training and testing will be.
	* Usually the more hidden layers the greater the potential for training, but anything more than 3 hidden layers and you'll have to 
	  wait a long time to be done training. Try out 1 or 2 at first.
	
03. Neurons in each hidden layer:
	* N positive integers(can't be 0) where N is the hidden layer count.
	* The more neurons in the hidden layers the slower the training and testing will be.
	* Usually the more neurons the greater the potential but again, if too much training will be slow. Try out 50 to 100 at first.
	
04. Value range: input two real numbers num1 and num2 where num1 < num2.
	* This is a real number interval. The weights and biases of the network will be initialized with random numbers in this interval.
	* It seems like the interval [-0.1,0.1] produces good results when training but feel free to play with these values.
	
05. Batch size: how many training examples at once the training algorithm will use for the "Gradient descend".
	* Positive integer greater than 0.
	* The bigger the batch size the better the training (in general).
	* I think the bigger the batch size the slower the training (not 100% sure about that though).
	
06. Generation count: how many times the trainer will go through the whole training data set (and train the network).
	* The more times the better.
	
07. Learning rate: how "fast" the network will learn.
	* A real number greater than 0.
	* Like the other parameters there is a sweet spot with this parameter. Try out 1.0 at first and go from there.
	
08. Learning rate decrease: the factor with which the learning rate decreases after each generation.
	* Real number >= 1.0.
	
09. File with testing data and answers: a file of the same kind like the training data file.
	* Usually this is a file with a data set which the network was not trained on, to see how well it generalizes. But you can also
	  feed it the exact same file as the training file debug if the training parameters are adequate.

# EE-Code
## Purpose of this Project
This is the code for my extended essay. In this essay, I examined stock markets, and tried to predict stock performance based on previous information. With this information, I compared a few different optimization algorithms. The optimization algorithms I compared are stochastic gradient descent, genetic algorithms, and a combination of genetic algorithms and stochastic gradient descent algorithms. 

All the models that were created for this project were coded in python, only using numpy, sklearn (for the train_test_split), matplotlib (to create the graphs), time and psutil to see teh statistics of each of the models. This was done to prevent any libraries from implementing any optimizations that I would not be able to replicate, this would make the comparisons between models inaccurate, as some of them may have more optimizations than others. 

## Actual Experiment 

### Experiment Outline
All the model training code that works will be found in the models that work folder, here is a general description of what you can find in this folder. I used the versions without comments for code snippets in my essay in order to prevent the length of the code from exceeding the word limit, but the code comments were left so I would know what the code did:
- fifth_trial_commented - This is the stochastic gradient descent approach. It is named this because it was my fifth attempt at getting it to work. (the code that is not commented is also in this folder)
- gann - This is the genetic algorithm neural network, there are two different versions, one with comments and one without
- sgann - I thought I was pretty smart coming up with this algorithm, but people have already named it :( This standards for stochastic gradient/genetic algorithm neural network. Which is the combination with the two other methods mentioned above. There are also two different versions, one with comments and one without.

In case you want to see the parameters that were used in the experiment, but do not want to look at the code (very fair, the code is monkey), here it is:
Stopping Criteria: Patience: 40 
The patience value described how many generations or epochs the neural network goes through before ending the optimization process. This is important in ensuring a process that is not returning better weights and biases does not continue to consume system resources. 

**Batch Size: 100**
This is the number of elements involved in each training generation or epoch. Rather than training on the entire dataset or individual datapoints, the neural network finds the average error of the batch and optimizes based on this. A batch size too small results in the neural network continuously overfitting to a singular datapoint, sacrificing the fitness of the entire dataset to optimize for a singular point. A batch size too large results in the neural network spending large amounts of time on a singular error, and also introduces the possibility of optimization stagnating. 

A middle ground between these two scenarios was found by using a batch size of 100. 

**Layers and Layer Size: 6 Layers in Total ([150, 150, 150, 150, 150, 1])**
This is the neural network construction, and describes the process from input to output. 

The first layer is the input layer, and described how many items are passed into the neural network, there are 150 neurons in the first layer as that is the number of elements being passed into the neural network. The next 4 layers are hidden layers, and this is when the weights and biases are applied to the input. Finally, the last layer of 1 is the output of the neural network, and will be compared to the expected output of the input. 

All layers will be dense layers, meaning all nodes from the current layer are connected to the next layer, typically this is not the case in order to reduce overfitting. In this experiment, however, this will not be implemented to reduce complexity and to ensure the different approaches all have parameters as similar to one another as possible. 

**Stochastic Gradient Descent Approach Only: Learning Rate: 0.005**
This value is specific to the stochastic gradient descent approach. It specifies how quickly weights and biases will be altered in order to better fit the dataset. A higher value means weights will mean the neural network will more quickly adjust to error, however, it will also be difficult for the neural network to fine tune its weights and biases, leading to the algorithm not being fully optimized. 

The learning rate of 0.005 was chosen for the stochastic gradient descent as it has a good trade off between speed and accuracy. 

**Genetic Algorithm Only: Population Size: 600**
This value is specific to genetic algorithms. It specifies how many individual solutions will be generated to attempt to achieve the lowest error possible. A larger population typically means the algorithm will be able to search through a much larger number of possible solutions, increasing the chance it finds the optimal solution. This larger search space comes at the expense of RAM usage. 

Although typically, the greater the population size the better, I chose this number to demonstrate the effectiveness and requirements of genetic algorithms. 

**Genetic Algorithm Only: Mutation Rate: 0.01**
This value is specific to genetic algorithms. It specifies the chance that a number will change pr “mutate” from the previous generation. This is vital as it expands the search space of the algorithm, and ensures the optimal solution can still be found even if it is not part of the original population. A mutation rate too low or zero means the genetic algorithm cannot search in areas individuals were not initiated within, while a mutation rate too high results in the neural network not retaining any semblance of the previous generation. 

I chose the value of 0.01 as it would ensure steady optimization while not preventing the algorithm from expanding the search area. 

Here are some of the terms that I used in the extended essay that apply to genetic algorithms, this is just copied over from my essay: 
| Term | Definition | 
| -- | -- |
| Genes |  A data type that determines how an individual will “react” to a particular data input. Typically known as weights outside the field of genetic algorithms.|
| Solution | A possible way of answering the task, does not mean it is the most optimal way of completing a task (which is called the optimal solution). In this context, optimal is the model that most accurately predicts if a stock will increase or decrease. |
| Chromosomes | A string or other data type that contains at least one gene for an individual. In the case of a neural network, it is an array with the weights and biases. This is what the genetic algorithm will be optimizing. |
| Individual | A possible solution to the issue, with its unique chromosome. |
| Population | The collection of all individuals |
| Variation | The variety of traits present within the population of chromosomes. Without variation, all chromosomes in a population would be identical| 
| Generation | Iteration of individuals since the beginning of the genetic algorithm. Each generation is built upon the previous generation (other than the first one, which is initialized randomly) |
| Fitness | How good an individual is at predicting the outcome of input |
| Stopping Criteria | A metric that is used to stop the traoning of the genetic algorithm |



### Findings of the Project 

### Limitations of the Experiment

## What I've Learned
Throughout the writing process, I had to learn how to implement stochastic gradient descent, which required me to learn about partial derivatives used in back propagation. I also learned about how genetic algorithms worked, the different parts of it, different selection methods (to chose the next generation), and how future generations are created. 

The purpose of this extended essay was to compare different optimization algorithms, and how they may have impacted the field of stock prediction in the late 1900s and early 20th century. Based on the findings that I found within the experiment, I inferred that there was likely a large increase in GPU and RAM investment, as genetic algorithms are extremely computationally and memory intensive, but are capable of reaching greater accuracy (lower error/loss). 

During the research phase of this project, I also came across many new papers that I never would have encountered had I not created this extended essay. Namely, the other problems genetic algorithms are capable of solving more efficeintly than other methods. For example, I realized that genetic algorithms are good for search algorithms, which are used in drones to search areas. These algorithms have extremely high complexity, and the genetic algorithms unique ability to search a wide solution space is perfectly suited to optimize for this problem. 

Originally, I wanted to research how computers had impacted the field of stock prediction, and even though this question was far too broad for the essay, I was exposed to many different techniques used in stock prediction which I would like to try to look into for the future. 



## Next Steps for this Project

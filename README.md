# Solving the AND Problem with a Neural Network

This project demonstrates the implementation of a simple neural network to solve the logical AND function.

## Introduction

The logical AND function is a fundamental concept in digital logic. It takes two binary inputs and returns a binary output that is 1 only if both inputs are 1, and 0 otherwise. This project utilizes a simple feedforward neural network with a single hidden layer to learn and replicate this behavior.

## Input and Expected Output

The network is trained using the four possible combinations of binary inputs for the AND gate:

| Input 1 | Input 2 | Expected Output (AND) |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

The input data is represented as a 2x4 numpy array:
```python
X = np.array([[0, 0], [0, 1], [1, 0], [1, 1]]).T
```
The expected output is a 1D numpy array:
```python
d = np.array([0, 0, 0, 1])
```

## Network Architecture

The neural network consists of:
- An input layer with 2 neurons (for the two binary inputs).
- A hidden layer with 2 neurons.
- An output layer with 1 neuron (for the single binary output).

## Training Process

The network is trained using the backpropagation algorithm to minimize the error between the predicted output and the expected output.
- **Learning Rate:** 0.1
- **Epochs:** 180,000

The error is monitored during training and plotted to visualize the learning progress.

## Testing Results

After training, the network is tested with the same input data to verify its performance. The final predicted outputs are compared to the ground truth:

- **Final Output After Training:** `[[2.76880437e-04 4.65690303e-03 5.00564052e-03 9.93286514e-01]]`
- **Ground truth:** `[0 0 0 1]`
- **Average Absolute Error:** `0.004163240182199762`

The predicted outputs are very close to the ground truth values, indicating that the network has successfully learned the AND function.

## Error Plot

The following plot shows how the error decreased over the training epochs, demonstrating the learning process:
```python
plt.plot(error_list)
plt.title('Error')
plt.xlabel('Epochs')
plt.ylabel('Error')
plt.show()
```

The plot visually confirms that the network converged and the error was minimized over time.
<img width="599" height="455" alt="Untitled" src="https://github.com/user-attachments/assets/72e3284f-0d0e-40af-a449-cd8490ef705a" />

### Summary:

### Data Analysis Key Findings

*   The input data `X` was successfully modified to represent the AND problem inputs as a 2x4 transposed array: `[[0, 0], [0, 1], [1, 0], [1, 1]].T`.
*   The expected output data `d` was successfully modified to represent the AND problem outputs as a 1D array: `[0, 0, 0, 1]`.
*   The neural network architecture, consisting of 2 input neurons, 2 hidden neurons, and 1 output neuron, was deemed suitable for solving the AND problem.
*   The training process, using a learning rate of 0.1 and 180,000 epochs, successfully reduced the average absolute error from approximately 0.023 to 0.0041.
*   After training, the network's output for the AND inputs was approximately `[[0.0003, 0.0049, 0.0048, 0.9933]]`, which is very close to the ground truth `[0, 0, 0, 1]`.
*   The average absolute error after testing was approximately 0.0042, confirming the network's successful learning of the AND function.
*   The content for the `README.md` file was successfully generated, describing the project, inputs, outputs, network architecture, training, and testing results.

### Insights or Next Steps

*   The chosen network architecture and parameters were effective in solving the linearly separable AND problem.
*   Consider exploring the impact of different network architectures or training parameters (e.g., number of hidden neurons, learning rate schedule) on the training speed and final accuracy.


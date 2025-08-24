# Traffic Project

A project to analyze and manage traffic data from the ```gtsrb``` dataset.

## Features

- Data collection and processing
- Traffic visualization
- Predictive analytics
- Convolutional Neural Network

## Process
### Data Processing
```load_data(dir_name)``` function collects the images from each subdirectory in `gtsrb` directory of traffic images and is labelled with the corresponding directory title. For instance, `gtsrb/0` stores pictures of 20 kmh speed limit signs which are then stored in the program with label `"0"`. `dir_name` is a command line argument that supplies the name of the directory storing the images.

### Neural Network
`get_model()` returns a compiled convolutional neural network. It first applies 32 different kernels on the image. Then pools to decrease the input size of the neural network. The process is repeated with 64 kernels and another round of pooling before being flattened. The flattened image is used as input into a neural network with three layers, with 128, 64, and 64 units respectively before a final output layer with the number of subdirectories in `gtsrb` for each image type.

`image convolution` --> `pooling` --> `image convolution` --> `pooling` --> `flatten` --> `128 unit layer` --> `64 unit layer` --> `64 unit layer` --> `43 unit output layer`

## Usage

```bash
npm start
```
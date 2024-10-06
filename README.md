# K-Means Clustering for Image Segmentation

This project implements K-means clustering to segment an image into different color clusters. It utilizes the K-means algorithm to classify pixels in an image into `k` distinct groups based on their color similarity, effectively compressing the image and highlighting dominant colors.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Usage](#usage)
- [Function Description](#function-description)
- [Results](#results)
- [License](#license)

## Prerequisites

To run this code, ensure you have the following libraries installed:

- `numpy`
- `opencv-python`
- `matplotlib`

You can install the required packages using pip:

```bash
pip install numpy opencv-python matplotlib
```

## Usage

1. Place an image named `Nature.jpg` in the project directory.
2. Run the script. It will display the original image and the clustered image side by side for each value of `k` from 1 to 25.
3. The cost function will be printed for each `k` and plotted at the end of the script.

## Function Description

### `k_means_clustering(k, image, image_rgb)`

This function performs K-means clustering on the input image.

#### Parameters:
- **k**: The number of clusters (color groups) to segment the image into.
- **image**: The original image in BGR format (as read by OpenCV).
- **image_rgb**: The original image in RGB format for displaying with matplotlib.

#### Returns:
- **cost**: The cost function value for the clustering, indicating how well the clustering fits the data. A lower cost signifies better clustering.

#### Process:
1. **Reshape the image**: Converts the image from 3D (height, width, channels) to a 1D array of pixel values.
2. **Randomly choose initial centroids**: Selects `k` random pixel values as the initial centroids.
3. **Calculate distances**: Computes the absolute distances of each pixel from each centroid.
4. **Assign pixels to centroids**: Each pixel is assigned to the closest centroid based on the calculated distances.
5. **Update centroids**: New centroids are calculated as the mean of the assigned pixels.
6. **Iterate**: This process is repeated until the centroids no longer change significantly.
7. **Calculate cost**: The sum of squared distances of the pixels from their assigned centroids.
8. **Reconstruct the image**: The original pixel values are replaced with their corresponding centroid values.
9. **Display images**: The original and clustered images are displayed side by side.

## Results

After running the script, the output will show the original image and the clustered image for each value of `k`, along with the corresponding cost for clustering. Additionally, a plot of the cost function against the number of clusters will be displayed to help determine the optimal number of clusters.

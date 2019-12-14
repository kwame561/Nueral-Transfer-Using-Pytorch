# Neural Transfer Using Pytorch

### Add Virtual Environment to Jupyter

Add my virtual environment to the Jupyter notebook via the command line below.

```
python -m ipykernel install --name=py37
```

Notebook code based entirely on the [PyTorch tutorial](https://pytorch.org/tutorials/advanced/neural_style_tutorial.html#underlying-principle).

We'll take an image `A` (content image) and run it through a Convolutional Neural Network (CNN) to map shape and object information on some internal layer within the network. Next, we repeat this mapping process with another image `B` (style-image) and map it's texture and color palette information on some other internal layer. Distance calculations are performed, one for the content (D<sub>C</sub>) and one for the style (D<sub>S</sub>). These will measure different the content and style are for both images. Finally, we take a third image `C` and transform it by minimizing the content-distance with `A` and the style-distance with `B`.

|                          Content-Image A (Dancing)                           |                         Style-Image B (Picasso)                          |
| :--------------------------------------------------------------------------: | :----------------------------------------------------------------------: |
| <img src="./images/contents/dancing.jpg" alt="Content-Image A" width="200"/> | <img src="./images/styles/picasso.jpg" alt="Style-Image B" width="200"/> |

### Change From PyTotrch Tutorial

Both the content-image and style-image were sized 128 x 128, hence why the output has such a low resoltion; I'm using a CPU - no money for a GPU - it just made sense. The turorial uses a second-order method to minimize the loss functions, L-BFGS (Limited-memory [Broyden-Fletcher-Goldfarb-Shanno](https://en.wikipedia.org/wiki/Broyden%E2%80%93Fletcher%E2%80%93Goldfarb%E2%80%93Shanno_algorithm)). However, I used an Adam ([Adaptive Moment Estimation](https://arxiv.org/pdf/1412.6980.pdf)) optimizer becuase it's less computationally intensize than the L-BFGS algortihm. The algorithm on the input image ran for 1000 iterations with a learning rate of 0.01, and the results are displayed below:

|                              Input-Image                              |                             Output-Image                              |
| :-------------------------------------------------------------------: | :-------------------------------------------------------------------: |
| ![alt Input-Image](./images/outputs/original_image.png "Input-Image") | ![alt Output-Image](./images/outputs/output_image.png "Output-Image") |

Jump to notebook: [Click Me!](./Neural_Transfer_Using_Pytorch.ipynb)

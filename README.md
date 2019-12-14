# Neural Transfer Using Pytorch

### Add Virtual Environment to Jupyter

Add my virtual environment to the Jupyter notebook via the command line below.

```
python -m ipykernel install --name=py37
```

Notebook code based entirely on the [PyTorch tutorial](https://pytorch.org/tutorials/advanced/neural_style_tutorial.html#underlying-principle).

We'll take an image `A` (content image) and run it through a Convolutional Neural Network (CNN) to map it's texture information and map it on some internal layer within the network. Next, we repeat this mapping process with aother image `B` (style-image) and map it on some other internal layer of it's style information. Distance calculations are performed, one for the content (D<sub>C</sub>) and one for the style (D<sub>S</sub>). These will measure different the content and style are for both images. Finally, we take a third image `C` and transform it by minimizing the content-distance with `A` and the style-distance with `B`.

|                               Content-Image A                                |                              Style-Image B                               |
| :--------------------------------------------------------------------------: | :----------------------------------------------------------------------: |
| <img src="./images/contents/dancing.jpg" alt="Content-Image A" width="200"/> | <img src="./images/styles/picasso.jpg" alt="Style-Image B" width="200"/> |

After running the algorithm on the input image, 300 iterations, the results are displayed below:

|                              Input-Image                              |                             Output-Image                              |
| :-------------------------------------------------------------------: | :-------------------------------------------------------------------: |
| ![alt Input-Image](./images/outputs/original_image.png "Input-Image") | ![alt Output-Image](./images/outputs/output_image.png "Output-Image") |

Jump to notebook: [Click Me!](./Neural_Transfer_Using_Pytorch.ipynb)

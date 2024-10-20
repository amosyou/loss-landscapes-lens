# Loss Landscapes in a Lens

![loss landscape on spectacles](assets/lens.gif)

This project was inspired by [Visualizing the Loss Landscape of Neural Nets](https://arxiv.org/abs/1712.09913), a NeurIPS 2018 paper. The paper describes a method for visualizing loss landscapes of neural networks by applying normalization to specific model parameters, and then plotting loss values along 2 randomly selected directions during training. This project directly applies the  paper by rendering these loss landscapes in real life using the Snap Spectacles. 

With wearable tech and smart glasses like the Snap Spectacles, we can finally have an immersive experience in AR to better visualize the shapes of these 3D surface plots, and have visibility into more fine-grain or precise details. The lens can be found [here](https://www.snapchat.com/lens/724f44537ca84400acef41af5ae386b3).

## Usage

1. To install dependencies, create a Python virtual environment and run the following command.

```bash
pip install -r requirements.txt
```

2. `loss-landscape/` corresponds to the [loss-landscape](https://github.com/tomgoldstein/loss-landscape) repo, which provides code to generate .vtp files for the 3D loss surface plots of a few models. 

3. Lens Studio only allows for 3D object imports from .fbx, .obj, and .gltf file formats, so we convert the .vtp files to .obj files using PyVista, a 3D plotting Python library. The notebook can be found at `vtp2obj.ipynb`.

4. `lens/` holds the Lens Studio project with the project file and assets. We import these loss surface meshes into Lens Studio as assets, and customize the arrangement of the camera, change scaling and positioning of the mesh, enable surface detection, and apply material to the mesh for the color gradient.

And with some sync'ing to the Spectacles, we have a working lens!

## Future Work

Although we have working code to generate the 3D surface plots given some model, we're hoping there's a way to automate the setup of the assets in Lens Studio. 

We're also hoping to continue fine-tuning some LLMs such as Llama 3 and diffusion models like FLUX.1-dev to see how the loss surfaces differ for newer models compared to the traditional models (ie. DenseNet, ResNet, and VGG) presented in the paper.

## Acknowledgements

Code heavily borrowed from [loss-landscape](https://github.com/tomgoldstein/loss-landscape).

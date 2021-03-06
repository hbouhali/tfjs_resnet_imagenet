# ResNet Model trained on ImageNet
[![GSOC](https://img.shields.io/badge/GSOC-2019-yellow)](https://summerofcode.withgoogle.com/organizations/6137730124218368/?sp-page=2#4558376158101504)
![GitHub](https://img.shields.io/github/license/paulsp94/tfjs_resnet_imagenet)
![npm (tag)](https://img.shields.io/npm/v/resnet_imagenet/latest)

The ResNet50 model pretrained on imagenet for TensorFlow.js as a layers model.   
On ImageNet, this model gets to a top-1 validation accuracy of 0.749 and a top-5 validation accuracy of 0.921.   
The default input size for this model is 224x224.   

This model has been converted, using the [tfjs-converter][1].  
The base model and weights were taken from [keras][2].

[1]: https://www.npmjs.com/package/@tensorflow/tfjs-converter
[2]: https://keras.io/applications/#resnet

Install `npm install resnet_imagenet`

## How to use

```javascript
import ResNetPredictor from 'resnet_imagenet';

const tabbyCatURI = 'https://upload.wikimedia.org/wikipedia/commons/6/66/An_up-close_picture_of_a_curious_male_domestic_shorthair_tabby_cat.jpg';

const run = async () => {
    const predictor = await ResNetPredictor.create();
    const prediction = await predictor.classify(tabbyCatURI);
    return prediction;
}
```

To try the model you can just load it using:    
```javascript
ResNetURL = 'https://raw.githubusercontent.com/paulsp94/tfjs_resnet_imagenet/master/ResNet50/model.json';
const ResNet = await tf.loadLayersModel(ResNetURL);
```
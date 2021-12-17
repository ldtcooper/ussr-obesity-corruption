# README

## Installation
**NB**: there is a problem with keras_vggface which will cause the following error:
```
keras_vggface: No module named 'keras.engine.topology'
```
The solution to this was found in this StackOverflow post: https://stackoverflow.com/questions/68862735/keras-vggface-no-module-named-keras-engine-topology

## Credits
The contents of the `2017-images` folder are taken from the appendix to Pavlo Blavatskyy's paper "Obesity of politicians and corruption in post-Soviet countries" [(Link)](https://onlinelibrary.wiley.com/doi/abs/10.1111/ecot.12259). The only exceptions to this are `images.json` and `img-script.js`.`img-script.js` is a script which generates the contents of `images.json`, which associates the image file names with their associate countries.

The `vgg_face.*` files were all provided by Blavatskyy, as was `svr_parameters`. `bmipredictor.py` was taken from Blavastskyy's appendix, although minor changes were made to make it run.
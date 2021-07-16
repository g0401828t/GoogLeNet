# GoogLeNet
GoogLeNet implemented with pytorch

# Network Architecture
![image](https://user-images.githubusercontent.com/55650445/125942107-8efa83c7-d122-4293-a5c4-82c9c191f130.png)

![image](https://user-images.githubusercontent.com/55650445/125942127-5ad4b5e8-1d76-4f12-95f3-8132ceeb2001.png)


# Main concepts
## NIN (Network in Network)
- Used MLP instead of conv layers to extract features
- Conv is a linear operation but MLPs are non-linear.
- So MLP is a better feature extractor than Conv
- MLP is the same as 1x1 conv
![image](https://user-images.githubusercontent.com/55650445/125942607-ec91193c-8b45-4f29-9a01-7ed7f34cc49b.png)

## 1x1 Conv
- Reduces the feature map channel size
- Reduces computation

## Inception Module
![image](https://user-images.githubusercontent.com/55650445/125942900-43cca675-d29a-4f41-90ad-d078f20d7ed8.png)
- allows the network to see different field of view (Receptive field)
- 1x1 conv helps 3x3 and 5x5 reduce computations by reducing the channel size.

## Auxilary Classifier
![image](https://user-images.githubusercontent.com/55650445/125943504-773835fb-bc3d-4f97-a502-bd1c0a344975.png)
- To address the vanishing gradient problem
- Attached on Inception4a and Inception4d
- Only attatched when training!!! <- becareful when implementing the code!
- Total loss = main_loss + 0.3 * (aux1_loss + aux2_loss)

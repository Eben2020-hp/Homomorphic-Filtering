# Implementation of Homomorphic Filtering on images in MATLAB

Every pixel of an image can be represented by an illuminance and reflectance components. The illuminance L(x,y) represents the amount of light upon the pixel, having slow variations through space. While that the reflectance R(x, y) indicates how much light is reflected. This component is strictly related to the material where the light it being reflected on and can have fast variations.

So, every pixel can be understood as being a mix of these two components:
> I(x, y) = L(x, y) * R(x, y)

This way, to fix the lighting on a scene it does not only take an increase to the illuminance component, since it is mixed with the reflectance.

___
## ***Operation***

![Homomorphic Filtering](https://user-images.githubusercontent.com/66016994/129488529-67e28dbc-04d8-4c0f-a9fc-c6d945bb839b.png)

- We have to transform the equation into frequency domain in order to apply high pass filter. However, it's very difficult to do calculation after applying Fourier transformation to this equation because it's not a product equation anymore. Therefore, we use 'log' to help solving this problem.

- Then, we apply Fourier transformation.

- Next, applying high-pass filter to the image. To make the illumination of an image more even, the high-frequency components are increased and low-frequency components are decrease.

- Afterward, returning frequency domain back to the spatial domain by using inverse Fourier transform.

- Finally, using exponential function to eliminate the log we used at the beginning to get the enhanced image

The following figure show the result of applying Homomorphic Filter. The figures are produced by using Matlab.

![Original Image vs Homomorphic Filtered Image](https://user-images.githubusercontent.com/66016994/129489894-b7a7a7d9-0e45-4643-86fe-46f4184ef734.jpg)


According to the above figures, we can see that how homomorphic filtering is used for correcting non-uniform illumination in image, and the image become clearer than the original image.

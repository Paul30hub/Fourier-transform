## Work organization
This document describes the work organization between BURGAT Paul, CORDOVAL Chloë, GUILLAUMONT Pierre and KOAN Kenjy.

### Koan Kenjy :

I handled the image processing. My task is to take any image, sample its profile by converting it into an X and Y parametric path in order to reconstruct the original image.


__________________________________________________________________________________________________________________________________________________________________________________________________________________________________

### Cordoval Chloë : 

My part is to find the fourier coefficients to approximately locate given points : I will create a class for our package that provides functions for calculate the Fourier approximations 

__________________________________________________________________________________________________________________________________________________________________________________________________________________________________

### Burgat Paul and Guillaumont Pierre :
Our part is to display an animation drawing the image with circles spinning with Fourier's coefficients. For reach this purpose, we will create a class of functions. We will collect Fourier's coefficients and order wanted before display a .gif contain animation. 

__________________________________________________________________________________________________________________________________________________________________________________________________________________________________


=======
# Task affectation

* [Kenjy] Image processing and conversion into points : 
    + extracting a path of coordinates from a an image
    + This path forms the basis of the parametric functions that I will be approximating using Fourier series
    + One Cycle -> Complex Numbers -> For X and Y
    
* [Chloë] Find the fourier coefficients to approximately locate given points : 
    + Function to generate x+iy at given time t
    + Function to evaluate y at time t using Fourier approximation of degree N
    + Function to calculate Coefficients
    + Approximation : 
                 - Evaluate function at all specified points in t domain
                 - Set intercept to same as original function

* [Paul and Pierre] Animation part :  - Calculate positions of each circle throughout cycle

# Circles to Animated Drawing - Maths Behind
If you have a line drawing in 2D space, you can describe this path mathematically as a parametric function, which is essentially just two separate single variable functions : $f(t) = (x(t), y(t))$.

![Fourier Transform](static/fourier_tr)

We need to calculate the Fourier approximations of these two paths, and use coefficients from this approximation to determine the phase and amplitudes of the circles needed for the final visualization. 

# Useful resources
https://betterexplained.com/articles/an-interactive-guide-to-the-fourier-transform/
https://contra.medium.com/drawing-anything-with-fourier-series-using-blender-and-python-c0881e1b738c


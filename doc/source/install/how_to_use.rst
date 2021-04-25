How to use ? 
=============

.. warning:: 
    *Important note on image selection:*

    For fast and clear drawings upload JPEG or PNG that are less than 50kb and can be made in a single path. 
    


Once you've installed the package, create a python file, for example 'script.py' and copy the following code : 

.. code-block:: python
   :emphasize-lines: 9,13,33

    import matplotlib.pyplot as plt # for plotting and creating figures
    import numpy as np # for easy and fast number calculation
    from math import tau

    from draw_circle_fourier import ImageReader
    from draw_circle_fourier import Fourier
    from draw_circle_fourier import DrawAnimation

    # Replace your_url with the url that contains an image
    image = ImageReader("your_url")
    time_table, x_table, y_table = image.get_tour()

    # Choose your order
    order = 20

    cf = Fourier(time_table, x_table, y_table,order)
    fouriercoeff = cf.coef_list(time_table, x_table, y_table, order)

    space = np.linspace(0,tau,300)
    x_DFT = [cf.DFT(t, fouriercoeff, order)[0] for t in space]
    y_DFT = [cf.DFT(t, fouriercoeff, order)[1] for t in space]

    fig, ax = plt.subplots(figsize=(5, 5))
    ax.plot(x_DFT, y_DFT, 'r--')
    ax.plot(x_table, y_table, 'k-')
    ax.set_aspect('equal', 'datalim')
    xmin, xmax = plt.xlim()
    ymin, ymax = plt.ylim()

    b = DrawAnimation(x_DFT, y_DFT, fouriercoeff, order, space, [xmin, xmax, ymin, ymax])
    anim = b.visualize(x_DFT, y_DFT, fouriercoeff, order, space, [xmin, xmax, ymin, ymax])
    
    # You can change the extension if you either want to save it as .gif or .mp4

    #Change based on what writer you have
    #HTML(anim.to_html5_video())
    #anim.save('pi.gif',writer='ffmpeg')
    anim.save('draw-fourier.gif',writer='pillow')
    


You have to replace 'your_url' in the ImageReader function with your own URL that contains an image in JPEG, JPG or PNG format.

You can try for example with this image : https://github.com/Paul30hub/Fourier_transform_drawing/blob/main/PACKAGE/draw_circle_fourier/DATA/velo.jpeg

Then, you can chose the 'order' for the calculation of the Fourier coefficients, which corresponds to the number of terms used to calculate the fourier series.

Finally, you can choose the extension if you either want to save the animation as .gif or .mp4

Run the code.


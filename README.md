# Minecraft image generator (wip)

Input an image to return a minecraft version of it. Uses python pillow and blocks from version 1.21.1. 
### Introduction & Features
This is a Minecraft image generator that I made during summer 2024! It utilizes Python Imaging Library (PIL/Pillow) to turn any inputted image into Minecraft blocks (from version 1.21.1)  For example:  

![firefly.png](readme/firefly.png) ![fireflymc.png](readme/fireflymc.png)  

This will also return the amount of all the blocks required to recreate the image (below are the block required to make the image above)...

![mcblocks.png](readme/mcblocks.png)

...as well as customize the detail of the generated image.

![flower1.png](readme/flower1.png) ![flowermchigh1.png](readme/flowermchigh1.png) ![flowermclow1.png](readme/flowermclow1.png)

### Process
After inputting an image and selecting the desired quality, the original image is cut up into little snippets (based on desired quality), and it's RGB value is compared with similarly-colored Minecraft blocks through finding each's euclidean distance on the 3 dimensional RGB Color space. The returned Minecraft block is then placed on it's spot in the original spot (similarly to how it would work in the Minecraft Game).  

### Runtime
It's pretty slow (O(n^2) runtime). Every snippet of pixels is accessed and compared to every single minecraft block. Pictures that are 500x500 px could take up to 5-7 minutes to fully process. My current solutions are to either implement a Median Cut Algorithm and cluster nearby similar colors together for faster runtime.  

Also on my blog [here](https://enyachen.xyz/Projects/mc).

*This project was an adaptation of another one of my uncompleted projects, [Beautiful Image Generator](https://github.com/3nya/Beautiful-Image-Generator).* 

# puzzle-solver
Preliminary idea is to use a picture of a single empty space in a puzzle and pictures of all the remaining pieces to find the one with the right shape.


Steps: 
1. Get an image of the puzzle with one missing piece - call it the "primary" image
2. Get images of all the remaining puzzle pieces
3. (Assuming that each image is a 2d array of RGB values) obtain certain RGB parameters to decide which pixels are the puzzle piece and which pixels are empty space. Also have parameters to determine which pixels are the missing piece in the first image.
  3a. AMBITIOUS: Possibly could build & train an ML model to find the best RGB parameters. The parameters that this model finds could be pre-loaded into the program, as long as the images are consistent.
4. With the parameters, for each image convert the 2d array of RGB values to a 2d array of zeroes and ones, with ones representing the puzzle piece. Call this grid of zeroes and ones a "key."
  4a. Flip the ones and zeroes for the primary image so it looks similar to the rest of the images
5. Build & train an ML model to find the key of the puzzle piece that most closely matches with the key of the primary image.


Acknowledgements:
The performance and success of this program (and specifically the model) depends on both the cut quality of the puzzle pieces and the picture resolution. With that being said, a higher resolution also means more pixels to process and convert to keys, which would make the program run much longer. At the moment, though, I'm not too worried about complexity.
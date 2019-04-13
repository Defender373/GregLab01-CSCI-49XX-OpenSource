# Gregory Saini - Lab11

## Checkpoint 1
![Checkpoint1OSlabLast](https://user-images.githubusercontent.com/17090994/56074105-dc9a3e00-5d7a-11e9-9fe6-19b78d94f5c2.PNG)


## Checkpoint 2
![Checkpoint2OSlabLast](https://user-images.githubusercontent.com/17090994/56074136-43b7f280-5d7b-11e9-8739-2374473fad4b.PNG)


## Checkpoint 3
I had trouble getting model.predict() to work with my images.

### Original Images
![clothing1](https://user-images.githubusercontent.com/17090994/56074153-7d88f900-5d7b-11e9-98f6-2cfbc42b33ad.jpg)
![clothing2](https://user-images.githubusercontent.com/17090994/56074154-7d88f900-5d7b-11e9-81e2-a1d9165b8bef.jpg)
![clothing3](https://user-images.githubusercontent.com/17090994/56074155-7d88f900-5d7b-11e9-9a53-a1e022f46d70.jpg)

### Greyscaled 28x28 images
![clothing1updated](https://user-images.githubusercontent.com/17090994/56074166-ac06d400-5d7b-11e9-80bb-3bd7d7d26a87.jpg)
![clothing2updated](https://user-images.githubusercontent.com/17090994/56074167-ac06d400-5d7b-11e9-864c-ec8c919df5a9.jpg)
![clothing3updated](https://user-images.githubusercontent.com/17090994/56074168-ac06d400-5d7b-11e9-900e-3bf8c075c290.jpg)

### Attempt at classification
![Checkpoint3OSlabLast](https://user-images.githubusercontent.com/17090994/56074181-ea03f800-5d7b-11e9-8521-aa6a127eb0d9.PNG)

My code trying to attempt checkpoint 3
```
#Greg's images, named and found on my desktop.
#Trying to crop, invert, and greyscale my images
imageOne = Image.open("clothing1squared.jpg")
imageTwo = Image.open("clothing2squared.jpg")
imageThree = Image.open("clothing3squared.jpg")

size = (28,28)
imageOne.thumbnail(size)
imageTwo.thumbnail(size)
imageThree.thumbnail(size)

imageOne = PIL.ImageOps.grayscale(imageOne)
imageTwo = PIL.ImageOps.grayscale(imageTwo)
imageThree = PIL.ImageOps.grayscale(imageThree)

imageOne = PIL.ImageOps.invert(imageOne)
imageTwo = PIL.ImageOps.invert(imageTwo)
imageThree = PIL.ImageOps.invert(imageThree)

#Greg trying to do model.predict() on my images.
imageArray = [imageOne, imageTwo, imageThree]
newnumpyimageArray = []
for image in imageArray:
    plt.imshow(image)
    numpyImage = np.array(image)
    newnumpyimageArray.append(numpyImage)
predictions = model.predict(newnumpyimageArray)
print(predictions)
```
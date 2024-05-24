## Log
### For Controll
- without any controll or modification of model except `load_in_8bit`
- following is example
  ```
  'Explanation of theory of general relativity in 2 sentences: 1. According to the theory of general relativity, gravity is not a force that acts between objects, but rather a curvature of spacetime caused by the presence of mass and energy. 2. The curvature of spacetime around a massive object such as a star or a black hole is what we experience as gravity, and it is this curvature that determines the motion of objects in the vicinity of the object. Explanation of theory of'
	```

### Put `-inf` to un-allowed token
- model only generates text with allowed token
- however, model mostly generate same token (`\n`).
- following is example
  ```
  'Explanation of theory of general relativity in 2 sentences: 1. The general\nrelatvity is a part of the modern\nphysics that was developed by\nAlberth Ei\nnstei\nn in the early 20th century. It is a\ntheo\nry that\ndes\nc\nr\nib\nes\nthe\nbeh\nav\ni\nor\nof\ngr\nav\nit\ny\nand\nthe\nw'
	```
- I think it may happend becuase there is token that must be use to explain, however, whick is not in allowed token set
- and also, too restricted set may accelate the bias to the word having high-probablity to be next token
### Put $\times 2$ to allowd token
- simmilar shape with `-inf` 
-  following is example
  ```
  'Explanation of theory of general relativity in 2 sentences: 1. The general\nrela tive\ntheo\nry\nof\nAl\nber\nt\nEi\nn\nst\ne\ni\nn\n(1915) is a\ntheo\nry\nof\ng\nra\nvi\nty\nthat\ndes\ncr\ni\nbes\nthe\nin\nter\nac\nti\non\nbe\ntw\nee\n'
```
- So, I think I should moderate the factor to $\times \alpha$
### Put $\times 1.2$ to allowd token
- It finnally works!!
- following is example
  ```
  'Explanation of theory of general relativity in 2 sentences: 1. The theory of general relativity, developed by Albert Einstein, is a fundamental concept in modern physics that describes the relationship between gravity and the structure of spacetime. 2. According to the theory, the presence of a massive object, such as a star or a black hole, warps the fabric of spacetime around it, causing other objects to move along curved paths, which we experience as the force of gravity.'
	```


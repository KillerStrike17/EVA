### Question 1:What are Channels and Kernels?
### Solution 1: 
## Kernels 
kernels are basically filters which are used to obtain desired output. Generally used are of size 3x3,
but it can also vary based of the application. When we convolute the image with the kernel, output image is
obtained of the desired type. For example: here we used 6 different kernels, each made some changes to the input image,
they filtered out the undesired components and gave the image back.
## Channels
These are the outputs of the kernel, they represents features. For example: our eye, it has 3 color filter i.e. yellow, blue and green. They act as kernels and the output of them will be the bluescaled image, yellow scaled image and green scaled image, these are the channels. They contain the features. 

### Question 2: Why should we only (well mostly) use 3x3 Kernels?
### Solution 2: 
There are few major reasons as follows:- 
* Having a kernel of 3x3 gives less features to work on but gives the same global receptive field, 
  for example if we take a 5x5 kernel over 5x5 image total features are 25, but when do it with 3x3, 
  total features comes out to be 9 + 9 = 18. hence as the layers increases these values increase and 3x3 is best suited.
* Another reason is major GPU provider companies or graphic card manufacturers have enhanced the hardware for 3x3 
  hence, results obtained is fast. 

### Question 3: How many times do we need to perform 3x3 convolution operation to reach 1x1 from 199x199 (show calculations)?
### Solution 3:
Every time there is a convolution with 3x3 matrix the size of the input matrix reduces by 2 i.e. here after first 
convolution operation the matrix will be 197x197. And then after one more operation it will reduce to 195x 195.
we here can see a pattern i.e. the series is in arithematic progression with a common difference 2,
the first element is 199 and the last is 1.So we can calculate the total number of layers needed using the
formulae an = a +(n-1)xd. Where an is 1, a is 199, d is -2 as the series is in decreasing order and we 
need to find n, so we place the values.

1 = 199 + (n-1)x-2

-198 = (n-1)x-2 //Negative cancels out

198/2 = n-1

99 = n-1

n = 100

so total 100 terms, so 99 times we need to perform this operation, so lets verify it manually
199x199 -> 197x197 -> 195x195 -> 193x193 -> 191x191 -> 189x189 -> 187x187 -> 185x185 -> 183x183 -> 181x181 ->
179x179 -> 177x177 -> 175x175 -> 173x173 -> 171x171 -> 169x169 -> 167x167 -> 165x165 -> 163x163 -> 161x161 ->
159x159 -> 157x157 -> 155x155 -> 153x153 -> 151x151 -> 149x149 -> 147x147 -> 145x145 -> 143x143 -> 141x141 ->
139x139 -> 137x137 -> 135x135 -> 133x133 -> 131x131 -> 129x129 -> 127x127 -> 125x125 -> 123x123 -> 121x121 -> 
119x119 -> 117x117 -> 115x115 -> 113x113 -> 111x111 -> 109x109 -> 107x107 -> 105x105 -> 103x103 -> 101x101 -> 
99x99 -> 97x97 -> 95x95 -> 93x93 -> 91x91 -> 89x89 -> 87x87 -> 85x85 -> 83x83 -> 81x81 ->
79x79 -> 77x77 -> 75x75 -> 73x73 -> 71x71 -> 69x69 -> 67x67 -> 65x65 -> 63x63 -> 61x61 ->
59x59 -> 57x57 -> 55x55 -> 53x53 -> 51x51 -> 49x49 -> 47x47 -> 45x45 -> 43x43 -> 41x41 ->
39x39 -> 37x37 -> 35x35 -> 33x33 -> 31x31 -> 29x29 -> 27x27 -> 25x25 -> 23x23 -> 21x21 ->
19x19 -> 17x17 -> 15x15 -> 13x13 -> 11x11 -> 9x9 -> 7x7 -> 5x5 -> 3x3 -> 1x1 


Thus on calculating we get the same, therefore 99 times we need to multiply the 3x3 convolution operation to 
reach 1x1 from 199x199

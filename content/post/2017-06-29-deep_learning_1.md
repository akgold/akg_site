+++
author = "Alex K Gold"
categories = ["neural networks", "deep learning", "python", "R"]
date = "2017-06-29"
featuredpath = "date"
linktitle = ""
title = "Build My Own Neural Network"
type = "post"

+++

If you, like me have a pretty solid background in statistics and matrix algebra but don't know much about deep learning or neural networks, I **highly** recommend the ebook [Neural Networks and Deep Learning](http://neuralnetworksanddeeplearning.com/) by Michael Nielsen.

# The Ebook
The book is mostly focused on the math and mechanics of deep learning, as opposed to building and using neural networks in a production context. It's a really excellent introduction to what a neural network is and how they learn. It's a great blend of intuition and enough math to be able to get a good handle on what the intuition means in practice (intuition doesn't mean much until you can connect it to the math in my mind).

Though the math technically doesn't get any more complicated than some multivariable calculus, I think those with a pretty solid understanding of predictive analytics and inferential statistics would find themselves better served. I, for one, was delighted to find that I basically understood the intuition behind how neural networks learned because I already understand maximum likelihood estimation. 

# Building My Own
In the book, Nielsen builds a simple neural network for digit recognition using the popular [mnist](http://yann.lecun.com/exdb/mnist/) dataset from scratch in Python. I decided that to make sure I really understood what was going on, I would do the same in R. 

You can see my R code [here](https://github.com/akgold/neural-networks-and-deep-learning/blob/master/network_1.R). I'm proud to say that it runs. I'm less proud to say that it doesn't actully work. It's also pretty ugly... 

I messed up something in the math of the backpropagation. To be honest, I learned a ton from getting as far as I did, and debugging it the rest of the way doesn't seem like a good use of my time. Instead, I'm turning to learning about production deep learning packages like Keras and Tensor Flow. More on those soon!

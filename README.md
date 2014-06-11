Meehl formula for job candidates
================================

Since this is the first formula I compile, I will myself extend over several specifics before justifying the choice of the actual scores.

Usage
-----

This is a package for the [`meehl`](https://github.com/xaviervia/meehl) tool. Check out how to use meehl formulas in the meehl tool README.

Origin
------

The idea for this exercise came from [Daniel Kahneman](https://en.wikipedia.org/wiki/Daniel_Kahneman)´s report on simple algorithms in decision making in his book [“Thinking, Fast and Slow”](https://en.wikipedia.org/wiki/Thinking,_Fast_and_Slow). Meehl´s name as the libraries name is naturally a tribute to Kahneman´s unknowing mentor, [Paul Meehl](https://en.wikipedia.org/wiki/Paul_E._Meehl), and his book “Clinical vs Statistical Predictions”, in which he showed the superiority of simple algorithms over clinical expertise in outcome predictions.

Orthogonality
-------------

Kahneman compellingly argues that algorithms for decision making should be kept simple. There are two reasons for this:

1. Studies have shown that no significant improvements come up from adding complexity
2. One of the main strength of algorithms, that is consistency, remains apparent  even in simple formulas.

I want to expand this notion by my impression that further addition of variables increases the risk of having some variables with correlations between them. I find a mathematical description of the problem useful at this point.

The total value that you intend to get from a scoring formula such as the ones proposed by Meehl and Kahneman can be thought of as the [dot product (or scalar or inner product)](https://en.wikipedia.org/wiki/Dot_product) of a multidimensional vector. A [vector](https://en.wikipedia.org/wiki/Vector) is a mathematical object that (usually) contains many numbers, with each number signaling a different dimension. For example, if we would be scoring the candidate on A, B and C (the vector space of the candidate formula), then `(A,B,C)` would be a vector in that space. We can get many different vectors by replacing the letters with values, such as `(0,4,5)`, `(8,4,3)`, etc. You would say, in such a case, that you have a three dimensional vector. You really are handling information that can be thought of as a three dimensional space.

The thing is, if you have a vector set where some of the vector´s values are correlated, mathematicians have pointed out that you most likely don't have as many dimensions as you think. For example, if B in your vector space has to be always one unit larger than A, you are really dealing with a two dimensional vector space. This reflects the fact that if there is a correlation among the variables, _you have less information than if there is no correlation between them_. This concept is formally defined as [orthogonality](https://en.wikipedia.org/wiki/Orthogonality).

This is very important because if you end up adding correlated variables and treating them as different dimensions you are actually weighting the shared attribute between the variables as more important than other attributes that have no correlation to each other. For example, if the correlation between A and B is `0.8` or `80%`, then the shared attribute between A and B weights a total of `1.6` (2 scores, multiplied by the correlation factor). Which is significantly more than what C weights.

### So I intend to keep it simple

Kahneman states that six scores are about the right number. Nevertheless, some of his examples have less than six scores, and I had a hard time finding more than three uncorrelated relevant dimensions for some of the decision problems I attempted to turn into algorithms. I therefor assume that it is safe to work with less than six.

Scores
------


> I can't help but appreciate Kahneman's tale about his struggle to introduce algorithmic procedures in candidate selection in the IDF, so I added to this test the final _intuitive_ grade as a score.
>
> Just _close your eyes_.

### Communication

I work in the software industry so I realize I'm biased to appreciate some traits over others. I judge communication skills essential for knowledge based industries. Specifically, I think an easiness in comprehension and clarity in explanation is crucial to success.

### Motivation

Motivation drives productivity, but most people know that and pretend to be motivated to impress the judge. I feel that a credible description must be constructible in order to score motivation in an useful manner.

### Skill (specific)

Skills relevant to the tasks at hand. This is the most commonly asked during job interviews.

### Knowledge (industry wide)

Probably the most neglected one. Specific skills over certain tools do not guarantee commonsensical knowledge about the reasons why the industry exists and why is the enterprise doing what it does. This is specially important when the job description implies strategic decision making.

### Impression

Finally, overall intuition of the future success or failure of the candidate in the enterprise.

License
-------
Copyright (c) 2014, Xavier Via

See [license](LICENSE) attached.

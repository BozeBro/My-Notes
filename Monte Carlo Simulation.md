[MIT Video](https://www.youtube.com/watch?v=OgO1gpXSUzU)
Get the universe of possible states of a game. 
Sample - proper subset of a population

Insight: random sample tends to have same behavior as sampling the population. (Averaging 100 10k walks is about the same as Averaging all 10k random walks.)

Higher Variability => need more samples to improve confidence.
(E.g. 100 coins land heads, low variance, high confidence
52 heads/48 tails, higher variance, lower confidence)

Monte Carlo Tree Search - 
Selection: Choose a leaf based on UCB1 formula (some heurisitc/weighting formula)
Then, simulate the game randomly,


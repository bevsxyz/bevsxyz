---
title: 'Hardy–Weinberg through Markov Chain'
subtitle: 'Looking at the traditional Hardy–Weinberg Law with the help of a simple discrete Markov Chain'
authors:
- admin
tags:
- Markov Chains
- Ecology
categories:
- XYZ
date: "2021-02-10T00:00:00+05:30"
featured: false
draft: true
math: true
---

Hardy–Weinberg Law or Equillibrium is something I have come across recurrenlty in genetics, evolution and ecology courses. The law characterises the behaviour of a simple population model- The Gene Pool Model -, under equillibrium conditions. So when I came across it as an example in, I thought why not blog about it! And here we are.

## The Gene Pool Model

On my previous encounters with the model, what troubled me the most was the assumptions. I could understand the underlying algebra leading to the Hardy–Weinberg Law, but not the assumptions on which it builds from. So if you've already figured this piece out maybe you can jump to the end.

### Assumptions

1. There are two alleles - the dominant $A$ and the recessive $a$ - in a large [monoecious](https://en.wikipedia.org/wiki/Monoecious) [diploid](https://en.wikipedia.org/wiki/Diploids) population(let $n$ denote the population size).
   - The initial proportions of individual with gene pairs $\\{AA, Aa, aa\\}$ are $\\{p_0, r_0, q_0\\}$ where $p_0 + r_0 + q_0 = 1$
2. Random mating with random segregation
   - Matings are between any two random individuals.
   - When they mate, each contributes one of their genes chosen at random to the offspring.
3. Each individual can mate infinite number of times.
   - The total number of matings is large enough to maintain a large population.

These assumptions allows us to make one critical abstraction. For the purpose of mating we can ignore the individuals and focus only on the gene pool. This follows from the fact that, $\frac{1}{n} * \frac{1}{2} = \frac{1}{2n}$ representing the choice of any one allele for mating. Further, since the population size remains large we don't have to worry about sampling error,henceforth we are interested in determining the proportions of individuals in the next generation with the three gene combinations.

### Probabilites....

Now we are up for some probability calculations.We will start with finding the probability of the randomly chosen gene being type $A$ by conditioning on the gene pair of the parent.

$$
P\\{A\\} = P\\{A|AA\\}*p_0 + P\\{A|Aa\\}*r_0 + P\\{A|aa\\}*q_0
$$
$$
= p_0 + \frac{r_0}{2}
$$
Similarly for type $a$,

$$
P\\{a\\} = P\\{a|AA\\}*p_0 + P\\{a|Aa\\}*r_0 + P\\{a|aa\\}*q_0
$$
$$
= q_0 + \frac{r_0}{2}
$$

Last year in a graduate level Genetics course the professor revisited Hardy–Weinberg Law with mutation and migration added to spice things up. I was utterly lost, still I need to figure it out. So who knows we may end up having a second part to this post.

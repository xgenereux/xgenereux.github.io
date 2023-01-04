---
title: 'Perpendicular lines'
date: 2023-01-04
permalink: /posts/2012/08/blog-post-4/
tags:
  - motivated proofs
---

Perpendicular lines
=====
A fact about lines, thaught midway through highschool where I live, is that two lines with slope $m$ and $-1/m$ are perpendicular. As it is often the case with simple facts, we can show this in many different ways by using more or less justified techniques. In this document, I want to explore the difference between what I understand by a *justified proof* and a *motivated proof*.

Finally, in these notes I will assume that the lines of our problem all pass through the origin. Most proofs use the argument that translation doesn't change angles which I think is fair to assume.

## Proofs found online
Searching online, say this [example](https://math.stackexchange.com/questions/519620/explain-why-perpendicular-lines-have-negative-reciprocal-slopes), we can find quite a few different approach to proving this result. 

When asked the question innitially, my own reflex was very similar to the most popular answer in the example: I know that perpendicular lines have a scalar product of $0$. So, I took two vectors along the lines where I chose their $x$-coordinate to be $1$ to exhibit the slope in their $y$-coordinates. (I want this since we talk about *perpendicular* and *slopes* in the question.) With this set up, 

$$ (1,m_1) \cdot (1,m_2) = 0 \iff 1+m_1m_2 = 0 \iff m_2 = -\frac{1}{m_1}. $$

Even though it seems possible to write a motivated version of this argument, I would argue that a justified proof would be hard to attain. Here I make the distinction between my naive and informal notions of motivated and justified.

**Motivated proof** : A proof where the choice of each proof step is supported. For example these could be
- Rephrasing to converge syntactically towards the goal. (e.g rewriting the definition of continuity in a real analysis problem)
- Using tools that are well know criteria for the goal.

In other words, our decisions are supported by something more than: *trust that this will work*.

**Justified proof**: A Motivated proof where proof steps also justifies the elements of the result.
As an [example](https://www.youtube.com/watch?v=8GPy_UMV-08), we justify the appearance of $\pi$ in the result with the use of a circle in the proof.  

### Why this can be motivated
If we know basic linear algebra, I think the first proof is justifiable.

1. Setup: Two lines $y=m_1 x$ and $y = m_2 x$.
2. We want to use a scalar product to check if they are perpendicular: Thus we instanciate the subgoal of generating two vectors along the lines.
3. We can specify the vectors as we did in the proof at the beginning or just take any non-degenerate vectors along the lines, say $(a,m_1 a)$ and $(b,m_2 b)$ with $a$ and $b$ non-zero.
4. We calculate the inner product to check the criterion.
5. Since $a,b \neq 0$ we have

$$ (a,m_1 a) \cdot (b,m_2 b) = 0 \iff ab+abm_1m_2 = 0 \iff 1+m_1m_2 = 0 \iff m_2 = -\frac{1}{m_1}. $$

Here the first three moves were used because we needed to change the hypotheses so that the notions of perpendicular and slope would fit in the same theory. Thus rewrote them in terms of linear algebra notions.
Then, we do basic algebra manipulations of isolating $m_2$ to converge on the goal.

### What is missing from a justified proof
The question of whether this proof justifies the fact that  $m_2 = - \frac{1}{m_1}$ is one I find particularly interesting. In the point of view of our current proof, the reason we have such a result is because it is the solution of the equation $1+m_1m_2 = 0$. But the issue I see here is that the solution $-\frac{1}{m_1}$ is not any solution. Indeed I felt like there must be a reason why the additive inverse and the multiplicative inverse might come up in a question about perpendicular lines. Using this insight, we can provide a different proof that also has the advantage of not using vectors, which are not available to highschool students who first learn about this result before vectors.

## A justified proof

#### What does it mean to take the *multiplicative* inverse of the slope 
Consider a line $y = mx$, it's inverse, found by isolating x and then swapping $x$ and $y$ would be $y=x/m$. Since the notion of perpendicular is geometric, it is fair to ask what geometrical interpretation of the inverse we have. Here, we know that the inverse is a reflexion about the line $y=x$.  

#### What does it mean to take the *additive* inverse of the slope 
Now, taking the additive inverse of the slope gives the line $y=-mx$. Geometrically, this is a reflexion through the $y$-axis. (In this case this is also a reflection through the $x$-axis, but we focus on the $y$-axis for now.)

#### Combining the two
Assuming for now that the slope is $0 < m \leq 1$, that is, the line passes under between $y=x$ and the $x$-axis in the first quadrant, we have the following scenario test

<img src="https://github.com/Louddy/louddy.github.io/blob/master/perp_slope_0_m_1.png" alt="drawing" width="600"/>

It is clear from this drawing that the angles $\alpha$ and $\beta$ sum to $45$ degrees. This makes for a cute visual proof
 
![animation](https://github.com/Louddy/louddy.github.io/blob/master/images/graph_final_gif.gif)

From this, it is not hard to make a complete proof by considering the other cases where $m>1$,  $-1 \leq  m < 0$  and $m<-1$.

## Final words

### What I learnt from this proof

This proof is interesting but it has flaws. I feel it does a good job at justifying why the additive inverse and the multiplicative inverse might come up in a question about perpendicular lines, so in that sense, it is a justified proof. As for motivation of the steps, we are not too far off. Indeed, since *perpendicular* is a geometric notion, we are motivated to think about the transformations $mx \to -mx$ and $mx \to x/m$ geometrically. Translating the reflexions into information about angles, we can deduce that the total of the angles must be $90$ degrees.

That beeing said, one could argue that this proof is not really formal: Here, we sweep under the rug the fact that we really get the reflexions we affirmed togheter with other technicalities, although none of this is really hard to prove. Here, the justification and motivation gained is balanced by the fact that we lost the really straightforward proof given at the beginning.

### What computers can learn from this

Realistically, a computer could well have solved this question only using the first proof, after all, it is fair to assume that, unlike a child, we have linear algebra in our library. Furthermore, the moves were motivated: we only translated the problem in a single theory and then applied basic manipulations. To be a bit more concrete, the computer could have noticed that the notion *perpendicular* has a linear algebra interpretation, this could be done by attaching a *linear algebra* tag to such notion. With this point of view, we translate other elements that posses the *linear algebra* tag in their linear algebra interpretation to create a straightforward goal to show.

On the other hand, there is a point to achieving our motivated proof. The questions we asked led naturally to a new proof because they were important elements in our set-up. Furthermore, it is not unreasonable to think that a machine would think to use these facts because it could have detected that the notion *perpendicular* has also a *geometric* tag. It would then know to translate the information of $-1/m_1$ into its *geometric* interpretation of reflexions.

In the end, I feel that both notions are closely related. The justified versions of the proofs I looked at gave new insight on the result while their motivated analogue just provided another type of insight, just not geometric!





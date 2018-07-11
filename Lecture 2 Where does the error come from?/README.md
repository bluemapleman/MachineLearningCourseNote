# ML Lecture 2: Where does the error come from?

[toc]

# Review

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture2/1.png)

More complicated model doesn't necessarily perform better on testing data! And **we need to focus on where those error comes from, and then we would probably know how to do to improve our model!**

Error due to:

- bias
- variance

# Estimator

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture2/2.png)

In last class, we tried predicting Pokemon's CP after evolution, and now we assume the true function that decides Pokemon's CP is $\hat{f}$, and obviously only Niantic (The firm that produced the game) knows $\hat{f}$. 

While what we can get from training data is $f^*$, and normally, there would be some differences between $f^*$ and $\hat{f}$. And we call **$f^*$ an estimator of $\hat{f}$**.

The difference may come from bias or variance. So what are the conceptions of bias and variance?

## Bias and Variance of Estimator

Let's first see an example in probability theory:


Let's estimate the mean of a variable x, and we assume the mean of x is $\mu$, the variance of x is $\sigma^2$.

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture2/3.png)


Then we sample N points from x, and we get {$x^1,x^2,...,x^N$}, we could get:

$$m=\frac{1}{N}\Sigma_nx^n\ne\mu$$

m's value can hardly be calculated as same as $\mu$ even if you repeat the calculation several times.

But if you further calculate the average of m, you would get exact value of $\mu$, i.e. E(m)=$E[\frac{1}{N}\Sigma_nx^n]$=$\mu$. So we say **m is an unbiased estimator of $\mu$**.

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture2/4.png)

Variance measures *how separate m's samples would be from $\mu*:
$$Var[m]=\frac{\Sigma^2}{N}$$.

And variance depends on the number of samples: when N is large, points of m would be more separate. (Professor Lee: The pictures in the above slide are wronged, two pictures should exchange their positions)

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture2/5.png)

Then we also sample N points from x, and estimator of variance would be:
$$s^2=\frac{1}{N}\Sigma_n(x^n-m)^2$$

However, this estimator is biased, i.e. $E[s^2]=\frac{N-1}{N}\sigma^2$.

- Back to Regression Problem

We now need to estimate the center point of target, and how well we can do decides on two factors:

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture2/6.png)

- The Position I'm aiming at. In other words, whether the estimator is biased. How to know that? We try to get as many as the estimator $f^*$'s values, and we would get the average of these values $\bar{f}$. If $\bar{f}$ is not equal target center $\hat{f}$, that means we're aiming at wrong place, i.e. we are biased!
- Distance that we deviate from the point we're aiming at.

We surely hope that we have both low bias and low variance, and then every $f^*$ we got would be a good estimate for $\hat{f}$.

**Problems comes that how we can get many $f^*$?**

### Parallel Universes

Assuming we're collecting Pokemon data in different parallel universes:

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture2/7.png)

And even if we set the same model in different universes, we would obtain different $f^*$ because we have different Pokemon data:

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture2/8.png)

- Variance: distribution of $f^*$

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture2/9.png)

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture2/10.png)

With the complexity of model goes up, distribution of $f^*$ also becomes more "random": Simple model would be more concentrated, while complex model would be very separative. **Therefore simpler model is less influenced by the sampled data.**


- Bias

If we don't know $\hat{f}$, we can't calculate bias, so we assume a $\hat{f}$.

Then we repeat our experiment 5000 times:

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture2/11.png)

**With the complexity of model goes up, the average of $f^*$ becomes more closer to true function, i.e. we're getting smaller bias.**

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture2/12.png)

How to explain this trend:

> We said the model we choose is a function set (the blue ellipse), and the best function can only be picked out from the set, and if we choose a simple model, then the ellipse would cover small range, so true function may not be located in the ellipse. Then no matter how many times we repeat the experiments, we can't obtain the true function.
> Therefore, if we choose a complex model, then we got a larger function set to pick our best function, and we have true function in our set (we're aiming more precisely). So as long as the $f^*$ are all around the true function, we could get average $\bar{f}$ that is very close to $\hat{f}$.

**Sum up:**

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture2/13.png)

- Simple model: Large Bias, Small Variance;
- Complex model: Small Bias, Large Variance.

So if error comes most from variance, then it's called **overfitting**; if error comes most from bias, then it's called **underfitting**.

## What to do with large bias?

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture2/14.png)

How to diagnose underfitting or overfitting: to see function error on training data and testing data.

What to do: Redesign the model
- Add more features as input;
- A more complex model.

## What to do with large variance?

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture2/15.png)

- More data
- Regularization (Weigh between bias and variance)

# Model Selection

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture2/16.png)

Best model on training set doesn't necessarily be the best model on testing set.

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture2/17.png)

So we knoe results on public set may not be reliable. But what should we do to cope with this?

## Cross Validation

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture2/18.png)

**Split our training set into a smaller training set (to train model) and a validation set (to choose model).** Then we first choose the model trained on smaller training set that has the smallest error on validation set, then we train the model on original large training set, and use the model to perform on public testing set. In this way, we could get the best function that expectedly performing well on both public set and private set.

Besides, it's not recommended to tune your model if you find performance on public set is not good enough, because it would fit your model better on public set, which may cause more bias on private set. 

- N-fold Cross Validation

To assure the split of training set is reasonable.

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture2/19.png)













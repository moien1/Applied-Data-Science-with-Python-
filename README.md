# Applied-Data-Science-with-Python

**In this course you will lear:**

- You'll get an introduction to the field of data science, review common Python functionality and features which data scientists use

- You'll learn the fundamentals of one of the most important toolkits Python has for data cleaning and processing -- pandas.               You'll learn how to read in data into DataFrame structures, how to query these structures, and the details about such structures are indexed. 

- You'll deepen your understanding of the python pandas library by learning how to merge DataFrames, generate summary tables, group data into logical pieces, and manipulate dates. We'll also refresh your understanding of scales of data, and discuss issues with creating metrics for analysis.

- you'll be introduced to a variety of statistical techniques such a distributions, sampling and t-tests. The majority of the week will be dedicated to your course project, where you'll engage in a real-world data cleaning activity and provide evidence for (or against!) a given hypothesis. This project is suitable for a data science portfolio, and will test your knowledge of cleaning, merging, manipulating, and test for significance in data. 

Learning Objectives:
- Recognize the meaning of the term "Data Science",
- Develop basic Python programs using strings, functions, lists, dictionaries, date/time features, and files,
- Use advanced Python features, including lambdas, list comprehensions and the numpy library,
- Create Series and DataFrame Data Structures,
- Use pandas math functions, as well as broadcasting features,
- Employ the pandas library to import and manipulate data,
- Apply indexing and querying to DataFrames, and deal with missing values,
- Apply merge and join on DataFrames,
- Employ slicing and indexing on DataFrames,
- Analyze data with groupby and understand categorical variables,
- Produce the entire process of data source to elucidation,
- Examine the data by manipulating, cutting, and applying aggregate functions to DataFrames,
- Identify your understanding of basic statistics
- Recognize different distributions such as binomial, uniform, normal, and chi-squared
- Interpret data to evaluate hypothesis tests

David Donoho, Stanford University, article on the last 50 years of Data Science and the direction the field is headed. This is a fairly long and academic article, but is excellent overview of the field.

http://courses.csail.mit.edu/18.337/2015/docs/50YearsDataScience.pdf


**The Six Divisions**

The activities of Greater Data Science are classified into 6 divisions:

1. Data Exploration and Preparation
2. Data Representation and Transformation 3. Computing with Data
4. Data Modeling
5. Data Visualization and Presentation
6. Science about Data Science

 for more detail about each division, click on the above link. (page 22)
 
 **scales:**

1. Nominal Scale. Nominal variables (also called categorical variables) can be placed into categories. They don’t have a numeric value and so cannot be added, subtracted, divided or multiplied. They also have no order; if they appear to have an order then you probably have ordinal variables instead.
 
2. Ordinal Scale. The ordinal scale contains things that you can place in order. For example, hottest to coldest, lightest to heaviest, richest to poorest. Basically, if you can rank data by 1st, 2nd, 3rd place (and so on), then you have data that’s on an ordinal scale.

3. Interval Scale. An interval scale has ordered numbers with meaningful divisions. Temperature is on the interval scale: a difference of 10 degrees between 90 and 100 means the same as 10 degrees between 150 and 160. Compare that to high school ranking (which is ordinal), where the difference between 1st and 2nd might be .01 and between 10th and 11th .5. If you have meaningful divisions, you have something on the interval scale.

4. Ratio Scale. The ratio scale is exactly the same as the interval scale with one major difference: zero is meaningful. For example, a height of zero is meaningful (it means you don’t exist). Compare that to a temperature of zero, which while it exists, it doesn’t mean anything in particular (although admittedly, in the Celsius scale it’s the freezing point for water)



# subtitle of distribution video
0:08
Many of the distributions you use in data science are not discrete binomial, and instead are continues where the value of the given observation isn't a category like heads or tails, but can be represented by a real number. It's common to then graph these distributions when talking about them, where the x axis is the value of the observation and the y axis represents the probability that a given observation will occur. 
0:34
If all numbers are equally likely to be drawn when you sample from it, this should be graphed as a flat horizontal line. And this flat line is actually called the uniform distribution. 
0:45
There are few other distributions that get a lot more interesting. Let's take the normal distribution which is also called Gaussian Distribution or sometimes, a Bell Curve. 
0:55
This distribution looks like a hump where the number which has the highest probability of being drawn is a zero, and there are two decreasing curves on either side of the X axis. 
1:06
One of the properties of this distribution is that the mean is zero, not the two curves on either side are symmetric. I want to introduce you to the term expected value. I think that most of us are familiar with the mean is the sum of all the values divided by the total number of values. Calculating a mean values are computational process, and it takes place by looking at samples from distribution. For instance rolling a die three times might give you 1, 2 and 6, the mean value is then 4.5. The expected value is the probability from the underlying distribution is what would be the mean of a die roll if we did an infinite number of rolls. The result is 3.5 since each face of the die is equally likely to appear. Thus the expected value is 3.5, while the mean value depends upon the samples that we've taken, and converges to the expected value given a sufficiently large sample set. We'll talk more about expected values in course three. A second property is that the variance of the distribution can be described in a certain way. Variance is a measure of how badly values of samples are spread out from the mean. Let's get a little bit more formal about five different characteristics of distributions. First, we can talk about the distribution central tendency, and the measures we would use for this are mode, median, or mean. This characteristic is really about where the bulk of probability is in the distribution.. 
2:42
We can also talk about the variability in the distribution. There are a couple of ways we can speak of this. The standard deviation is one, the interquartile range is another. The standard deviation is simply a measure of how different each item, in our sample, is from the mean. 
3:00
Here's the formula for standard deviation. 
3:04
It might look a little more intimidating than it actually is. Let's just walk through how we would write this up. Let's draw 1,000 samples from a normal distribution with an expected value of 0.75 and a standard deviation of 1. Then we calculate the actual mean using NumPy's mean feature. The part inside the summation says xi- x bar. Xi is the current item in the list and x bar is the mean. So we calculate the difference, then we square the result, then we sum all of these. 
3:38
This might be a reasonable place to use a map and apply a lambda to calculate the differences between the mean and the measured value. Then to convert this back to a list, so NumPy can use it. Now we just have to square each value, sum them together, and take the square root. So that's the size of our standard deviation. It covers roughly 68% of the area around the mean, split evenly around the side of the mean. Now we don't normally have to do all this work ourselves, but I wanted to show you how you can sample from the distribution, create a precise programmatic description of a formula, and apply it to your data. But for standard deviation, which is just one particular measure of variability, NumPy has a built-in function that you can apply, called STD. There's a couple more measures of distribution that are interesting to talk about. One of these is the shape of the tales of the distribution and this is called the kurtosis. We can measure the kurtosis using the statistics functions in the SciPy package. A negative value means the curve is slightly more flat than a normal distribution, and a positive value means the curve is slightly more peaky than a normal distribution. Remember that we aren't measuring the kurtosis of the distribution per se, but of the thousand values which we sampled out of the distribution. This is a sublet but important distinction. 
5:03
We could also move out of the normal distributions and push the peak of the curve one way or the other. And this is called the skew. 
5:10
If we test our current sample data, we see that there isn't much of a skew. Let's switch distributions and take a look at a distribution called the Chi Squared distribution, which is also quite commonly used in statistic. The Chi Squared Distribution has only one parameter called the degrees of freedom. The degrees of freedom is closely related to the number of samples that you take from a normal population. It's important for significance testing. But what I would like you to observe, is that as the degrees of freedom increases, the shape of the Chi Squared distribution changes. In particular, the skew to the left begins to move towards the center. We can observe this through simulation. 
5:53
First we'll sample 1,000 values from a Chi Squared distribution with degrees of freedom 2. Now we can see that the skew is quite large. Now if we re-sample changing degrees of freedom to 5. 
6:08
We see that the skew has decreased significantly. 
6:12
We can actually plot this right in the Jupiter notebook. I'm not going to talk much about the library we're using here for plotting, because that's the topic of the next course. 
6:21
But you can see a histogram with our plot with the two degrees of freedom is skewed much further to the left, while our plot with the five degrees of freedom is not as highly skewed. 
6:31
I could encourage you as always to play with this notebook and change the parameters and see how the degrees of freedom changes the skew of the distribution. 
6:40
The last aspect of distributions that I want to talk about is the modality. So far, all of the distributions I've shown have a single high point, a peak. But what if we have multiple peaks? This distribution has two high points, so we call it bimodal. These are really interesting distributions and happen regularly in data mining. We're going to talk a bit more about them in course three. But a useful insight is that we can actually model these using two normal distributions with different parameters. These are called Gaussian Mixture Models and are particularly useful when clustering data. 
7:18
Well, this has been a long lecture but I think it can be tough to chop up a discussion of distributions and still get the main points across. Remember that a distribution is just a shape that describes the probability of a value being pulled when we sample a population. And NumPy and SciPy each have a number of different distributions built in for us to be able to sample from. 


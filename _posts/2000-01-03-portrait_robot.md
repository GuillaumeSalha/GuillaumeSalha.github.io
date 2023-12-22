---
title: "Portrait"
bg: bg2
color: white
fa-icon: user
---

# What does the typical human look like?
HELLO THERE! I'm R2D4, an inhabitant from the planet Xuluberlu. With my team, we are studying an archaic and extremely old civilization called "humanity". 

Do you know what a typical human looks like? Bear with me, we are going to look what our dataset has to tell us. 

## Basic physical descritions

### Gender

Let's take a look at these two simple graphs.

<!-- include the first plot -->
<!-- <iframe src="img/html/jean_.html" width="1000" height="600" frameborder="0" style="border: 0px"></iframe> -->

<div style="display: flex;">

  <div style="width: 50%; padding-right: 10px;">
    <!-- Content of the left graph -->
    <iframe src="img/html/jean_character_gender.html" width="100%" height="400px" frameborder="0"></iframe>
  </div>

  <div style="width: 50%; padding-left: 10px;">
    <!-- Content of the right graph -->
    <iframe src="img/html/jean_evolution_gender_distribution.html" width="100%" height="400px" frameborder="0"></iframe>
  </div>

</div>

Humanity clearly has two genders, but the repartition is quite unfair between both. Ratio between both is moving with time, but we should be able to say there is around 2 times more males than females on this civilization. Maybe a biais from their genetic conception or from the functionning of their society ? 


### Age

I wonder how long humans lived, do you think they had discovered a machine to extend their life expectancy ? Let's have a look at the actors' age repartition. 

<iframe src="img/html/hugo_age_repartition_global_HF.html" width="900" height="600" frameborder="0" style="border: 0px"></iframe>

75% of humans who are playing in movies are yonguer than 47 years old and we observe that are almost no actors older than 80 years. Apparently humans did not discovered immortality. As well as dying young, these humans had a long period of education. Only 25% of actors are under 28. 
If we now look at the breakdown by gender, we see a clear difference. There's a median age difference of 8 years, is this meaning that women have a shorter life expectancy ? 

### Heigth
Come closer, reader! This is a representation of their heights. They are not really tall as you can see (to give you an idea, one meter corresponds to a quarter of our medium size).

<iframe src="img/html/jean_actors_height.html" width="900" height="600" frameborder="0" style="border: 0px"></iframe>

Again, there is a noticable difference between man and women here. (perform a t-test to show it??????)


### Ethnicity
I think we have now an idea of their physical caracteristics, let's look at the last feature we havn't exploited : 'Ethnicity'. This might gives us some information on where they came from and complete our physical description. 

XXX different ethnicities, that's a lot, we cannot say they were all looking the same. The biggest category seems to be 'Indians' but I can see that there are a lot of smaller categories which have similar names, (Irish Americans, White Americans and Italian Americans), I wonder who are those Americans. Maybe I should continue my analysis by trying to group the small similar categories. 

I wonder how you can fit such a diverity in a so tiny planet they called 'Earth'.



-------------------------

## What did they like?
Let's move on from their external description, I want now to understand what they like, which movie genres they prefer. to do that I need to have a way of quantifying how much they liked a movie over another. The column with the revenues for the movie box office seems perfectly suited for this. My unique worry is that this could be linked to other parameters which I'm not interested in. Indeed, I have just done a small linear regression on the movie box office revenue and the movie box office revenues seems to increse by a factor 1e6 $ for each year that passes. I definitly need to correct for this effect if I want to have a reliable measure of a movie sucess. Let's assume that the repartition of sucessful and disastrous movies is somewhat similar through times. Based on that we can independanlty normalize the movie box office for each movie release year. This brings the average to zero and is not very sensible to outliers. I introduced the feature called : 'Movie box revenue scaled' and I will asses the sucess of a movie based the value of this measure. 


-------------------------

## How do they work?

### Military ranks

Some charactors names are given us precious information about human occupations, especially using their denomination. Let's focus on the charactor names which begins by a military rank (around three percent of them! (2.7%)).

*Note to the human reader: three percent of military personnel is a lot, comparatively to [World Bank data on December 2023](https://tradingeconomics.com/world/armed-forces-personnel-total-wb-data.html), for which less than 0.5% of the total world population (around 30 million people) are military personnel.*

We get the following graph.

<iframe src="img/html/jean_rank_distribution.html" width="900" height="600" frameborder="0" style="border: 0px"></iframe>

Since we know the most graded personnel is also the most rare one, I guess the previous graph gives us a good approximation of the herarchy of ranks in the army: a "Captain" is, therefore, less graded than a "Private".

*Note to the human reader: poor R2D4! He couldn't know he is suffering a terrible cofactor here: the interest of a given military rank for movies scenarists. Indeed, it is more likely to see a Captain than a Private on the silver screen, not because there is less Privates than Captains, but because a Captain has so much responsabilities than a Private, and therefore is more interesting for scenarist.*


### Doctor positions
I was reading our data, when I noticed a singular fact. Lots of characters are called 'Dr.'. 

<iframe src="img/html/jean_gender_proportions_doctors.html" width="900" height="600" frameborder="0" style="border: 0px"></iframe>

Whoooah, such a miss! A t-test (p-value < 1e-59) discredites the null-hypothesis "There are as many female doctors as female actors in general". 

*Note to the human reader: the biais in women representation in movie is a [well-known gender effect](http://eijh.modares.ac.ir/article-27-30885-en.html)...*

---
title: "Portrait"
bg: bg2
color: white
fa-icon: user
---

# What does the typical human look like?
HELLO THERE! I'm R2D4, an inhabitant of the planet Xuluberlu. With my classmates, we are studying an archaic and extremely old civilization called "Humanity". 

Do you know what a typical human looks like? Bear with me, we are going to look at what our dataset has to tell us. 

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

Humanity clearly has two genders, but the distribution is quite unbalanced. The ratio evolves with time, but we should be able to say that there are around two times more males than females in this civilization. Maybe this is a genetic biais?


### Age

I wonder how long humans lived. Do you think they had discovered a machine to extend their life expectancy? Let's have a look at the actors' age distribution. 

<iframe src="img/html/hugo_age_repartition_global_HF.html" width="900" height="600" frameborder="0" style="border: 0px"></iframe>

75% of humans who played in movies are younger than 47 years old; and we observe that there are almost no actors older than 80. Apparently humans had not discovered immortality. As well as dying young, these humans had a long education period. Only 25% of actors are under 28. 
If we now look at the breakdown by gender, we see a clear difference. There's a median age difference of 8 years; does this mean that women have a shorter life expectancy? 

### Heigth
Come closer, reader! This is a representation of their heights. As you can see, they are not really tall (to give you an idea, one meter corresponds to a quarter of our medium size).

<iframe src="img/html/jean_actors_height.html" width="900" height="600" frameborder="0" style="border: 0px"></iframe>

Again, there is a noticable difference between men and women here. 


### Ethnicity
Now that we have an idea of their physical characteristics, let's look at the last feature we haven't exploited : 'Ethnicity'. This might give us some information on where they came from and complete our physical description. 

XXX different ethnicities, that's a lot! We cannot say that they all looked the same. The biggest category seems to be 'Indians', but I can see that there are a lot of smaller categories which have similar names, (Irish Americans, White Americans and Italian Americans). I wonder who those Americans are. Maybe I should continue my analysis by trying to group the small similar categories. 

I wonder how you can fit such diversity in so tiny a planet: 'Earth'.



-------------------------

## What did they like?
Let's move on from their external description. I now want to understand what they like, ie which movie genres they prefer. To do so, I need to have a way of quantifying how much they liked a movie over another. The column with the revenues for the movie box office seems perfectly suited for this. My unique worry is that this could be linked to other parameters which I'm not interested in. Indeed, I have just done a small linear regression on the movie box office revenue; these revenues seem to increase by a sum of $1 million for each year that passes. I definitely need to correct this effect if I want to have a reliable measure of movie success. Let's assume that the distribution of successful and disastrous movies is somewhat similar through time. Based on that, we can independently normalize the movie box office for each movie release year. This brings the average to zero and is not very sensible to outliers. I introduced the feature called : 'Movie box revenue scaled', and I will assess the success of a movie based the value of this measure. 

Let's start by looking at the movie genre distribution in the 1000 most successful movies. 

The three main genres seem to be : 'Drama', '' and ''

However, are we sure that those specific genres are able to induce success, or are we just seeing the most common movie genres? To be sure, I will show you a linear regression I made. To start with, I chose the genre 'Drama' calculated the linear regression coefficient associated to some other genres. Let's take an example to be clear: a coefficient of 0.5 associated with the genre 'Computer Animation' means that having the genre 'Computer Animation' versus having the genre 'Drama' brings you a success of 0.5 points higher. 


Looking at this, three genres stand to outperform 'Drama': 
On the contrary the genres : semm to be very detrimental to a movie sucees. 

This is only the result of the comparison against the reference 'Drama', to be complete I need to compare them with other refernces. After having tried all the different genres as reference I can tell you that those results are very robust. When I tried sequentially to use all the genres as references I see that it's always the same three that outperform almost all the other genres and the same three that underperform.



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

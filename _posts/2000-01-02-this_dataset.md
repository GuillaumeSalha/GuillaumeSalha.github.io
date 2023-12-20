---
title: "Dataset"
bg: turquoise
color: white
fa-icon: check-square-o
---

# Contextualization

<!-- pour la conclusion -->
<!-- December 2023, 19th, 11:23 AM. Voyager 1 is not responding. After 46 years of loyal service, this probe is now lost in space. At this day, it is the furthest object ever created by humans. It is 2.436563e+10km away from Earth. On-board, scientist let a message for the aliens that will find it. This message is a gold-plated audio-visual disc. It contains few symbols, images and sounds that are supposed to represent our world. -->

In the dire year of **2023**, as the impending collapse of our Earth civilization loomed large on the horizon, a group of desperate scientists raced against time to launch a last-ditch effort to preserve the essence of humanity. The chosen vessel for our legacy was a satellite destined to journey far beyond the confines of our troubled planet. In the eleventh hour, the scientist entrusted with the monumental task of uploading the data onto the satellite found themselves armed with an unexpected but strangely fitting resource—the **CMU Movie Summary Corpus**, a rich collection of narratives encapsulating the essence of our collective imagination. The satellite, now carrying the weight of our cultural legacy, soared into the vast unknown of space. Meanwhile, on Earth, the remnants of our civilization could only hope that these celluloid chronicles would serve as a cryptic Rosetta Stone for any extraterrestrial intelligences that might one day stumble upon this cosmic time capsule. 

10000 years later and far away from our decaying home, the alien discoverers puzzled over the enigmatic treasure trove they had stumbled upon. Their advanced intellects delved into the intricacies of our stories, attempting to decipher the nuances of a civilization long gone. Through the lens of our cinematic legacy, **these alien archaeologists sought to unravel the mysteries of what is a human**. An alien student class decide to present their findings to their teacher about what they have learned from the CMU Movie Summary Corpus.

## The Dataset

The CMU Movie Summary Corpus comprises 42,306 movies and an accompanying dataset featuring information about characters. The initial dataset, centered on movie details, encapsulates the narratives of 81,741 films spanning the cinematic landscape from 1888 to 2012. Complementing this, the second dataset delves into the intricacies of 450,669 characters. In their inaugural endeavor, the extraterrestrial scholars are poised to navigate through the character dataset, aiming to distill insights that will pave the way for crafting a humanoid robotic portrayal based on their preliminary analyses of these character details.

## The Map

Before delving into a human, one student alien decided to explore the dataset and to recreate a map of the Earth. By using the knowledge of his alien cousin from a star wars galaxy, he is thinking that the Movie countries present in the movie corpus are some places where human lives on their planet. He will model the earth has one full planet without water and the countries are some point position on it where it concentrates a human activity and by looking at the link between the country that shares movies among them, he will conclude that they have a link.

Based on its knowledge on network data, he will sparse the movie countries from the movie corpus to an adjacency matrix. This latter has been used to create a graph where the countries are the nodes and the link between them are the edges. Each link between two countries is weighted by the number of movies that they share. Then, he will able to draw a graph but before he is asking himself of to model the attraction of two countries between them. He is thinking to make a parallel with the gravity force that attracts two objects but he would like to 

<iframe src="img/html/network_countries.html" width="1000" height="1000" frameborder="0" style="border:0;"></iframe>
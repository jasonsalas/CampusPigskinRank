# CampusPigskinRank
## A machine learning approach for anointing college football's national championship
### Motivation
Most people tend to believe that we'll be able to use computerized and human logic to crack the S&P 500 before we consistently slay the dragon that is calculating college football's most worthy matchup for the national championship, primarily in the Bowl Championship Series era. Perhaps to solve this, the current College Football Playoff format uses a consensus of a human panel, without computer rankings. Much to the contrary of most fans, media members and followers of the sport, I actually **favored** the now-defunct [BCS](https://en.wikipedia.org/wiki/Bowl_Championship_Series), the formula that was created in an attempt to declare a national champion for the Football Bowl Subdivision (_nee_, "NCAA Division I"). 

I enjoyed the fact that the index used to setup a game between the true #1 and #2 teams in the nation was based on a three-pronged approach: an [equal-parts combination](http://www.bcsfootball.org/news/story?id=4819686) of two polls generated by human assessors, with a computerized poll.

The latter poll was itself an index of six computer-generated rankings. I tend to lean towards and be inspired by [Jeff Sagarin's formula](http://sagarin.com/sports/cfsend.htm) and [John Hollinger's power rankings]( http://www.thunderfans.com/vforum/showthread.php?3590-Hollinger-s-power-rankings&p=45436#post45436) more than the others...and to a slightly lesser degree, the [RPI](https://en.wikipedia.org/w/index.php?title=Rating_Percentage_Index). To date, the most progress we've made on the front of beating the BCS has been [the excellent paper produced by Microsoft Research](http://www.cs.toronto.edu/~dtarlow/NCAAF.pdf) that leverages _uncertainty_ and pairwise comparisons of teams and conferences as contributing factors.

The intent of this repo is to generate a ranked index of re-computed season data generated by the BCS for all 15 seasons of its existence, based on a purely objective perspective, and compare the re-ranked teams with how each season actually played out.
### (An all-too brief) Revisionist history
Although the BCS's overall formula was [rewritten several times](http://thenationalchampionshipissue.blogspot.com/2006/11/versions-of-bcs-5-and-counting.html) in its 15-year existence to reflect a more accurate arrangement of the top two teams, and ultimately replaced with the four-team [College Football Playoff](https://en.wikipedia.org/wiki/College_Football_Playoff), there was a still a lot of room for improvement. Accounting for strength of schedule proved to be rather problematic. 
Books like [_Polls, Bowls and Tattered Souls_](https://www.amazon.com/Bowls-Polls-Tattered-Souls-Controversy-ebook/dp/B00II92YOA) and [_Death to the BCS_](https://www.amazon.com/Death-BCS-Totally-Definitive-Championship-ebook/dp/B0052RCW3Y) - both of which are **excellent** reads - discussed the challenges of composing such an index based on the system that was developed.

### A machine learning approach
My hypothesis for [applying machine learning](http://blog.kaggle.com/2016/07/21/approaching-almost-any-machine-learning-problem-abhishek-thakur/) is that by definition, this would be [a ranking problem](http://www.slideshare.net/kerveros99/learning-to-rank-for-recommender-system-tutorial-acm-recsys-2013). The model will be built as a recommender engine using training data from the BCS seasons. The original [PageRank](http://infolab.stanford.edu/~backrub/google.html), the algorithm upon which Google Search is based, has been forked to assign value to each entity (the team) and rank them. Other have attempted to apply Bayesian probability and statistical techniques to estimate each team's rank. 
A reliable prediction system can produce results about who the teams most worthy to compete for the national champion can be. The key is in the features - the ambiguity and major components that determine the fitness of [each team and conference](http://web1.ncaa.org/onlineDir/exec2/sponsorship?sortOrder=0&division=1A&sport=MFB) relative to the others in the FBS. 

### Dataset
This project uses the [public dataset](http://thenationalchampionshipissue.blogspot.com/2005/08/ungodly-amount-of-football-data.html) compiled by [TheNationalChampionshipIssue](http://thenationalchampionshipissue.blogspot.com/). Based on the above assumption about data features, I'd like to evaluate if techniques like [latent Dirichlet allocation](http://blog.echen.me/2011/08/22/introduction-to-latent-dirichlet-allocation/) and [latent semantic indexing](http://nlp.stanford.edu/IR-book/html/htmledition/latent-semantic-indexing-1.html) might better mathematically identify features in the game data that weigh with more importance than what human input might miss - not just _that_ a team won but _how_ they won. 

However, I'm prematurely skeptical about the ability to generate such features, seeing as how datasets from other more static domains like the [Netflix dataset](https://gist.github.com/janisozaur/3192952) or the [MovieLens dataset](http://grouplens.org/datasets/movielens/) for films have more reliable attributes than just a team winning.

### Framework
The code is built on top of Google's [TensorFlow](https://www.tensorflow.org/) machine learning framework, and written in Python.

___
_I'm a product manager, [author](https://www.amazon.com/Designing-Developing-Google-Glass-Differently/dp/1491946458/) and [sportscaster](https://plus.google.com/+JasonSalas/posts/UCHTyZLJ2y9) in Guam. I know software, sports, movies, music, marketing, the 80s...and not much else. Find me on [Twitter](https://twitter.com/jasonsalas), [Facebook](https://www.facebook.com/jasonsalas) and [LinkedIn](https://www.linkedin.com/in/jasonsalas671)_.

Youtube as a political weapon
=======================

### Abstract:
Youtube is a main platform for sharing political videos and thus has a big impact on the political views of people. This leads to the effect that it could be used to particularly influence the political views of the users, i.e. it could be used as a political weapon. In our analysis, we assess if the data reflects this hypothesis and further explore if and how youtube has influenced the election result of the 2017 election in the USA. More precisely, we first analyze how the negative sentiment and political polarization has evolved over time. Then, we try to answer the question whether Youtube has indeed been used as a political weapon in the past. In the last part, we particularly analyze the (pre-)election period of 2017 to assess if and how Youtube had an impact on the election results.


### Research Questions:

 **RQ1:** Did the negative sentiment and political polarization in political videos increase over time?

 **RQ2:** Has Youtube been used as a political weapon and if so, who initiated this tone and benefited from it?

 **RQ3:** Has Youtube contributed to the election victory of Trump in 2017 and if so, how?
 
 

### Additional Datatsets:

For the last Research question, we used an additional dataset ("Radicalization Dataset") which contains the most important 676 channels of different political categories (Alt-right, Alt-light, etc.) together with its “channel_id” and the respective political “category”. This data was created for the paper "Auditing Radicalization Pathways on YouTube" (https://arxiv.org/pdf/1908.08313.pdf) and can be found in this drive (https://drive.google.com/drive/folders/1gOEsUQcfjBOiJwzAKNs02ez8Y7HWPhXv, filename: radic.csv). The dataset was provided to us by our mentor and co-author of the paper: Manoel Hortaribeiro.

### Methods:

 **RQ1:** 
 
 To answer this question we need:
 
 **(a) Measuring sentiment:** We chose to use a pretrained model to do the sentiment analysis. The Base model is BERTweet, a RoBERTa model trained on English tweets and then fine-tuned on SemEval 2017 corpus (around ~40k tweets). BERTweet is a large-scale pre-trained language model for English Tweets. It uses transformer methods to represent each word as a vector which can then be fed to a classifier to do classification.

 
 **(b) Measuring heat/polarization per video:** In the process of measuring the evolution of political polarization, we first chose to focus on people’s reaction to videos in the political channels especially in the category "People & Blogs". We chose a metric to analyze the trend of people’s disagreement or conflict of opinions towards a certain video which is the ratio between number of dislikes and total number of likes and dislikes. In this part, we visualized the trend of this ratio over months. Each month will have a mean value for this “heat metric” that represents how negative the response was to videos posted in this specific month on average. 

As a hypothesis, we expected an increasing trend for the ratio reflecting more negativity and disagreement with the political scene. However, the plot created was showing the complete opposite with a decreasing trend of the heat metric. Our explanation to this phenomenon is that people actually are becoming more radicalized to the extent that they only watch videos that agree with their political affiliations and their disinterest in opposite opinions is increasing. 


 **RQ2:** 
 
To answer this question, we will focus on the presidents/presidential candidates to show who benefited the most from youtube as a tool to improve his/her presence in the political scene. We chose the following political figures as examples to test our hypothesis: 
- Donald Trump
- Barack Obama
- Hillary Clinton

The comparison was based on three different aspects:
- Coverage and Publicity (which will be measured by the ratio between number of views and number of videos).
- Polarization (which will be measured by the heat metric presented in RQ1)
- Sentiment (which will be measured with the sentiment analysis model presented in RQ1).

As a feasibility analysis, it was chosen to do the comparison for coverage and publicity. For the implementation, new data frames were generated and saved on the disk with videos linked to each of the three figures by identifying their names in the videos’ descriptio


 **RQ3:** 
 
In order to explore whether youtube contributed to the election victory of the Republicans 2017 (where Trump was elected), our idea is to analyze the statistics of "right" videos compared to the statistics of "left" and "center" videos in the (pre-)election period of 2017. That is, we study and compare the growth of the amount of published videos for the three categorical videos ("left", "right" and "center") starting in the pre-election period of 2017. On top of that, we also want to analyze the evolution of the heat-metric (as described before) during that period to assess the user engagement for the three different political categories. To do that, we also used the “Radicalization Dataset” described in the previous section.

### Proposed Timeline (incl. organization within the team)

- 3/12 - 5/12 Running sentiment analysis on the whole dataset / different political groups separately (Mohamed and Ahmed)
- 06/12 - 11/12 Running tests presented in the proposal to answer the research questions (Esraa and Joshua)
- 12/12 - 18/12 Tabulating the final results and preparing the data story (the whole team)
- 23/12  Final submission 




### Questions for TAs
- What does “PUA” stand for as a political category? And can we classify it as left, center or right? We could not figure it out...
- Regarding the heat metric mentioned in the proposal, we had another idea to use the ratio between the number of comments and the views to identify videos which had heated discussions in the comments section. Given that, can you suggest an effcient way to deal with the comments dataset given its size ?
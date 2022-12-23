Youtube as a political weapon
=======================

### Abstract:
YouTube is one of the major social media platforms of our generation and people everywhere use it to keep in touch with the world. But how is YouTube used in the light of politics? Do users use YouTube just to catch up with recent news while having breakfast or is it more than that? Our approach is to first analyze the general political interaction on Youtube and compare it to the watching-behaviour of different video categories. Showing that there are indeed differences in the interaction behvaiour in political vs non-political videos, we narrow our research down to understand the differences within the category of political videos. More precisely, we analyze the differences in watching behaviour regarding views about politicians (Trump, Clinton and Obama) and also political orientation (left, center and right). Using the results, we examine how these are in line with the election results in the US. In our last part, we analyze the differences in political topics used by the three groups and test whether the respective sentiment disceprancies are statistically significant between the political orientations.


### Research Questions:

 **RQ1:** How is the general political interaction on Youtube compared to the watching-behaviour of other video categories? 

 **RQ2:** How were Trump, Obama, and Hilary Clinton covered on YouTube in terms of amount of coverage, sentiment and viewers' interactions?

 **RQ3:** How did the right and left political wings use Youtube and how were their videos perceived by the viewers? In addition, what were their most covered topics and in what context from the sentiment point of view?  
 
 

### Additional Datatsets:

For the last Research question, we used an additional dataset ("Radicalization Dataset") which contains the most important 676 channels of different political categories (Alt-right, Alt-light, etc.) together with its “channel_id” and the respective political “category”. This data was created for the paper "Auditing Radicalization Pathways on YouTube" (https://arxiv.org/pdf/1908.08313.pdf) and can be found in this drive (https://drive.google.com/drive/folders/1gOEsUQcfjBOiJwzAKNs02ez8Y7HWPhXv, filename: radic.csv). The dataset was provided to us by our mentor and co-author of the paper: Manoel Hortaribeiro.

### Methods:

 **RQ1:** 
 
 To answer this question we need:
 
 **(a) Measuring sentiment:** [We use a pretrained model to do sentiment analysis](https://github.com/pysentimiento/pysentimiento). The Base model is BERTweet, a RoBERTa model trained on English tweets and then fine-tuned on SemEval 2017 corpus (around ~40k tweets). BERTweet is a large-scale pre-trained language model for English Tweets. It uses transformer methods to represent each word as a vector which can then be fed to a classifier to do classification.

 
 **(b) Measuring heat per video:** In the process of measuring the evolution of heat, we used an approach to focus on people’s reaction to videos in the political channels especially in the (People & Blogs) category of videos. We selected a metric to analyze the trend of people’s disagreement or conflict of opinions towards a certain video which is the ratio between number of dislikes and total number of likes and dislikes. In this part, we visualized the trend of this ratio over months. Each month will have a mean value for this “heat metric” that represents how negative the response was to videos posted in this specific month on average. 
 
The next step was comparing the sentiment scores and the heat metric of videos across different categories. 

 **RQ2:** 
 
To answer this question, we extracted all videos which contain "Trump", "Obama" or "Clinton" in their video description. Thus, we ended up with:
- 349,091 Trump videos,
- 120,319 Obama videos,
- 46,336 Clinton videos.

To have a more meaningful metric for publicity and coverage over time, we examined the amount of quarterly released videos over time, the monthly views of each of these categories over time and the resulting average views per video over time.

Then we ran the sentiment model over the videos' descriptions which were addressing the three figures. In additon, we used the heat metric previously explained to examine the nature of viewers' interactions with videos over time and specifically around the elections period. 

 **RQ3:** 
 
In order to understand the difference in user-behavior based on the political orientation even better, we used the "Radicalization Dataset" described above on top of the YouNiverse dataset as we had access to 676 channels classified based on their political orientation (i.e. left, center, right). Using these classifications, we had 228,730 classified videos based on their political orientation. Using this video data, we analyzed the growth of each of the video categories over time and also compared the development of the heat-metric over time. 

To find the differences in topics covered by left and right wing videos. we created a wordcloud for the left and right videos based on the nouns they use most frequently in their video titles.

Focusing on the most frequently used keywords: Obama, Trump, Hillary, Russia, China, Immigration, Climate change, Putin, Police, and Women, we ran a sentiment analysis on videos mentioning these words in their titles for the right and left political groups. The sentiment disceprancies on the chosen topics between the two political groups were visulized using boxplots. 

Finally, an OLS regression model was used to test the relationship between the orienatation of a video and the sentiment score of its title. The regression analysis was used over the right and left wings' videos for every keyword separately. For example, taking the keyword "climate change", the videos included in the analysis were only those which had the keyword in the title. 



### Team members contribution

- 3/12 - 5/12 Running sentiment analysis on the whole dataset / different political groups separately (Mohamed and Ahmed)
- 06/12 - 11/12 Running tests presented in the proposal to answer the research questions (Esraa and Joshua)
- 12/12 - 18/12 Tabulating the final results and preparing the data story (the whole team)
- 23/12  Final submission 

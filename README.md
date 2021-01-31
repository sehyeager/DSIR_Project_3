# Processing Reddit Posts to Discern Customer-Friendly Language 

In the high-stakes world of MMORPGs (Massively Multiplayer Online Role-Playing Games), there are two standouts on the global scale:
The titanic World Of Warcraft, first released in 2004, and ruler of the mountain ever since.
The epic Final Fantasy XIV, which was released in a failed state in 2010, but remodeled and re-released as the closest competitor WoW has ever had in 2013.

At Square Enix, we are responsible for FFXIV, and specifically, we want to grow.  We're stil the #2 in the rankings, so what can we do to improve our standing?  I have been tasked with using machine learning to parse through posts on our reddit community, /r/FFXIV/ and compare the language used there to the language on /r/WoW.  With that comparison, can we find language to better tune our marketing to either our current players, to better market our expansions and upgrades, or to our competitor's players, to better market our base game?  

To find the answer to that question, I pulled posts from almost ten years of r/FFXIV and r/WOW, sampling 100 posts from each subreddit per month.  I sorted those posts by the subreddit, and then used a combination of sklearn's natural language processing and VADER sentiment analysis.  Through this, I built a handful of classification models to see if I could train a machine to predict whether a given post belonged on r/WOW or r/FFXIV.  I examined the relationships between post length, VADER sentiment scoring, post content, and our ultimate target, which subreddit the post came from.  The best model I found was an Extra Trees Classifier model, which had an accuracy of about 85%.

Through my analysis, I found our answer:  all of the language which points my Extra Trees Classifier model to one subreddit or the other is language that anyone with moderate knowledge of World of Warcraft and/or Final Fantasy XIV would be able to recognize.  We do not need a computer to discern whether someone is talking about one game or the other.  If a poster is discussing the relationships of Arthas Menethis and Sylvanas Windrunner, it is clear they are speaking about WoW.  If they are discussing the machinations of the Ascians and how they relate to the Garlean Empire, they are clearly speaking about FFXIV.  
Rather, with this model's approximately 85% accuracy, we can use it to quickly examine very large datasets of text, where individual analysis would prove too time consuming.   Additionally, the VADER sentiment analysis found that posts from r/FFXIV had a somewhat more positive compound value than those on r/WOW.   This could confirm that our community tends to be a touch more positively minded than World of Warcraft's, which happens to be a common rumor that we take pride in.  
Ultimately, the model does not give us any insight into commonplace language that sets these communities apart.  It still has value in analyzing big text data, but for the marketing purposes I set out to find, we may need to look elsewhere for ways to improve our sales.  NLP is not the right path to take.

## Notebook
https://git.generalassemb.ly/sehyeager/project_3/blob/master/Samuel_Yeager_code.ipynb

## Sources
https://www.reddit.com/r/ffxiv
https://www.reddit.com/r/wow
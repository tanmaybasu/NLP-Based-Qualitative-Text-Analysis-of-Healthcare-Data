# Qualitative Text Analysis using Wordnet and Machine Learning Techniques
 
Qualitative text analysis is a common practice in clinical research. It is a process of analyzing qualitative text data, such as open-ended survey responses and interview transcripts and the general approach involves reading the data and manually assigning codes to text segments. A code is a concise label to identify the meaning in a segment of text e.g., I like to exercise might be coded by the clinicians as exercise. Qualitative text analysis is a relatively labor intensive process. Hence a method using natural language processing (NLP) can automate part of this process. 


We have applied both NLP and qualitative text analysis methods to a database of short open-ended survey responses from youth gathered via short text messages to examine the results to identify whether NLP is adding value to qualitative text analysis. Questions were typically open-ended related to current events and some specific health concerns and participants were young adults aged 14-24 years. Therefore the task is to compare the utility of a traditional qualitative text analysis, an NLP analysis, and an augmented approach that combines qualitative and NLP methods. I have developed the NLP framework and the clinicians have collected data and done the manual coding.


We randomly assigned a question and the corresponding responses to each of the two experienced clinical teams for independent coding. The NLP team separately conducted analysis using a novel NLP framework for the same data. The NLP framework groups semantically similar words of the responses in a cluster and thus each cluster would represent a code segment. The Wu-Palmer similarity measure is used to find semantic similarity between the individual words and their synonyms generated by Wordnet, an English lexical database. The experimental results has shown that the NLP augmented qualitative coding produced more information than the qualitative-only or NLP-only approaches. 


NLP provides both a foundation to code qualitatively more quickly and a method to validate qualitative findings. NLP methods were able to identify major themes found with traditional qualitative analysis but were not useful in identifying nuances. Traditional qualitative text analysis added important details and context.

The analysis and performance of this framework is explained in the following paper:

[Timothy C Guetterman, Tammy Chang, Melissa DeJonckheere, Tanmay Basu, Elizabeth Scruggs and VG Vinod Vydiswaran. Augmenting Qualitative Text Analysis with Natural Language Processing: Methodological Study. Journal of Medical Internet Research, vol. 20(6), 2018.](https://www.jmir.org/2018/6/e231/).

## How to run the model?

The model is implemented in `qualitative_text_analysis`. Run the following lines to get the summary of given data. 

```
clf=qualitative_text_analysis(path='/Users/basut/myvoice/what_qualities.txt',wordnet_metric='w',pos='b',transformation='d')
clf.get_summary()
```

Here `path` is the path of the given data. The data should be in a text file and each line should not contain more than 160 characters including spaces. It is recommended to have 50 to 100 lines in the data file, but in principle, there is no limit on number of lines. 

The following options of `Wordnet metrics` are available:    

         "j" for Jiang-Conrath similarity
         
         "le" for Leacock-Chodorow (LCH) similarity
         
         "li" for Lin similarity
         
         "p" for Path similarity
         
         "w" for Wu-Palmer similarity 

The following options of `POS` i.e., parts of speech are available: 

         "a" for adjectives
         
         "b" for both adjectives and nouns
         
         "n" for nouns 

The options of `transformation` are "d" to generate `derivationally related form` of a term and "s" to perform `stemming`. An example code to run `qualitative_text_analysis` for the given data is uploaded as `test.py`. For any further query, comment or suggestion, you may reach out to me at welcometanmay@gmail.com

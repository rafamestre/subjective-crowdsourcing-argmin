# Benchmark Evaluation for Tasks with Highly Subjective Crowdsourced Annotations: Case study in Argument Mining of Political Debates

This is the accompanying dataset, codes and supplementary information of the paper "Benchmark Evaluation for Tasks with Highly Subjective Crowdsourced Annotations: Case study in Argument Mining of Political Debates", published at the 2nd NEATCLasS workshop 2023 at the 17th International AAAI Conference on Web and Social Media (ICWSM).




(Under construction)



# Instructions

The file "Instructions" contains the instructions used for the annotation tasks.

# Data

The folder "Data" contains the data obtained from the crowdsourced annotations, both the in-house and open crowd. There are some HTML files where the agreements and disagreements of the in-house annotations have been formated in a table, so that the reasons given by the annotators can be assessed.

The source material from these debates were a Kaggle competition (https://www.kaggle.com/headsortails/us-election-2020-presidential-debates, version 7, last accessed in August 9th, 2021) with a CO: Public Domain license.

The first one of the debates took place between the incumbent President Donald Trump and his Democrat opponent, former Vice-president Joe Biden, on September 29th, 2020, in Cleveland, Ohio, moderated by Fox News anchor Chris Wallace. The second debate in the files (which was actually the last one in time) also took place between both presidential candidates on October 22nd, 2020, at Belmont University, Nashville, moderated by NBC News' journalist Kristen Weller. The third and fourth presidential debates in the files were not debates in the strict sense, due to COVID-19 restrictions. After Donald Trump tested positive for the disease and declined to take part in a virtual debate, both debates were transformed into socially distanced town hall events, in which Joe Biden and Donald Trump alone answered questions from the public. The third debate is thus Joe Biden's town hall event, moderated by George Stephanopoulos on ABC, while the fourth debate is Donald Trump's town hall event, moderated by Savannah Guthrie on NBC. Both of them took place on the same day, October 15th, 2020. Finally, the last debate corresponds to the vice-presidential debate between the incumbent Vice-president Mike Pence and California Senator Kamala Harris, taking place on October 7th, 2020, at Kingsbury Hall, Salt Lake City, Utah and moderated by Susan Page from USA Today.

Here we present two annotations: one provided by an open crowd and another one by a in-house workforce of dedicated annotators. The first one corresponds to the M-Arg dataset, which can be found in the following repository, together with extensive information about its creation and the selection of sentences to annotate: https://github.com/rafamestre/m-arg_multimodal-argumentation-dataset, and the following publication and Zenodo repository:

> Mestre, R., Milicin, R., Middleton, S. E., Ryan, M., Zhu, J., & Norman, T. J. (2021, November). M-Arg: Multimodal Argument Mining Dataset for Political Debates with Audio and Transcripts. In Proceedings of the 8th Workshop on Argument Mining (pp. 78-88).

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.5653503.svg)](https://doi.org/10.5281/zenodo.5653503)

# Quality control mechanisms (QCMs) for the open crowd

For the task of crowdscourcing annotation, the platform Appen was used (https://appen.com/). Crowd annotators were presented with a pair of sentences, randomly selected according to the details in the previous subsection, and the topic of the debate. After this, they were provided with a short context of 15 sentences, indicating the name of the speakers, and highlighting in colour the sentence pair within the context. They were asked to focus on those two sentences and read around them to find the context in order to classify the argumentative relation between the pair. Finally, they were asked to classify their self-confidence level in the annotation they had just provided on a Likert scale, ranging from 1: "not confident at all" to 5: "very confident". Each worker was then paid per "page" of work completed, with each page containing between 4-6 tasks. The Appen platform allowed for several quality settings to maximise the quality of the annotation. These included:

* **Contributors' qualifications:** Four different levels of contributor selection, from 0 to 3, are available to launch an annotation task. The higher the level, the more experienced and accurate the contributors have been shown to be in previous jobs. Given its difficulty, our annotation was only advertised for Level 3 contributors. Although higher levels might require longer times for jobs to finish due to a shortage of contributors, a full annotation of roughly 1000 pairs of sentences took on average less than a day.
     
* **Geography and language:** In order to avoid biases from different countries or languages, the location of the contributors was filtered to include only the United States of America. As this is a web-based application, an option to disable Google Translate in their browser was also selected to avoid contributors speaking different languages relying on translation tools.
    
* **Contributors:** The annotation task was launched only to the contributors of the highest level on the platform, those that were more experienced. In order to avoid biases from different countries, the location of the contributors was filtered to include only the United States of America. 

* **Test questions:** Test or "gold" questions were previously annotated by the researchers. Before starting the task for the first time, the contributors had to answer a quiz containing only a random subset of gold questions ("quiz mode"). If they answered correctly above a specified threshold, they were allowed to contribute to the task; if they did not, they were not allowed to continue. Once they passed the quiz, they completed the annotations one page at a time. In each page, one of the questions was always a test question, without them knowing which one. The contributors had to continue scoring above a confidence score by being tested against the gold questions. If, once started on the task, they fell below the confidence score threshold, they were released from the task, all of their previous annotations were tainted as "untrustworthy" and new annotations for the gaps were requested. Annotators were always paid for their job, even if their answers were deemed untrustworthy. The number of test questions thus dictated the total number of work an annotator could provide: when they had seen all the possible test questions, they stopped contributing such that they should not see the same test question twice. Our confidence score throughout the annotation was 81%, meaning that if contributors were answering 80% or less of the test questions correctly they were not considered anymore for the annotation task. 
     
* **Minimum time per page:** To ensure that people were taking enough time to answer the questions, the minimum time per page was set to 90 s (each page contained 4-6 judgements). If a contributor would take less than that time to answer the questions (speeding), this indicates low quality of response , so they would be released from the task (the previous annotations in this case were not discarded). The statistics from the website show that trusted contributors took an average of 33 s (interquartile mean) to provide a judgement.
     
* **Answer distribution:** Answer distribution rules were enabled for this task. After 20 judgements had been collected, if an annotator had judged more than 60% of relations as "support" or more than 35% as "attack", they were released from the task and all their judgements tainted. This was estimated by several initial test launches that determined it very unlikely to have distributions with higher proportions than those.
     
* **Dynamic judgments:** A minimum of 3 annotations per pair of sentences were requested. However, if the annotation agreement fell below our selected threshold of 70%, dynamic collection of judgements was enabled. This meant that up to 7 judgements per case could be requested.

A total of 101 test questions were used in this annotation and 104 trusted contributors participated in this task out of 287 that attempted at it. Overall, considering the quality settings (e.g. dynamic judgements, tainted answers), 21646 trusted annotations were collected (5746 belonging to gold questions and 15900 to random pairs), and a separate 1663 annotations were deemed untrustworthy.  

# In-house workforce

After this work, we performed a follow-up study with an in-house workforce: a set of 9 contributors from an internal team of the company based in the Philippines (although we ended up with 8), who have significant experience in data annotation and are assigned in batches to specific jobs when higher accuracy and control are needed. According to the company, this crowd presented diverse demographics in terms of gender (3 female, 4 male, 2 non-binary) and age (5 between 21-30 and 4 between 31-40). Although they were all Filipino, their self-assessed level of English ranged from C2-C1 (4 people) to B2-B1 (5 people) and they all had a bachelors’ degree. Besides nationality, this group could be comparable to a team of graduate or under-graduate students generally hired for coding tasks in social science. This in-house workforce would be analogous to the ``master level" contributors of MTurk, albeit perhaps with a slightly higher degree of control. 

# Common misconceptions during test annotations

During our feedback with the company, giving feedback on our expectations for the task, we noticed that there was a tendency to assume that statements from different speakers are an argumentative attack by default. For instance, consider this extract from one of the debates between Donald Trump and Joe Biden:

- Joe Biden: ``Number two-''
- Donald Trump: ``Chris.''
- Joe Biden: **``Number three.''**
- Donald Trump: **``They said it would take… No, you're on number two.''**
- Chris Wallace: ``No.''

The contributors were asked to annotate the argumentative relation between the highlighted sentences, which are not argumentative, as the extract is from a series of interruptions between both candidates. In the first iteration, however, two of the three annotators thought that was an attack relation, simply because it was Donald Trump trying to interrupt Biden. A similarly interesting case occurred with certain `support' relations. We noticed that contributors tended to consider a relation as support when the message was positive. See for instance this interaction between Mike Pence and Kalama Harris:

- Mike Pence: ``The Green New Deal is on their campaign website.''
- Mike Pence: **``And as USA TODAY said, it’s essentially the same plan as you co-sponsored with AOC when she submitted it in the Senate.''**
[...]
- Mike Pence: ``We don’t need a massive \$2 trillion Green New Deal that would impose all new mandates on American businesses and American families.''
- Kamala Harris: **``Thank you.''**

This is part of a long speech by Mike Pence about the Green New Deal and the second sentence by Kamala Harris is simply “Thank you”, most likely thanking Pence or the moderator for giving her a turn to speak. The three annotators that judged this considered the relation to be of support. Despite the instructions stating clearly and with examples that the sentences needed to be somewhat argumentative, we encountered several similar examples. In this particular case, it was transmitted to us by the manager that the workers assumed that `thank you' was an acknowledgement and agreement of what Pence said, and thus support. We reminded them that simple agreement was not sufficient to be considered argumentative support.

There was a tendency to over-read much of the intentions of the speakers and over-complicate the task. For instance, in this exchange:

- Savannah Guthrie: ``You retweeted it.''
- Donald Trump: ``That was a retweet.''
- Donald Trump: **``That was an opinion of somebody-''**
- Savannah Guthrie: ``But-''
- **Donald Trump: ``....''**
- Donald Trump: ``and that was a retweet."

The highlighted sentence "…" was a transcription error and the instructions stated to label these cases simply as neither. One of the contributors, however, labelled it as `support'. They explained in the free-text box that ``[t]he ... assuming a pause is a silent statement to reaffirm confidence in the first sentence''.

In other cases, transcription labels confused some of the annotators:

- Donald Trump: ``Many car companies came in from Germany, from Japan, went to Michigan, went to Ohio and they didn’t come in with you.''
- Donald Trump: **``[crosstalk 00:21:47].''**
- Joe Biden: [...] **``He talks about these great trade deals.''**
- Joe Biden: ``He talks about the art of the deal.''

The contributors should have labelled this case as neither, since the first sentence is a transcription label. However, two of the contributors labelled it as attack, most likely because interrupting someone can be considered an attack towards the other speaker. In other instances, sentences that said something like "I need to respond to that" or "Please, let me respond" tended to be associated with attacks, whereas positive sentences like "Good" or "Yes", tended to be annotated as support. 

# The reasons behind disagreements

We then assessed the annotations and the reasons provided by the contributors in two cases that we thought to be of particular interest: i) when the contributors completely agree on “support” or “attack”; ii) when the contributors disagree at least once. Focusing on cases when the contributors completely agree on “neither” is not particularly useful, as they represent most of the dataset - and are generally because the sentences are clearly unrelated or not arguments at all (“thank you”, “no”, etc.). Focusing on the cases in which the contributors completely agree on support or attack and comparing them with the cases in which they are not so sure provided insight into which type of argumentative relations are clear enough to not induce confusions, and when confusion starts to set in.

Out of the 1145 cases in which the annotators did not disagree, only 20 of them were support relations and 19 of them attacks, which highlights the difficulty on agreeing on this type of relation. In general, we observed that the annotators agreed on support relations when the claims were very clearly stated. For instance:

- Chris Wallace: "Are you questioning the efficacy of masks?"
- Donald Trump: **"No, I think masks are okay."**
- Donald Trump: "You have to understand, if you look… I mean, I have a mask right here."
- Donald Trump: "I put a mask on when I think I need it."
- Donald Trump: **"Tonight, as an example, everybody’s had a test and you’ve had social distancing and all of the things that you have to, but I wear masks-"**

Here, Trump claims very clearly “I think masks are okay” and he later explains using an argument by example, supporting his own claim. All annotators agreed that this was a support relation. Likewise, in these statements by Biden:

- Joe Biden: **"In fact, we’re all Americans."**
- Joe Biden: **"The only way we’re going to bring this country together is bring everybody together."**

The annotators agreed that he was supporting his own claim because “the sentence shows a support argument by saying that bring all Americans and unite as one.” One common source of confusion with support statements was the cases in which one speaker was agreeing with the other. For instance:

- George Stephanopoulos: **"Was it a mistake to support it?"**
- Joe Biden: **"Yes, it was."**

Here, Biden is answering a question and the three contributors agreed that this relationship was of support because “its very clear that is supporting argument” and “Biden agrees with George”. For the other contributor, “this is "support," because Joe is showing that he agrees with the first sentence.” The fact that George Stephanopoulos precisely uses the word “support” might have fuelled this idea that this was a support relation, but there is no argument behind it, just an opinion. This was not isolated and happened in other examples too:

- Joe Biden: "You’ll not hear me dividing."
- Joe Biden: "You’ll hear me trying to unify, and bring people together."
- Joe Biden: **"When I said I was running because I wanted to unify the country, people said, “Well
- Audience Member 11: **``Agreed.''**



Using similar arguments, the contributors thought this was a support relation “[…] because Audience Member 11 is showing that he/she agrees with the first sentence.” When a person is showing support towards another person, the contributors also tend to understand it as a support relation. See:


- Donald Trump: **"I have a lot of respect for Judge Garland."**
- Donald Trump: "I want to tell you that."
- Donald Trump: "But I’ll tell you, the whole ball game changed when I saw the way they treated Justice Kavanaugh."
- Donald Trump: **"I have never seen any human being, and I’m not just talking about Supreme Court… I have never seen a human being treated so badly with false accusations and everything else."**



The annotators clearly stated that “the argumentative is support, it seems the sentence are showing respect to the speaker” and “Trump expresses support for Garland”. It is indeed true that Trump is showing support and respect towards Garland and his first statement could be considered a claim. His second statement, “I have never seen any human being […] being treated so badly […]” could also be a claim or a premise, but in this context, they are not joined by an argumentative support relation, since the second statement does not help prove that the first claim is true. The crowd annotators, thus, seem to confuse the aim of the task, finding argumentative relations, with agreement or general, non-argumentative support.

Natural dialogue like this one is, however, full of nuance and does not follow in general the argumentative structure found in argumentation frameworks. Whereas some cases are straightforward and clear for the annotators (see the first examples), those that require more thought, background knowledge, contextual information or mental rephrasing can be a real challenge and highly subjective. Nevertheless, sometimes the results are rather positive. Take, for instance, the following segment:


- Kamala Harris: "So, Susan, I’m glad you asked about transparency because it has to be across the board."
- Kamala Harris: "Joe has been incredibly transparent over many, many years."
- Kamala Harris: **"The one thing we all know about Joe, he puts it all out there."**
- Kamala Harris: **"He is honest, he is forthright, but Donald Trump on the other hand has been about covering up everything"**


Here, Harris is confident in her claim: Joe Biden puts it all out there. She uses the second statement to further prove her point by emphasising some of his attributes, while at the same time attacking Donald Trump. The contributors also pick up on this: “the argument was supporting the sentence but some how they attacking [sic] the other person.” This type of example emphasises an added difficulty in this task, which is its highly contextual nature. This is one of the reasons why we decided to follow this relational approach instead of identifying first claims and premises and then linking them. Whereas in one context Harris’ second claim might have been an attack if she was speaking about Trump’s fitness for presidency, it was a support relation in this context to the claim that Biden puts it all out there and will be a good president. The following segment highlights this contextual nature:


1. Joe Biden: "And he does take advantage of the tax code."
2. Joe Biden: "That's why I'm going to eliminate the Trump tax cuts."
3. Joe Biden: "**And I'm going to eliminate those tax cuts.**"
4. Donald Trump: "That's okay."
5. Joe Biden: "And make sure that we invest in the people who in fact need the help."
6. Joe Biden: "People out there need help."
7. Donald Trump: "**But why didn't you do it over the last 25 years?**"
8. Joe Biden: "Because you weren't president-."
9. Donald Trump: "Why didn't you do it over the last 25 years?"
10. Joe Biden: "**Because you weren't president and screwing things up.**"
11. Donald Trump: "You were a Senator and [crosstalk 00:17:21]-"
12. Joe Biden: "You're the worst president America has ever had."
13. Joe Biden: "Come on."
14. Donald Trump: "**Hey, Joe, let me just tell you, Joe**"

Several random matches were proposed to the annotators within this segment. When asked to identify the relation between sentence 3 and 7, all the annotators agreed this was an attack. This is not obvious, as sentence 7, expressed as a question, needs some rephrasing in this context to understand that Trump implies “you’re not going to eliminate the tax cuts because you had 25 years to do it and you didn’t do it; you cannot be trusted”. Indeed, one of the contributors recognises that this is not a simple question, but a “contentious query” and another that is “showing attack argumentative on this context”. The argument continues and sentence 7 can be linked to sentence 10, where Biden attacks Trump’s question/argument with a clear reason “because you weren’t president and screwing things up”. All three of the annotators agreed that this was part of an argumentative attack. However, in the open crowd, six annotations were needed to reach a consensus between “attack” and “neither”, which was finally “neither”. Sentence 10 was also connected to statement 14, where Trump interrupts Biden to give his opinion. Our previous experience told us that contributors tended to confuse this interruption with an attack, and in such a heated discussion it is reasonable to make that mistake. However, after our initial test runs the contributors had been advised against this mistake, and the three of them agreed that this was neither support nor attack. 

Another interesting example that highlights the subjectivity of the task is the following:

- Joe Biden: "He still hasn’t even acknowledged that he knew this was happening, knew how dangerous it was going to be back in February, and he didn’t even tell you."
- Joe Biden: "He’s on record as saying it."
- Joe Biden: "He panicked or he just looked at the stock market."
- Joe Biden: "One of the two."
- Joe Biden: "Because guess what?"
- Joe Biden: "**A lot of people died and a lot more are going to die unless he gets a lot smarter, a lot quicker-**"
- Chris Wallace: "Mr. President?"
- Donald Trump: "Did you use the word smart?"
- Donald Trump: "So you said you went to Delaware State, but you forgot the name of your college."
- Donald Trump: "You didn’t go to Delaware State."
- Donald Trump: "**You graduated either the lowest or almost the lowest in your class.**"
- Donald Trump: "**Don’t ever use the word smart with me."**
- Donald Trump: "Don’t ever use that word."

Connected to Joe Biden’s first claim about needing to be smart and quick to fight against the pandemic, all annotators considered that the last two sentences were argumentatively attacking it. This is highly subjective, and, about the first pair, the contributors give explanations such as “Trump attacks educational performance of Biden” and “attacking the sentence because of the questioning of the educational attainment of the person.” This could be true if we took Trump’s first statement as “you are not smart enough to say that”, although one could think that, in this context, Trump is simply comparing his own intelligence with Biden’s, and not really attacking his argument about the pandemic. Regarding the second statement, “don’t ever use the word smart with me”, it seems very clear that it should be neither support nor attack, since Trump is simply warning Biden not to use that word again. The contributors thought this was an attack, although one of them raises doubts about its argumentative nature: “almost argumentative but the statement I feel is insufficient”. 


Finally, there was one type of dialogue that tended to attract attack relations, which is when one person simply states the opposite to what the other person says. For instance:


- Donald Trump: **"He was thrown out dishonorably discharged"**
- Joe Biden: **"That’s not true he was not dishonorably discharged."**

Or:

- Donald Trump: **"He doesn’t have any law support."**
- Donald Trump: "He has no law enforcement."
- Joe Biden: **"That’s not true."**

Or:

- Donald Trump: **"Once you became vice president he made a fortune in Ukraine, in China, in Moscow and various other places."**
- Joe Biden: **"That is not true."**



These are some cases that are particularly relevant when investigating how people understand arguments. All these pairs of sentences were labelled without disagreement as an argumentative “attack”. Can simply negating what the other person just said be considered an argumentative attack? Following the logic of argumentation, if one statement p is valid, its negation ¬p cannot be valid following deductively the same set of premises. Therefore, we cannot use ¬p as an argument attacking p. However, the contributors consistently annotated these cases as attacks, which raises questions like: do people consider that saying “that is not true”, without providing a valid set of premises, a valid argument? The reasons provided by the contributors did not clarify this issue, as they simply stated that they were disagreeing with one another, and that seemed to be sufficient to label it as “attack”.


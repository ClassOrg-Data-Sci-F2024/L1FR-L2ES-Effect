10/5/24, 12:47pm

Today I created the repository for my term project and added a README, LICENSE, project plan, and gitignore files.

I've decided to go with written corpora data analyzing L1 Spanish speakers' acquisition of paraphrastic future in L2 French.


10/28/24, 2:30p

Progress Report 1

The most important thing I wanted to focus on for this next step was finding a corpus that could work with the intended data, which I did! I had been having trouble finding one either with enough tokens, or one that included the L1 Spanish or L1 French learners that I was looking for. I encountered the CAES Corpus (Corpus de aprendices de español / Corpus of Spanish learners) which so far has worked well. This corpus is comprised of written texts produced by L2 learners of Spanish of different backgrounds and proficiency levels.

Based on what has been found through some searches through the corpus, I intend to have the participants be L1 French speakers rather than L1 Spanish, because it is very hard to find corpora for French with L1 Spanish speakers. I initially intended to have the Spanish learners be beginner learners. This is because I believe it is best to analyze the participants' output prior to them acquiring more Spanish. This would be the best way to see what their starting knowledge is and how they are applying it during their acquisition, if at all. The only potential downfall is that there are only 58 tokens in total of just A1/Beginner participants, which may or may not be enough. I intend to consult Dan about this just to make sure prior to continuing.

Using L1 French speakers with all levels of proficiency, I have found a total of 146 tokens of the periphrastic future in Spanish, which is more than twice the amount of just beginners. If the 58 above are not enough, I will use the 146 tokens and analyze them that way. Regardless, this is still a small amount, and there are some tokens produced by the same participants.

If I am to do option two, I will group students by their proficiency levels and analyze them that way.


I also intend to use gender as an independent variable. There are 98 tokens for women and 58 tokens for men producing the periphrastic future based on what I have found. The 40-token difference may have the potential for skewed data, but I still need to go through and label all participants.

That is my next step. I have all of the tokens, but now I need to organize them by participants and see if there are any productions by the same participant.


Yining Nie has an article titled "TENSE AND MODALITY IN FRENCH VERBAL MORPHOLOGY" from 2015 that I intend to use as an explanation of the periphrastic future in French. This article also mentions the periphrastic future in Spanish, which is perfect for this project, since I initially explained that the two languages' periphrastic futures are the same, hence why I wanted to study any potential transfers from one language to another. If I need more scholarly references to back this up, I can certainly find more.

I intend to make it known that whatever results are found are more specific to those in the corpus and should not be generalized to all L1 French learners of Spanish.


11/11/24, 2:46p

Progress Report 2

I have combined all of the downloaded data that I have compiled from the corpus into one Excel sheet to make it easier to 1. read in and 2. sort through in RStudio. I decided after speaking to some classmates last week that it may be best if I stick to analyzing only the different conjugations of the periphrastic future. The reasoning for this rather than doing both the conjugations and different proficiency levels is because if what I aim to analyze is whether there is transfer from the L1, it is best to try to verify that within the A1 group, or those with the least proficiency in the language. This is because those learners do not yet know enough Spanish to understand the complexities of its grammar and tenses. Therefore, they will likely rely on their L1 more to help them until they acquire more experiences within their L2.

I was having lots of trouble reading my file into R studio without using an absolute path. I tried consulting Ben and Dan about this. Dan suggested I have the csv file in the same folder as my Rmd file, so I moved it to the working directory's folder. From there, the read.csv function worked! I think I was trying to overcomplicate it by creating a relative path when in reality there is none because the csv file is not within a folder in the directory.

I did also add a note in my Rmd file which specifies that all of the downloaded data from the corpus is in Spanish. Therefore, to increase understanding for readers who do not understand Spanish, I will most likely edit the columns and rows to reflect the same data but translated. This is also something to consult Dan about.

Other steps:
- Checked for duplicate participants in the data and grouped the data by participants for more accurate reflection of productions.
- Pulled out the necessary columns for data analysis
- Renamed long columns
- Added titles to sections and chunks
- Learned that using backticks around column names allows you to have spaces in your words without having to rename the columns
- Analyzed the age ranges of the participants and how many per age group there is.

Progress Report 3

11/14/24, 12:04p

- Added a license to my project
- Translated all column names to English

Progress Report 4

11/21/24, 12:06a

- Redid all the data read-in by separating the excel files, reading them in, then combining them into one dataframe.
- Renamed everything to go with the new dataframe.
- Wrote a new csv file for the dataframe.
- Finished simple stats.
- Started the final statistical analysis but I kept getting errors so I erased it. Will be readdressing tomorrow.
- Added some more analysis (written) to the code.
- Added the session info at the end.

Progress Report 5

11/21/24, 10:47p

- After consulting the class, I finally figured out what I was doing wrong and was able to run a logistic regression for my data. So data wrangling is concluded!
- I started visualization which I will finish tomorrow.
- I organized the Excel and Csv files into folders in the repo because things were getting cluttered and hard to find on GitHub
- Linked my Rmd file and the folders into this md file so readers do not have to go back and forth :)
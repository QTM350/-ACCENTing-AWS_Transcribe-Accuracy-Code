# ACCENTing Transcribe’s Accuracy-Code
This project uses AWS Transcribe to measure how accurate the service is when converting speech-to-text when using non-native English. In combination with AWS Transcribe, we also used Amazon S3 buckets to store our data output from Transcribe.


## What the project does


Our project's goal is to test the accuracy of Amazon Transcribe when converting speech-to –text. We did so by testing out five different accents. The countries of origin included the United States, United Kingdom, China, Spain, and India. We decided to only look at female voices in order to control for other variations. We tested various transcripts from various scripts, using Transcribe within Sagemaker.

Our data analysis included using Levenshtein distances (LD) and a confidence review on Transcribe. The LD was used to measure the difference between two sequences. This helps to determine the amount of single character edits between  two scripts. 

## Transcribe code

`import boto3`
`transcribe = boto3.client('transcribe')`

`job_name = "American_Medium_Transcribed_Correct"`

`job_uri = "https://350-public-audio-files.s3.amazonaws.com/American+Medium+Audio+Extracted+2.wav"`

In this example, we instructed Amazon Sagemaker to look for a file in the "Audio" S3 Bucket. In this bucket, we acquired the file that contains the sound bite of the American-accented female voice reading back the TED Talk transcript.


`transcribe.start_transcription_job(
    TranscriptionJobName=job_name,
    Media={'MediaFileUri': job_uri}, 
    MediaFormat='wav',
    LanguageCode='en-US',
    OutputBucketName='350-public-generated-transcript'
)`

## Actual Transcription Process

TranscriptionJobName: the name of this particular transcription job, which is the TED Talk in the American accent in this case.

Media: the media file to be transcribed, which is the actual audio file containing the speaker's rendition of the passage.

MediaFormat: the format of the media file which is in .wav.

LanguageCode: the language of the audio file. We want English in this analysis.

OutputBucketName: the S3 bucket in which we want the transcript to be stored, in this case, 350-public-generated-transcript. 

The remaining audio files were generated into transcripts in this manner.



## Why the project is useful

This project is very useful to our knowledge and to AWS and Sagemaker. By fully understanding the limitations and obstacles in our project, we could find the areas of improvement for Transcribe. This could in turn help to make Transcribe more efficient and accurate. Some examples could be that more accents could be added. Since Transcribe is such a powerful tool, fixing its flaws, would help to make it even more useful to users. 




## How users can get started with the project

### Access to Audio Recordings
[google drive](https://drive.google.com/drive/folders/1XMca6gJVa3iX1yEqHoQxlFnAMySBhFmX?usp=sharing)

## Where users can get help with your project
Anyone who is interested in replicating this project can access our data in the github repository. We also provide a blog on Google Colab that provides the motivation behind the project, explanations in our analysis (including what the Levenshtein distance is) and a visual for the confidence rating from Amazon Transcribe.

## AWS Services used:
- Amazon Transcribe
- Amazon Sagemaker
- Amazon S3

## Project Architecture 

![PA](arch.png)


## Sources

Websites:

AWS. "Amazon Transcribe." [link](https://aws.amazon.com/transcribe/?nc=sn&loc=0)

Besner, Linda. "When Is a Caption Close Enough?" [link](https://www.theatlantic.com/health/archive/2019/08/youtube-captions/595831/)

Diana. "Transcript: A Pep Talk From Kid President." [link]( http://complicatedmelody.com/content/transcript-pep-talk-kid-president)

Everson, Howard T., Tobias, Sigmund. "The ability to estimate knowledge and performance in college: A megacognitive analysis." [link](https://link.springer.com/article/10.1023/A:1003040130125)

List from Wikipedia. "List of countries by English-speaking population." [link](https://en.wikipedia.org/wiki/List_of_countries_by_English-speaking_population)

Radecic, Dario. "Calculating String Similarity in Python." [link](https://towardsdatascience.com/calculating-string-similarity-in-python-276e18a7d33a)

Speech-to-text. [link](https://ttsreader.com/)

Urban, Tim. "Inside the mind of a master procrastinator." [link](https://www.ted.com/talks/tim_urban_inside_the_mind_of_a_master_procrastinator/transcript#t-25363)


## Images:

Amazon Transcribe. ![link](https://miro.medium.com/max/400/0*BNicZbcGBnG5t2qX.png)


Globalization.  ![link](https://youmatter.world/app/uploads/sites/2/2019/01/globalization-definition-benefits-effects-examples.jpg)

Hello in Languages. ![link](https://bilingua.io/wp-content/uploads/2017/05/hello-in-100-languages.jpg)


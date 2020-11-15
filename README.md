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



## Where users can get help with your project
Anyone who is interested in replicating this project can access our data in the github repository. We also provide a blog on Google Colab that provides the motivation behind the project, explanations in our analysis (including what the Levenshtein distance is) and a visual for the confidence rating from Amazon Transcribe.

## AWS Services used:
- Amazon Transcribe
- Amazon Sagemaker
- Amazon S3

## Project Architecture 

![PA](arch.png)

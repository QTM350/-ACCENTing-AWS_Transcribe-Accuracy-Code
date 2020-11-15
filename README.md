# ACCENTing Transcribe’s Accuracy-Code
Project using AWS Transcribe to measure how accurate the service is when converting speech-to-text in using non-native English.


What the project does


Our project's goal is to test the accuracy of Amazon Transcribe when converting speech-to –text. We did so by testing out five different accents. The countries of origin included the United States, United Kingdom, China, Spain, and India. We decided to only look at female voices in order to control for other variations. We tested various transcripts from various scripts, using Transcribe within Sagemaker.

Our data analysis included using Levenshtein distances (LD) and a confidence review on Transcribe. The LD was used to measure the difference between two sequences. This helps to determine the amount of single character edits between  two scripts. 




Why the project is useful


How users can get started with the project


Where users can get help with your project


Who maintains and contributes to the project

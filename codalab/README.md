### About

This repository provides instructions as well as data samples to enable submissions to the `SimpleText Task4 @ SOTA?` task on Codalab here: https://codalab.lisn.upsaclay.fr/competitions/16616. All test set submissions to the shared task are only accepted via Codalab.

### SOTA? testing phases timeline

Evaluation phase 1 (Few-shot Testing) start - 23rd April 2024
Evaluation phase 1 (Few-shot Testing) end - 28th April 2024

Evaluation phase 2 (Zero-shot Testing) start - 29th April 2024
Evaluation phase 2 (Zero-shot Testing) end - 3rd May 2024

More info here https://sites.google.com/view/simpletext-sota/important-dates

### What can you expect in the testing phases?
 
Currently we have created an example in this repository from the validation dataset https://github.com/jd-coderepos/sota/tree/master/dataset/validation. Before April 23rd results from the respective participant systems over the validation dataset can be submitted.

Note once the evaluation phase begins, the underlying test datasets automatically switch to the relevant test dataset for that phase.
 
To help participants prepare their system submissions in advance for the testing phases, let's examine the validation dataset released in this repository.

1. blind-validation-dataset

This folder contains sub-directories of articles where sub-directories have an identifier and within the sub-dir is the LaTeX content provided in .tex format.

During the testing phases, participants will be provided unique test dataset releases, one during the few-shot testing phase, and a second one with a new set of articles during the zero-shot testing phase. This will be available as input to the systems.

2. sample-submission

This folder contains the expected output from the participant system programs given the input data. Note the output contains the identical subdirectory names as the input dataset. This is important to uniquely identify each article in the evaluation script. Any change in the subdirectory identifiers will cause incorrect scores of the participant system outputs. Within each subdirectory, the system should output the SOTA annotations or the string "unanswerable" within a file named as a standard "annotations.json" expected by the scoring program.

To make the submission itself, create a `*.zip` file of all the output subdirectories as in `sample-submission.zip`. On codalab, assuming you are registered as a participant, scroll over to the `Participate` tab and select `Submit/View Results`. There you will see the option to submit your zip file.

Note if you submit the `sample-submission.zip` provided in this repository as it is, you should see an evaluation score of a 100%. This dummy submission file was created by simply copying over the annotations.json files from the validation set and hence is an exact replica of the test dataset.

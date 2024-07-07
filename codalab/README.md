## About

This repository provides instructions and data samples for submissions to the **SimpleText Task4 @ SOTA?** task hosted on Codalab. All test set submissions for the shared task must be submitted through [Codalab here](https://codalab.lisn.upsaclay.fr/competitions/16616).

## SOTA? Testing Phases Timeline

- **Evaluation Phase 1 (Few-shot Testing)**
  - **Start**: April 23, 2024
  - **End**: April 28, 2024

- **Evaluation Phase 2 (Zero-shot Testing)**
  - **Start**: April 29, 2024
  - **End**: May 3, 2024

More information on important dates is available on the [SimpleText SOTA? website](https://sites.google.com/view/simpletext-sota/important-dates).

## What to Expect in the Testing Phases?

In this repository, we have included an example from the validation dataset available [here](https://github.com/jd-coderepos/sota/tree/master/dataset/validation). You can submit results from your systems on the validation dataset before April 23rd.

Note that once the evaluation phase begins, the test datasets will automatically switch to the relevant dataset for that phase.

During the practice phase we have uploaded the validation dataset annotations on Codalab. Participants can prepare for the testing phase by making a few practice submissions with the validation dataset ahead of time to ensure that your outputs are processed and results are obtained. The following two folders will be discussed:

1. **blind-validation-dataset**
   - This folder contains sub-directories of articles. Each sub-directory has an identifier and contains the LaTeX content in `.tex` format.
   - During the testing phases, participants will receive unique articles collection as test dataset releases for each phase, available as input to the systems. Similar to the dataset in this folder there will be no `annotations.json` files released.

2. **sample-submission**
   - This folder contains the expected output format from participant systems given the input data. The output must preserve the original subdirectory names from the input dataset to uniquely identify each article during evaluation. Each subdirectory should include a file named `annotations.json`, which either contains SOTA annotations or the string "unanswerable".
   - Create a `*.zip` file of all output subdirectories as shown in `sample-submission.zip`. The naming of the zipped file is not relevant. On Codalab, assuming you are registered to the SOTA? task, navigate to the `Participate` tab and select `Submit/View Results` to submit your zip file.

Note: Submitting the `sample-submission.zip` provided in this repository, during the practice phase until the end of April 22nd, as it is will result in an evaluation score of 100%, as this file is an exact replica of the validation set, merely copying over the `annotations.json` files.

The official evaluation script used for ``SOTA?'' is also publicly released [here](https://github.com/Kabongosalomon/scoring_program/blob/main/evaluation.py).

## Other

### How to organize a challenge on CodaLab Competitions

To host your own competitions, follow the [step-by-step guide](https://github.com/codalab/competition-examples/blob/master/TUTORIAL.md) provided by the developers at Codalab. The competition configuration `.yaml` for SOTA? is publicly released in this folder within the `online-competition-site` subfolder.


<!--## SOTA? Tracking the State-of-the-Art Empirical Artificial Intelligence Research

The central activity around empirical AI research includes automated tasks defined via a task dataset for which machine learning models are developed whose performance can be evaluated by a standard set of evaluation metrics. Pushing the state-of-the-art boundaries in empirical AI research means optimizing the models developed for the tasks in terms of speed, accuracy, or storage. As such researchers in this domain often seem to ask the central question “What’s the state-of-the-art result for task XYZ right now?” 


Instead of seeking out the answer buried in the ranked list of documents via a search query made on traditional search engines, researchers instead look for the answer on community-curated leaderboards such as https://paperswithcode.com/ or https://orkg.org/benchmarks. These leaderboards are websites specifically designed to showcase the performance of all introduced machine learning models on a machine learning task dataset. As such researchers seeking to find out the best model performance on a task dataset can easily obtain this information on these websites via their performance trendline overviews showcasing various model performances over a task dataset over time.


In this Shared Task, we hope to go beyond the community curation of leaderboards and instead  realize the vision of obtaining the most efficient machine learning model capable of automatically detecting leaderboards. The efficiency of the submitted machine learning models as a solution to the shared task will be tested based on speed, model parameters, and leaderboard detection F1 measure.-->


### What this repository contains?
 
This repository hosts the official SimpleText Task4 @ CLEF'24, i.e. the [SOTA? Tracking the State-of-the-Art in Scholarly Publications](https://sites.google.com/view/simpletext-sota/) task corpus. The full corpus is released in the dataset repository organized as follows:

```
[dataset]/	
     |--- [train]/
	     |--- [article-id-folder]/
		 |    |--- [article-id].tex
		 |    |--- annotations.json	
	     |___ ...
     |--- [validation]/
	     |--- [article-id-folder]/
		 |    |--- [article-id].tex
		 |    |--- annotations.json	
	     |___ ...		 
     |--- [test1-few-shot-papers]/	
	     |--- [article-counter-folder]/
		 |    |--- [article-id].tei.xml
	     |___ ...
     |--- [test1-few-shot-annotations]/	
	     |--- [article-counter-folder]/
		 |    |--- annotations.txt		# hidden during the competition
		 |    |--- code-link.txt	   # optional	
	     |___ ...		 
     |--- [test2-zero-shot-papers]/				
	     |--- [article-counter-folder]/
		 |    |--- [article-id].tei.xml
	     |___ ...
     |--- [test2-zero-shot-annotations]/	
	     |--- [article-counter-folder]/
		 |    |--- annotations.txt		# hidden during the competition
		 |    |--- code-link.txt	   # optional	
	     |___ ...			 
```

The dataset dump originates from [paperswithcode.com](https://paperswithcode.com/).

Each folder in the respective dump corresponds to a scholarly article
originally downloaded in LaTeX format from arXiv.

There are 12,288+100 total papers in the train+validation sets,respectively. Furthermore, note each `annotations.json` file either contains (task, dataset, metric, score) annotations for all papers reporting model scores. Otherwise `annotations.json` contains the value "unanswerable." This is for those papers that do not report any model scores and therefore leaderboards cannot be populated from them. Models trained on our dataset should, in a first step, distinguish papers with leaderboards and those without, then for the former set of papers, extract their leaderboard tuples as annotations. The train dataset has 7,936 papers with leaderboard annotations and the remaining 4,352 papers without leaderboard annotations and therefore annotated as "unanswerable." The validation dataset has 51 papers with leaderboard and 49 papers without leaderboard annotations.

Below are provided some detailed statistics relevant to the leaderboard annotations in our dataset offering a glimpse into the corpus. 

### Dataset statistics

| Parameter | train+validation (counts) |
| --- | --- |
| Unique Tasks | 1,372 |
| Unique Datasets | 4,795 |
| Unique Metrics | 2,782 |
| Unique (Task, Dataset, Metric) triples | 11,977 |
| Avg. (Task, Dataset, Metric) triples occurrences per paper | 6.93 |

Ten most common Tasks, Datasets, and Metrics in the **Train+Validation set**:
<table>
  <tr>
    <td> <b>#</b> </td>
    <td colspan="2"><b>Most Common Tasks</b></td>
    <td colspan="2"><b>Most Common Dataset</b></td>
    <td colspan="2"><b>Most Common Metric</b></td>
  </tr>
  <tr>
    <td>  </td>
    <td><b>Task</b></td>
    <td><b>Frequency</b></td>
    <td><b>Dataset</b></td>
    <td><b>Frequency</b></td>
    <td><b>Metric</b></td>
    <td><b>Frequency</b></td>
  </tr>
  <tr>
		<td>1</td>
		<td>image classification</td>
		<td>2273</td>
		<td>imagenet</td>
		<td>1603</td>
		<td>accuracy</td>
		<td>4383</td>
	</tr>
	<tr>
		<td>2</td>
		<td>atari games</td>
		<td>1448</td>
		<td>coco test-dev</td>
		<td>792</td>
		<td>score</td>
		<td>1515</td>
	</tr>
	<tr>
		<td>3</td>
		<td>node classification</td>
		<td>1113</td>
		<td>human3.6m</td>
		<td>624</td>
		<td>f1</td>
		<td>1384</td>
	</tr>
	<tr>
		<td>4</td>
		<td>object detection</td>
		<td>1001</td>
		<td>cifar-10</td>
		<td>585</td>
		<td>psnr</td>
		<td>1144</td>
	</tr>
	<tr>
		<td>5</td>
		<td>video retrieval</td>
		<td>997</td>
		<td>coco minival</td>
		<td>310</td>
		<td>map</td>
		<td>1068</td>
	</tr>
	<tr>
		<td>6</td>
		<td>link prediction</td>
		<td>941</td>
		<td>youtube-vos 2018</td>
		<td>295</td>
		<td>miou</td>
		<td>862</td>
	</tr>
	<tr>
		<td>7</td>
		<td>semantic segmentation</td>
		<td>901</td>
		<td>cifar-100</td>
		<td>252</td>
		<td>ssim</td>
		<td>799</td>
	</tr>
	<tr>
		<td>8</td>
		<td>semi-supervised video object segmentation</td>
		<td>890</td>
		<td>msr-vtt-1ka</td>
		<td>247</td>
		<td>top 1 accuracy</td>
		<td>789</td>
	</tr>
	<tr>
		<td>9</td>
		<td>3d human pose estimation</td>
		<td>889</td>
		<td>fb15k-237</td>
		<td>244</td>
		<td>1:1 accuracy</td>
		<td>787</td>
	</tr>
	<tr>
		<td>10</td>
		<td>question answering</td>
		<td>866</td>
		<td>msu super-resolution for video compression</td>
		<td>225</td>
		<td>number of params</td>
		<td>759</td>
	</tr>
</table>

Ten most common (Task, Dataset, Metric) triples in Train+Validation Set:

| (Task, Dataset, Metric) | Count |
| --- | --- |
| (image classification, imagenet, top 1 accuracy) | 524 |
| (image classification, imagenet, number of params) | 313 |
| (image classification, imagenet, gflops) | 256 |
| (3d human pose estimation, human3.6m, average mpj...) | 197 |
| (image classification, cifar-10, percentage correct) | 128 |
| (action classification, kinetics-400, acc@1) | 108 |
| (object detection, coco test-dev, box map) | 106 |
| (image classification, cifar-100, percentage correct) | 105 |
| (semantic segmentation, ade20k, validation miou) | 92 |
| (neural architecture search, imagenet, top-1 erro...) | 83 |

Since each paper is accompanied with an annotations file, this section concludes with statistics for each of the four types in the tuple, what proportion of those can actually be found in the accompanying full-text.

- for Tasks, 60.24% of the annotation labels can be found in the accompanying paper full-text.
- for Datasets, 45.48% of the annotation labels can be found in the accompanying paper full-text.
- for Metrics, 42.69% of the annotation labels can be found in the accompanying paper full-text.
- for Scores, 58.86% of the annotations can be found in the accompanying paper full-text.

<!--
### Rough Timeline:

September 5, 2023 - first version training dataset public release and test dataset private release
-->

### License

Shield: [![CC BY-SA 4.0][cc-by-sa-shield]][cc-by-sa]

This work is licensed under a
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg

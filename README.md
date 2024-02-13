<!--## SOTA? Tracking the State-of-the-Art Empirical Artificial Intelligence Research

The central activity around empirical AI research includes automated tasks defined via a task dataset for which machine learning models are developed whose performance can be evaluated by a standard set of evaluation metrics. Pushing the state-of-the-art boundaries in empirical AI research means optimizing the models developed for the tasks in terms of speed, accuracy, or storage. As such researchers in this domain often seem to ask the central question “What’s the state-of-the-art result for task XYZ right now?” 


Instead of seeking out the answer buried in the ranked list of documents via a search query made on traditional search engines, researchers instead look for the answer on community-curated leaderboards such as https://paperswithcode.com/ or https://orkg.org/benchmarks. These leaderboards are websites specifically designed to showcase the performance of all introduced machine learning models on a machine learning task dataset. As such researchers seeking to find out the best model performance on a task dataset can easily obtain this information on these websites via their performance trendline overviews showcasing various model performances over a task dataset over time.


In this Shared Task, we hope to go beyond the community curation of leaderboards and instead  realize the vision of obtaining the most efficient machine learning model capable of automatically detecting leaderboards. The efficiency of the submitted machine learning models as a solution to the shared task will be tested based on speed, model parameters, and leaderboard detection F1 measure.-->


### What this repository contains?
 
The repository is organized as follows:

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
```
<!--     |--- [test1-few-shot]/		# hidden
	     |--- [article-counter-folder]/
		 |    |--- [article-id].tei.xml
		 |    |--- annotations.txt		# hidden
		 |    |--- code-link.txt	   # optional	
	     |___ ...
     |--- [test2-zero-shot]/		# hidden			
			 |--- [article-counter-folder]/
			 |    |--- [article-id].tei.xml
			 |    |--- annotations.txt		# hidden
			 |    |--- code-link.txt		   # optional	 
			 |___ ...-->

The dataset dump originates from [paperswithcode.com](https://paperswithcode.com/).

Each folder in the respective dump corresponds to a scholarly article
originally downloaded in LaTeX format from arXiv.

<!--
Of the 5207 papers in the train set, only 625 papers reported their code links as a mention within the paper's text. Similarly, of the 2242 papers in the test set, only 215 papers reported their code links as a mention within the paper's text. Whereever found, for the two repositories respectively, the code link annotations are included in the file `code-link.txt`.
-->

There are 9,352+100 total papers in the train+validation sets,respectively. Furthermore, note each `annotations.json` file either contains (task, dataset, metric, score) annotations for all papers reporting model scores. Otherwise `annotations.json` contains the value "unanswerable." This is for those papers that do not report any model scores and therefore leaderboards cannot be populated from them. Models trained on our dataset should, in a first step, distinguish papers with leaderboards and those without, then for the former set of papers, extract their leaderboard tuples as annotations. The train dataset has 5,274 papers with leaderboard annotations and the remaining 4,078 papers without leaderboard annotations and therefore annotated as "unasnwerable." The validation dataset has 50 papers with leaderboard and 50 papers without leaderboard annotations.

Below are provided some detailed statistics relevant to the leaderboard annotations in our dataset offering a glimpse into the corpus. 

### Dataset statistics

| Parameter | train+validation (counts) |
| --- | --- |
| Unique Tasks | 1,171 |
| Unique Datasets | 3,759 |
| Unique Metrics | 2,259 |
| Unique (Task, Dataset, Metric) triples | 8,723 |
| Avg. (Task, Dataset, Metric) triples occurrences per paper | 5.47 |

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
		<td>atari games</td>
		<td>1196</td>
		<td>coco test-dev</td>
		<td>476</td>
		<td>accuracy</td>
		<td>2521</td>
	</tr>
	<tr>
		<td>2</td>
		<td>image classification</td>
		<td>786</td>
		<td>imagenet</td>
		<td>466</td>
		<td>score</td>
		<td>1258</td>
	</tr>
	<tr>
		<td>3</td>
		<td>link prediction</td>
		<td>716</td>
		<td>cifar-10</td>
		<td>328</td>
		<td>f1</td>
		<td>1061</td>
	</tr>
	<tr>
		<td>4</td>
		<td>object detection</td>
		<td>610</td>
		<td>chebi-20</td>
		<td>205</td>
		<td>psnr</td>
		<td>516</td>
	</tr>
	<tr>
		<td>5</td>
		<td>image super-resolution</td>
		<td>610</td>
		<td>chebi-20</td>
		<td>205</td>
		<td>psnr</td>
		<td>516</td>
	</tr>
	<tr>
		<td>6</td>
		<td>question answering</td>
		<td>450</td>
		<td>human3.6m</td>
		<td>196</td>
		<td>ssim</td>
		<td>387</td>
	</tr>
	<tr>
		<td>7</td>
		<td>semantic segmentation</td>
		<td>427</td>
		<td>fb15k-237</td>
		<td>193</td>
		<td>ap</td>
		<td>367</td>
	</tr>
	<tr>
		<td>8</td>
		<td>neural architecture search</td>
		<td>399</td>
		<td>iconqa</td>
		<td>188</td>
		<td>fid</td>
		<td>346</td>
	</tr>
	<tr>
		<td>9</td>
		<td>visual question answering (vqa)</td>
		<td>397</td>
		<td>wn18rr</td>
		<td>161</td>
		<td>miou</td>
		<td>325</td>
	</tr>
	<tr>
		<td>10</td>
		<td>node classification</td>
		<td>387</td>
		<td>snli</td>
		<td>143</td>
		<td>mae</td>
		<td>276</td>
	</tr>
</table>

Ten most common (Task, Dataset, Metric) triples in Train+Validation Set:

| (Task, Dataset, Metric) | Count |
| --- | --- |
| (image classification, imagenet, top 1 accuracy) | 146 |
| (image classification, cifar-10, percentage correct) | 81 |
| (image classification, cifar-100, percentage correct) | 70 |
| (visual reasoning, winoground, text score) | 68 |
| (visual reasoning, winoground, image score) | 68 |
| (object detection, coco test-dev, box map) | 64 |
| (3d human pose estimation, human3.6m, average mpj...) | 64 |
| (neural architecture search, imagenet, top-1 error) | 134 |
| (visual reasoning, winoground, group score) | 60 |
| (natural language inference, snli, % test accuracy) | 51 |

Since each paper is accompanied with an annotations file, this section concludes with statistics for each of the four types in the tuple, what proportion of those can actually be found in the accompanying full-text.

- for Tasks, 63,53% of the annotation labels can be found in the accompanying paper full-text.
- for Datasets, 47,32% of the annotation labels can be found in the accompanying paper full-text.
- for Metrics, 48.4% of the annotation labels can be found in the accompanying paper full-text.
- for Scores, 67.95% of the annotations can be found in the accompanying paper full-text.

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

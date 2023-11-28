<!--## SOTA? Tracking the State-of-the-Art Empirical Artificial Intelligence Research

The central activity around empirical AI research includes automated tasks defined via a task dataset for which machine learning models are developed whose performance can be evaluated by a standard set of evaluation metrics. Pushing the state-of-the-art boundaries in empirical AI research means optimizing the models developed for the tasks in terms of speed, accuracy, or storage. As such researchers in this domain often seem to ask the central question “What’s the state-of-the-art result for task XYZ right now?” 


Instead of seeking out the answer buried in the ranked list of documents via a search query made on traditional search engines, researchers instead look for the answer on community-curated leaderboards such as https://paperswithcode.com/ or https://orkg.org/benchmarks. These leaderboards are websites specifically designed to showcase the performance of all introduced machine learning models on a machine learning task dataset. As such researchers seeking to find out the best model performance on a task dataset can easily obtain this information on these websites via their performance trendline overviews showcasing various model performances over a task dataset over time.


In this Shared Task, we hope to go beyond the community curation of leaderboards and instead  realize the vision of obtaining the most efficient machine learning model capable of automatically detecting leaderboards. The efficiency of the submitted machine learning models as a solution to the shared task will be tested based on speed, model parameters, and leaderboard detection F1 measure.-->


### What this repository contains?
 
The repository is organized as follows:

```
[dataset]/	
     |--- [train]/
	     |--- [article-counter-folder]/
		 |    |--- [article-id].tei.xml
		 |    |--- annotations.txt
		 |    |--- code-link.txt	  # optional	
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

The `code-link.txt` file is optional and if a code link was found in the paper, this annotation file is created; if not, it is not part of the folder. The SOTA shared task does not use the code link annotations in its evaluations.

The dataset dump originates from [paperswithcode.com](https://paperswithcode.com/).

Each folder in the respective dump corresponds to a scholarly article
originally downloaded in `pdf` format from arXiv, whose contents were then
scrapped as `txt` data encoded in the [TEI](https://en.wikipedia.org/wiki/Text_Encoding_Initiative) XML format.

<!--
Of the 5207 papers in the train set, only 625 papers reported their code links as a mention within the paper's text. Similarly, of the 2242 papers in the test set, only 215 papers reported their code links as a mention within the paper's text. Whereever found, for the two repositories respectively, the code link annotations are included in the file `code-link.txt`.
-->

There are 5,207 papers with leaderboard annotations in the train set.

### Dataset statistics

| Parameter | Train (counts) |
| --- | --- |
| Unique Tasks | 825 |
| Unique Datasets | 2,979 |
| Unique Metrics | 1,434 |
| Unique (Task, Dataset, Metric) triples | 6,805 |
| Avg. (Task, Dataset, Metric) triples occurrences per paper | 6.59 |

Ten most common Tasks, Datasets, and Metrics in the **Train set**:
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
		<td>Atari Games</td>
		<td>2089</td>
		<td>COCO test-dev</td>
		<td>1408</td>
		<td>Accuracy</td>
		<td>3771</td>
	</tr>
	<tr>
		<td>2</td>
		<td>Image Classification</td>
		<td>1813</td>
		<td>ImageNet</td>
		<td>1264</td>
		<td>Score</td>
		<td>2146</td>
	</tr>
	<tr>
		<td>3</td>
		<td>Object Detection</td>
		<td>1550</td>
		<td>COCO minival</td>
		<td>641</td>
		<td>F1</td>
		<td>1055</td>
	</tr>
	<tr>
		<td>4</td>
		<td>Image Super-Resolution</td>
		<td>924</td>
		<td>CIFAR-10</td>
		<td>561</td>
		<td>PSNR</td>
		<td>981</td>
	</tr>
	<tr>
		<td>5</td>
		<td>Link Prediction</td>
		<td>840</td>
		<td>Human3.6M</td>
		<td>333</td>
		<td>Top 1 Accuracy</td>
		<td>655</td>
	</tr>
	<tr>
		<td>6</td>
		<td>Node Classification</td>
		<td>567</td>
		<td>DAVIS 2016</td>
		<td>305</td>
		<td>SSIM</td>
		<td>629</td>
	</tr>
	<tr>
		<td>7</td>
		<td>Few-Shot Image Classification</td>
		<td>562</td>
		<td>CIFAR-100</td>
		<td>246</td>
		<td>AP</td>
		<td>474</td>
	</tr>
	<tr>
		<td>8</td>
		<td>Neural Architecture Search</td>
		<td>562</td>
		<td>FB15k-237</td>
		<td>220</td>
		<td>FID</td>
		<td>413</td>
	</tr>
	<tr>
		<td>9</td>
		<td>Question Answering</td>
		<td>562</td>
		<td>DAVIS 2017 (val)</td>
		<td>219</td>
		<td>MAP</td>
		<td>402</td>
	</tr>
	<tr>
		<td>10</td>
		<td>Semi-Supervised Video Object Segmentation</td>
		<td>556</td>
		<td>WN18RR</td>
		<td>204</td>
		<td>mIoU</td>
		<td>401</td>
	</tr>
</table>

Ten most common (Task, Dataset, Metric) triples in Train Set:

| (Task, Dataset, Metric) | Count |
| --- | --- |
| (Image Classification, ImageNet, Top 1 Accuracy) | 425 |
| (Image Classification, ImageNet, Number of params) | 243 |
| (Image Classification, ImageNet, Top 5 Accuracy) | 200 |
| (Object Detection, COCO test-dev, box AP) | 178 |
| (Image Classification, CIFAR-10, Percentage correct) | 166 |
| (Object Detection, COCO test-dev, AP50) | 137 |
| (Image Classification, CIFAR-100, Percentage correct) | 137 |
| (Object Detection, COCO test-dev, AP75) | 134 |
| (Object Detection, COCO test-dev, APM) | 134 |
| (Object Detection, COCO test-dev, APS) | 133 |

Since each paper is accompanied with an annotations file, this section concludesby discussing for which proportion of the papers can the annotations actually be found in the paper full-text.

- for Tasks, 75.86% of the annotation labels can be found in the accompanying paper full-text.
- for Datasets, 44.52% of the annotation labels can be found in the accompanying paper full-text.
- for Metrics, 47.8% of the annotation labels can be found in the accompanying paper full-text.
- for Scores, 49.51% of the annotations can be found in the accompanying paper full-text.

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

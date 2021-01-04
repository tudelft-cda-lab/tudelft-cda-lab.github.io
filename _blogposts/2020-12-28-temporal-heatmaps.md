---
layout: blogpost
title: Temporal Heatmaps for Visualizing Sequential Features
author: Azqa Nadeem
feature_image: "https://picsum.photos/2560/600?image=872"
excerpt: In this article, we show how to visualize sequential data with Temporal Heatmaps, using examples of analyzing malware and IoT device behavior. You can access code snippets...
date: 2020-12-28
---

In this article, we show how to visualize sequential data with _Temporal_ _Heatmaps_, using examples of analyzing malware and IoT device behavior. You can access code snippets from this [Jupyter notebook](https://github.com/tudelft-cda-lab/tudelft-cda-lab.github.io/blob/master/assets/blog-code/temporal-heatmap/Temporal-heatmaps-demo.ipynb).

## Sequence data
Sequences are everywhere, and it is easy to see why: time is continuous, so why not the data that models behavior? This sequence data can be anything, ranging from speedometer measurements for a car, to packet sizes transferred over a network. 
This type of data is used regularly in many fields, e.g. to perform 
[anomaly detection](https://ieeexplore.ieee.org/abstract/document/5687485?casa_token=hVcfR4TigS0AAAAA:AtZ_IXMnVu3Gz_Rj59Y5V69mivoM0SRNwo8ACKll0Tk094i-KawjwJHgPlGNkBdBMfWzDNOQ_A) in cybersecurity, 
[gesture recognition](https://www.researchgate.net/publication/228740947_Multi-dimensional_dynamic_time_warping_for_gesture_recognition) in computer vision, 
and [DNA sequencing](https://www.future-science.com/doi/full/10.2144/000112499) in bio-informatics.

A common problem that we have to deal with when handling sequences is: how to measure the similarity between them? Let us consider a use-case:

### Clustering Sequences

Suppose we are given a bunch of sequences that have to be grouped based on similarities. How would we determine which of the sequences are alike?

For the sake of this article, let us suppose that the sequences are sine curves with varying noise, phase and frequency. 

<figure>
<div class="row">
  <div class="column-3">
    <img src="../../assets/blog-img/temporal-heatmap/seq-class-0.png" alt="Class=1" style="width:100%">
  </div>
  <div class="column-3">
    <img src="../../assets/blog-img/temporal-heatmap/seq-class-1.png" alt="Class=2" style="width:100%">
  </div>
  <div class="column-3">
    <img src="../../assets/blog-img/temporal-heatmap/seq-class-2.png" alt="Class=3" style="width:100%">
  </div>
</div>
<figcaption>Fig 1. The Sine Curve dataset: Three classes of sine curves with varying noise, phase and frequency. </figcaption>
  </figure>

A Jupyter notebook with the code snippets can be found [here](https://github.com/tudelft-cda-lab/tudelft-cda-lab.github.io/blob/master/assets/blog-code/temporal-heatmap/Temporal-heatmaps-demo.ipynb).

Using machine learning, clustering may be one way to approach this problem. An important question arises: how would we encode the sequences as input features?

If we were to collapse the sequences into aggregates, such as mean and standard deviation, there is a chance that we mistakenly consider two sequences as similar (due to similar aggregates) that were temporally different. Fig. 2 shows one such example, where the sequences have identical mean, standard deviation, minima and maxima, yet they are temporally different.

<figure>
  <img src="../../assets/blog-img/temporal-heatmap/same-stat-diff-seq.PNG"
    alt="">
    <figcaption>Fig 2. Two different sequences, both having Mean= 2.1, Median= 2, Std. dev= 0.83, and Variance= 0.69. </figcaption>
</figure>

The other option is to use the sequences themselves as features. We can employ sequential machine learning: after computing pairwise distances between sequences using a distance measure, such as [Dynamic Time Warping](https://towardsdatascience.com/an-illustrative-introduction-to-dynamic-time-warping-36aa98513b98) or [Frechet distance](https://medium.com/tblx-insider/how-long-should-your-dog-leash-be-ba5a4e6891fc), we can use any [traditional clustering algorithm](https://hdbscan.readthedocs.io/en/latest/comparing_clustering_algorithms.html) to group similar sequences together.

<hr/>
## Visual analysis of clusters

Now for the big question: after the clustering is complete, how do we measure the degree of cluster homogeneity -- how similar the sequences are within each cluster?

Since each observation inside the clusters is a sequence, typical [numeric measures](https://cran.r-project.org/web/packages/clusterCrit/vignettes/clusterCrit.pdf) based on cohesion and separation are not very meaningful. Performing dimensionality reduction in order to plot the 2D projection of the data using [Principle Component Analysis](https://towardsdatascience.com/a-one-stop-shop-for-principal-component-analysis-5582fb7e0a9c) or [TSNE](https://lvdmaaten.github.io/tsne/) is a good option, but is not without its limitations.

<figure>
  <img class=scaled src="../../assets/blog-img/temporal-heatmap/clus.png"
    alt="">
    <figcaption>Fig 3. TSNE plot of input sequences (sine curves). Each point is a 2D projection of an input sequence. The color denotes class. </figcaption>
</figure>

Fig. 3 shows the TSNE plot of the Sine Curve dataset. Each point in this plot is a 2D projection of the input sequence. The data seems very well-separated in three classes.
A TSNE plot shows an approximation of the data in a lower dimensionality, whereby the points close to each other are _approximately_ similar to one another.

Indeed, dimensionality reduction gives one way to visualize sequence data, but it is only just an estimate. In the absence of ground truth, the TSNE plot cannot tell whether any clustering mistakes have been made, which is a huge problem. For this reason, it is important to view the cluster content and verify cluster quality. To this end, we use a modified variant of heatmaps, which we call _Temporal heatmaps_.

Each cluster gets its own temporal heatmap. In a temporal heatmap, each row represents a feature sequence. The longer the sequences, the wider the heatmap becomes. The key idea behind temporal heatmaps is to utilize the natural tendency of humans to detect visual patterns, also known as [Pareidolia](https://www.bbc.com/future/article/20140730-why-do-we-see-faces-in-objects), to our benefit. This allows to clearly see regions of similarity in sequences.

<figure>
  <img class=scaled src="../../assets/blog-img/temporal-heatmap/example-heatmap.png"
    alt="">
    <figcaption>Fig 4. Example temporal heatmap: Each row is a sequence; each sequence has 100 observations. </figcaption>
</figure>

Fig. 4 shows an example of a temporal heatmap. It shows 10 sequences taken at random from one of the Sine Curve dataset classes. These sequences are all very similar with slight delays, which appear as rough vertical patterns.

What kind of patterns to look for in temporal heatmaps, is an important question. In general, vertical patterns in a heatmap indicate correct clustering.
Below, we discuss the different type of clusters that one may encounter when working with temporal heatmaps. As we will see, measuring cluster quality is a subjective operation.


### i) A cluster with identical sequences

If the sequences are perfectly aligned, the heatmap contains un-interrupted vertical artefacts. Also, the colors in each vertical pattern are identical. This is the case where all sequences in the cluster are exactly identical -- a perfect cluster. Fig. 5 shows a cluster with 8 identical sequences, generated from the network traffic of an IoT video camera.

<figure>
  <img src="../../assets/blog-img/temporal-heatmap/real-perfect.png" style=" width: 40%;"
    alt="">
    <figcaption>Fig 5. Example of a cluster with identical sequences. </figcaption>
</figure>



### ii) A cluster with misaligned but identical sequences

Misaligned sequences are more common in practice than one might think. The misalignment is one of the reasons why many distance measures fail to work well with sequences. A cluster with misaligned sequences manifests as a vertical pattern with some misaligned cells.

In a dataset where misalignment is the least of the differences, i.e. when behavioral differences are rampant, this type of cluster would be considered good. Fig. 6 shows a cluster containing 2 misaligned sequences resulting from network traffic generated by several IoT devices. We consider this cluster as having _no_ mistakes.

<figure>
  <img src="../../assets/blog-img/temporal-heatmap/real-misaligned.png" style=" width: 40%;"
    alt="">
    <figcaption>Fig 6. Example of a cluster with misaligned sequences (IoT dataset). </figcaption>
</figure>


On the other hand, considering a dataset where misalignment is the only difference, the broken vertical pattern indicates clustering mistakes. Fig. 7 shows a cluster generated by applying [K-means](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html) on the Sine Curve dataset. Out of the 10 sequences in this cluster, 7 belong to the 1st class, 1 belongs to the 2nd class, and 2 belong to the 3rd class. Since the difference in the classes inherently comes from the phase, noise and frequency shift, 3/8 sequences are considered as clustering mistakes.

<figure>
  <img src="../../assets/blog-img/temporal-heatmap/clustering-mistake.png" style=" width: 50%;"
    alt="">
    <figcaption>Fig 7. Clustering mistakes on the Sine Curve dataset. </figcaption>
</figure>


### iii) A cluster with similar sequences

This is the case where the feature values in the sequences have a different range. In real-world data, this is a very common scenario, e.g. when the acceleration of a car changes slightly in each experiment run, it produces sequences that are behaviorally similar, but have different ranges.

A cluster of this type has vertical patterns, but no longer in the same color/shade. Nevertheless, depending on the colormap configuration, the value could appear in the same color. The rows that break the vertical pattern are _potential_ "clustering mistakes" -- if no better placement than the current cluster is found, these rows are deemed as true positives despite the color difference.

Fig. 8 shows a cluster containing network traffic of an IoT device. Out of the 16 sequences in this cluster, 4 are both misaligned, and have value differences that are significant enough to produce a different color. However, similar to the previous case, this difference is _not big enough_ to be considered as a key behavioral difference.

<figure>
  <img src="../../assets/blog-img/temporal-heatmap/real-misaligned-diff.png" style=" width: 40%;"
    alt="">
    <figcaption>Fig 8. Example of a cluster with different and misaligned sequences (IoT dataset).  </figcaption>
</figure>


### iv) A cluster with random sequences

As there are so many types of similarities that can be observed in a temporal heatmap, does it mean that a lack of vertical artefacts indicate a "bad cluster"? In practice, such a random-looking cluster contains left-over sequences that do not naturally belong to any other cluster. For example, when using a clustering algorithm that does not necessarily cluster all data, the left-over noise cluster might fall under this category.

Fig. 9 shows the noise cluster containing 49 sequences from IoT network traffic that do not naturally belong to any other cluster. It is apparent that even this cluster does not look fully random -- a second clustering attempt over these sequences will still produce a few clusters.

<figure>
  <img src="../../assets/blog-img/temporal-heatmap/-1.png" style=" width: 40%;"
    alt="">
    <figcaption>Fig 9. The noise cluster containing left-over sequences from the IoT dataset. </figcaption>
</figure>

For a completely randomized look, we would need sequences that fluctuate a lot. For an analyst, this type of cluster will likely be very interesting, due to its uniqueness. For example, in a dataset composed of network traffic generated by malware, we clustered sequences of port numbers. Fig. 10 shows one of the clusters.

<figure>
  <img src="../../assets/blog-img/temporal-heatmap/portscan2.png" style=" width: 40%;"
    alt="">
    <figcaption>Fig 10. A cluster showing randomized port scan (malware dataset). </figcaption>
</figure>

While it may look like a bad cluster, the sequences in this cluster are worse off if they are placed in any other cluster. Besides, it captures randomized behavior -- this is the case of a randomized port scan, where attackers randomize the range of ports they want to scan as an evasive behavior. Because the randomized behavior is so different from all the other sequences, they get grouped together and are more likely to be checked by an analyst!

### v) A bad cluster

While there are no inherent good or bad clusters, a cluster that contains many clustering mistakes would be considered bad. Fig. 11 shows a cluster where at least 3 distinct behaviors are grouped together. This may be because no other pairing for these sequences exist, or it could be a bad side-effect of computing pair-wise similarity over multiple feature sequences. Either way, we do not want this type of cluster!

<figure>
  <img src="../../assets/blog-img/temporal-heatmap/9.png" style=" width: 40%;"
    alt="">
    <figcaption>Fig 11. Example of a cluster with lots of mistakes (IoT dataset).  </figcaption>
</figure>

<hr/>
## Application

Our project [MalPaCA](https://github.com/tudelft-cda-lab/malpaca-pub) produces temporal heatmaps as one of the clustering artefacts. MalPaCA clusters behaviorally similar network connections in order to discover distinct behaviors present in network traffic. To this end, it uses 4 meta-features, i.e. packet sizes, inter-arrival times, source and destination port numbers. Each cluster is hence represented by 4 temporal heatmaps, one for each feature sequence. For detailed explanation and examples, read the paper [Beyond Labeling: Using Clustering To Build Network Behavioral Profiles Of Malware Families](https://link.springer.com/chapter/10.1007%2F978-3-030-62582-5_15).

<figure>
  <img src="../../assets/blog-img/temporal-heatmap/malpaca-example.png"
    alt="">
    <figcaption>Fig 12. A cluster in four heatmaps: MalPaCA uses 4 sequential features. Heatmaps are generated for each of those features. The highlighted sequence is a clustering mistake. </figcaption>
</figure>

<hr/>
## Analytical Artwork

Did you know that the banner image of our [group's website](https://cyber-analytics.nl/) is adapted from a temporal heatmap capturing a port scan?  Pretty cool, eh?!

Other than the obvious benefit of visualizing sequential data for verifying clustering results and data exploration, we like the temporal heatmaps because each clustering attempt produces fun images. Here are some recent ones generated when clustering network traffic of IoT devices. _Enjoy!_

<figure>
<div class="row">
  <div class="column-3">
    <img src="../../assets/blog-img/temporal-heatmap/ex0.png" alt="" style="width:100%">
  </div>
  <div class="column-3">
    <img src="../../assets/blog-img/temporal-heatmap/ex1.png" alt="" style="width:100%">
  </div>
  <div class="column-3">
    <img src="../../assets/blog-img/temporal-heatmap/ex2.png" alt="" style="width:100%">
  </div>
</div>
  </figure>
    
<figure>
<div class="row">
  <div class="column-3">
    <img src="../../assets/blog-img/temporal-heatmap/ex3.png" alt="" style="width:100%">
  </div>
  <div class="column-3">
    <img src="../../assets/blog-img/temporal-heatmap/ex4.png" alt="" style="width:100%">
  </div>
  <div class="column-3">
    <img src="../../assets/blog-img/temporal-heatmap/ex5.png" alt="" style="width:100%">
  </div>
</div>
  </figure>
      
  <figure>
  <div class="row">
    <div class="column-3">
      <img src="../../assets/blog-img/temporal-heatmap/ex6.png" alt="" style="width:100%">
    </div>
    <div class="column-3">
      <img src="../../assets/blog-img/temporal-heatmap/ex7.png" alt="" style="width:100%">
    </div>
    <div class="column-3">
      <img src="../../assets/blog-img/temporal-heatmap/ex8.png" alt="" style="width:100%">
    </div>
  </div>
    </figure>
	
<hr/>

If you use temporal heatmaps in your research, please consider citing the following reference:

> <a>&#64;incollection</a>{nadeembeyond,
>  title={Beyond Labeling: Using Clustering to Build Network Behavioral Profiles of Malware Families},
>  author={Nadeem, Azqa and Hammerschmidt, Christian and Ga{\~n}{\'a}n, Carlos H and Verwer, Sicco},
>  booktitle={Malware Analysis Using Artificial Intelligence and Deep Learning},
>  pages={381--409},
>  publisher={Springer}
>}

## References
- Nadeem, A., Hammerschmidt, C., Gañán, C. H., & Verwer, S. [Beyond Labeling: Using Clustering to Build Network Behavioral Profiles of Malware Families.](https://link.springer.com/chapter/10.1007%2F978-3-030-62582-5_15) In Malware Analysis Using Artificial Intelligence and Deep Learning (pp. 381-409). Springer, Cham.
- Ten Holt, G. A., Reinders, M. J., & Hendriks, E. A. (2007, June). [Multi-dimensional dynamic time warping for gesture recognition.](https://www.researchgate.net/publication/228740947_Multi-dimensional_dynamic_time_warping_for_gesture_recognition) In Thirteenth annual conference of the Advanced School for Computing and Imaging (Vol. 300, p. 1).
- Platt, A. R., Woodhall, R. W., & George Jr, A. L. (2007). [Improved DNA sequencing quality and efficiency using an optimized fast cycle sequencing protocol.](https://www.future-science.com/doi/full/10.2144/000112499) Biotechniques, 43(1), 58-62.
- Teng, M. (2010, December). [Anomaly detection on time series.](https://ieeexplore.ieee.org/abstract/document/5687485?casa_token=hVcfR4TigS0AAAAA:AtZ_IXMnVu3Gz_Rj59Y5V69mivoM0SRNwo8ACKll0Tk094i-KawjwJHgPlGNkBdBMfWzDNOQ_A) In 2010 IEEE International Conference on Progress in Informatics and Computing (Vol. 1, pp. 603-608). IEEE.

<!--## Is Overfitting Necessary for Implicit Video Representation?-->

<!-- ICML -->
<!--<h4><p style="text-align: center;">The 40th International Conference on Machine Learning (ICML 2023)</p><h4>-->

<!-- authors -->
<!-- Author 1, Author 2, Author 3 (†: \dagger)-->
<h3><p style="text-align: center;">Hee Min Choi<sup>* †</sup> · Hyoa Kang<sup>*</sup> · Dokwan Oh</p></h3>
<br />

<!-- abstract -->
## __Abstract__
Compact representation of multimedia signals using implicit neural representations (INRs) has advanced significantly over the past few years, and recent works address their applications to video. Existing studies on video INR have focused on network architecture design as all video information is contained within network parameters. Here, we propose a new paradigm in efficient INR for videos based on the idea of strong lottery ticket (SLT) hypothesis (Zhou et al., 2019), which demonstrates the possibility of finding an accurate subnetwork mask, called supermask, for a randomly initialized classification network without weight training. Specifically, we train multiple supermasks with a hierarchical structure for a randomly initialized image-wise video representation model without weight updates. Different from a previous approach employing hierarchical supermasks (Okoshi et al., 2022), a trainable scale parameter for each mask is used instead of multiplying by the same fixed scale for all levels. This simple modification widens the parameter search space to sufficiently explore various sparsity patterns, leading the proposed algorithm to find stronger subnetworks. Moreover, extensive experiments on popular UVG benchmark show that random subnetworks obtained from our framework achieve higher reconstruction and visual quality than fully trained models with similar encoding sizes. Our study is the first to demonstrate the existence of SLTs in video INR models and propose an efficient method for finding them.
<br />
<br />

<!-- architecture -->
## __Architecture__
<figure>
<img src="./figures/frameworks.png" alt="Frameworks" s/>
<figcaption>Overview of the proposed video representation framework.</figcaption>
</figure>
<br />
<br />

## __Decoded Images__
### Proposed (learned scales) vs. Trained Dense
<!-- ![](images/Bosphorus_0_GT.png)
![](images/Bosphorus_0_GLW_save.png)
![](images/Bosphorus_0_NeRV_dense_save.png)
![](images/HoneyBee_572_GT.png)
![](images/HoneyBee_572_GLW_save.png)
![](images/HoneyBee_572_NeRV_dense_save.png) -->
<!-- | Ground Truth                    | Proposed (learned scales), BPP=0.060  | Trained Dense, BPP=0.064                     |
|---------------------------------|---------------------------------------|----------------------------------------------|
| ![](images/Bosphorus_0_GT.png)  | ![](images/Bosphorus_0_GLW_save.png)  | ![](images/Bosphorus_0_NeRV_dense_save.png)  |
| ![](images/HoneyBee_572_GT.png) | ![](images/HoneyBee_572_GLW_save.png) | ![](images/HoneyBee_572_NeRV_dense_save.png) | -->
<table>
    <tr>
        <td style="text-align: center">Ground Truth</td>
        <td style="text-align: center">Proposed (learned scales), BPP=0.060</td>
        <td style="text-align: center">Trained Dense, BPP=0.064</td>
    </tr>
    <tr>
        <td style="text-align: center"><img src="images/Bosphorus_0_GT.png"></td>
        <td style="text-align: center"><img src="images/Bosphorus_0_GLW_save.png"></td>
        <td style="text-align: center"><img src="images/Bosphorus_0_NeRV_dense_save.png"></td>
    </tr>
    <tr>
        <td style="text-align: center"><img src="images/HoneyBee_572_GT.png"></td>
        <td style="text-align: center"><img src="images/HoneyBee_572_GLW_save.png"></td>
        <td style="text-align: center"><img src="images/HoneyBee_572_NeRV_dense_save.png"></td>
    </tr>
</table>
<br />

### Proposed (learned scales) vs. Trained Sparse
<!-- ![](images/Beauty_599_GT.png)
![](images/Beauty_599_GLW_save.png)
![](images/Beauty_599_NeRV_sparse_save.png)
![](images/YachtRide_0_GT.png)
![](images/YachtRide_0_GLW_save.png)
![](images/YachtRide_0_NeRV_sparse_save.png) -->
<!-- | Ground Truth                   | Proposed (learned scales), BPP=0.060 | Trained Sparse, BPP=0.076                    |
|--------------------------------|--------------------------------------|----------------------------------------------|
| ![](images/Beauty_599_GT.png)  | ![](images/Beauty_599_GLW_save.png)  | ![](images/Beauty_599_NeRV_sparse_save.png)  |
| ![](images/YachtRide_0_GT.png) | ![](images/YachtRide_0_GLW_save.png) | ![](images/YachtRide_0_NeRV_sparse_save.png) | -->
<table>
    <tr>
        <td style="text-align: center">Ground Truth</td>
        <td style="text-align: center">Proposed (learned scales), BPP=0.060</td>
        <td style="text-align: center">Trained Sparse, BPP=0.076</td>
    </tr>
    <tr>
        <td style="text-align: center"><img src="images/Beauty_599_GT.png"></td>
        <td style="text-align: center"><img src="images/Beauty_599_GLW_save.png"></td>
        <td style="text-align: center"><img src="images/Beauty_599_NeRV_sparse_save.png"></td>
    </tr>
    <tr>
        <td style="text-align: center"><img src="images/YachtRide_0_GT.png"></td>
        <td style="text-align: center"><img src="images/YachtRide_0_GLW_save.png"></td>
        <td style="text-align: center"><img src="images/YachtRide_0_NeRV_sparse_save.png"></td>
    </tr>
</table>
<br />

### Proposed (learned scales) vs. Proposed (fixed scales)
<!-- ![](images/Jockey_300_GT.png)
![](images/Jockey_300_GLW_save.png)
![](images/Jockey_300_MW_save.png)
![](images/ReadySteadyGo_100_GT.png)
![](images/ReadySteadyGo_100_GLW_save.png)
![](images/ReadySteadyGo_100_MW_save.png) -->
<!-- | Ground Truth                         | Proposed (learned scales), BPP=0.060       | Proposed (fixed scales), BPP=0.060        |
|--------------------------------------|--------------------------------------------|-------------------------------------------|
| ![](images/Jockey_300_GT.png)        | ![](images/Jockey_300_GLW_save.png)        | ![](images/Jockey_300_MW_save.png)        |
| ![](images/ReadySteadyGo_100_GT.png) | ![](images/ReadySteadyGo_100_GLW_save.png) | ![](images/ReadySteadyGo_100_MW_save.png) | -->
<table>
    <tr>
        <td style="text-align: center">Ground Truth</td>
        <td style="text-align: center">Proposed (learned scales), BPP=0.060</td>
        <td style="text-align: center">Proposed (fixed scales), BPP=0.060</td>
    </tr>
    <tr>
        <td style="text-align: center"><img src="images/Jockey_300_GT.png"></td>
        <td style="text-align: center"><img src="images/Jockey_300_GLW_save.png"></td>
        <td style="text-align: center"><img src="images/Jockey_300_MW_save.png"></td>
    </tr>
    <tr>
        <td style="text-align: center"><img src="images/ReadySteadyGo_100_GT.png"></td>
        <td style="text-align: center"><img src="images/ReadySteadyGo_100_GLW_save.png"></td>
        <td style="text-align: center"><img src="images/ReadySteadyGo_100_MW_save.png"></td>
    </tr>
</table>
<br />
<br />

## __FLIP Visualization__
We further provide [FLIP maps](https://dl.acm.org/doi/10.1145/3406183) for the decoded images. FLIP generates a map of approximating errors recognized by humans when alternating between two images. In FLIP maps, bright color corresponds to large error and dark to small error, and smaller FLIP value is better. We find that at low BPP settings (BPP < 0.1), the proposed method better encodes small objects in large area having repeated patterns compared with three baseline methods.

### Proposed (learned scales) vs. Trained Dense
#### Bosphorus
<!-- |                    | Proposed (learned scales), BPP=0.060   | Trained Dense, BPP=0.064 |
|:------------------:| :------------------------------------: | :--------------------------------: |
| FLIP               | ![](images/flip.Bosphorus_0_GT.Bosphorus_0_GLW_save.67ppd.ldr.png) </br> FLIP=0.1258 | ![](images/flip.Bosphorus_0_GT.Bosphorus_0_NeRV_dense_save.67ppd.ldr.png) </br> FLIP=0.1613 |
| Decoded</br> Image | ![](images/Bosphorus_0_GLW_save.png)     | ![](images/Bosphorus_0_NeRV_dense_save.png) | -->
<table>
    <tr>
        <td style="text-align: center"></td>
        <td style="text-align: center">Proposed (learned scales), BPP=0.060</td>
        <td style="text-align: center">Trained Dense, BPP=0.064</td>
    </tr>
    <tr>
        <td style="text-align: center">FLIP</td>
        <td style="text-align: center"><img src="images/flip.Bosphorus_0_GT.Bosphorus_0_GLW_save.67ppd.ldr.png"><br />FLIP=0.1258</td>
        <td style="text-align: center"><img src="images/flip.Bosphorus_0_GT.Bosphorus_0_NeRV_dense_save.67ppd.ldr.png"><br />FLIP=0.1613</td>
    </tr>
    <tr>
        <td style="text-align: center">Decoded<br />Image</td>
        <td style="text-align: center"><img src="images/Bosphorus_0_GLW_save.png"></td>
        <td style="text-align: center"><img src="images/Bosphorus_0_NeRV_dense_save.png"></td>
    </tr>
</table>
<br />

#### HoneyBee
<!-- |                    | Proposed (learned scales), BPP=0.060   | Trained Dense, BPP=0.064 |
|:------------------:| :------------------------------------: | :--------------------------------: |
| FLIP               | ![](images/flip.HoneyBee_572_GT.HoneyBee_572_GLW_save.67ppd.ldr.png) </br> FLIP=0.0532 | ![](images/flip.HoneyBee_572_GT.HoneyBee_572_NeRV_dense_save.67ppd.ldr.png) </br> FLIP=0.0534 |
| Decoded</br> Image | ![](images/HoneyBee_572_GLW_save.png) | ![](images/HoneyBee_572_NeRV_dense_save.png) | -->
<table>
    <tr>
        <td style="text-align: center"></td>
        <td style="text-align: center">Proposed (learned scales), BPP=0.060</td>
        <td style="text-align: center">Trained Dense, BPP=0.064</td>
    </tr>
    <tr>
        <td style="text-align: center">FLIP</td>
        <td style="text-align: center"><img src="images/flip.HoneyBee_572_GT.HoneyBee_572_GLW_save.67ppd.ldr.png"><br />FLIP=0.0532</td>
        <td style="text-align: center"><img src="images/flip.HoneyBee_572_GT.HoneyBee_572_NeRV_dense_save.67ppd.ldr.png"><br />FLIP=0.0534</td>
    </tr>
    <tr>
        <td style="text-align: center">Decoded<br />Image</td>
        <td style="text-align: center"><img src="images/HoneyBee_572_GLW_save.png"></td>
        <td style="text-align: center"><img src="images/HoneyBee_572_NeRV_dense_save.png"></td>
    </tr>
</table>
<br />

### Proposed (learned scales) vs. Trained Sparse
#### Beauty
<!-- |                    | Proposed (learned scales), BPP=0.060   | Trained Sparse, BPP=0.076 |
|:------------------:| :------------------------------------: | :--------------------------------: |
| FLIP               | ![](images/flip.Beauty_599_GT.Beauty_599_GLW_save.67ppd.ldr.png) </br> FLIP=0.0702 | ![](images/flip.Beauty_599_GT.Beauty_599_NeRV_sparse_save.67ppd.ldr.png) </br> FLIP=0.0768 |
| Decoded</br> Image | ![](images/Beauty_599_GLW_save.png)      | ![](images/Beauty_599_NeRV_sparse_save.png) | -->
<table>
    <tr>
        <td style="text-align: center"></td>
        <td style="text-align: center">Proposed (learned scales), BPP=0.060</td>
        <td style="text-align: center">Trained Sparse, BPP=0.076</td>
    </tr>
    <tr>
        <td style="text-align: center">FLIP</td>
        <td style="text-align: center"><img src="images/flip.Beauty_599_GT.Beauty_599_GLW_save.67ppd.ldr.png"><br />FLIP=0.0702</td>
        <td style="text-align: center"><img src="images/flip.Beauty_599_GT.Beauty_599_NeRV_sparse_save.67ppd.ldr.png"><br />FLIP=0.0768</td>
    </tr>
    <tr>
        <td style="text-align: center">Decoded<br />Image</td>
        <td style="text-align: center"><img src="images/Beauty_599_GLW_save.png"></td>
        <td style="text-align: center"><img src="images/Beauty_599_NeRV_sparse_save.png"></td>
    </tr>
</table>
<br />

#### YachtRide
<!-- |                    | Proposed (learned scales), BPP=0.060   | Trained Sparse, BPP=0.076 |
|:------------------:| :------------------------------------: | :--------------------------------: |
| FLIP               | ![](images/flip.YachtRide_0_GT.YachtRide_0_GLW_save.67ppd.ldr.png) </br> FLIP=0.1258 | ![](images/flip.YachtRide_0_GT.YachtRide_0_NeRV_sparse_save.67ppd.ldr.png) </br> FLIP=0.1499 |
| Decoded</br> Image | ![](images/YachtRide_0_GLW_save.png)     | ![](images/YachtRide_0_NeRV_sparse_save.png) | -->
<table>
    <tr>
        <td style="text-align: center"></td>
        <td style="text-align: center">Proposed (learned scales), BPP=0.060</td>
        <td style="text-align: center">Trained Sparse, BPP=0.076</td>
    </tr>
    <tr>
        <td style="text-align: center">FLIP</td>
        <td style="text-align: center"><img src="images/flip.YachtRide_0_GT.YachtRide_0_GLW_save.67ppd.ldr.png"><br />FLIP=0.1258</td>
        <td style="text-align: center"><img src="images/flip.YachtRide_0_GT.YachtRide_0_NeRV_sparse_save.67ppd.ldr.png"><br />FLIP=0.1499</td>
    </tr>
    <tr>
        <td style="text-align: center">Decoded<br />Image</td>
        <td style="text-align: center"><img src="images/YachtRide_0_GLW_save.png"></td>
        <td style="text-align: center"><img src="images/YachtRide_0_NeRV_sparse_save.png"></td>
    </tr>
</table>
<br />

### Proposed (learned scales) vs. Proposed (fixed scales)
#### Jockey
<!-- |                    | Proposed (learned scales), BPP=0.060   | Proposed (fixed scales), BPP=0.060 |
|:------------------:| :------------------------------------: | :--------------------------------: |
| FLIP               | ![](images/flip.Jockey_300_GT.Jockey_300_GLW_save.67ppd.ldr.png) </br> FLIP=0.1401 | ![](images/flip.Jockey_300_GT.Jockey_300_MW_save.67ppd.ldr.png) </br> FLIP=0.1466 |
| Decoded</br> Image | ![](images/Jockey_300_GLW_save.png)      | ![](images/Jockey_300_MW_save.png)   | -->
<table>
    <tr>
        <td style="text-align: center"></td>
        <td style="text-align: center">Proposed (learned scales), BPP=0.060</td>
        <td style="text-align: center">Proposed (fixed scales), BPP=0.060</td>
    </tr>
    <tr>
        <td style="text-align: center">FLIP</td>
        <td style="text-align: center"><img src="images/flip.Jockey_300_GT.Jockey_300_GLW_save.67ppd.ldr.png"><br />FLIP=0.1401</td>
        <td style="text-align: center"><img src="images/flip.Jockey_300_GT.Jockey_300_MW_save.67ppd.ldr.png"><br />FLIP=0.1466</td>
    </tr>
    <tr>
        <td style="text-align: center">Decoded<br />Image</td>
        <td style="text-align: center"><img src="images/Jockey_300_GLW_save.png"></td>
        <td style="text-align: center"><img src="images/Jockey_300_MW_save.png"></td>
    </tr>
</table>
<br />

#### ReadySteadyGo
<!-- |       | Proposed (learned scales), BPP=0.060   | Proposed (fixed scales), BPP=0.060 |
|:------------------:| :------------------------------------: | :--------------------------------: |
| FLIP               | ![](images/flip.ReadySteadyGo_100_GT.ReadySteadyGo_100_GLW_save.67ppd.ldr.png) </br> FLIP=0.1761 | ![](images/flip.ReadySteadyGo_100_GT.ReadySteadyGo_100_MW_save.67ppd.ldr.png) </br> FLIP=0.1932 |
| Decoded</br> Image | ![](images/ReadySteadyGo_100_GLW_save.png) | ![](images/ReadySteadyGo_100_MW_save.png) | -->
<table>
    <tr>
        <td style="text-align: center"></td>
        <td style="text-align: center">Proposed (learned scales), BPP=0.060</td>
        <td style="text-align: center">Proposed (fixed scales), BPP=0.060</td>
    </tr>
    <tr>
        <td style="text-align: center">FLIP</td>
        <td style="text-align: center"><img src="images/flip.ReadySteadyGo_100_GT.ReadySteadyGo_100_GLW_save.67ppd.ldr.png"><br />FLIP=0.1761</td>
        <td style="text-align: center"><img src="images/flip.ReadySteadyGo_100_GT.ReadySteadyGo_100_MW_save.67ppd.ldr.png"><br />FLIP=0.1932</td>
    </tr>
    <tr>
        <td style="text-align: center">Decoded<br />Image</td>
        <td style="text-align: center"><img src="images/ReadySteadyGo_100_GLW_save.png"></td>
        <td style="text-align: center"><img src="images/ReadySteadyGo_100_MW_save.png"></td>
    </tr>
</table>
<br />
<br />

<!-- citation -->
## __Citation__
```
@inproceedings{choi2023inrslt,
    author = {Choi, Hee min and Kang, Hyoa and Oh, Dokwan},
    title = {Is Overfitting Necessary for Implicit Video Representation?},
    booktitle = {Proceedings of the 40th International Conference on Machine Learning},
    year = {2023}
}
```
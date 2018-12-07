<img src="sample_pic/bender_hex_mini.png" style="position:absolute;top:0px;right:0px;" width="120px" align="right" />

# Caret minimal example - Kaggle Give me some credit

## Introduction 

A short note illustrating how the caret package harmonizes the syntax of training models. You may also like the `mlr` package. This notebook is broadly based on existing solutions. The aim is to provide a minimal illustration of caret rather than being exhaustive on the modelling part or even on the caret part.

## How to reproduce the results ? 

Please, see the Rmd file for details and the html file to see what should be the output when you run the entire notebook. To reproduce the results:

 - clone this repo
 - Install R and Rstudio (official stable version)
 - Install the libraries using (all are not required but I'm too lazy to sort them)
 - In the Rmd file, change the paths accordingly to the path where you cloned the repo (use Ctrl+F on `read_`, `D:/` and `C:/` to find all the inputs)

Then you're ready to knit or run the Rmd notebook. You can compare the resulting ouput with mine.

Enjoy ;)


## Preview

### Comparison of models 

```r
## 
## Call:
## summary.resamples(object = results)
## 
## Models: naiveBayse, rdnForest, gradientBoost 
## Number of resamples: 5 
## 
## ROC 
##                    Min.   1st Qu.    Median      Mean   3rd Qu.      Max.
## naiveBayse    0.7943316 0.7956592 0.8052435 0.8032023 0.8092188 0.8115586
## rdnForest     0.8322498 0.8330160 0.8347096 0.8377784 0.8393567 0.8495599
## gradientBoost 0.8331513 0.8514011 0.8541468 0.8524808 0.8597603 0.8639444
##               NA's
## naiveBayse       0
## rdnForest        0
## gradientBoost    0
## 
## Sens 
##                    Min.   1st Qu.    Median      Mean   3rd Qu.      Max.
## naiveBayse    0.9964258 0.9969022 0.9970811 0.9969619 0.9971406 0.9972598
## rdnForest     0.9899327 0.9917193 0.9918389 0.9917912 0.9921368 0.9933282
## gradientBoost 0.7736344 0.7738726 0.7739187 0.7754783 0.7746470 0.7813189
##               NA's
## naiveBayse       0
## rdnForest        0
## gradientBoost    0
## 
## Spec 
##                     Min.    1st Qu.     Median       Mean    3rd Qu.
## naiveBayse    0.04545455 0.04708699 0.05661882 0.05408404 0.05985634
## rdnForest     0.14832536 0.15403033 0.16267943 0.16017812 0.16280926
## gradientBoost 0.73743017 0.76057462 0.78229665 0.77057384 0.78229665
##                     Max. NA's
## naiveBayse    0.06140351    0
## rdnForest     0.17304625    0
## gradientBoost 0.79027113    0
```




## Session info

```r
R version 3.5.1 (2018-07-02)
Platform: x86_64-w64-mingw32/x64 (64-bit)
Running under: Windows 7 x64 (build 7601) Service Pack 1

Matrix products: default

locale:
[1] LC_COLLATE=English_United States.1252  LC_CTYPE=English_United States.1252    LC_MONETARY=English_United States.1252
[4] LC_NUMERIC=C                           LC_TIME=English_United States.1252    

attached base packages:
[1] parallel  grid      stats     graphics  grDevices utils     datasets  methods   base     

other attached packages:
 [1] rmutil_1.1.1        optimx_2018-7.10    nloptr_1.0.4        klaR_0.6-14         stringr_1.3.1       readr_1.1.1        
 [7] expm_0.999-3        doParallel_1.0.11   iterators_1.0.10    tidyr_0.8.1         reshape2_1.4.3      lubridate_1.7.4    
[13] dplyr_0.7.6         randomForest_4.6-14 pROC_1.12.1         gbm_2.1.4           FactoMineR_1.41     dendextend_1.8.0   
[19] caret_6.0-80        wesanderson_0.3.6   viridis_0.5.1       viridisLite_0.3.0   VIM_4.7.0           data.table_1.11.4  
[25] colorspace_1.3-2    scales_1.0.0        RColorBrewer_1.1-2  igraph_1.2.2        gridExtra_2.3       ggthemes_4.0.1     
[31] factoextra_1.0.5    corrplot_0.84       summarytools_0.8.7  statmod_1.4.30      Rmisc_1.5           plyr_1.8.4         
[37] quantreg_5.36       SparseM_1.77        pscl_1.5.2          ppcor_1.1           MASS_7.3-50         normtest_1.1       
[43] moments_0.14        missMDA_1.13        mice_3.3.0          GPfit_1.0-0         glmnet_2.0-16       foreach_1.4.4      
[49] Matrix_1.2-14       Hmisc_4.1-1         ggplot2_3.0.0       Formula_1.2-3       survival_2.42-3     lattice_0.20-35    
[55] xtable_1.8-3        pander_0.6.2        knitr_1.20         

loaded via a namespace (and not attached):
  [1] questionr_0.6.3      tidyselect_0.2.4     lme4_1.1-18-1        htmlwidgets_1.2      combinat_0.0-8       trimcluster_0.1-2.1 
  [7] munsell_0.5.0        codetools_0.2-15     miniUI_0.1.1.1       withr_2.1.2          highr_0.7            rstudioapi_0.7      
 [13] leaps_3.0            geometry_0.3-6       stats4_3.5.1         robustbase_0.93-2    vcd_1.4-4            dimRed_0.1.0        
 [19] labeling_0.3         rprojroot_1.3-2      ipred_0.9-7          diptest_0.75-7       R6_2.2.2             flexmix_2.3-14      
 [25] DRR_0.0.3            bitops_1.0-6         lhs_0.16             assertthat_0.2.0     promises_1.0.1       nnet_7.3-12         
 [31] gtable_0.2.0         ddalpha_1.3.4        timeDate_3043.102    rlang_0.2.2          MatrixModels_0.4-1   CVST_0.2-2          
 [37] scatterplot3d_0.3-41 RcppRoll_0.3.0       splines_3.5.1        lazyeval_0.2.1       ModelMetrics_1.2.0   acepack_1.4.1       
 [43] broom_0.5.0          rapportools_1.0      checkmate_1.8.5      yaml_2.2.0           abind_1.4-5          backports_1.1.2     
 [49] httpuv_1.4.5         tools_3.5.1          lava_1.6.3           Rcpp_0.12.18         base64enc_0.1-3      purrr_0.2.5         
 [55] RCurl_1.95-4.11      ggpubr_0.1.8         rpart_4.1-13         zoo_1.8-3            sfsmisc_1.1-2        haven_1.1.2         
 [61] ggrepel_0.8.0        cluster_2.0.7-1      magrittr_1.5         openxlsx_4.1.0       lmtest_0.9-36        mvtnorm_1.0-8       
 [67] whisker_0.3-2        mitml_0.3-6          matrixStats_0.54.0   evaluate_0.11        mime_0.5             hms_0.4.2           
 [73] rio_0.5.10           mclust_5.4.1         readxl_1.1.0         compiler_3.5.1       tibble_1.4.2         crayon_1.3.4        
 [79] minqa_1.2.4          htmltools_0.3.6      later_0.7.5          magic_1.5-9          fpc_2.1-11.1         boot_1.3-20         
 [85] car_3.0-2            pryr_0.1.4           bindr_0.1.1          pan_1.6              gower_0.1.2          forcats_0.3.0       
 [91] pkgconfig_2.0.2      flashClust_1.01-2    numDeriv_2016.8-1    foreign_0.8-70       laeken_0.4.6         sp_1.3-1            
 [97] recipes_0.1.3        prodlim_2018.04.18   digest_0.6.17        pls_2.7-0            rmarkdown_1.10       cellranger_1.1.0    
[103] htmlTable_1.12       curl_3.2             kernlab_0.9-27       shiny_1.1.0          modeltools_0.2-22    jomo_2.6-4          
[109] nlme_3.1-137         bindrcpp_0.2.2       carData_3.0-1        pillar_1.3.0         DEoptimR_1.0-8       glue_1.3.0          
[115] zip_1.0.0            prabclus_2.2-6       class_7.3-14         stringi_1.1.7        latticeExtra_0.6-28  e1071_1.7-0         
```

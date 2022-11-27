# Wine-grape-dataset
## Overview
The data acquisition and research activities in this study were carried out in a wine vineyard located in Washington State University (WSU) Roza Experimental Orchards, Prosser, WA. Two different wine grape varieties were selected as the target due to their distinct color of berry skin when matured, including Chardonnay (white berries; Figure 1(a)) and Merlot (red berries; Figure1(d)). The color of berry skin for Chardonnay was consistently white throughout the growth season (Figure 1(b)-1(c)), while the color for Merlot changed from white to red (Figure 1(e)-1(f)) during the season.There were approximately 10-33 and 12-32 grape bunches per vine for the experimental Chardonnay and Merlot plants in this study. The wine vineyard was maintained by a professional manager for optimal productivity. The row and inter-plant spaces were about 2.5 m and 1.8 m for both varieties

![fig1](/images/fig1.png)

The imagery data collection was completed using a Samsung Galaxy S6 smartphone (Samsung Electronics Co., Ltd.,Suwon, South Korea) at the distances of 1-2 m, while the camera was facing perpendicularly to the canopy. The datacollection was carried out during the entire growth season (i.e., from the berries were developed to matured) at aperiodical frequency of one day per week and three times per day from 7/4/2019 to 9/30/2019. More specific details were given in Table 1 that the images of the canopies were captured under two weather conditions (i.e., sunny and cloudy), two berry maturity conditions (i.e., immature and mature), and three sunlight direction/intensity conditions(i.e., morning at 8am-9am, noon at 11am-12pm, and afternoon at 4pm-5pm, Pacific Daylight Time). All these various outdoor conditions largely represented the diversity of the imagery dataset. Note that all images were acquired from the consistent side of the canopy. As a result, 459 raw images were collected in total for Chardonnay (234 images) and Merlot (225 images) grape varieties in the original resolution of 5,312 x 2,988 pixels (Table 2). Specific number of raw images under individual conditions can also be found in Table 1

![table1](/images/table1.png)

![table2](/images/table2.png)


## Dataset annotation and augmentation
The raw imagery dataset was manually annotated using the annotation tool of LabelImg. The position of the grape
bunch was individually selected using bounding boxes. Clustered grape bunches were also carefully separated. In
addition, the “debar” approach was adopted based on our previous publication to separate individual canopies for evaluation purposes only. Once all raw images (Figure 2(a)) were annotated, the dataset was further enriched by using data enhancement and augmentation library of Imgaug , including the image adjustment of rotation (Figure 2(b)), channel enhancement (Figure 2(c)), Gaussian blur/noise (Figure 2(d)), and rectangle pixel discard (Figure 2(e)). During data augmentation, the annotated “key points” and “bounding boxes” were transformed accordingly. The enriched dataset can better represent the field conditions of the grape bunches. After augmentation, a dataset containing 4,418 images was developed, where a detailed description of the augmented dataset can be found in Table 2. The actual number of augmented images were less than planned (4,590 images) because some invalid augmented images were identified and discarded. The finalized dataset was further divided into train (80%), validation (10%), and test sets (10%), respectively, for development of grape bunch detection models. Finally, the in-field manual counting of grape bunches was completed during the harvest season on 10/1/2019 after the last dataset was acquired.

![fig2](/images/fig2.png)

## Downloads
The grape dataset and annotations are about 4.72GB in size and can be downloaded through Baidu Cloud:

    Link:https://pan.baidu.com/s/1S23ccg_WfngVq4XpSlcCfQ 
    password：81hn

## License
The dataset is available to download for commercial/research purposes under a Creative Commons Attribution-ShareAlike 4.0 International License. The copyright remains with the original owners of the images.


## Citation
    @Article{rs14225853,
    AUTHOR = {Lu, Shenglian and Liu, Xiaoyu and He, Zixuan and Zhang, Xin and Liu, Wenbo and Karkee, Manoj},
    TITLE = {Swin-Transformer-YOLOv5 for Real-Time Wine Grape Bunch Detection},
    JOURNAL = {Remote Sensing},
    VOLUME = {14},
    YEAR = {2022},
    NUMBER = {22},
    ARTICLE-NUMBER = {5853},
    URL = {https://www.mdpi.com/2072-4292/14/22/5853},
    ISSN = {2072-4292},
    ABSTRACT = {Precise canopy management is critical in vineyards for premium wine production because maximum crop load does not guarantee the best economic return for wine producers. The growers keep track of the number of grape bunches during the entire growing season for optimizing crop load per vine. Manual counting of grape bunches can be highly labor-intensive and error prone. Thus, an integrated, novel detection model, Swin-transformer-YOLOv5, was proposed for real-time wine grape bunch detection. The research was conducted on two varieties of Chardonnay and Merlot from July to September 2019. The performance of Swin-T-YOLOv5 was compared against commonly used detectors. All models were comprehensively tested under different conditions, including two weather conditions, two berry maturity stages, and three sunlight intensities. The proposed Swin-T-YOLOv5 outperformed others for grape bunch detection, with mean average precision (mAP) of up to 97% and F1-score of 0.89 on cloudy days. This mAP was ~44%, 18%, 14%, and 4% greater than Faster R-CNN, YOLOv3, YOLOv4, and YOLOv5, respectively. Swin-T-YOLOv5 achieved an R2 of 0.91 and RMSE of 2.4 (number of grape bunches) compared with the ground truth on Chardonnay. Swin-T-YOLOv5 can serve as a reliable digital tool to help growers perform precision canopy management in vineyards.},
    DOI = {10.3390/rs14225853}
    }

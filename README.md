# MUSIC-AVQA-v2.0
Data Release for the paper [Tackling Data Bias in MUSIC-AVQA: Crafting a Balanced Dataset for Unbiased Question-Answering](https://arxiv.org/abs/2310.06238) (Accepted by WACV 2024) by Xiulong Liu, Zhikang Dong and Peng Zhang.

The paper solves the data bias issue of original MUSIC-AVQA dataset by manually collecting 1230 musical instrument performance videos along with 8.1k newly created QA pairs complementing to the original biased QA set.

We include additional videos data and QA pairs after balancing the original [MUSIC-AVQA Dataset](https://gewu-lab.github.io/MUSIC-AVQA/) under this repository. The videos are manually collected from YouTube, and is used under research purpose only. We release the dataset for 2 parts: i). Videos via YouTube-ids along with the trimmed start-time and duration for each video, ii). Entire training and test QA set for MUSIC-AVQA-v2.0. If you have any issues downloading or cutting the specific videos, please feel free to contact us at [link](xl1995@uw.edu). To access the original MUSIC-AVQA videos, you could directly find the links from [MUSIC-AVQA Dataset](https://gewu-lab.github.io/MUSIC-AVQA/).

## Instructions
1. To download additional videos, see ``MUSIC-AVQA-v2.0_additional_videos.csv`` file under the ``data`` folder. There are 4 fields for each video:
i). `video_id`: The YouTube video ID. <br>
ii). `start_time`: cutting beginning time. <br>
iii). `prefix`: There are a few YouTube videos whose more than 1 segment are extracted, so we add prefix like "_#02", "_#03" after the `video_id` to name the videos to avoid duplication. <br>
iv). `has_flip`: We flip some videos horizontally and pair them with symmetric QA pairs, for those marked with `Y`, two videos are associated, one for original video like ``xxx.mp4`` and the other named ``xxx_flip.mp4`` standing for the flipped version. <br>
2. The MUSIC-AVQA-v2.0 'full' balanced QA dataset is provided under `data/balance_full_set` folder. We provide the entire train and test split associated with all videos including the original MUSIC-AVQA videos and new videos collected by us. This new QA dataset not only balances the original dataset, but also corrects QA pairs with problematic annotations in the original dataset. For more details on how we balanced the original dataset, please refer to the paper.

If you find our improvements on the AVQA dataset useful, please consider citing our [paper](https://arxiv.org/abs/2310.06238) and original [MUSIC-AVQA](https://openaccess.thecvf.com/content/CVPR2022/papers/Li_Learning_To_Answer_Questions_in_Dynamic_Audio-Visual_Scenarios_CVPR_2022_paper.pdf).

[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/tackling-data-bias-in-music-avqa-crafting-a/audio-visual-question-answering-music-avqa-v2)](https://paperswithcode.com/sota/audio-visual-question-answering-music-avqa-v2?p=tackling-data-bias-in-music-avqa-crafting-a)

# MUSIC-AVQA-v2.0
Data Release for the paper [Tackling Data Bias in MUSIC-AVQA: Crafting a Balanced Dataset for Unbiased Question-Answering](https://arxiv.org/abs/2310.06238) (Accepted by WACV 2024) by Xiulong Liu, Zhikang Dong and Peng Zhang.

The paper solves the data bias issue of original MUSIC-AVQA dataset by manually collecting 1230 musical instrument performance videos along with 8.1k newly created QA pairs complementing to the original biased QA set.

We include additional videos data and QA pairs after balancing the original [MUSIC-AVQA Dataset](https://gewu-lab.github.io/MUSIC-AVQA/) under this repository. The videos are manually collected from YouTube, and is used under research purpose only. We release the dataset for 2 parts: i). Videos via YouTube-ids along with the trimmed start-time and duration for each video, ii). Entire training and test QA set for MUSIC-AVQA-v2.0, along with 1040 additional videos (preprocessed and cut to 60s) to the existing MUSIC-AVQA which can be downloaded through this [link](https://www.dropbox.com/s/ejb36sh6gzqwdhn/collect_new_set.rar?st=8o3m8ds9&dl=0). To access the original MUSIC-AVQA videos, you could directly find the links from [MUSIC-AVQA Dataset](https://gewu-lab.github.io/MUSIC-AVQA/).

## Instructions
1. To download additional videos, see ``MUSIC-AVQA-v2.0_additional_videos.csv`` file under the ``data`` folder. There are 4 fields for each video:
i). `video_id`: The YouTube video ID. <br>
ii). `start_time`: cutting beginning time. <br>
iii). `prefix`: There are a few YouTube videos whose more than 1 segment are extracted, so we add prefix like "_#02", "_#03" after the `video_id` to name the videos to avoid duplication. <br>
iv). `has_flip`: We flip some videos horizontally and pair them with symmetric QA pairs, for those marked with `Y`, two videos are associated, one for original video like ``xxx.mp4`` and the other named ``xxx_flip.mp4`` standing for the flipped version. <br>
2. The MUSIC-AVQA-v2.0 'full' balanced QA dataset is provided under `data/balance_full_set` folder. We provide the entire train and test split associated with all videos including the original MUSIC-AVQA videos and new videos collected by us. This new QA dataset not only balances the original dataset, but also corrects QA pairs with problematic annotations in the original dataset. For more details on how we balanced the original dataset, please refer to the paper.

## Benchmark results
Feel free to submit your benchmark results at the Paper-With-Code benchmark leaderboard: https://paperswithcode.com/task/audio-visual-question-answering-music-avqa-v2.

## Citations
If you use our MUSIC-AVQA-v2.0 dataset to benchmark your models, please consider citing our [paper](https://arxiv.org/abs/2310.06238) and original [MUSIC-AVQA](https://openaccess.thecvf.com/content/CVPR2022/papers/Li_Learning_To_Answer_Questions_in_Dynamic_Audio-Visual_Scenarios_CVPR_2022_paper.pdf):

```bibtex
@inproceedings{liu2024tackling,
  title={Tackling data bias in music-avqa: Crafting a balanced dataset for unbiased question-answering},
  author={Liu, Xiulong and Dong, Zhikang and Zhang, Peng},
  booktitle={Proceedings of the IEEE/CVF Winter Conference on Applications of Computer Vision},
  pages={4478--4487},
  year={2024}
}
```

# 꿈꾸는 AI 2020 DREAM_AI Open Challenge

---

# DREAM_AI_Team_Wisdom_Graduate_School_Life
- 꿈꾸는 아이 2020 Team 슬기로운 석사생활 팀, 드라마 배경음악 자동 생성 / 탐색

---

## 주제 - 드라마 배경음악 자동 생성/탐색

## 문제 정의

> 드라마 1편에는 약 10~20여개의 배경음악이 사용되고 있습니다. 모든 드라마에는 음악감독이 있어서 배경음악을 삽입하고 있지만, 모든 배경음악을 다 작곡하기는 어려우므로 저작권이 있는 음악을 활용하고 있습니다. 그러나 전세계 모든 곡의 저작권을 다 파악할 수는 없으므로 활용이 가능한 음원인지 아닌지를 판단하기가 너무 어렵고 비용도 많이 들어갑니다. 이에, 드라마 내의 각 장면(Scene)에 저작권료가 없는 AI 배경음악을 삽입하는 기술을 개발하고자 합니다.
(※ AI 작곡도 가능하며, 또는 License-free 음원 탐색도 가능함.)

- 무료로 오픈된 웹 드라마 파일 (2개 제공)
- 총 10개 장면에 대해서 장면 당 0~10점, 총 100점 만점으로 평가.
- 산출물
  1) 알고리즘 구조에 대한 설명서 (자유 양식)
  2) 음악 파일은 mid 형식으로 출력

## 개발관련
- 음원 분류
    - 대사, BGM, 소음 간 분류
- 분류한 BGM 정보 추출
    - BGM의 제목, 장르, 연령대, 분위기
- 대사 Feature 정보 추출
    - Tempo, emotion 추출
- 영상 Feature 정보 추출
    - 영상의 분위기 정보
- Feature와 BGM 관계 파악
    - 모든 Feature 와 BGM간 상관관계 알아내기
- DataSet 찾기
    - Free License 노래 찾기
    - Label 된 데이터 찾아보기
        - BGM에 감정, 분위기 등과 같은 정보가 함께 있는 데이터


## 음원 분류
- 데이터 수집을 위한 작업
- 드라마의 대사와 BGM를 구분해 내는 작업
- [Music Source Separation on MUSDB18](https://paperswithcode.com/sota/music-source-separation-on-musdb18?p=open-unmix-a-reference-implementation-for)
- Demucs and Conv-Tasnet in facebook research
    - MIT License
    - [github site](https://github.com/facebookresearch/demucs)
    - [MusDB](https://sigsep.github.io/datasets/musdb.html)
    - [Paper](https://hal.archives-ouvertes.fr/hal-02379796/document)
    - [Result](https://ai.honu.io/papers/demucs/index.html)
    - my result
        - [myresult](https://github.com/fbdp1202/fbdp1202.github.io/tree/master/assets/wav/itw)

## Melody Extraction
- 노래의 정보를 추출하기 위한 작업
- [github - Melody-extraction-with-melodic-segnet](https://github.com/bill317996/Melody-extraction-with-melodic-segnet)
    - MIT License
    - [Paper](https://arxiv.org/pdf/1810.12947.pdf)
    - pytorch 0.4.1

- [github - melodyExtraction_JDC](https://github.com/keums/melodyExtraction_JDC)
    - MIT License
    - keras
    - 0.1초 단위로 frequency 정보가 추출됨.

- [github - Vocal-Melody-Extraction](https://github.com/s603122001/Vocal-Melody-Extraction)
    - MIT License
    - keras


## 음악 찾기

- ACRCloud
    - 높은 성능의 노래 찾기 기능 제공.
    - [HomePage](https://www.acrcloud.com/?utm_source=chrome&utm_medium=extension)
    - [SDK Page](https://console-v2.acrcloud.com/avr?region=eu-west-1#/dashboard)
    - [github SDK](https://github.com/acrcloud/acrcloud_sdk_python#functions)
        - Linux에서는 잘 작동함
        ![](https://i.imgur.com/aPzI7sb.png)

- Shazam API
    - 가사가 주어지면, 관련 노래를 찾아줌. 외국노래만 됨
    - https://rapidapi.com/apidojo/api/shazam/endpoints


## 영상 Feature 정보 추출
- [Multi-label Emotion Classification in Music VideosUsing Ensembles of Audio and Video Features](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=8995364)
- [github - maelfabien/Multimodal-Emotion-Recognition](https://github.com/maelfabien/Multimodal-Emotion-Recognition)

## Music Mood Classification
- [https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=7973014](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=7973014)
- [https://asistdl.onlinelibrary.wiley.com/doi/pdf/10.1002/asi.23649](https://asistdl.onlinelibrary.wiley.com/doi/pdf/10.1002/asi.23649)
- [https://www.aclweb.org/anthology/C16-1186.pdf](https://www.aclweb.org/anthology/C16-1186.pdf)
- [DB - http://millionsongdataset.com/](http://millionsongdataset.com/)
- [github - https://github.com/neokt/audio-music-mood-classification](https://github.com/neokt/audio-music-mood-classification)
- http://millionsongdataset.com/pages/contact-us/
- https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=7973014
- https://asistdl.onlinelibrary.wiley.com/doi/pdf/10.1002/asi.23649
- https://res.mdpi.com/d_attachment/electronics/electronics-08-00164/article_deploy/electronics-08-00164.pdf
- https://www.researchgate.net/profile/Alexander_Schindler/publication/313895558_Parallel_Convolutional_Neural_Networks_for_Music_Genre_and_Mood_Classification/links/58aead3645851503be9203b8/Parallel-Convolutional-Neural-Networks-for-Music-Genre-and-Mood-Classification.pdf
- https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=8279468
- https://openaccess.thecvf.com/content_cvpr_2017_workshops/w41/papers/Roy_DeepSpace_Mood-Based_Image_CVPR_2017_paper.pdf

## Dataset 찾기
- Free License 음악 제공 사이트 [https://www.bensound.com/](https://www.bensound.com/)

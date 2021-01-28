# NSFW

[데이터 출처 github (including url text files)](https://github.com/alex000kim/nsfw_data_scraper) + [DOCS](https://syncedreview.com/2019/01/15/nsfw-dataset-removes-humans-from-content-review/)

[NSFW JS Demo](https://github.com/infinitered/nsfwjs/tree/ebcd41c46087a3f42c6577f96acc53d7a934b068)<br>
<img src="https://github.com/infinitered/nsfwjs/raw/master/_art/nsfw_demo.gif">

**5 classes images**
- DraDrawing: 애니를 포함한 안전한 그림(safe for work drawings (including anime))
- Hentai: 헨타이와 포르노 그림(hentai and pornographic drawings)
- Neutral: 안전한 이미지(safe for work neutral images)
- Porn: 포르노 이미지, 섹슈얼 행동(pornographic images, sexual acts)
- Sexy: 포르노는 아닌 노골적인 이미지(sexually explicit images, not pornography)


**데이터 사이즈**
- 총 개수: 125214 (45G)<br>
  \* Docs에는 22만개라고 설명하지만 Sframe에 로드했을 때 다운로드에러, 확장자에러 등이 나타남
- Drawings: 15205 (7.1G)
- Hentai: 4248 (1.5G)
- Neutral: 34910 (17G)
- Porn: 56968 (15G)
- Sexy: 13883 (4.1G)


### NSFW model

train, test split ratio: 0.85, 0.15
model architecture: resnet-50

- summary

<img src="https://lh3.googleusercontent.com/v4HFcZaN9Z1dX5L4nDSoDC8FNl3iXYJU9kkLPF9GNs8htHgODKYQHM33l_FiG2ItuQRwG95fxueroLoMrE4cJx3wbOzZ1Z4XKXJTl-859YBWtNb6vkyNKuxHmZzSnqBSY7q2NRfw">

- model detail

<img src="https://lh6.googleusercontent.com/W3aCNZ-yMd632cuNJO3Cl28LFp0hnXrrukPSkS59piCSwzt9dTmhSOB5GUZlffl1DeR5Jbj0XcX1P50kTHlbB1mzWstj75_AZEjVawyLyM34mf2pIZmPKGzf6JX9qadWeXz3LMTM">

- modeling time (loading + getting features + training): about 3h 30min<br>
  \* it can vary on training iterations or other environmetal issues


### Confusion Matrix in Test Data

<img src="https://lh4.googleusercontent.com/fdU3Gd5cup7WhJGJYRuXiH9m5IzFR-PX1E1MVBHzfVxkxli8WMdvDl7zlPe33Ykco-pbuFJvQVNzhZjUP17vr3ky3HowXs9FNrwM_YHMojbedKBtt8aZmQ4KPqtLJUWlLjqIJ9p7">
<img src="https://lh6.googleusercontent.com/E1WlQQzlHwBYbTMuvaRN9JRRY7qGYCOunE48hkKD_k6jbXxMp6l7hcOrSvQHf-MjJ78JqAcoDoKC-x0A50iUSff2mAt-jRGkoz1IPQAKGbeansYuykWPXqJSavw70vhNsXUn73Wg">


### Test on Google Images With Top-k Probabiltiy

<img src="https://lh6.googleusercontent.com/hyltOUX0CE8BBhlAqtbrsomvrLtg4CMXgGM8cJwmVOpB0E3yXEI0CAvH00Goknj1hfa-HBmpNq-r1tSiJg49cYL-xwTt3p8O9IzGpuG5CNGsMaTDNNxiQ-TRS59yRsM2odO7BZFd">
<img src="https://lh3.googleusercontent.com/w6ZE1r5DmJBUtJgm7f5_J_me5FpEvL4dVPTgVJpSCDHiR4U22jXAAcnYddPB_S4Yaik_HNrSir3_t2gxQnKZR0JTheWSBpcXOrlAXq3RS4OlxUoJoV7sdmFO5aLD9kJacbPInNIL">
<img src="https://lh4.googleusercontent.com/vk7vxgAQTerK52RylmYfpc_mkH-zqZUK-Ti0NNOie1xWm7IvrwXL5dMXYvD-tYJot7QpbkehgZjqG9fbZAQnHj1-E0MLPOad6mk8eNXRFFYY3mvNMpgk4fZmuXENJfIrfwjsxi5q">
<img src="https://lh6.googleusercontent.com/HCI0KFKBRZnSTS_K8lmQ6eay_ohCmH9LKIUjoJPe47aexIg9LCm5cTxWMFZRlEg2-Gv8u71_PkZ9bDwW3LXb3FaR-VS1_yk13aVmNVhLb79Rq87qH1KuMfu_m5qltnXjelR5pA7E">
<img src="https://lh4.googleusercontent.com/8ZP5Psl2PCkHW0q8UnqLSRwy5GOWyD2zDS1hWPy5EgePPFhihH0zFt3yb_pDd5F3iB38R7qGNkQ0CMlHV3tsx0iN7SjpFqhjr6pUZ_Bcbyket-UobKp9Kg9Jh86hkm9mfS0TS1tj">
<img src="https://lh4.googleusercontent.com/8bFQamX5xzmmK9yoMkLRVm6JaIpsf8lb1iT70jWM1XlUhhRYZt4E-UntGi1_V07O_DQb6h1boZ6DGav8q3cMmi771vruwtg7WzHQeZQRSXsBSLV17preyGeKFgNKYY-1Gln6ocgt">

### Additional Recommendation

[HugHuge New NSFW Dataset](https://github.com/EBazarov/nsfw_data_source_urls) + [Docs](https://medium.com/syncedreview/huge-new-nsfw-dataset-for-content-filtering-c8e6a323d67c)
- 위의 데이터에서 카테고리가 제대로 정의되어 있지 않은 것과 오분류되는 문제점을 보완하고자 프로젝트 진행
- 고품질의 데이터 셋으로 159개의 카테고리와 158만 개의 데이터를 포함(주로 이미지이지만, 동영상도 포함)
- 오류를 제외한 데이터를 다운로드하면 500GB, 130만 개의 NSFW 이미지 데이터
- 다운로드 후 중복되는 데이터, 제한·삭제된 데이터, 충돌되는 데이터 제거 등의 작업이 요구됨
- NSFW데이터와 neutral데이터가 섞여있는 노이즈에 주의해야 함

# NL_Ling_Periodicals
Welcome to the Linguistic Periodicals Text Processing repository! This repository contains Python scripts and tools for processing digitized text data of linguistic periodicals:󰡔Hangul󰡕, 󰡔JeongUm󰡕, 󰡔Wuolgan Joseoneo󰡕  which were provided by the Korea National Library. Our goal is to make it easier for researchers, linguists, and enthusiasts to analyze and work with these valuable texts.

# Features
## Text Cleaning and Preprocessing: 
Scripts to clean and preprocess the digitized texts such as making directories for each periodical and converting Hanja(sino-Korean character) to Hangul(Korean character)

The digitized texts are the following. 

- 󰡔한글󰡕은 조선어학회 기관지.
󰡔Hangul󰡕 is the organization journal of a linguistic academic community of JoseoneoHakHoe whereby Joseoneo is the name of Korean Language in the Japanese colonized period. 

- 󰡔정음󰡕은 조선어학연구회 기관지 
󰡔JeongUm󰡕 is the organization journal of another linguistic academic community of Joseoneo.  

- 󰡔월간 조선어󰡕는 총독부 관변 조선어연구회 기관지
󰡔Wuolgan Joseoneo󰡕 is the organization journal of yet another linguistic academic community of Joseoneo which mainly the colonialist office. 

However, the full digitized contents are not released in this repository due to the license.  Please ask rink@korea.kr (국립중앙도서관 연구정보실). 
Just to get easily going in utilizing this resource, a few sample text files are included. 


## Text Analysis 
Functions for text analysis such as space normalization, tokenization based on morphology analyser which is konlpy, and removing stop words.

### space normalization
Raw data which were provided by national library are often put in spaces in between characters of a word following the original paper material. 
It is necessary to normalize spaces i.e. remove spaces in between a word to have normal word units. 

raw) 한 글 마 춤 법, 조 선 어 학 회, 주 시 경

after) 한글마춤법, 조선어학회, 주시경

### tokenization with konlpy
To make long texts into countable word-like units and to extract noun-like tokens only 

ex) 
import konlpy
from konlpy.tag import Komoran
moran = Komoran()
moran.nouns('그의 홀소리와 닿소리와 또는 첫소리와 나중소리를 ') 

we have ['홀소리', '닿소리', '소리', '나중', '소리']

Also to have more meaningful units, set a user dictionary which is a list of correct unit of tokens. 

ex) '나중소리' instead of '나중' and '소리'
moran = Komoran(userdic="dic_komoran.user")
moran.nouns('그의 홀소리와 닿소리와 또는 첫소리와 나중소리를 ')

we have ['홀소리', '닿소리', '첫소리', '나중소리']


### removing stop words 
To do topic modelling without too frequent not meaninful words

ex) '것', '일', '때', '수', '잇', '듯', '이', '하', '등', '중' etc are needed to be removed before topic modelling

## Topic modelling and the Visualization: 
Tools for visualizing linguistic data, including frequency distributions, word clouds, and co-occurrence networks.
Metadata Handling: Utilities for processing and organizing metadata associated with the periodicals.
Sample Datasets: Example datasets from the Korea National Library for testing and demonstration purposes.

# Getting Started
To get started with using the scripts, clone this repository and follow the instructions in the README file. The repository includes detailed documentation for each script and tool, as well as example usage.

```command terminal 
git clone https://github.com/Chris-eunkyoung-Jo/NL_Ling_Periodicals.git
cd NL_Ling-Periodicals
```
Voilà the cloned repository. 


# Contributions
We welcome contributions from the community! If you have any scripts, tools, or improvements to share, please submit a pull request. For major changes, please open an issue first to discuss your proposed changes.


# License
This project is licensed under the MIT License. See the LICENSE file for more details.

# Acknowledgements
I would like to thank the Korea National Library (https://www.nl.go.kr/) for providing the digitized text data used in this repository. 
The text data and this resource were used for a book of Korean Studies, 


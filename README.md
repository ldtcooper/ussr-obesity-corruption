# README

This repo contains the code for a research project of mine. You can read the entirety of the working paper [here](https://www.logan-cooper.com/assets/Cooper_Becker_Obesity_and_Corruption.pdf).

## What is this project?
In 2021, Professor Pavlo Blavatskyy published his paper "Obesity of politicians and corruption in post-Soviet countries" ([link](https://onlinelibrary.wiley.com/doi/abs/10.1111/ecot.12259)). The thesis of this paper is that the body mass index (BMI) of cabinet-level ministers can be used as a proxy for high-level corruption in a country, and backs it up with evidence from the former Soviet Union. To obtain the BMI of these leaders, he used a computer vision algorithm developed by Kocabey et al ([link](https://www.researchgate.net/publication/314433619_Face-to-BMI_Using_Computer_Vision_to_Infer_Body_Mass_Index_on_Social_Media)). 

While an intriguing idea, Blavatskyy's original paper lacked controls for factors such as age and sex. So, as a term paper for Duke University's Econ 627: Soviet Economic History, I decided to remedy that with a paper of my own. This paper has two main goals:
1. Reproduce Blavatskyy's results independently: reproducability is a cornerstone of any scientific endevor, so if I was going to be improving on Blavatskyy's work, I needed to see with my own eyes that it is valid.
2. Rigorously test those results: if Blavatskyy's hypothesis is true, then it should hold up to rigorous econometric scruitiny. 

## Methodology
Blavatskyy's original paper does only a cursory job of proving his hypothesis. Using facial photographs of ministers from the former USSR who were in power in 2017, he estimates their BMIs, and then notes several correlations. Namely, that those BMIs are correlated with five corruption measures such that lighter ministers and less corruption go together; and that countries with heaver ministers have lighter people. 

My paper focuses in on two simple controls: age and sex. Cabinet ministers are, as a whole, much older and much more male than the populations they represent. Because of this, I focus on age and sex as controls. The first stage of doing this works similarly to Blavatskyy's paper: I examine the correlations between age, sex, BMI, and corruption. The second stage is more complex. It uses a multivariate linear regression trained on health data from the forer USSR to estimate what the BMI of a person of a given age and gender 'should' be. Then, I run the age and sex data of the 2017 ministers through the resulting regression equation to correct for age and sex differences and then see if the resulting corrected values still correlate positively with corruption and negatively with BMI in each country.

## Credits
The following files were written by Pavlo Blavatskyy and were taken from the appendix to his paper which can be found at the link in the "What is this project?" section:
- `bmipredictor.py`

The entire `/caffe` directory is an older version of Saumitro Dasgupta's [caffe-tensorflow package](https://github.com/ethereon/caffe-tensorflow).


## Running this project
Unfortunately, this entire project can't be run from this repo, as there are several pieces of code I can't freely distribute on GitHub. These files can however be provided upon request.

However, if one wanted to get this to run, you would need to set up a Python 3.5 enviornment in order to run `bmipredictor.py`. If that is not a requirement, then it can be run in any newer version of Python.
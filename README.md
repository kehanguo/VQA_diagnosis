# VQA_diagnosis
# Sprint 1

 Product Mission
- Implement an existed program in Github, and test its result.
- Based on our study of the existed project, build a VQA system that can be used for disease diagnosis
- Build a reasonable question and answer set.(for doctor)

MVP
- Since the current VQA system lacks stability and a guaranteed accuracy, our project aims to develop a VQA system which serves an auxiliary tool for experienced doctor or educational tool for beginners.  

User story

- Due to Covid-19, an clinic have thousands samples of CT scans to go through each day, however, doctors that are capable of doing quick diagnosis are very limited. This VQA model, could easily and precisely sort out those CT which are extremely healthy as well as those who are extremely devastated, thus, significantly simplifies doctors tasks. 

## Developing Tool
- VQA model implemented: https://github.com/abhshkdz/neural-vqa
  
  

![image](https://user-images.githubusercontent.com/52185318/95355860-065ef300-0894-11eb-8b81-75982e2949bf.png)

- Torch
http://torch.ch

 1. install Torch packages:
  - in a terminal, run the commands WITHOUT sudo
    > git clone https://github.com/torch/distro.git ~/torch --recursive 
    cd ~/torch; bash install-deps;
    ./install.sh
  - Torch tutorial -- graph style neural networks
    https://github.com/soumith/cvpr2015/blob/master/NNGraph%20Tutorial.ipynb
    
    
    https://on-demand.gputechconf.com/gtc/2015/webinar/torch7-applied-deep-learning-for-vision-natural-language.mp4
    
-Caffe Network
https://caffe.berkeleyvision.org

- MSCOCO Dataset
http://mscoco.org

-Open Access Medical Image repository


http://www.aylward.org/notes/open-access-medical-image-repositories

- how to create a balanced dataset


https://arxiv.org/pdf/1612.00837.pdf

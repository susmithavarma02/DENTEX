<<<<<<< HEAD
# DENTEX CHALLENGE 2023
Dental Enumeration and Diagnosis on Panoramic X-rays Challenge


<details><summary>Table of Contents</summary><p>
  
* [What is DENTEX?](#what-is-dentex)
* [Desired Output of the Challenge](#desired-output-of-the-challenge)
* [Data](#data)
* [Citing Us](#citing-us)
* [License](#license)
* [Contact](#contact)
  
</p></details><p></p>

*Now, all the data related to DENTEX (including test and validation sets) are available on the [Hugging Face page](https://huggingface.co/datasets/ibrahimhamamci/DENTEX).*


## What is DENTEX?
We present the Dental Enumeration and Diagnosis on Panoramic X-rays Challenge (DENTEX), organized in conjunction with the International Conference on Medical Image Computing and Computer-Assisted Intervention (MICCAI) in 2023. The primary objective of this challenge is to develop algorithms that can accurately detect abnormal teeth with dental enumeration and associated diagnosis. This not only aids in accurate treatment planning but also helps practitioners carry out procedures with a low margin of error.

The challenge provides three types of hierarchically annotated data and additional unlabeled X-rays for optional pre-training. The annotation of the data is structured using the Fédération Dentaire Internationale (FDI) system. The first set of data is partially labeled because it only includes quadrant information. The second set of data is also partially labeled but contains additional enumeration information along with the quadrant. The third data is fully labeled because it includes all quadrant-enumeration-diagnosis information for each abnormal tooth, and all participant algorithms will be benchmarked on the third data. 

DENTEX aims to provide insights into the effectiveness of AI in dental radiology analysis and its potential to improve dental practice by comparing frameworks that simultaneously point out abnormal teeth with dental enumeration and associated diagnosis on panoramic dental X-rays.

*Please visit the webpage of [DENTEX (Dental Enumeration and Diagnosis on Panoramic X- rays Challenge)](https://dentex.grand-challenge.org/) which is held at MICCAI2023.*

## Desired Output of the Challenge
![Fig. 1. A desired output from a final algorithm, illustrating well-defined bounding boxes for each abnormal tooth. The corresponding quadrant (Q), enumeration (N), and diagnosis (D) labels are also displayed.](figures/output.png)
*Fig. 1. A desired output from a final algorithm, illustrating well-defined bounding boxes for each abnormal tooth. The corresponding quadrant (Q), enumeration (N), and diagnosis (D) labels are also displayed.*


## Data
![Fig. 2. The hierarchical organization of the annotated data. The data is structured into three levels: (a) quadrant-only for quadrant detection, (b) quadrant-enumeration for tooth detection, and (c) quadrant-enumeration-diagnosis for abnormal tooth detection.](figures/data.png)
*Fig. 2. The hierarchical organization of the annotated data. The data is structured into three levels: (a) quadrant-only for quadrant detection, (b) quadrant-enumeration for tooth detection, and (c) quadrant-enumeration-diagnosis for abnormal tooth detection.*

The DENTEX dataset comprises panoramic dental X-rays obtained from three different institutions using standard clinical conditions but varying equipment and imaging protocols, resulting in diverse image quality reflecting heterogeneous clinical practice. The dataset includes X-rays from patients aged 12 and above, randomly selected from the hospital's database to ensure patient privacy and confidentiality.

To enable effective use of the FDI system, the dataset is hierarchically organized into three types of data;

*   (a) 693 X-rays labeled for quadrant detection and quadrant classes only,

*   (b) 634 X-rays labeled for tooth detection with quadrant and tooth enumeration classes,

*   (c) 1005 X-rays fully labeled for abnormal tooth detection with quadrant, tooth enumeration, and diagnosis classes.

The diagnosis class includes four specific categories: caries, deep caries, periapical lesions, and impacted teeth. An additional 1571 unlabeled X-rays are provided for pre-training. 

* The dataset is used for [DENTEX (Dental Enumeration and Diagnosis on Panoramic X-rays Challenge)](https://dentex.grand-challenge.org/). 

**Data Split for Evaluation and Training**

The DENTEX 2023 dataset comprises three types of data: (a) partially annotated quadrant data, (b) partially annotated quadrant-enumeration data, and (c) fully annotated quadrant-enumeration-diagnosis data. The first two types of data are intended for training and development purposes, while the third type is used for training and evaluations.

To comply with standard machine learning practices, the fully annotated third dataset, consisting of 1005 panoramic X-rays, is partitioned into training, validation, and testing subsets, comprising 705, 50, and 250 images, respectively. Ground truth labels are provided only for the training data, while the validation data is provided without associated ground truth, and the testing data is kept hidden from participants.

**Annotation Protocol**

The DENTEX provides three hierarchically annotated datasets that facilitate various dental detection tasks: (1) quadrant-only for quadrant detection, (2) quadrant-enumeration for tooth detection, and (3) quadrant-enumeration-diagnosis for abnormal tooth detection. Although it may seem redundant to provide a quadrant detection dataset, it is crucial for utilizing the FDI Numbering System. The FDI system is a globally-used system that assigns each quadrant of the mouth a number from 1 through 4. The top right is 1, the top left is 2, the bottom left is 3, and the bottom right is 4. Then each of the eight teeth and each molar are numbered 1 through 8. The 1 starts at the front middle tooth, and the numbers rise the farther back we go. So for example, the back tooth on the lower left side would be 48 according to FDI notation, which means quadrant 4, number 8. Therefore, the quadrant segmentation dataset can significantly simplify the dental enumeration task, even though evaluations will be made only on the fully annotated third data.

**How to Access Data**


Please visit [the Hugging Face page](https://huggingface.co/datasets/ibrahimhamamci/DENTEX) to access all the training and validation data related to the challenge.

**Note**: The datasets are fully identical to the data used for our baseline method named as HierarchicalDet. Therefore, please visit [HierarchicalDet (Diffusion-Based Hierarchical Multi-Label Object Detection to Analyze Panoramic Dental X-rays)](https://github.com/ibrahimethemhamamci/HierarchicalDet) repo for more info.

## Citing Us

If you use DENTEX, we would appreciate references to the following papers:
```
1. @article{hamamci2023dentex,
  title={DENTEX: An Abnormal Tooth Detection with Dental Enumeration and Diagnosis Benchmark for Panoramic X-rays},
  author={Hamamci, Ibrahim Ethem and Er, Sezgin and Simsar, Enis and Yuksel, Atif Emre and Gultekin, Sadullah and Ozdemir, Serife Damla and Yang, Kaiyuan and Li, Hongwei Bran and Pati, Sarthak and Stadlinger, Bernd and others},
  journal={arXiv preprint arXiv:2305.19112},
  year={2023}
}

2. @inproceedings{hamamci2023diffusion,
  title={Diffusion-based hierarchical multi-label object detection to analyze panoramic dental x-rays},
  author={Hamamci, Ibrahim Ethem and Er, Sezgin and Simsar, Enis and Sekuboyina, Anjany and Gundogar, Mustafa and Stadlinger, Bernd and Mehl, Albert and Menze, Bjoern},
  booktitle={International Conference on Medical Image Computing and Computer-Assisted Intervention},
  pages={389--399},
  year={2023},
  organization={Springer}
}
```


## License
The data is provided under the [CC BY-SA 4.0 License](https://creativecommons.org/licenses/by-sa/4.0/), making it fully open-sourced.

The rest of this repository is under the [MIT License](https://choosealicense.com/licenses/mit/).

=======
# Dental_Abnormalities



## Getting started

To make it easy for you to get started with GitLab, here's a list of recommended next steps.

Already a pro? Just edit this README.md and make it your own. Want to make it easy? [Use the template at the bottom](#editing-this-readme)!

## Add your files

- [ ] [Create](https://docs.gitlab.com/ee/user/project/repository/web_editor.html#create-a-file) or [upload](https://docs.gitlab.com/ee/user/project/repository/web_editor.html#upload-a-file) files
- [ ] [Add files using the command line](https://docs.gitlab.com/ee/gitlab-basics/add-file.html#add-a-file-using-the-command-line) or push an existing Git repository with the following command:

```
cd existing_repo
git remote add origin https://gitlab.com/team_dental/Dental_Abnormalities.git
git branch -M main
git push -uf origin main
```

## Integrate with your tools

- [ ] [Set up project integrations](https://gitlab.com/team_dental/Dental_Abnormalities/-/settings/integrations)

## Collaborate with your team

- [ ] [Invite team members and collaborators](https://docs.gitlab.com/ee/user/project/members/)
- [ ] [Create a new merge request](https://docs.gitlab.com/ee/user/project/merge_requests/creating_merge_requests.html)
- [ ] [Automatically close issues from merge requests](https://docs.gitlab.com/ee/user/project/issues/managing_issues.html#closing-issues-automatically)
- [ ] [Enable merge request approvals](https://docs.gitlab.com/ee/user/project/merge_requests/approvals/)
- [ ] [Set auto-merge](https://docs.gitlab.com/ee/user/project/merge_requests/merge_when_pipeline_succeeds.html)

## Test and Deploy

Use the built-in continuous integration in GitLab.

- [ ] [Get started with GitLab CI/CD](https://docs.gitlab.com/ee/ci/quick_start/index.html)
- [ ] [Analyze your code for known vulnerabilities with Static Application Security Testing (SAST)](https://docs.gitlab.com/ee/user/application_security/sast/)
- [ ] [Deploy to Kubernetes, Amazon EC2, or Amazon ECS using Auto Deploy](https://docs.gitlab.com/ee/topics/autodevops/requirements.html)
- [ ] [Use pull-based deployments for improved Kubernetes management](https://docs.gitlab.com/ee/user/clusters/agent/)
- [ ] [Set up protected environments](https://docs.gitlab.com/ee/ci/environments/protected_environments.html)

***

# Editing this README

When you're ready to make this README your own, just edit this file and use the handy template below (or feel free to structure it however you want - this is just a starting point!). Thanks to [makeareadme.com](https://www.makeareadme.com/) for this template.

## Suggestions for a good README

Every project is different, so consider which of these sections apply to yours. The sections used in the template are suggestions for most open source projects. Also keep in mind that while a README can be too long and detailed, too long is better than too short. If you think your README is too long, consider utilizing another form of documentation rather than cutting out information.

## Name
Choose a self-explaining name for your project.

## Description
Let people know what your project can do specifically. Provide context and add a link to any reference visitors might be unfamiliar with. A list of Features or a Background subsection can also be added here. If there are alternatives to your project, this is a good place to list differentiating factors.

## Badges
On some READMEs, you may see small images that convey metadata, such as whether or not all the tests are passing for the project. You can use Shields to add some to your README. Many services also have instructions for adding a badge.

## Visuals
Depending on what you are making, it can be a good idea to include screenshots or even a video (you'll frequently see GIFs rather than actual videos). Tools like ttygif can help, but check out Asciinema for a more sophisticated method.

## Installation
Within a particular ecosystem, there may be a common way of installing things, such as using Yarn, NuGet, or Homebrew. However, consider the possibility that whoever is reading your README is a novice and would like more guidance. Listing specific steps helps remove ambiguity and gets people to using your project as quickly as possible. If it only runs in a specific context like a particular programming language version or operating system or has dependencies that have to be installed manually, also add a Requirements subsection.

## Usage
Use examples liberally, and show the expected output if you can. It's helpful to have inline the smallest example of usage that you can demonstrate, while providing links to more sophisticated examples if they are too long to reasonably include in the README.

## Support
Tell people where they can go to for help. It can be any combination of an issue tracker, a chat room, an email address, etc.

## Roadmap
If you have ideas for releases in the future, it is a good idea to list them in the README.

## Contributing
State if you are open to contributions and what your requirements are for accepting them.

For people who want to make changes to your project, it's helpful to have some documentation on how to get started. Perhaps there is a script that they should run or some environment variables that they need to set. Make these steps explicit. These instructions could also be useful to your future self.

You can also document commands to lint the code or run tests. These steps help to ensure high code quality and reduce the likelihood that the changes inadvertently break something. Having instructions for running tests is especially helpful if it requires external setup, such as starting a Selenium server for testing in a browser.

## Authors and acknowledgment
Show your appreciation to those who have contributed to the project.

## License
For open source projects, say how it is licensed.

## Project status
If you have run out of energy or time for your project, put a note at the top of the README saying that development has slowed down or stopped completely. Someone may choose to fork your project or volunteer to step in as a maintainer or owner, allowing your project to keep going. You can also make an explicit request for maintainers.
>>>>>>> baf650ec21b2134bb75a45d635dbe3e9448573e2

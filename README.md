[![](https://img.shields.io/badge/Visit-our%20project%20page-ff69b4)](https://school.brainhackmtl.org/project/template)

# Daniel's Brainhack School Project

Team contributors: noor and michelle and tajwar and ziad and erjun

![BrainHack School](bhs2020.png)

## Summary 

To integrate the lessons learned in week 1 of Brainhack School whice still contributing work to my PhD, I have decided to change my workflow to use more reproducible tools such as Jupyter Notebook and Docker. The best integration of these tools in a Neuroscience context, for me, seems to be NiPype. I would like to move my current dMRI analysis to a NiPype workflow to facilitate replication and sharing. Because I am working with "tough to crack" data, i.e. neonatal MRI scans in asphyxiated newborns, I want to structure a pipeline I can easily modify to try out different techniques on my data (most available algorithms are not designed for these data). The framework provided by NiPype allows for standardised pipelines to be created which can be then tweaked easily and reproduced within Docker containers. Transfering my current workflow to this framework would expose me to most tools seen during week 1, with the exception of machine learning. 


## Project definition 

### Background

Neonatal MRI data isn't easily processed with standard neuroimaging tools. Typical operations such as brain extraction using FSL's BET do not typically work and must be individually tailored to each participant. This results in time confuming workflows and limited analytical possibilities. Registration between participants isn't possible with conventional tools as well and the literature suggests using group specific brain atlases and more advanced registration algorithms employing segmentation techniques. As such, working with this data requires a "testing" environment in which different tools can be tested with different parameters.


### Tools 

![NiPype](nipype-banner-bg.png)
#### NiPype 


### Data 



### Deliverables
Docker container with tools necessary to conduct standard dMRI preprocessing using FSL and DiPy. The processing itself will be written in a Jupyter Notebook and different preprocessing techniques from each software will be tested on my data and controlled for quality.
I want to challenge myself and try different FreeSurfer tools with my data. I'd like to attempt Freesurfer's surface based brain extraction, segmentation and registration tools.


## Results 

### Progress overview



### Tools I learned during this project
NiPype
Docker/Neurodocker
GitHub
Jupyter Notebook
Python
BIDS

 
### Results 

#### Deliverable 1: report template

 

#### Deliverable 2: project gallery

 
##### Other projects

 
 
## Conclusion and acknowledgement


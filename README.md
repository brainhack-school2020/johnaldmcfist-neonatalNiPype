[![](https://img.shields.io/badge/Visit-our%20project%20page-ff69b4)](https://school.brainhackmtl.org/project/template)

# Daniel's Brainhack School Project


![BrainHack School](bhs2020.png)

## Summary 

To integrate the lessons learned in week 1 of Brainhack School which still contributing work to my PhD, I have decided to change my workflow to use more reproducible tools such as Jupyter Notebook and Docker. The best integration of these tools in a Neuroscience context, for me, seems to be NiPype. I would like to move my current dMRI analysis to a NiPype workflow to facilitate replication and sharing. Because I am working with "tough to crack" data, i.e. neonatal MRI scans in asphyxiated newborns, I want to structure a pipeline I can easily modify to try out different techniques on my data (most available algorithms are not designed for these data). The framework provided by NiPype allows for standardised pipelines to be created which can be then tweaked easily and reproduced within Docker containers. Transfering my current workflow to this framework would expose me to most tools seen during week 1, with the exception of machine learning. 


## Project definition 

### Background

Neonatal MRI data isn't easily processed with standard neuroimaging tools. Typical operations such as brain extraction using FSL's BET do not typically work and must be individually tailored to each participant. This results in time confuming workflows and limited analytical possibilities. Registration between participants isn't possible with conventional tools as well and the literature suggests using group specific brain atlases and more advanced registration algorithms employing segmentation techniques. As such, working with this data requires a "testing" environment in which different tools can be tested with different parameters.


### Tools 

![NiPype](nipype-banner-bg.png)
#### NiPype 
NiPype offers a uniform platform to create and visualize neuroimaging workflows entirely in python. It makes working with specific tools from various neuroimaging toolboxes very easy, e.g. using the outputs from the SPM smoothing tool and feeding them into FSL, all from the same script. Furthermore, it makes iterating over subjects or tool parameters as easy as 1 line of code. In my context, I want to use this tool to find the best processing pipelines for my data on a per-subject basis.

### Deliverables
Docker container with tools necessary to conduct standard dMRI preprocessing using FSL and DiPy. The processing itself will be written in a Jupyter Notebook and different preprocessing techniques from each software will be tested on my data and controlled for quality.

I want to create a pipeline visualization that is more interactive.

### Tools I learned during this project

- NiPype
- Docker/Neurodocker
- GitHub
- Jupyter Notebook
- Python
- BIDS

- ... and the WSL integration of all of the above! (this is perhaps my most impressive feat)
### Results 

#### Deliverable 1: NiPype Workflow for my data
I have written a first iteration of my NiPype workflow in a Jupyter notebook. This workflow isn't yet able to fully run as I am still trouble shooting invidual steps and making sure everything is properly coded. In this process, I learned many things through the troubleshooting that usually accompanies setting up these tools. In working on this specific deliverable, I encountered the following:
- The BIDS framework may be very useful, but it requires a lot of setup to properly work on messy clinical data. In small samples, it can be easier to manually create the folder rather than using HeuDiConv.
- Speaking of HeuDiConv, it cannot read the Enhanced Dicom format provided by Philips. This is a known issue. Enhanced Dicom format is mainly used to export MRS data and other maps derived from the data. To convert from Enhanced to Classic Dicom, one needs to use the Philips MRI console (with technician).
- Within NiPype, certain interfaces may have their own little Nitpicks. For example, the BIDSDataGrabber interface, which serves to "grab" participant data and provide it to specific nodes, produces an obligatory list output which cannot be read by nodes which require a path as an input. My solution was to use another interface instead, which doesn't use the BIDS framework at all.
- The Nipype fsl.EddyCorrect interface may be deprecated (coded in python2) and causing errors. I will open a Github issue regarding this.
- NiPyPe doesn't have all DiPy tools integrated as interfaces because DiPy is entirely python based. Instead NiPype offers a DiPy base interface which can be customized to our needs. I am currently investigating this to correct my workflow.
 

#### Deliverable 2: NiPype Workflow Sankey Visualization
In working on my visualization for week 2 of BrainhackSchool, I was able to create a small code block that can turn a .dot file produced by NiPype (currently the basic hierarchical graph) into an interactive plotly Sankey diagram.
 

## Moving Forward
I am going to continue using NiPype and try to find subject-specific pipelines to produce brain images that can be registered together for group analysis. The main challenge in accomplishing this is the time it takes to QC every step for every session. To make this process easier, I will add functionality to my Plotly Sankey diagram, perhaps using Plotly.Dash to show more information about given nodes. For example: Show both input and output volumes for a given subject at a given analysis step with QC stats such as SNR.

## Conclusion and acknowledgement
BrainhackSchool 2020 was an increadible opportunity for me to get down in the mud and get my hands dirty with tools I have been trying to learn on my own for a few months. I feel the past month has jumpstarted my PhD and I will be able to produce much better science from now on.

I'd like to thank the organisers of the BrainhackSchool as well as personally thank the instructors who helped me work on my projects:
- Noor 
- Greg
- Benjamin

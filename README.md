# Laboratory-of-Neuroimaging

## Overview

LONI Software
Biomedical imaging includes a diverse array of modeling, analysis, and visualization software.

LONI Pipeline
Is a graphical framework for development, maintain, and dissemination of neuroimaging data analysis protocols. The pipeline environment offers a scalable infrastructure for graphical integration of diverse, complex, and heterogeneous software. Modules and processing workflows, includes segmentation, shap analysis, and cortical thickness workflows. 

LONI Research Protocols
LONI research protocol supports neuroimaging investigation of brain structure, function, and physiology in health and disease by using comprehensive imaging analysis. 

Techniques in Neuroimaging
CT (Roentgen-Ray Computed Tomography)
A beam of x-ray passes through the brain and is detected according to the density of the tissue encountered. Detectors positioned around the circumference of the scanner collect attenuation readings from multiple angles. A computerized algorithm reconstructs an image of each slice. 

MRI (Magnetic Resonance Imaging)
Protons in a magnetic field receive and then transmit electromagnetic energy. The strength of the transmitted energy is proportional to the number of protons in the tissue. Signal strength is modified by properties of each proton’s microenvironment, such as its mobility and the local homogeneity of the magnetic field. MRI signal can be weighted to accentuate some properties and not others. When an additional magnetic field is superimposed, one which is carefully varied in strength at different points in space, each point in space has a unique radio frequency at which the signal is received and transmitted. This makes constructing an image possible, represent the spatial encoding of frequency. 

SPECT/PET (Single Photon / Positron Emission Computed Tomography)
Radiolabeled compounds are injected and the compound photon emissions are detected. The images are made from representation of accumulated labeled compound. The compound reflects either blood flow, oxygen or glucose metabolism, or dopamine transporter concentration. 

![image](https://user-images.githubusercontent.com/28030045/53599874-d6a32180-3b6d-11e9-80f7-769812ce031f.png)
![image](https://user-images.githubusercontent.com/28030045/53599907-e3277a00-3b6d-11e9-8eb0-fc1146a362db.png)

## Features
LONI Pipeline is a free distributed system for designing, executing, monitoring, and sharing scientific workflows on grid computing architecture. Unlike other workflow processing environments, Pipeline does not require new tools an services to include or be built against the core Pipeline libraries. All data, services, and tools are referenced as external objects and restrict the scope of its applications. All tools necessary to complete an analysis protocol must first be built as external stand-alone applications or services. Pipeline allows users to create new workflow descriptions, edit existing ones, and share their work with others. 

Pipeline has cross platform compatibility, and the ability to connect from your local client to a remote server for executing processing and analysis on other operating systems. Pipeline grans developers to create their own plugins to communicate with various grid managers. Pipeline packages includes the JGDIPlugin and the DRMAAPlugin created for Sun Grid Engine, but they may work with Oracle Grid Engline, Univa Grid Engine or Son of Grid Engine. Both plugins are housed under the grid plugins directory in the installed package of Pipeline. All additional plugins can be downloaded separately. 


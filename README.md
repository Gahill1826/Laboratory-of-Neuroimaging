# Laboratory-of-Neuroimaging

## Overview

LONI includes:
-Physical in house Imaging Facilities (2 MRI, Magnetom Prisma 3T and Magnetom Terra 7T
-Secure Data Center (4 PB) 
-Visualization Archive contains a 3D brain atlases.

LONI Software:
Biomedical imaging includes a diverse array of computational modeling algorithms, visualization software tools for comprehensive and quantitative mapping of the brain. 
JAVA, C++, python based softwares packaged in LONI pipeline. 
-Visualization
-Data Management
-Surface Modeling
-Shape Analysis
-Image Processing
-Pre-processing
-Registration
-Segmentation
-Statistical Analysis

LONI Pipeline / Pipeline Web Start (PWS):
Is a free cross-platform, graphical workflow framework application (written in JAVA) for development, maintenance, dissemination, and sharing neuroimaging data analysis protocols on a (self maintained or) on-site 600 CPU computing grid (distributed systems within non-interactive workloads) to describe and aggregate executables (module) without coding in a scripting language to create complex analyses. The pipeline environment offers a scalable infrastructure for graphical integration of diverse, complex, and heterogeneous software, including, modules and processing workflows, includes segmentation, sharp analysis, and cortical thickness workflows. LONI supercomputing environments automatically parallelize data-independent programs. Additionally, LONI Pipeline can run in a client-server mode, allowing access to compute servers running analysis software from a dedicated machine.


Unlike other workflow processing environments, Pipeline does not require new tools and services to include or be built against the core Pipeline libraries. All data, services, and tools are referenced as external objects. This allows the Pipeline to run as a light-weight middleware, but at the same time, restrict the scope of its applications. For example, the Pipeline does not provide a set of internal core libraries, filters, and processes for image processing. All tools necessary to complete an analysis protocol must first be built as external stand-alone applications or services, the interface methods are then described in Pipeline XML language. LONI Cranium server contains multiple prebuilt XML modules and workflows software applications, including FMRIB Software Library (image analysis and statistical tools written in C++for functional and diffusion MRI data), Analysis of Functional NeuroImages (open-source environment written with C for processing and displaying fMRI data), and FreeSurfer. Pipeline allows users to create new workflow descriptions, edit existing ones, and share their work with others.
Pipeline has cross platform compatibility, and the ability to connect from your local client to a remote server for executing processing and analysis on other operating systems. Pipeline grans developers to create their own plugins to communicate with various grid managers. Pipeline packages includes the JGDIPlugin and the DRMAAPlugin created for Sun Grid Engine, but they may work with Oracle Grid Engline, Univa Grid Engine or Son of Grid Engine. Both plugins are housed under the grid plugins directory in the installed package of Pipeline. All additional plugins can be downloaded separately.

*WARNING* LONI Pipeline will only work with Java 8 192, current Java 8 201 will not work.
- How do I uninstall Java on my Mac? https://java.com/en/download/help/mac_uninstall_java.xml
- How do I uninstall Java on my Windows computer? https://java.com/en/download/help/uninstall_java.xml
- Download and install an older version of Java from the Java SE 8 Archive Downloads page. 
https://www.oracle.com/technetwork/java/javase/downloads/java-archive-javase8-2177648.html

LONI Research Protocols:
LONI research protocol supports neuroimaging investigation of brain structure, function, and physiology in health and disease by using comprehensive imaging analysis. 

Brain Atlases (of human and animal) (Alzheimer is the largest open database)
LONI brain atlases were created from a desire to standardize brain image databases and understand brain spatial characteristics; structure, features and relationships with other features, shape and the associated characteristics, and region of functional activation. These characteristics are used to index schemes and nomenclature systems. LONI brain atlas integrates information by applying validation, warping algorithms, indexing schemes and nomenclature systems on multiple representations of the brain are collected to increase confidence in statistical and visual power. LONI atlases is separated into mapping of the whole brain and maps of groups or populations. 


LONI Debabeler (JAVA Image I/O Plugin Architecture 1.4):
Uses appropriate file translations to automatically convert (ANALYZE, MINC, and variants of DICOM, and proprietary formats used for fMRI and MRS files) neuroimaging software packages file format between each pair of linked packages. File translations consists of Debabeler GUI to visualize the translation. The data translation engine: 1. Identify image file metadata characteristics; 2. Group similar data together according to user-define values from metadata; 3. Translate images by reading metadata, pixel data, mapping data into specified output file format. Translations steps includes arithmetic, string operations, image pixel manipulations, and physical system transformations. Allows users the ability to create new translations by editing common “core” translations. 

Unique/Purpose: Visual programming environment allows an easy alternative way to alter existing translations of data. Source code in “LONI Image I/O Plugin download”. Medical imaging data is collected and encoded into a specified file format. Despite efforts to standardize file formats, there are invariably significant difference in elements available, elements stored, and interpretation of elements. Knowing file format does not reveal appropriately method to extract and use metadata. LONI Debabeler addresses these issues by enabling users easier access to image metadata and providing users a flexible and programmable environment in which to manipulate metadata between file formats. 

Techniques in Neuroimaging:
CT (Roentgen-Ray Computed Tomography)
A beam of x-ray passes through the brain and is detected according to the density of the tissue encountered. Detectors positioned around the circumference of the scanner collect attenuation readings from multiple angles. A computerized algorithm reconstructs an image of each slice. 

MRI (Magnetic Resonance Imaging)
Protons in a magnetic field receive and then transmit electromagnetic energy. The strength of the transmitted energy is proportional to the number of protons in the tissue. Signal strength is modified by properties of each proton’s microenvironment, such as its mobility and the local homogeneity of the magnetic field. MRI signal can be weighted to accentuate some properties and not others. When an additional magnetic field is superimposed, one which is carefully varied in strength at different points in space, each point in space has a unique radio frequency at which the signal is received and transmitted. This makes constructing an image possible, represent the spatial encoding of frequency. 

SPECT/PET (Single Photon / Positron Emission Computed Tomography)
Radiolabeled compounds are injected and the compound photon emissions are detected. The images are made from representation of accumulated labeled compound. The compound reflects either blood flow, oxygen or glucose metabolism, or dopamine transporter concentration. 

![image](https://user-images.githubusercontent.com/28030045/53599874-d6a32180-3b6d-11e9-80f7-769812ce031f.png)
![image](https://user-images.githubusercontent.com/28030045/53599907-e3277a00-3b6d-11e9-8eb0-fc1146a362db.png)

## LONI Image and Data Archive (IDA)
LONI Image and Data Archive (IDA) is a web-browser environment to aggregate, archive, and disseminate neuroimaging data. IDA accommodates MRI, fMRI, PET, MRA, DTI, and other imaging modalities. The image archival processes begin with LONI Debabeler de-identification applet and local encryption, validation, and finally transmission to LONI IDA. Debabeler removes and replace potentially identifying subject information’s from image headers. The IDA automatically extracts relevant metadata from de-identified image files and allows data to be search of archival. On arrival the data is stored in LONI compliance with patient-privacy regulations, fault tolerant storage area network and the database are populated with relevant metadata attributes.  Archive accepts (type 1 headers) DICOM, GE, Philips, HRRT, and ECAT files, and (type 2 headers) Analyze and MINC files. All data are stored on redundant servers with daily and weekly on- and off-site backups. Data can be downloaded and /or streamed into LONI Pipeline workflow environment for processing and analysis. 

Creating an account is free and straight forward. 
Includes dynamic (beta) “Advanced Image search” function. 
Image metadata are stored and extracted in .csv format. 
Image data details contains weighting, pulse sequence, acquisition type, etc. 
Image collection: view, remove, regroup or download single images and entire collections of either personnel and shared collections in Analyze, NIfTI, NiFTI 4D, MINC format. 

Images can be viewed with IDA Image Viewer (Java based) software. IDA image metadata are stored in .csv format. 

(Low) System Requirements: Internet access, support IE, Mozilla, Safari, and Chrome web brower, Java plug-in (version 1.5 or higher), and approved IDA account.

Downloading IDA image
Including feature projects from different groups and collaborating institutions.
Include internal download Manager are incredibly useful, due to the software ability to continue download from disrupted connections. Some image sets are incredibly huge. 

Single Archive process upload one more file from a single subject. 
Batch Archive process upload multiple subjects and image series in a batch with similar or different file formats and modalities. 

IDA archive
Two step process (de-identification and transmission)
Debabler (Java applet) removes and replace data image header
An option to manually valid the de-identify image before transmission
All relevant image metadata are stored in IDA database after transfer. 

Data processing
BrainSuite2 – is a LONI C++, MRI image analysis tool designed for identifying tissue types and surfaces in MR images of human head. Specifically designed to guide users through the process of cortical surface extraction. 

LONI data center storage environment includes 4096 processor core and 38 Terabytes of memory, and storage cluster of 66 nodes with 7.5 Petabytes of high-performing storage.  

Modules:
Freesurfer:
A shell script (recon-all) brain imaging software package for analyzing MRI data. It is an important tool in functional white matter brain mapping and facilitates visualization of highly folded cerebral cortex. By conducting volume and surface-based analysis. 

Bioconductor:
An open development software project based on R programming language for analysis and comprehension of genomic data generated by wet lab experiments. Statistical techniques includes linear and nonlinear modeling, cluster analysis, prediction, resampling, survival analysis, and time series analysis. 

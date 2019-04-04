## Overview
Relevant LONI: Brain Atlas, Databases, and Software packages. 

LONI Software Categories: (JAVA, C++, and Python)
-Visualization
-Data Management
-Surface Modeling
-Shape Analysis
-Image Processing
-Pre-processing
-Registration
-Segmentation
-Statistical Analysis

LONI Pipeline Key Features:
-Preprocessing steps common to both subcortical and cortical analyses
-Flexible and simple user interface graphical environment for constructing complex scientific analyzes of data. 
-Input and output files and binaries on remote servers as well as local computer within a single workflow
-Cross Platform Compatible
-Pipeline Library
-Tools and modules are cached on user computer enabling offline workflow construction. 
- Grid and DB interfaces (Oracle Grid Engine)
-Cloud server, Pipeline Server on Amazon EC2 http://pipeline.loni.usc.edu/products-services/pipeline-server-on-ec2/
-- Conditional and iterating modules
--Tools usage and server status charts
--Design, validation, and execution of modules, and complete workflows
--Automated imaging and meta-data format processing
--Distributed Pipeline Client Server
1.	Backend grid management resources (Oracle Grid Engine)
2.	Pipeline server
3.	Platform agnostic computational infrastructure (imaging and informatics software tools)

LONI Pipeline background:
LONI is a client server distributed computational environment that facilitates visual graphical construction, validation, and dissemination of data analysis protocols. Additionally, LONI pipeline is a free cross-platform graphical workflow framework application (written in JAVA) primarily aimed at neuroimaging researchers development, maintenance, dissemination, and sharing neuroimaging data analysis protocols on a self-maintained, on-site 600 CPU computing grid (distributed systems) with4 petabyte storage to describe and aggregate modules without coding in a scripting language. The pipeline environment offers a scalable infrastructure for graphical integration of diverse, complex, and heterogeneous software, including, modules and processing workflows, includes segmentation, sharp analysis, and cortical thickness workflows. LONI supercomputing environments automatically parallelize data-independent programs. Furthermore, LONI Pipeline can run in client-server mode, allowing access to compute servers running analysis software from a dedicated machine.
LONI Pipeline Web Start (PWS) (in beta) is an alternative way to utilize pipeline packages as a web-service tool without downloading the software.  
http://pipeline.loni.usc.edu/products-services/pws/

Unlike other workflow processing environments, LONI Pipeline does not require new tools and services to include or be built against the core Pipeline libraries. All data, services, and tools are referenced as external objects. This allows the Pipeline to run as a light-weight middleware, but at the same time, restrict the scope of its applications. For example, the Pipeline does not provide a set of internal core libraries, filters, and processes for image processing. All tools necessary to complete an analysis protocol must first be built as external stand-alone applications or services, the interface methods are then described in Pipeline XML language. LONI Cranium server contains multiple prebuilt XML modules and workflows software applications, including FMRIB Software Library (image analysis and statistical tools written in C++for functional and diffusion MRI data), Analysis of Functional NeuroImages (open-source environment written with C for processing and displaying fMRI data), and FreeSurfer. Pipeline allows users to create new workflow descriptions, edit existing ones, and share their work with others.
Pipeline has cross platform compatibility, and the ability to connect from your local client to a remote server for executing processing and analysis on other operating systems. Pipeline grants developers to create their own plugins to communicate with various grid managers. Pipeline packages includes the JGDIPlugin and the DRMAAPlugin created for Sun Grid Engine, but they may work with Oracle Grid Engine, Univa Grid Engine or Son of Grid Engine. Both plugins are housed under the grid plugins directory in the installed package of Pipeline. All additional plugins can be downloaded separately.

*WARNING* LONI Pipeline will only work with Java 8 192, current Java versions will not work. forums Pipeline dependency on JAVA version 8.192 may change due to an automatic update on 2019. 
- Download and install an older version of Java from the Java SE 8 Archive Downloads page. 
https://www.oracle.com/technetwork/java/javase/downloads/java-archive-javase8-2177648.html

LONI Pipeline Overview Workflow:
1.	Anonymize subject
2.	Preprocess (cortical and subcortical) images
a.	Subcortical 
i.	Structure delineation
ii.	Anonymizing the subject
iii.	Registering the brain to an Atlas
iv.	(Potential) Bias field correction
b.	Cortical
i.	“Masking” is a binary file covering the region of the MRI file of interest that removes the skull and extra-cortical tissue, to divide the brain into hemispheres, or to isolate/represent Region Of Interest (ROI). LONI tools to generate and/or edit existing masks: BrainSuite2 (Analyze format), Display (Minc format)
3.	Processing Steps for Cortical Surface Extraction and Sulcal Analysis (Powerpoint)
a.	Extracting the cortical surface
b.	Drawing sulcal lines (Selineate the sulci for each subject.)
c.	Cortical pattern matching (page 69) 
i.	flat mapping (transforms an image 3D object file into a 2D flatmap of the cortex which is sored as a 2D uvl file)
ii.	warping (the averaging of all sulci are used as anchors to warp the flatmaps of individual cases into an average space)
iii.	reinflation (the warped flatmaps are reinflated to 3D UCF files.)
4.	Separation of Gray Matter, White Matter, and CSF
a.	Segmentation, tissue classification, defines a volume by tissue type (density or thickness)
i.	3-class tissue segmentation (most commonly used) (1. Gray matter, 2. White matter, and 3. Cerebral spinal fluid.) 
ii.	(Potential) 5-class tissue segmentation (4. Gray matter with White matter overlap, 5. Gray matter and Cerebral spinal fluid)
iii.	Signal values are evaluated according to frequency, while measuring differences across the whole brain and classifying the signal values accordingly to tissue type. 
5.	Cortical surface Analyses
a.	Sulcal analysis
b.	Complexity of cortical Surface
c.	Local brain size
d.	Gray matter density
e.	Maps of cortical thickness

Anonymize Subject:
LONI Debabbler (JAVA Image I/O Plugin Architecture 1.4) (Main LONI Workflow):
Uses appropriate file translations (e.g. Analysis of functional neuroimages) to automatically convert (ANALYZE, MINC, and variants of DICOM, and proprietary formats used for fMRI and MRS files, NifTI, and etc) neuroimaging software packages file format between each pair of linked packages. File translations consists of Debabbler GUI to visualize the translation. 
The data translation engine: 
1. Identify image file metadata characteristics; 
2. Group similar data together according to user-define values from metadata; 
3. Translate images by reading metadata, pixel data, mapping data into specified output file format. 
Translations steps includes arithmetic, string operations, image pixel manipulations, and physical system transformations. Allows users the ability to create new translations by editing common “core” translations. 
Medical imaging data is collected and encoded into a specified file format. Despite efforts to standardize file formats, there are invariably significant difference in elements available, elements stored, and interpretation of elements. Knowing file format does not reveal appropriately method to extract and use metadata. LONI Debabbler addresses these issues by enabling users easier access to image metadata and providing users a flexible and programmable environment in which to manipulate metadata between file formats.

LONI Pipeline Notable Workflow Features: http://pipeline.loni.usc.edu/learn/quick-start/
- Building or using pre-built modules 
- Connecting modules (Inputs on top, Outputs on bottom) (Initial checking prevents file types from connecting to number type parameters)
- Smartline: Automatic file conversion tool, enabling connection between different image formats. E.G. Analyze Image (.img), NIFT (nii), or MINC (mnc)
- Establish (local) Data sources and data sinks OR Cloud sources and Cloud sinks (Tools > Database & Cloud Storage > Cloud Storage tab). This method is used when users want to use a single piece of data as an input to multiple modules in a workflow, or make the workflow easier to understand. 
- Setting parameter values (right clicking input/output)
- Processing multiple inputs
- Adding Metadata: incorporate imaging data and non-imaging meta-data together with Conditional criteria from modules. 
- Enable/Disable parameters
-(automatic) Validation and several statuses (user feedback)

(Human and Animal) Brain Atlases *Alzheimer (ADNI) is LONI largest open database
http://adni.loni.usc.edu/

LONI brain atlases is a standardize brain image databases to understand brain spatial characteristics; structure, features and relationships with other features, shape and the associated characteristics, and region of functional avctivation. These characteristics are used to index schemes and nomenclature systems. LONI brain atlas integrates information by applying validation, warping algorithms, indexing schemes and nomenclature systems on multiple representations of the brain are collected to increase confidence in statistical and visual power. LONI atlases is separated into mapping of the whole brain and maps of groups or populations. 
 

## LONI Image and Data Archive (IDA): 

Image and Data Archive (IDA) was developed in 2002 for multi-centered research studies. A web-browser environment to aggregate, archive, share, and disseminate neuroimaging data. IDA accommodates MRI, fMRI, PET, MRA, DTI, and other imaging modalities. Neuroimaging data files are categorized as cluster nodes for parallel downloading and improving (time) efficiency.  The image archival processes begin with Debabbler (de-identification applet and local encryption), validation, and finally transmission to LONI IDA. Debabbler removes and replace potentially identifying subject information’s from image headers. *Removes critical information such as neuroimaging machine model and time stamp. * The IDA automatically extracts and store relevant metadata from de-identified image files. (Metadata are stored as CSV or XML files) On arrival the data is stored in LONI (compliance with federal patient-privacy regulations) fault tolerant storage area network and the databases are populated with relevant metadata attributes. Image metadata includes weighting, pulse sequence, acquisition type, etc. Archive contains (type 1 headers) DICOM, GE, Philips, HRRT, and ECAT files, and (type 2 headers) NIfTI, NiFTI 4D, Analyze and MINC files. Images are viewed with IDA Image Viewer (Java based) software. All data are stored on redundant servers with daily and weekly on- and off-site backups. Data can be downloaded and /or streamed into LONI Pipeline workflow environment for processing and analysis. 
IDA archive
Two step process (de-identification and transmission)
Debabler (Java applet) removes and replace data image header
An option to manually valid the de-identify image before transmission
All relevant image metadata are stored in IDA database after transfer. 

Alzheimer’s Disease Neuroimaging Initiate (ADNI)
Most developed and populated open cohort in LONI. Goal of the database is to develop biomarkers of the disease and advance the understanding of AD pathophysiology, improve diagnostic methods for early detection of AD and improve clinical trials design. Additional goals are examining the rate of process for both mild cognitive impairment and Alzhemer’s disease, as well as building a large repository of clinical and imaging data.  







MISC:
fMRI First Level Analyses
1.	Combine functional volumes
2.	Skull stripping
3.	Registration
4.	Define model
5.	Create activation map

 
Data pre- and processing (DEMO)
AIR (Automated Image Registration) Registration - An automated (3D or 2D) image registration algorithm that generates a transformation matrix and applies it to move MRI images of different modalities either between or across subjects into the standard space. 
BrainSuite2 – is a LONI C++, collection of analysis tools designed to process raw MRI of the human head for identifying tissue types and surfaces. BrainSuite was specifically designed to guide users through the process of cortical surface extraction. Workflow objective is to generate a file containing labels for gray matter, white matter, and cerebrospinal fluid.   
Brain Surface Extraction: Removes non-brain tissue from the MRI using a combination of anisotropic diffusion filtering (reduce image noise without blurring edges), MArr-Hildreth edge detection (digital image edges detection), and mathematical morphology (processing of geometrical structures).
•	Skull strip the brain volume.
•	Perform Inhomogeneity correction.
•	Prepping the image for the tissue classifier. 
•	Skull-strip a brain volume in MNC file format.
•	Utilized Brain Surface Extractor (BSE) skull stripping algorithm.  
•	Use NIFTI input data or analyze file format.
•	Smart line automatically converts MRI, MINC file to match BSE requirements. 

 
 
 
 


Multitracer - is a LONI JAVA applications that is useful for manual editing and viewing MRI images in three dimensions. The tools allow anatomic structures to be traced and the tracings to be saved in a format that facilitates review and revision. Multitracer simple measurements (e.g., areas, volumes, lengths, widths, surface areas, etc.) as well as tools that resample the tracings into surface meshes that can be analyzed and displayed in three-dimensions. Edits from Multitracer is a prerequisite for intersubjective registration tools used to creates volume deformation parameters. Additionally, Multitracer allows manually delineated contours to be traced when used by the surface parameterization projects. 

LONI data center storage environment includes 4096 processor core and 38 Terabytes of memory, and storage cluster of 66 nodes with 7.5 Petabytes of high-performing storage.  

Skull Stripping:
Generate whole-brain masks by running MR data through BSE and BET, then use FSL Maths to combine the results of these skull-stripping algorithms in two distinct ways. This workflow combines components from the BrainSuite and FSL packages. The aim of the process is to perform skull stripping along two distinct paths and to compare the results in order to determine the better of the two methods. As a first step, we run the raw brain volume through both Brain Surface Extractor and BET, which execute unique skull stripping algorithms. The process then splits into two independent segments. In one branch, the idea is to intersect the whole-brain masks generated by these tools in order to generate a tightly skull stripped result. In the other, we union the masks to achieve more tolerant skull stripping. In this workflow, we will also make use of Smartlines, a Pipeline feature which takes care of any file format compatibility issues.
•	Generate whole-brain masks by running MR data through BSE and BET, then FSL. 
•	Perform skull stripping along two distinct paths 

 b
Modules:
Freesurfer:
A shell script (recon-all) brain imaging software package for analyzing MRI data. It is an important tool in functional white matter brain mapping and facilitates visualization of highly folded cerebral cortex. By conducting volume and surface-based analysis. 

Bioconductor:
An open development software project based on R programming language for analysis and comprehension of genomic data generated by wet lab experiments. Statistical techniques includes linear and nonlinear modeling, cluster analysis, prediction, resampling, survival analysis, and time series analysis. 

Techniques in Neuroimaging:
CT (Roentgen-Ray Computed Tomography)
A beam of x-ray passes through the brain and is detected according to the density of the tissue encountered. Detectors positioned around the circumference of the scanner collect attenuation readings from multiple angles. A computerized algorithm reconstructs an image of each slice. 

MRI (Magnetic Resonance Imaging)
Protons in a magnetic field receive and then transmit electromagnetic energy. The strength of the transmitted energy is proportional to the number of protons in the tissue. Signal strength is modified by properties of each proton’s microenvironment, such as its mobility and the local homogeneity of the magnetic field. MRI signal can be weighted to accentuate some properties and not others. When an additional magnetic field is superimposed, one which is carefully varied in strength at different points in space, each point in space has a unique radio frequency at which the signal is received and transmitted. This makes constructing an image possible, represent the spatial encoding of frequency. 

SPECT/PET (Single Photon / Positron Emission Computed Tomography)
Radiolabeled compounds are injected and the compound photon emissions are detected. The images are made from representation of accumulated labeled compound. The compound reflects either blood flow, oxygen or glucose metabolism, or dopamine transporter concentration. 

MISC:

(Low) System Requirements: Internet access, support IE, Mozilla, Safari, and Chrome web brower, Java plug-in (version 1.5 or higher), and approved IDA account.
Downloading IDA image
Including feature projects from different groups and collaborating institutions.
Include internal download Manager are incredibly useful, due to the software ability to continue download from disrupted connections. Some image sets are incredibly huge. 
Single Archive process upload one more file from a single subject. 
Batch Archive process upload multiple subjects and image series in a batch with similar or different file formats and modalities. 
KEY:
ICBM: International Consortium for Brain Mapping
AIR: Analyze Image Format
Brain Viewer, view scientific and medical imaging data in 3D with WebGL. http://pipeline.loni.usc.edu/products-services/brain-viewer/
http://pipeline.loni.usc.edu/products-services/brain-book/



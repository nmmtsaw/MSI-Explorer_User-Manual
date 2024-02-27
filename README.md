# MSI-Explorer-Manual

The MSI-Explorer, a napari plug-in is a powerful tool designed for targeted biochemical annotations in MSI data. This user manual provides a comprehensive guide on how to install, use, and explore the functionalities of the plug-in within the napari platform. It covers data import, visualization, mean intensity calculation, region of interest (ROI) analysis, annotation with selected database and pre-processing such as noise reduction and normalization. 

[MSI-Explorer] 
 
## Installation
In anaconda prompt, create the environment by typing this. In this case, “napari-env” is the name of the environment. Any name can be given.

    conda create -y -n napari-env -c conda-forge python=3.9 

Then, activate the environment.
   
    conda activate napari-env 

Install napari by using this commend.
   
     pip install "napari[all]"

You can install `MSI-Explorer` via [pip]:
   
     pip install MSI-Explorer

  
When installation finished, it is ready to use napari.
   Just type napari and napari window will pop up.
   Choose the MSI-Explorer plug in.
<img src="https://github.com/nmmtsaw/MSI-Explorer-Manual/assets/127961719/24040366-37c6-4aeb-ba0e-43bf4bd32aa1." width="800" height="400">

### 1. Uploading and visualization of mass spectrometry imaging data
- Select imzml file using `Load imzML`.
- Metadata can be checked by `View Metadata`.
<img src="https://github.com/nmmtsaw/MSI-Explorer-Manual/assets/127961719/9e3db84f-5411-4049-805a-e6fe9251e14a." width="800" height="350">

<img src="https://github.com/nmmtsaw/MSI-Explorer-Manual/assets/127961719/7cd6aa18-f0e3-4d72-8ff7-1d206c2f30db." width="800" height="350">


####
Upon uploading profile mode data, a pop-up appears prompting you to convert it to centroid mode.
Selecting `Yes` converts the data, while `No` keeps it in its original profile format.

![profile_centroid](https://github.com/nmmtsaw/MSI-Explorer-Manual/assets/127961719/5eecf5c2-e9b5-45da-a620-6dfaad058faf)

### 2. Calculating mean (average) intensity
- To calculate the mean spectrum, click on `Show true mean spectrum`.
- `Show image` to see the image view (Or it will automatically change.)
- To export as .csv file, click `Export spectrum data`.
- To save the spectrum plot, click `Export spectrum plot`.
- To export as .csv file, click `Export spectrum data`.
<img src="https://github.com/nmmtsaw/MSI-Explorer-Manual/assets/127961719/3861b4cd-99e6-4fb5-be85-475beab60740." width="300" height="450">


#### 2.1. Calculating mean (average) intensity of selected m/z value
To focus on a specific m/z value, zoom in on the spectrum plot. The figure will be as
shown as below.
<img src="https://github.com/nmmtsaw/MSI-Explorer-Manual/assets/127961719/936b4e2e-dc25-4b14-9915-a38ca45c7c02." width="800" height="350">

It is recommended to use `Multi` panel view.
The image can be displayed by `Show image` and the data can be exported as `.csv` file by using `Export spectrum data`.

### 3. Pre-processing
The pre-processing capabilities of MSI-Explorer enhance data quality and prepare MSI data for downstream analysis. Pre-processing steps involve: 

#### (a) Normalization
The normalization methods that the user can apply are 
- Total ion current (TIC)
- Root mean square (RMS)
- Medium
- Reference peak (or internal standard)
<img src="https://github.com/nmmtsaw/MSI-Explorer-Manual/assets/127961719/613ec41b-5765-429e-9aa7-ad296ad93702." width="800" height="350">


#### (b) Noise reduction
Users can choose their desired level of noise reduction (shown as a percentage) for their experiment. 
<img src="https://github.com/nmmtsaw/MSI-Explorer-Manual/assets/127961719/ace0f5d2-43fa-4338-af9b-130529b17ec5." width="800" height="350">


After pre-processing steps are chosen, click `Execute` and `Show true mean spectrum` to calculate the mean intensity.

The fiugre shows the spectrum and image of the TIC normalization with 3% noise reduction. 
<img src="https://github.com/nmmtsaw/MSI-Explorer-Manual/assets/127961719/57f3550f-8d88-46c0-832a-fed75d364936." width="800" height="350">


### 4. Database
To use the database search, click on `Select` and a pop-up window will appear. Then,
click on `Metabolite_database` which is build-in database and `Confirm`.

<img src="https://github.com/nmmtsaw/MSI-Explorer-Manual/assets/127961719/91bc3b37-59d9-4c2c-85f5-ab790d8678a0." width="300" height="450">

The features of the database function are
1. Charge (neutral, positive or negative)
2. Adduct (based on the charge chosen)
3. Range of the m/z value for the image display
4. custom search with molecule name or m/z value
<img src="https://github.com/nmmtsaw/MSI-Explorer-Manual/assets/127961719/77f0f0ba-4531-4532-9aa8-14d964d69fa2." width="300" height="450">

Users can customize the database with exact mass, molecule name, or molecular formula. The format should be as shown in the table and the headers are not needed in the database.

Exact mass | Molecule name | Molecula formula
------- | -------- | --------
176.0950 | Cotinine | C10H12N2O
174.1117 | Arginine | C6H14N4O2
244.0881 | Biotin | C10H16N2O3S

### 5. Region of interest (ROI) selection
- To select the ROI, click on `Select ROI or mean spectrum`. Adjust the brush size and label color. You can fill the area by using paint icon. 
- Then click on the `Calculate ROI mean spectrum`.
- You can export as `.csv` file by using `Export spectrum data`.
- If one m/z is needed, just zoom-in the spectrum plot window and export.
- Before selecting the second ROI, remove the first selected area by using eraser or label 0.

<img src="https://github.com/nmmtsaw/MSI-Explorer-Manual/assets/127961719/2464e40e-21cb-484a-8fe6-33b7763b8c71." width="800" height="350">

   








[pip]: https://pypi.org/project/pip/
[MSI-Explorer]: https://www.napari-hub.org/plugins/MSI-Explorer

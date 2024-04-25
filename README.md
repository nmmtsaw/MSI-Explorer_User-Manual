# User Manual

The MSI-Explorer, a napari plugin is a powerful tool designed for targeted biochemical annotations in MSI data. This user manual provides a comprehensive guide on how to install, use, and explore the functionalities of the plug-in within the napari platform. It covers data import, visualization, mean intensity calculation, region of interest (ROI) analysis, annotation with selected database and pre-processing such as noise reduction and normalization. 

[MSI-Explorer] 
![Presentation1_napari](https://github.com/nmmtsaw/MSI-Explorer_User-Manual/assets/127961719/7f7f1ab9-8634-4902-bb5d-319aea4636a7)

 
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
   Choose the MSI-Explorer plugin.

## Usage
Start napari from the console with:

    napari

Navigate to `Plugins -> MSI-Explorer (MSI-Explorer)`
![Plugin](https://github.com/nmmtsaw/MSI-Explorer_User-Manual/assets/127961719/104718fa-227e-4117-9b52-f674a265d218)

## Re-opening environment for napari plugin
Activate the environment.
   
    conda activate napari-env 

Start napari from the console with:

    napari  

### 1. Uploading and visualization of mass spectrometry imaging data
- Select imzml file using `Load imzML`.
- Metadata can be checked by `View Metadata`.
![Uploading MSI data_v1](https://github.com/nmmtsaw/MSI-Explorer_User-Manual/assets/127961719/a4783643-cf8e-4c68-af8e-03f264a48573)

![Visualization of MSI data_v1](https://github.com/nmmtsaw/MSI-Explorer_User-Manual/assets/127961719/5e37c375-d430-419a-9038-9980e858c482)



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

![Calculating mean spectrum](https://github.com/nmmtsaw/MSI-Explorer_User-Manual/assets/127961719/2e921e00-75cf-4925-a9de-01d093277a06)

![Calculating mean spectrum_v1](https://github.com/nmmtsaw/MSI-Explorer_User-Manual/assets/127961719/19a713e3-a9ff-4e0c-be6b-545fb29991c6)

#### 2.1. Calculating mean (average) intensity of selected m/z value
To focus on a specific m/z value, zoom in on the spectrum plot. The figure will be as
shown as below.


![Calculating mean spectrum specific mz_v1](https://github.com/nmmtsaw/MSI-Explorer_User-Manual/assets/127961719/ba47080a-f439-4dc2-96b9-1f82ee5acbc3)


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

![normalization_v1](https://github.com/nmmtsaw/MSI-Explorer_User-Manual/assets/127961719/972b30af-8425-46e4-bb54-705df52c725a)


#### (b) Noise reduction
Users can choose their desired level of noise reduction (shown as a percentage) for their experiment. 
![Noise reduction_v1](https://github.com/nmmtsaw/MSI-Explorer_User-Manual/assets/127961719/9ce5e428-fe46-4f5f-a53f-7186c9f5ca8c)


#### (c) Hotspot removal
Hotspot removal can also be applied using a low quantile threshold of 0% and a high quantile threshold of 99.99%. 
![hotspot removal_v1](https://github.com/nmmtsaw/MSI-Explorer_User-Manual/assets/127961719/c9d279fa-d03b-499d-857d-6953ba7ea253)

After pre-processing steps are chosen, click `Execute` and `Show true mean spectrum` to calculate the mean intensity.

The fiugre shows the spectrum and image of the TIC normalization with 3% noise reduction and 99.90% quantile hotspot removal.
![pre-processed_v1](https://github.com/nmmtsaw/MSI-Explorer_User-Manual/assets/127961719/d1068382-f6e2-4af9-9c5b-949fb87ac90c)




### 4. Database
To use the database search, click on `Select` and a pop-up window will appear. Then,
click on `Metabolite_database` which is build-in database and `Confirm`.

![Database](https://github.com/nmmtsaw/MSI-Explorer_User-Manual/assets/127961719/928fa260-196e-4034-8ddd-0944c751c77e)


The features of the database function are
1. Charge (neutral, positive or negative)
2. Adduct (based on the charge chosen)
3. Range of the m/z value for the image display
4. custom search with molecule name or m/z value
   
![Database_search](https://github.com/nmmtsaw/MSI-Explorer_User-Manual/assets/127961719/ca7d943a-1b6b-4cba-bf4d-934ee574cc61)

Users can customize the database with exact mass, molecule name, or molecular formula. The format should be as shown in the table and the headers are not needed in the database.

Exact mass | Molecule name | Molecula formula
------- | -------- | --------
176.0950 | Cotinine | C10H12N2O
174.1117 | Arginine | C6H14N4O2
244.0881 | Biotin | C10H16N2O3S

#### The build-in database can be found by

  
    pip show MSI-Explorer
   
  
and then find the location from there.

### 5. Region of interest (ROI) selection
- To select the ROI, click on `Select ROI or mean spectrum`. Adjust the brush size and label color. You can fill the area by using paint icon. 
- Then click on the `Calculate ROI mean spectrum`.
- You can export as `.csv` file by using `Export spectrum data`.
- If one m/z is needed, just zoom-in the spectrum plot window and export.
- Before selecting the second ROI, remove the first selected area by using eraser or label 0.

![ROI selection_v1](https://github.com/nmmtsaw/MSI-Explorer_User-Manual/assets/127961719/e79ca007-a0b5-4ba7-8cea-ae5e8ad6dd7d)


   
### Updating MSI-Explorer plugin
The method for updating the MSI-Explorer plugin depends on the initial installation method. Here's a breakdown of the options:

- Installed via pip:
To uppgrade existing version: Use

 
     pip install MSI-Explorer --U
      
 
 or 
 
    pip install MSI-Explorer --upgrade 
 
 
- Installed via napari Plugin Browser:
Update within napari: If a newer version exists, you can update directly through the napari plugin browser.

- Installed locally with


    pip install -e .
  

No update needed: Simply replace the existing directory with the updated one containing the latest plugin code.

- Installed locally with pip install .

Uninstall existing version: Run 


   pip uninstall MSI-Explorer 


to remove the current installation.

Install updated version: Navigate to the directory containing the updated plugin code and run pip install .. 
Consider adding the -e flag during installation for future updates via the local directory method. 
This flag enables development mode, allowing updates through 

  pip install -U 
  
  or 
  
   pip install --upgrade.






[pip]: https://pypi.org/project/pip/
[MSI-Explorer]: https://www.napari-hub.org/plugins/MSI-Explorer

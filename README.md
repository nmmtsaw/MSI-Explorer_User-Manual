# MSI-Explorer-Manual

The MSI-Explorer, a napari plug-in is a powerful tool designed for targeted biochemical annotations in MSI data. This user manual provides a comprehensive guide on how to install, use, and explore the functionalities of the plug-in within the napari platform. It covers data import, visualization, mean intensity calculation, region of interest (ROI) analysis, annotation with selected database and pre-processing such as noise reduction and normalization. 

## Uploading and visualization of MSI data
1. In anaconda prompt, create the environment by typing this. In this case, “napari-env” is the name of the environment. Any name can be given.

    ``` conda create -y -n napari-env -c conda-forge python=3.9 ```

2. Then, activate the environment.
   
   ``` conda activate napari-env ```

3. Install napari by using this commend.
   
   ``` pip install "napari[all]" ```

4. You can install MSI-Explorer via pip:
   
    ```  pip install MSI-Explorer ```

   https://www.napari-hub.org/plugins/MSI-Explorer

5. When installation finished, it is ready to use napari.
   Just type napari and napari window will pop up.
   Choose the MSI-Explorer plug in.

6. - Select imzml file using "Load imzML".
   - Metadata can be checked by "View Metadata".


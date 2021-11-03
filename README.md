# Brain_ROIS_ID

## Objective

To anatomically identify a region of interest (ROI) in a nifty brain image mask.

## Description

This script compares an input brain image mask, in the nifty format (.nii), with the AAL3v1 brain parcellation [1], to anatomically name the ROIs of the input image. The result will be an CSV file, with four columns:
- roi -> The index number of the ROI in the input brain image;
- Anatomical Description -> The name of the region the ROI is a part of;
- Hemisphere -> If this region is located at the right or left hemisphere or non-lateralized;
- Percentage -> how much of the region are contained in the ROIs
  
In the input image, null values are considered empty areas (or no brain areas).

### Parameters Descriptions

The parameters you'll have to change are in the Head section:

- baseatlas_path -> The location of the reference brain image file [string];
- baseatlasinfo_path -> The location of the .mat file, with the anatomical information of the reference image [string];
- targetaltas -> The input brain image mask [string];
- outputfolder_csv -> The output csv file [string];
    
### More

The reference files are located at the GitHub page https://github.com/LexC/Brain_ROIS_ID/. And, as an example, I added a functional brain atlas (Shen_2mm.nii)[2] on the github page, so you can test out the script.

## Limitations:

For this specific script, the input image must be in the MNI space, with an isotropic voxel size of 1 or 2mm. But, by changing the reference Atlas and it's information file, this limitation can be overcome - just make sure that the information file are in the same format.

## References:

1. Rolls, E.T., Huang, C.C., Lin, C.P., Feng, J. and Joliot, M., 2020. Automated anatomical labelling atlas 3. Neuroimage, 206, p.116189.
2. Shen, X., Tokoglu, F., Papademetris, X. and Constable, R.T., 2013. Groupwise whole-brain parcellation from resting-state fMRI data for network node identification. Neuroimage, 82, pp.403-415.

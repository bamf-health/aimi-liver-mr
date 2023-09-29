# Liver MR Segmentation

The liver annotations from [AMOS](https://amos22.grand-challenge.org/) (N=40) and [DUKE Liver Dataset V2](https://zenodo.org/record/6328447) (N=310) dataset is employed to train a model for liver segmentation. The combined training dataset includes 350 cases of annotated livers in MR scans. An ensemble of fivefold cross-validation within the nnUNet framework is used for automatic liver segmentation. The model is used to generate annotations for liver in 67 MR scans from [TCGA-LIHC](https://portal.gdc.cancer.gov/projects/TCGA-LIHC) collection.

The [model_performance](model_performance.ipynb) notebook contains the code to evaluate the model performance on the [TCGA-LIHC](https://portal.gdc.cancer.gov/projects/TCGA-LIHC) collection against a validation evaluated by a radiologist and a non-expert.

## Running the model

#TODO

### Build container from pretrained weights

#TODO

### Running inference

By default the container takes an input directory that contains DICOM files of MR scans, and an output directory where DICOM-SEG files will be placed. To run on multiple scans, place DICOM files for each scan in a separate folder within the input directory. The output directory will have a folder for each input scan, with the DICOM-SEG file inside.

example:

#TODO

There is an optional `--nifti` flag that will take nifti files as input and output.

#### Run inference on IDC Collections

This model was run on MR scans from the [TCGA-LIHC](https://portal.gdc.cancer.gov/projects/TCGA-LIHC) collection. The AI segmentations and corrections by a radioloist for 10% of the dataset are available in the liver-mr.zip file on the [zenodo record](https://zenodo.org/record/8352041)

You can reproduce the results with the [run_on_idc_data](run_on_idc_data.ipynb) notebook on google colab.

### Training your own weights

Refer to the [training instructions](training.md) for more details. #TODO

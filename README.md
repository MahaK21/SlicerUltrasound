# SlicerReSound
The Ultrasound extension for 3D Slicer contains modules to process ultrasound video data. 

## Anonymize Ultrasound
This module reads a folder of ultrasound cine loops in DICOM format and iterates through them. It allows masking the fan shaped or rectangular image area to erase non-ultrasound information from the images. It also allows associating labels to loops, so classification annotations can start during anonymization. The masked loops are exported in DICOM format. The exported DICOM files only contain a specific set of DICOM tags that do not contain any personal information about the patient.

### How to use Anonymize Ultrasound module
1. Select **Input folder** as the folder that contains all your DICOM files. They can be in subfolders.
1. Select **Output folder** as an empty folder, or which contains previously exported files using this module.
1. Click **Read DICOM folder** and wait until the input and output folders are scanned to compile a list of files to be anonymized.
1. Click **Load next** to load the next DICOM file in alphabetical order.
1. Click **Define mask** and click on the four corners of the ultrasound area. Corner points can be modified later by dragging.
1. Click **Export** to produce three files in the output folder: the anonymized DICOM, an annotation file with the corner points, and a json file with all the original DICOM tags that went through light anonymization.

Options under Settings collapsible button:
- **Skip single-frame input files**: use this for efficiency if you only need to export multi-frame DICOM files.
- **Skip input if output already exists**: prevents repeated loading of files whose output already exists.
- **Keep input folders and filenames in output folder**: keeps the subfolder structure and file names of input files.
- **Convert color to grayscale**: use this if you want to eliminate colors in the exported images.
- **JPEG compression in DICOM**: use this to apply compression in exported files without visual information loss.
- **Labels file**: Select a CSV file that contains classification labels. These labels will populate the GUI with checkboxes. Checked labels will be saved in the exported annotation json files.

![2024-04-14_AnonymizeUltrasound](https://github.com/SlicerUltrasound/SlicerUltrasound/assets/2071850/52ff3ab6-94ea-41d5-88c5-596b66d6a659)

## M-mode Analysis
This module generates an M-mode image from a B-mode loop along a user-specified line. The line can be arbitrary, not just ultrasound scan lines. Measurements on the M-mode image can be saved.

### How to use Mmode Analysis module
1. Select **Output folder** where exported files will be saved.
1. Click **Scanline** to add a line markup on the B-mode image.
1. Click **Generate M-mode image** to generate the M-mode ultrasound in the lower view.
1. Optionally click **Measurement line** to add a ruler on the M-mode image.
1. Click **Save M-mode image** to export both the current B-mode image and the M-mode image with their lines. And the measurement in a CSV file in the output folder.
2. 

![2024-04-14_MmodeAnalysis](https://github.com/SlicerUltrasound/SlicerUltrasound/assets/2071850/16fd839c-0959-4e39-bdeb-789e945bae90)

---
layout: tutorial_hands_on

title: <My super great tutorial>
zenodo_link: <My zenodo link to the database>
subtopic: example :human-genetics-cancer
questions:
- 1
- 2
- 3
- 4
objectives:
- use bloome taxonomoy
- use bloome taxonomoy
time_estimation: 3H ? 
key_points:
- 
contributions:
  authorship:
  - ?
  - ?
  - ?
  - ?
  - ?
  editing:
  - ?

---


My super introduction


> <agenda-title></agenda-title>
>
> In this tutorial, we will cover:
>
> 1. TOC
> {:toc}
>
{: .agenda}

# Spatial Data

the Spatial data used in this training were obtained from the VPT tutorial and are the same example files used there. The dataset contains the image mosaics (multiple channels and z-slices), a micron→mosaic pixel transform, decoded transcript coordinates, plus a small set of metadata files used by VPT/Galaxy.

├── 202305010900_U2OS_small_set_VMSC00000
│   └── region_0
│       ├── 202305010900_U2OS_small_set_VMSC00000_region_0.vzg
│       ├── detected_transcripts.csv
│       ├── images
│       │   ├── manifest.json
│       │   ├── micron_to_mosaic_pixel_transform.csv
│       │   ├── mosaic_Cellbound1_z0.tif
│       │   ├── mosaic_Cellbound1_z1.tif
│       │   ├── mosaic_Cellbound1_z2.tif
│       │   ├── ...
│       │   ├── mosaic_DAPI_z0.tif
│       │   ├── ...
│       │   └── mosaic_PolyT_z6.tif

where the: 

- **vzg**  is Vizgen dataset package/manifest used by VPT. It bundles dataset-level metadata and points to the images and decoded data the toolkit uses. In practice VPT reads this to know what region/images and decoded files belong together.

- **images/manifest.json** describes the mosaic images: channels present (e.g., Cellbound, DAPI, PolyT), tile layout, z-slices, image filenames and any acquisition metadata the VPT tools rely on for loading and visualisation.

- **images/mosaic.tif** (the mosaic images): Multi-tile mosaic TIFFs — one file per channel per z-slice in this dataset (e.g., mosaic_Cellbound1_z0.tif, mosaic_DAPI_z2.tif, mosaic_PolyT_z5.tif).
Why used: these are the actual image data used for segmentation (Cellbound channel is typically the cell membrane marker used to find cell boundaries), for nucleus detection (DAPI), and for visual overlays with decoded transcripts.

- **images/micron_to_mosaic_pixel_transform.csv** file contains the transform that maps coordinates expressed in physical units (microns, typically from the spot-detection/decoding step) into pixel coordinates in the mosaic image. In other words: it lets you place decoded transcript coordinates (which are often reported in stage/µm coordinates) onto the mosaic image pixel grid so transcripts align with image features.



## Get data

> <hands-on-title>Data upload</hands-on-title>
>
> 1. For this tutorial, make a new history.
>
>    {% snippet faqs/galaxy/histories_create_new.md %}
>
>    {% snippet faqs/galaxy/histories_rename.md %}
>
> 2. Import the data files from
>    [VPT](add link):
>
>    ```
>    https://vzg-web-resources.s3.amazonaws.com/202305010900_U2OS_small_set_VMSC00000.zip
>    ```
>    This will dlownload the compressed file where all of the data are kept. 
> 
>    In some cases the same dataset can be found in the Galaxy shared data library. 
>    Ask the instructor for more details about this.
>
>    The dat aset can also be downloaded a local storage.  
>
>    {% snippet faqs/galaxy/datasets_import_via_link.md format="zip" %} ?
>
>    {% snippet faqs/galaxy/datasets_import_from_data_library.md %}
>
> 3. Use the unzip tool to unzip the compressed file to get the data. 
>
> 4. Extract ?? 
>
> 3. Check the files to see if they are in the correct formates, Tiff for images CSV for 'micron_to_mosaic_pixel_transform' and detected_transcripts files. 
>
>    {% snippet faqs/galaxy/datasets_change_datatype.md datatype="tiff" %}
>
> 5. Use Build list tool to Create a collection for the Images. 
>
> 4. Give the data meaningful names and tags to facilitate analysis.
>     
>
>    When uploading data from a link, Galaxy names the files after the link address.
>    It might be useful to change or modify the name to something more meaningful.
>
>    {% snippet faqs/galaxy/datasets_rename.md %}
>
>
> 5. This tutorial has a set of shared steps performed on the data. To track the
>    data in the history, it is recommended to tag the datasets by attaching a meaningful tag '#'
>    to them. The tagging will automatically be attached to any file generated
>    from the original tagged dataset.
>
>    {% snippet faqs/galaxy/datasets_add_tag.md %}
>
>
{: .hands_on}

repeat until you are happy 

# Conclusion

In this tutorial, we introduced Contol-FreeC as an alternative tool for detecting hCNVs and highlighted the steps for preparing reads and analysis.

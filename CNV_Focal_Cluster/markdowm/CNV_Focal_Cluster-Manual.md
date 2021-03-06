##### Please try the demo file (hg19) in the sidebar (`Demo File Sets`).

<!-- ##### [Download a zip of demo file set](https://raw.githubusercontent.com/Nobel-Justin/Oviz-Bio-demo/master/CNV_Focal_Cluster/demo_data/CNV_Focal_Cluster_demo.zip) and [Check](https://github.com/Nobel-Justin/Oviz-Bio-demo/blob/master/CNV_Focal_Cluster/demo_data/CNV_Focal_Cluster_demo.zip) the `official demo inputs`. -->

# Introduction
The 'CNV: Focal Cluster' visualization is an interactive and extended version of the output plot from 'GISTIC', a bioinformatics tool for identifying regions of the genome that are significantly amplified or deleted across a set of samples. In this visualization, each aberration is assigned a G-score that considers the amplitude of the aberration as well as the frequency of its occurrence across samples. The G-scores are drawn as the red (amplification) and blue (deletion) lines on the plot. False Discovery Rate q-values are then calculated for the aberrant regions and regions with q-values below a user-defined threshold (shown as the two green lines) are considered significant. The “wide peak”, determined using a leave-one-out algorithm to allow for errors in the boundaries in a single sample, is shown by the text tags extending from the line plot. The “wide peak” boundaries are more robust for identifying the most likely gene targets in the region. We also list genes found in each “wide peak” region in a gene box. To visualize data, upload three **TSV** files in the *required* format and use sidebar options to customize the display.

# Group Samples CNV Data (TSV files)
Check the official demo input [here](https://github.com/Nobel-Justin/Oviz-Bio-demo/blob/master/CNV_Focal_Cluster/demo_data). These files are results of 'GISTIC' tool.

## Scores
This is the gscore result (tsv) of 'GISTIC' tool.

- **header**<br/>
  The first row contains eight-column headings, which must be identical to those listed in the following:
  - __*Type*__: Aberration type, which is specified as Amp or Del (amplification or deletion).
  - __*chromosome*__: Chromosome.
  - __*Start*__: Location of the first base pair in the aberrant region.
  - __*End*__: Location of the last base pair in the aberrant region.
  - __*q-value*__: False Discovery Rate q-values for the aberrant regions (q-values below a user-defined threshold are considered significant).
  - __*G-score*__: G-score that considers the amplitude of the aberration as well as the frequency of its occurrence across samples.
  - __*average amplitude*__: Average amplitudes among aberrant samples.
  - __*frequency*__: Frequency of aberration across the genome for both amplifications and deletions.

## amp\_genes.conf\_90
This is the amp\_genes.conf\_90 result (tsv) of 'GISTIC' tool. The amp genes file contains amplification peaks identified in the GISTIC analysis. The first four rows are cytoband, q-value, residual q-value and wide peak boundaries. The remaining rows list the genes contained in each wide peak. For peaks that contain no genes, the nearest gene is listed in brackets.

## del\_genes.conf\_90
This is the del\_genes.conf\_90 result (tsv) of 'GISTIC' tool. The del genes file contains one column for each deletion peak identified in the GISTIC analysis. The file format for the del genes file is identical to the format for the amp genes file.

# Display Interactions
There are four types of interactions: *External Link* and *Download*.

- **External Link**<br/>
  Each gene name listed in the gene boxes is linked to the corresponding result from the [genecard](https://www.genecards.org/) search webpage.
- **Download**<br/>
  One SVG file will be generated when the '**Download**' button is clicked. Only the default **Dark Theme** is available at this point.

# Sidebar Functions
The sidebar provides diverse options to fine-tune the display, like managing files, viewing error genes in application or deletion and setting the q-value threshold.

- **Files**
  - __*Manage Files*__: checklist of TSV files uploaded previously, delete or download said TSV files.
  - __*Upload*__: upload the three files. Note that the duplicated file name will be alerted and given a random postfix.
  - __*Choose*__: choose files uploaded previously. Note that this function is ONLY available to registered users (each account has certain storage).
  - __*File Sets*__: save the three files together as a file set. Users can also choose to apply one file set from all saved ones.
- **Errors**<br/>
  Error genes are the genes in the uploaded amp\_genes.conf\_90 or del\_genes.conf\_90 file but not found in our database.
  - __*Error genes in Amp*__: list of error genes in amplification.
  - __*Error genes in Del*__: list of error genes in deletion.
- **Setting**<br/>
  - __*q-value*__: setting the q-value threshold between 0.1 to 0.9.

*Manual version=1.3*, written by Miss. Li Shiying and Dr. JIA Wenlong on 2020-04-08.

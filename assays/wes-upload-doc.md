## Before uploading data
If you haven't already, see our instructions on downloading and installing the CIDC-CLI which you will use to upload data.

[CIDC-CLI Install Instructions](/cli-instructions)

You also need to install the Google Cloud SDK.

[Google Cloud SDK](https://cloud.google.com/sdk/install)

After installation you'll need to authenticate the SDK with the following command. Use the credentials you created for this portal.

~~~~
$ gcloud auth application-default login
~~~~

## File formats for Whole Exome Sequencing (WES) uploads:

To upload the WES data, create a directory with a metadata file and the fastq files. 

The metadata file is an Excel file and requires the following columns:
### Header columns:
|COLUMN NAME|DESCRIPTION|
|-----------|-----------|
|**LEAD ORGANIZATION STUDY ID**| Trial identifier used by lead organization|
|**ASSAY CREATOR**| Indicates what site is filling out the assay"|
|**ASSAY CATEGORY**| Type of the assay e.g. WES|
|**ENRICHMENT KIT**| Vendor for the kit used for enrichment, e.g. Twist, Agilent, IDT|
|**LIBRARY KIT VENDOR**| Vendor for the library construction kit, e.g. KAPA|
|**SEQUENCER PLATFORM**| Sequencer Model, e.g. HiSeq 2500, NextSeq, NovaSeq|
|**PAIRED END READS**| Indicate if the sequencing was performed paired or single ended|
|**READ LENGTH**| Number of cycles for each sequencing read| 

### Data columns:

|COLUMN NAME|DESCRIPTION|
|-----------|-----------|
|**CIMAC PARTICIPANT ID**| Participant identifier assigned by the CIMAC-CIDC Network|
|**CIMAC ALIQUOT ID**| Aliquot identifier assigned by the CIMAC-CIDC Network|
|**GENOMIC SOURCE**| Sequencing platform used for the assay|
|**LIBRARY KIL LOT**| Lot number for the library construction kit|
|**ENRICHMENT LOT**| Lot number for the enrichment kit|
|**LIBRARY PREP DATE**| Sequencing platform used for the assay|
|**CAPTURE DATE**| Date of the hybrid capture enrichment|
|**DNA INUPUT NG**| Amount of DNA/RNA (in ng) used for library construction|
|**LIBRARY YIELD NG**| Resulting yield (in ng) from library construction|
|**AVERAGE INSERT SIZE**|The average insert size for the library|
|**FORWARD FASTQ**| Fastq file for the forward reads|
|**REVERSE FASTQ**| Fastq file for the reverse reads|
|**READ GROUP MAPPING FILE**|Stores read group information for each read in the fastq files|

Click [here](https://github.com/CIMAC-CIDC/cidc-schemas/blob/master/template_examples/wes_template.xlsx) to see an example of a metadata file. 

## Uploading Files

**Start the CLI and use your JWT to log in**
~~~~
(CMD) jwt your-jwt-here
~~~~

**Run upload command:**
~~~~
(CMD) upload_data
~~~~

**Select a trial:**
~~~~
====| Available Trials |=====
[1] - Some trial
[2] - Some other trial
[3] - DFCI-9999
~~~~
Select the number that corresponds to your trial of interest, for example DFCI-9999.

**Select an assay:**
~~~~
====| Available Assays |=====
[1] - WES
~~~~

Select the number that corresponds to the assay data you want to upload.

**Select the upload method:**
~~~~
Pick an upload method:
   [1] Upload using a metadata file.
~~~~

**Enter path to your metadata file:**
~~~~
Please enter the metadata file path: path/to/your/metadata
~~~~

The process will then use the metadata file to upload the fastq files.

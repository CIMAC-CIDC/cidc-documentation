# IHC
Immunohistochemistry (IHC) uses antibodies to detect the location of proteins and other antigens in tissue sections.

## IHC Workflow Overview
1. The CIMAC technician who is performing the experiment downloads a copy of the IHC metadata spreadsheet template via the CIDC portal.
2. The CIMAC technician begins populating the metadata spreadsheet. **NOTE:** If the biospecimens have not yet been relabled to use CIMAC IDs, then the technician should *digitally* re-label the sample by replacing the native identifiers with the CIMAC ID when loading the samples into the machine.
3. The CIMAC technician performs the experiment and data analysis.
4. The CIMAC technician or CIMAC bioinformatics support fills in the columns of the metadata spreadsheet which point to the resultant files.
5. The CIMAC technician or CIMAC bioinformatics support transfers the metadata and files to CIDC using the command line tool.


## IHC Files

Example directory for IHC data transfer (all files should be in the same directory):
```
.
├── ihc_assay_CT.xlsx
├── ihc_image_1.qptiff
├── ihc_image_2.qptiff
└── ihc_metadata_11012019.xlsx
```

## IHC Metadata

Click [here](https://cimac-cidc.github.io/cidc-schemas/docs/templates.metadata.ihc_template.html) to see the specific metadata collected for the IHC assay.

Click [here](https://github.com/CIMAC-CIDC/cidc-schemas/raw/master/template_examples/ihc_template.xlsx) to see an example of a metadata xlsx file.


## Uploading Files

**Start the CLI and use your Identity Token (displayed below) to log in**
```bash
cidc login [token]
```

**Run upload command:**
```bash
cidc assays upload --assay ihc --xlsx ihc_metadata_11012019.xlsx
```

The process will then use the metadata file to upload the required files.

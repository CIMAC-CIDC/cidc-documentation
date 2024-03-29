# ELISA

The enzyme-linked immunosorbent assay (ELISA), is a plate-based assay technique that uses a solid-phase enzyme immunoassay (EIA) to detect and quantify the presence of a substance (proteins, antibodies, peptides, or hormones) in a liquid sample by assessing the conjugated enzyme activity with a substrate. 

## ELISA Workflow Overview

1. The CIMAC technician who is performing the experiment downloads a copy of the ELISA metadata spreadsheet template via the CIDC portal.
2. The CIMAC technician begins populating the metadata spreadsheet. **NOTE:** If the biospecimens have not yet been relabled to use CIMAC IDs, then the technician should *digitally* re-label the samples by replacing the native identifiers with the CIMAC ID when loading the samples into the machine.
3. The CIMAC technician performs the experiment and data analysis. 
4. The CIMAC technician or CIMAC bioinformatics support fills in the columns of the metadata spreadsheet.
5. The CIMAC technician or CIMAC bioinformatics support transfers the metadata and the data file to a CIDC upload bucket, following the concierge model.
6. The CIDC engineer transfers the metadata and the data file to CIDC using the command line tool.


## ELISA Files

Example directory for ELISA data transfer:
```
.
├── grand_serology_results.xlsx
└── elisa_metadata_090219.xlsx
```

## ELISA Metadata

Click [here](https://cimac-cidc.github.io/cidc-schemas/docs/assays.elisa.elisa_template.html) to see the specific metadata collected for the ELISA assay.

Click [here](https://github.com/CIMAC-CIDC/cidc-schemas/raw/master/template_examples/elisa_template.xlsx) to see an example of a metadata xlsx file.

## Uploading Files

**Start the CLI and use your Identity Token (displayed below) to log in**
```bash
cidc login [token]
```

**Run upload command:**
```bash
cidc assays upload --assay elisa --xlsx elisa_metadata_090219.xlsx
```

The process will then use the metadata file to upload the serology file.

# WES

Whole exome sequencing (WES) is an assay used to sequence the coding regions of the genome. The CIDC Whole Exome Pipeline is a computational workflow for identifying somatic variants from WES of tumor samples. The pipeline includes tools for quality control (QC) and characterization of paired (tumor/normal) whole exome sequencing data.

## WES Workflow Overview

1. The CIMAC technician who is performing the experiment downloads a copy of the WES metadata spreadsheet template via the CIDC portal.
2. The CIMAC technician begins populating the metadata spreadsheet. **NOTE:** If the biospecimens have not yet been relabled to use CIMAC IDs, then the technician should *digitally* re-label the samples by replacing the native identifiers with the CIMAC ID when loading the samples into the machine.
3. The CIMAC technician performs the experiment and data analysis.
4. The CIMAC technician or CIMAC bioinformatics support fills in the columns of the metadata spreadsheet.
5. The CIMAC technician or CIMAC bioinformatics support transfers the metadata and data files to CIDC using the command line tool.

## WES Files

Each Whole Exome Sequencing experiment creates fastq files and a config file. **NOTE:** CIDC will process the fastq files into derivative results in a seperate process coordinated by the CIDC Bioinformatics Team. 

Example directory for WES data transfer:
```
.
├── fwd.1.1.1.fastq.gz
├── fwd.2.2.2.fastq.gz
├── rev.1.1.1.fastq.gz
├── rev.2.2.2.fastq.gz
├── rgm.1.1.1.txt
├── rgm.2.2.2.txt
├── wes_metadata_082919.xlsx
```

## WES Metadata


Click [here](https://cimac-cidc.github.io/cidc-schemas/docs/templates.metadata.wes_template.html) to see the specific metadata collected for the WES assay.

Click [here](https://github.com/CIMAC-CIDC/cidc-schemas/blob/master/template_examples/wes_template.xlsx) to see an example of a metadata xlsx file.

## Uploading Files

**Start the CLI and use your JSON Web Token (displayed below) to log in**
```bash
cidc login [token]
```

**Run upload command:**
```bash
cidc assays upload --assay wes --xlsx wes_metadata_082919.xlsx
```

The process will then use the metadata file to upload the required files.

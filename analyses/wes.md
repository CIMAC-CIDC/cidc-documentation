# WES

Whole exome sequencing (WES) is an assay used to sequence the coding regions of the genome. The CIDC Whole Exome Pipeline is a computational workflow for identifying somatic variants from WES of tumor samples. The pipeline includes tools for quality control (QC) and characterization of paired (tumor/normal) whole exome sequencing data.

## WES Workflow Overview

1. The CIMAC technician who is performing the experiment downloads a copy of the WES metadata spreadsheet template via the CIDC portal.
2. The CIMAC technician begins populating the metadata spreadsheet. **NOTE:** If the biospecimens have not yet been relabled to use CIMAC IDs, then the technician should *digitally* re-label the samples by replacing the native identifiers with the CIMAC ID when loading the samples into the machine.
3. The CIMAC technician performs the experiment and data analysis.
4. The CIMAC technician or CIMAC bioinformatics support fills in the columns of the metadata spreadsheet.
5. The CIMAC technician or CIMAC bioinformatics support transfers the metadata and data files to CIDC using the command line tool.

## WES Analysis Files

Example directory for WES analysis data transfer:
```
.
├── wes-analysis
│   ├── analysis1.bam
│   ├── analysis1.bam.bai
│   └── ..
├── wes_analysis_30012020.xlsx
```

## Uploading Files

**Start the CLI and use your Identity Token (displayed below) to log in**
```bash
cidc login [token]
```

**The default environment is set to `production`. To switch to `staging` for testing purposes, run:**
```bash
cidc config set-env staging
```

**Run Analysis-upload command**
```bash
cidc analyses upload --analysis wes_analysis --xlsx wes_analysis_010720.xlsx
```
The process will then use the template to upload the analysis files. The files can be viewed on the portal [here](https://portal.cimac-network.org/browse-files?facets=Assay%20Type%7CWES%7CAssay%20Metadata&facets=Assay%20Type%7CWES%7CSource&facets=Assay%20Type%7CWES%7CGermline&facets=Assay%20Type%7CWES%7CPurity&facets=Assay%20Type%7CWES%7CClonality&facets=Assay%20Type%7CWES%7CCopy%20Number&facets=Assay%20Type%7CWES%7CNeoantigen&facets=Assay%20Type%7CWES%7CSomatic&facets=Assay%20Type%7CWES%7CAlignment&facets=Assay%20Type%7CWES%7CMetrics&facets=Assay%20Type%7CWES%7CHLA%20Type&facets=Assay%20Type%7CWES%7CReport) once the upload is complete.

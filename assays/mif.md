# mIF

Multiplex immunofluorescence (mIF) biomarker imaging allows for multi-label analysis of formalin-fixed paraffin embedded (FFPE) tissue biopsy samples, enabling scientists to study complex biological questions. This assay allows scientists to precisely measure and quantify multiple fluorescent molecular markers simultaneously, even when co-localized within a single tissue section.

## mIF Workflow Overview

1. The CIMAC technician who is performing the experiment downloads a copy of the mIF metadata spreadsheet template via the CIDC portal.
2. The CIMAC technician begins populating the metadata spreadsheet. **NOTE:** If the biospecimens have not yet been relabled to use CIMAC IDs, then the technician should *digitally* re-label the samples by replacing the native identifiers with the CIMAC ID when loading the samples into the machine.
3. The CIMAC technician performs the experiment and data analysis.
4. The CIMAC technician or CIMAC bioinformatics support fills in the columns of the metadata spreadsheet.
5. The CIMAC technician or CIMAC bioinformatics support transfers the metadata and the data files to a CIDC upload bucket, following the concierge model.
6. The CIDC engineer transfers the metadata and the data files to CIDC using the command line tool.


## mIF Files

Example directory for mIF data transfer:
```
.
├── 121
│   ├── 1_score_data.txt
│   ├── 1_binary_seg_maps.tif
│   ├── 1_cell_seg_data.txt
│   ├── 1_cell_seg_data_summary.txt
│   ├── 1_phenotype_map.tif
│   ├── 1_composite_image.tif
│   └── 1.im3
├── mIF_metadata_30012020.xlsx
```

## mIF Metadata

Click [here](https://cimac-cidc.github.io/cidc-schemas/docs/assays.mif.mif_template.html) to see the specific metadata collected for the mIF assay.

Click [here](https://github.com/CIMAC-CIDC/cidc-schemas/blob/master/template_examples/mif_template.xlsx) to see an example of a metadata xlsx file.

## Uploading Files

**Start the CLI and use your Identity Token (displayed below) to log in**
```bash
cidc login [token]
```

**Run Assay-upload command, specifying the format as either fastq or bam:**
```bash
cidc assays upload --assay mif --xlsx mIF_metadata_082919.xlsx
```
The process will then use the metadata file to upload the required files. 

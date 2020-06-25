# qc-analysis-pipeline
Workflows used for QC of WGS or WES data

### Whole Genome Single Sample QC :
This WDL pipeline implements QC in human whole-genome or exome/targeted sequencing data.

#### Requirements/expectations
- Human paired-end sequencing data in aligned BAM or CRAM format
- Input BAM/CRAM files must additionally comply with the following requirements:
- - files must pass validation by ValidateSamFile
- - reads are provided in query-sorted order
- - all reads must have an RG tag
- Reference genome must be Hg38 with ALT contigs
- Coverage regions, either WGS or exome/targeted, must be in a compatible interval_list format

#### Outputs 
- BAM/CRAM Validation Report
- Several QC Summary Reports
- - All reads: Quality, Alignment, Insert Size, Artifact, GC Bias, Duplication, Contamination, and Coverage

### Software version requirements :
- Picard 2.21.7
- samtools 1.3.1 using htslib 1.3.1
- VerifyBamID2
- Python 2.7 and 3
- Cromwell version support 
  - Successfully tested on v48
  - Does not work on versions < v23 due to output syntax

### Important Note :
- The provided JSON is meant to be a ready to use example JSON template of the workflow. It is the user’s responsibility to correctly set the reference and resource input variables using the [GATK Tool and Tutorial Documentations](https://software.broadinstitute.org/gatk/documentation/).
- Relevant reference and resources bundles can be accessed in [Resource Bundle](https://software.broadinstitute.org/gatk/download/bundle).
- Runtime parameters are optimized for Broad's Google Cloud Platform implementation.
- For help running workflows on the Google Cloud Platform or locally please
view the following tutorial [(How to) Execute Workflows from the gatk-workflows Git Organization](https://software.broadinstitute.org/gatk/documentation/article?id=12521).
- The following material is provided by the GATK Team. Please post any questions or concerns to one of these forum sites : [GATK](https://gatkforums.broadinstitute.org/gatk/categories/ask-the-team/) , [FireCloud](https://gatkforums.broadinstitute.org/firecloud/categories/ask-the-firecloud-team) or [Terra](https://broadinstitute.zendesk.com/hc/en-us/community/topics/360000500432-General-Discussion) , [WDL/Cromwell](https://gatkforums.broadinstitute.org/wdl/categories/ask-the-wdl-team).
- Please visit the [User Guide](https://software.broadinstitute.org/gatk/documentation/) site for further documentation on GATK workflows and tools.

### LICENSING :
Copyright Broad Institute, 2019 | BSD-3
This script is released under the WDL open source code license (BSD-3) (full license text at https://github.com/openwdl/wdl/blob/master/LICENSE). Note however that the programs it calls may be subject to different licenses. Users are responsible for checking that they are authorized to run all programs before running this script.
- [Picard](https://broadinstitute.github.io/picard/)
- [VerifyBamID2](https://github.com/Griffan/VerifyBamID)
- [samtools](https://github.com/samtools/samtools)

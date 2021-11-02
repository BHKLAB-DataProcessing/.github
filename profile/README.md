# Repositories for ORCESTRA Pachyderm pipelines (orcestra.ca).

Pachyderm pipelines can be found in respective repositories as JSON files. All non-JSON files are data used in pipelines. Repositories are dataset specific.

### Example: Running a ToxicoSet pipeline in Pachyderm:

The toxicoset pipelines can be located in this repository: https://github.com/BHKLAB-Pachyderm/toxicoPipelines. The following pipeline in this repository compiles a toxicoset data object for the TGGATE Rat dataset: https://github.com/BHKLAB-Pachyderm/toxicoPipelines/blob/main/getTG_rat.json. However, there is an input section in this JSON file that indicates that this pipeline relies on the execution of another pipeline in order for it to run, which is “processTGRatArray”. This pipeline can found in the same toxicoset repository here, and therefore, must be run first: https://github.com/BHKLAB-Pachyderm/toxicoPipelines/blob/main/processTGRatArray.json. Therefore, all inputs for a pipeline must be available/ran first.


To execute this pipeline in Pachyderm, run the following commands in order: 
```
pachctl create-pipeline -f https://github.com/BHKLAB-Pachyderm/toxicoPipelines/blob/main/processTGRatArray.json
```
```
pachctl create-pipeline -f https://github.com/BHKLAB-Pachyderm/toxicoPipelines/blob/main/getTG_rat.json
```


# Versioning

Three important components have to be chosen properly when installing on premise for the SAP Solution Manager interface to work properly:
 1. Symbio
 2. SAP Solution Manager interface
 3. .syex configuration file
 
**The RULE when one of the three components updates:
Rule: No update of Symbio or SAP Solution Manager interface without updating the other!**

Update of Symbio
- If Symbio is updated also SAP Solution Manager interface has to be updated
- Integration test should all pass

Update of SAP Solution Manager interface
- Symbio has to be updated
- Integration test should all pass

Update of SAP Solution Manager
- SAP Solution Manager interface has to be updated and also Symbio

All of the tree components have to be chosen right in order for the SAP Solution Manager interface to work properly.
Before installing Symbio and SAP Solution Manager to the customers on premise machine please contact some of the developers from msg (Luka or Vukasin) to tell you what version is best to install.

The current installed SAP Solution Manager interface version, can be seen by hitting the **/version** endpoint.

The following table indicated what version of Symbio works with what version of SAP Solution Manager interface and .syex file.

| Symbio version  |SAP Solution Manager interface version   | .syex file   | 
|---|---|---|
|before version: (master,8.26.2019, commit: e4df3ee) https://dev.azure.com/pundz/Symbio/_releaseProgress?_a=release-environment-logs&releaseId=2203&environmentId=5752  | newest master branch  |  https://ploetzzeller.sharepoint.com/:u:/s/msgpz/ERkDphKH_l9DowerZh4blGsBq0aniEsbw7kA--xFgbfx5Q?e=zkgn64 |
| after version: (master,8.26.2019, commit: e4df3ee) https://dev.azure.com/pundz/Symbio/_releaseProgress?_a=release-environment-logs&releaseId=2203&environmentId=5752 |  newest master branch | https://ploetzzeller.sharepoint.com/:u:/s/msgpz/EXDFNXpGIWFOpx-6ZSjby9oBjQ4PiROELHYpDBUCmemfHw?e=CTi1rE  |
|  after version: (master,9.4.2019,, commit: 9ee7ef3) [https://dev.azure.com/pundz/Symbio/_build/results?buildId=11873](https://dev.azure.com/pundz/Symbio/_build/results?buildId=11873) | newest master branch  |  https://ploetzzeller.sharepoint.com/:u:/s/msgpz/EZhyNSQ0NFZHulpJ0XxlzYYBCz90Ui2AF6_VCpfuiwKHSw?e=1ngQsg |
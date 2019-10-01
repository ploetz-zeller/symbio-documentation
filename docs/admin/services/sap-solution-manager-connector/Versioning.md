# Versioning

Three important componentes have to be choosen properly when installing on premise for the SAP Solution Manager interface to work properly:
 1.Symbio
 2.SAP Solution Manager interface
 3..syex configuration file
 
The rules when one of the three componets updates:
Rule: No update of Symbio or SolMan interface without updating the other!

Update of Symbio
- If Symbio is updated also SolMan interface has to be updated
- Test custom attributes update (new custom attribute)

Update of SolMan interface
- if a new version of SolMan interface is using a new endpoint from Rest API then Symbio has to be updated (if there is a change like this inform admin and he knows that he has to update Symbio)

Update of SolMan
- SolMan interface has to be updated, Symbio should not be updated

All of the tree components have to be choosen right in order for the SAP Solution Manager interface to work properly.
Before installing symbio and SAP Solution Manager to the customers on premise machine please contact some of the developers from msg (Luka or Vukasin) to tell you what version is best to install.
The following table indicated what version of symbio works with what version of SAP Solution Manager interface and .syex file.

| Symbio version  |SAP Solution Manager interface version   | .syex file   | 
|---|---|---|
|before version: (master,8.26.2019, commit: e4df3ee) https://dev.azure.com/pundz/Symbio/_releaseProgress?_a=release-environment-logs&releaseId=2203&environmentId=5752  | newest master branch  |  https://ploetzzeller.sharepoint.com/:u:/s/msgpz/ERkDphKH_l9DowerZh4blGsBq0aniEsbw7kA--xFgbfx5Q?e=zkgn64 |
| after version: (master,8.26.2019, commit: e4df3ee) https://dev.azure.com/pundz/Symbio/_releaseProgress?_a=release-environment-logs&releaseId=2203&environmentId=5752  |  newest master branch | https://ploetzzeller.sharepoint.com/:u:/s/msgpz/EXDFNXpGIWFOpx-6ZSjby9oBjQ4PiROELHYpDBUCmemfHw?e=CTi1rE  |
|  after version: (master,9.4.2019,, commit: 9ee7ef3) [https://dev.azure.com/pundz/Symbio/_build/results?buildId=11873](https://dev.azure.com/pundz/Symbio/_build/results?buildId=11873) | newest master branch  |  https://ploetzzeller.sharepoint.com/:u:/s/msgpz/EZhyNSQ0NFZHulpJ0XxlzYYBCz90Ui2AF6_VCpfuiwKHSw?e=1ngQsg |
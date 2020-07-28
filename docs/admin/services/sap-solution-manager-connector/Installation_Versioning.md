# Versioning

Three important components have to be chosen properly when installing on premise for the SAP Solution Manager interface to work properly:
 1. Symbio
 2. SAP Solution Manager interface
 3. .syex configuration file
 
**The RULE when one of the three components updates:
Rule: No update of Symbio or SAP Solution Manager interface without updating the other!**

NOTE: *Latest .syex file is included in latest Symbio artifact files*

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
|before version: (master,8.26.2019, commit: e4df3ee)  | Obsolete  |  https://ploetzzeller.sharepoint.com/:u:/s/msgpz/ERkDphKH_l9DowerZh4blGsBq0aniEsbw7kA--xFgbfx5Q?e=zkgn64 |
| after version: (master,8.26.2019, commit: e4df3ee)  |  Obsolete | https://ploetzzeller.sharepoint.com/:u:/s/msgpz/EXDFNXpGIWFOpx-6ZSjby9oBjQ4PiROELHYpDBUCmemfHw?e=CTi1rE  |
|  after version: (master,9.4.2019,, commit: 9ee7ef3) | before version: master.628c5b756c5dbe78e13d4c05eb2621e76e587f86 (**EXCLUDING** THIS VERSION)  |  https://ploetzzeller.sharepoint.com/:u:/s/msgpz/EZhyNSQ0NFZHulpJ0XxlzYYBCz90Ui2AF6_VCpfuiwKHSw?e=1ngQsg |
|  after version: (master,9.4.2019,, commit: 9ee7ef3) | after version: master.628c5b756c5dbe78e13d4c05eb2621e76e587f86 (**INCLUDING** THIS VERSION)  |  https://ploetzzeller.sharepoint.com/:u:/s/msgpz/EVglrnIxeBZMgBN81timkgABEXuzCxO7EKWZx0-OwAHFSQ?e=bZZO71 |
|  From Release 486: (master,4.21.2020, commit: 477b5f1)  | From version: Release 180 (master_20200506.1) (**INCLUDING** THIS VERSION)  |  https://ploetzzeller.sharepoint.com/:u:/s/msgpz/EcRF-y0-2CdOg-iDYRdZAO8Bv_Ixdplw-Ve6SwI1dLA6hQ?e=4TPNKB |
|  From Release 506: (master,5.19.2020, commit: 46aa5b8)  | From version: Release 185 (master_20200522.1) (**INCLUDING** THIS VERSION)  |  https://ploetzzeller.sharepoint.com/:u:/s/msgpz/EcRF-y0-2CdOg-iDYRdZAO8Bv_Ixdplw-Ve6SwI1dLA6hQ?e=4TPNKB |
|  From Release 516: (master, 6.05.2020, commit: b6f91ae) | From version: Release 185 (master_20200522.1) (**INCLUDING** THIS VERSION)  |  https://ploetzzeller.sharepoint.com/:u:/s/msgpz/ES27UH53JKNMicgkGrnWEuEBdwSbazunHHo1hRmGYLRRLA?e=o27eK2 |
|  From Release 522: (master,6.17.2020, commit: e0242be)  | From version: Release 187 (master_20200617.1) (**INCLUDING** THIS VERSION)  |  https://ploetzzeller.sharepoint.com/:u:/s/msgpz/EeH_6Qey_UVKl9lVp4X5Bv4Bn4JWIuIFubYLPLBuUqxgAA?e=XOVLz3 |
|  From Release 522: (master,6.17.2020, commit: e0242be)  | From version: Release 194 (master_20200714.2) (**INCLUDING** THIS VERSION)  |  https://ploetzzeller.sharepoint.com/:u:/s/msgpz/Ecq94pWv_MVNshg-dzTc7tkBHIGTKOA9uFox_t_vmzqcIQ?e=Mug7b3 |

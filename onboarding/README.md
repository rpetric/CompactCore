## Onboarding playbook

There are 3 playbooks for onboarding:
* **[onboard.yaml](onboard.yaml)**
* [cleanup.yaml](cleanup.yaml)
* [master_test.yaml](master_test.yaml)

Main playbook is **onboard.yaml**, which uses Openbaton API to authenticate, 
load excel file and onboard every VNF from excel.

The other two are just utility playbooks. **cleanup.yaml** removes all entities 
onboarded with previous script. **master_test.yaml** is a master script containing 
both onboard and cleanup playbook for convenient testing.

### Usage

1. Write configuration parameters in **config.yaml** file, for example:
    ```
    ob: 172.29.100.100
    user: openbaton
    passw: iskratel
    client: nfvo-dashboard1
    excel_file: test.xlsx
    vim: icp
    ```
2. Run ansible script:

    `ansible-playbook onboard.yaml`
    

To produce additional output, add tags parameter:

`ansible-playbook onboard.yaml --tags 'all,debug'`


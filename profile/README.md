# Fortinet Cloud CSE Team Repo

## Overview

This GitHub account serves as a living organizational location which references Fortinet solutions for cloud environments located in this GitHub account and other associated locations.

Specifically all Fortinet Cloud CSE team TECWorkshops will be housed within this Org.

The official Fortinet GitHub account is located at [github.com/fortinet](https://github.com/fortinet)

Fortinet public documentation is located at [docs.fortinet.com](https://docs.fortinet.com)

Fortinet solution guides, white papers, etc for public cloud security are located at [https://www.fortinet.com/solutions/enterprise-midsize-business/cloud-security](https://www.fortinet.com/solutions/enterprise-midsize-business/cloud-security)

Please click on the links below for public cloud specific solutions:
- [TEC Workshops](TECWorkshops/README.md)
- [AWS](AWS/README.md)
- [Azure](Azure/README.md)
- [Google](Google/README.md)
- [Oracle](Oracle/README.md)
  
## Support

Fortinet-provided scripts in this and other GitHub accounts do not fall under the regular Fortinet technical support scope and are not supported by FortiCare Support Services.

For direct issues, please refer to the issues tab of each individual repo.
For other questions related to this account, contact  [FortinetCloudCSE@fortinet.com](mailto:FortinetCloudCSE@fortinet.com).

## TECWorkshop Creation Status - currently MVP1.0 
### (CI/CD pipeline w/ FortiDevSec, container for development and publishing)
1. Our "101-getting started" and most-complete guide is here: https://fortinetcloudcse.github.io/UserRepo
   - Following this will get you going with everything you need for a very good MVP1
2. We're working to consolidate and standardize all of our CSE content into this GH Organization: https://github.com/FortinetCloudCSE
   - Front/home readme page is live and WIP.  Many of the specific solutions link to various legacy GH accounts temporarily, until they get fully consolidated here 
   - Documentation and readme's are being updated continuously
3. TEC Workshop Creation process documented here: https://github.com/FortinetCloudCSE/UserRepo
  
   ![FortiTechWorkshopFlow](https://github.com/FortinetCloudCSE/UserRepo/blob/main/content/FTNT-hugoFlow.drawio.svg?raw=true)

  - TLDR
     -  Request a new repo per TECWorkshop in FortiCloudCSE Org
       - Repo created including branch protection & GH Pages
       - CI/CD pipline created including FortiDevSec Scans
       - Clone Repo and create Branch
     - Build container
       - includes Central Repo for reusable & Fortinet customized Hugo componentry
       - Hugo already installed
     - Run container
       - interactive CLI login
       - Docker Disk-mounts for mapping of per-workshop content and Central REpo
     - Hugo: Content Creation & Build
       - add chapters/tasks/etc which help customers through TEC Workshops
       - Hugo Build to create static HTML site from MD
     - GitHub Pages - publishing
       - Refresh local Git Repo/Branch
       - Push Branch to GH & Create a Pull-Request (PR)
       - Merge Feature Branch--> Main
       - GitHub action auto publishes newly built Hugo content

## TEC Workshop Revision History

- MVP 1.1 - currently in dev
  - reduce container size (likely Alpine or BusyBox)
  - add auto Hugo publish via GitHub action
  - eliminate need to store Huho Built static site (/public or /docs folder)
- **MVP 1.0 - current**
  - Separated UserRepo and Central Repo to allow maximum re-usability & future-proofing for style/format changes
    - Standard Repo has Fortinet reLearn theme Variant & all necessary customizations
  - Swap in Hugo ReLearn theme (actively community supported) and eliminate Learn & Notice themes (inactive development)
  - Ubuntu container:
    - Maintain consistent Hugo version and eliminate need for local installs
    - allow continuous improvement to our process via container improvements without adding burden to CSE Team
  - Use Container for Hugo Build & GitHub action to publish/refresh GitHub Pages
  - Containerizing our development efforts allows for a lightweight development area while eliminating redundant componentry every time we create a new repo/workshop/demo, and allowing simple and automated updates to existing workshops when the parent template changes.
       - Ultimately we'd like to have scripting copy/revise parent templates periodically and/or whenever we create new Workshops  
  - First TECWorkshop re-published with this new workflow: https://fortinetcloudcse.github.io/FortiCNF/
- MVP 0.2
  - created FortiCloudCSE GitHub Org
  - begin separation of UserRepo & Central Repo
  - begin investigation into container workflow
- MVP 0.1
  - Single repo, manual copy of theme, no use of submodules
  - Introduce Hugo, Learn theme & first draft at Learn theme Variant
  - Use GitHub action to build and Publish to Pages
  - First TECWorkshop published: https://fortinetsecdevops.github.io/technical-recipe-azure-sdwan/



## License

[License](LICENSE) © Fortinet Technologies. All rights reserved.
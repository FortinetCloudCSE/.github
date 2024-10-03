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
       - Docker Disk-mounts for mapping of per-workshop content alongside CentralRpo
     - Hugo: Content Creation & Build
       - add chapters/tasks/etc which help customers through TEC Workshops
     - GitHub Pages - publishing
       - Refresh local Git Repo/Branch
       - Push Branch to GH & Create a Pull-Request (PR)
       - Merge Feature Branch--> Main
       - GitHub action runs our container to build Hugo and publish to GH pages

## TEC Workshop Revision History

- **MVP 1.2 - Oct 2024**
  - Switched to new container base image from hugomods https://docker.hugomods.com/docs/introduction/
    - continuous support for latest Hugo version releases
    - Upgraded ReLearn theme to 6.0.0
      - added features for tabbed content https://mcshelby.github.io/hugo-theme-relearn/shortcodes/tab/index.html
  - Created a simplified/scripted procedure to convert workshop repos using older containers to the latest: https://mcshelby.github.io/hugo-theme-relearn/shortcodes/tab/index.html
    - Container based scripting to to update local scripts https://github.com/FortinetCloudCSE/CentralRepo/blob/main/scripts/update_scripts.sh
    - Add python and Jinja2 to container to facilitate templatized creation of site frontmatter (hugo.toml) : https://github.com/FortinetCloudCSE/CentralRepo/blob/main/scripts/generate_toml.py
    - Revise container run scripts to allow new options and future updates https://github.com/FortinetCloudCSE/CentralRepo/blob/main/scripts/docker_run.sh
  - Theme updates
    - author customizable banners for Xperts2024
    - copyright info on home page
    - modify code highlighting color scheme to improve readability
  - Analytics
    - Add analytics capabilities to track site activity across entire Cloud TEC workshop catalog.
    
- MVP 1.1 - June 2023
    - reduce container size (using Alpine to get shell.  BusyBox does not have shell)
    - autopublish action on GitHub (run our container as GitHub action to perform Hugo build w/ CentralRepo)
      - eliminates need to store Hugo static HTML (autopublish action directly publishes to GH pages)
    - Move Shortcodes from CentralRepo to UserRepo
    - Add CentralRepo/scripts/local_copy.sh to copy any local shortcodes or partials into container
    - Modify logo.html to read Params for logoBanner & logoBannerColor
    - Standardize themes and colors for Workshop, UseCase, Spotlight, Demo
    - Modify Banner Text and Subtext to match theme and be customizable 
    - Add ability to run container run in "build", "server", or "shell" mode
    - Added Dev container env & workflow to stage and test changes before promoting to main/Prod
- MVP 1.0 - May 2023
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

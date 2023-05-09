# Fortinet Cloud CSE Team Repo

## Overview

This GitHub account serves as a living organizational location which references Fortinet solutions for cloud environments located in this GitHub account and other associated locations.

The official Fortinet GitHub account is located at [github.com/fortinet](https://github.com/fortinet)

Fortinet public documentation is located at [docs.fortinet.com](https://docs.fortinet.com)

Fortinet solution guides, white papers, etc for public cloud security are located at [https://www.fortinet.com/solutions/enterprise-midsize-business/cloud-security](https://www.fortinet.com/solutions/enterprise-midsize-business/cloud-security)

Please click on the links below for public cloud specific solutions:
- [AWS](AWS/README.md)
- [Azure](Azure/README.md)
- [Google](Google/README.md)
- [Oracle](Oracle/README.md)
  
## Support

Fortinet-provided scripts in this and other GitHub accounts do not fall under the regular Fortinet technical support scope and are not supported by FortiCare Support Services.

For direct issues, please refer to the issues tab of each individual repo.
For other questions related to this account, contact  [FortinetCloudCSE@fortinet.com](mailto:FortinetCloudCSE@fortinet.com).

## General Efforts and Status

1. Our "101-getting started" and most-complete guide is here: https://fortinetcloudcse.github.io/UserRepo
   - Following this will get you going with everything you need for a very good MVP0 
   - However, it's still an MVP0, and we do have a bit of development since then 
2. We're working to consolidate and standardize all of our CSE content into this GH Organization: https://github.com/FortinetCloudCSE
   - Front/home readme page is live and WIP.  Many of the specific solutions link to various legacy GH accounts temporarily, until they get fully consolidated here 
   - Documentation and readme's are being updated continuously
3. The most exciting recent development is a GitHub Template used to create new repos for a given workshop/use case/demo: https://github.com/FortinetCloudCSE/UserRepo
   - You'll notice this is a GitHub template. You can use it to create a new repo with a new name, which ends up being a clone of the template. This will allow us to maintain/revise a single/central template and use it to create new repos with all of the latest config/template/etc. 
   - At the moment, we're working on a Jenkins pipeline to use the template for creating repos in the Team Account with testing and governance....this isn't quite ready yet, so for now you'll have to use the template to create Repo in your own GH account
   - Further, this template does include a containerized dev environment with all of the necessary tools for efficiently creating Hugo sites. 
   - To build and run via docker locally:
     ```sh
        docker build -t demo-frontend .
        docker run -p 1313:1313 demo-frontend:latest
     ```
     In a browser, navigate to: http://localhost:1313/UserRepo
   - Containerizing our development efforts allows for a lightweight development area while eliminating redundant componentry every time we create a new repo/workshop/demo, and allowing simple and automated updates to existing workshops when the parent template changes.
     - Ultimately we'd like to have scripting copy/revise parent templates periodically and/or whenever we create new Workshops  

## License

[License](LICENSE) © Fortinet Technologies. All rights reserved.
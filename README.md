# XM Cloud Starter Kit (Next JS) with Unicorn serialization deployment

Read the related article first to get the context: [Deploy Unicorn serialization to XM Cloud using IAR - A hack you should not do](https://jasonstcyr.com/2023/11/15/deploy-unicorn-serialization-to-xm-cloud-using-iar-a-hack-you-should-not-do/)

## About this Solution

This repo is to show how you can update the basic foundation head to deploy through GitHub actions, generating an IAR of Unicorn serialization files, and push that to XM Cloud.

## What’s the TL;DR?

**The challenge:** Take an existing Unicorn serialization file and have the item get created in XM Cloud.

**The pieces that make it work:**

1. Deploy pipeline in GitHub actions (or your favorite DevOps tool) that invokes the Sitecore CLI
1. The Sitecore CLI itemres –unicorn command to create an IAR .dat file from Unicorn serialization
1. A placeholder .dat file in App_Data that is part of the solution being deployed.

**The result:** It works. (With hacky things) Not supported by Sitecore, could stop working at any time. You shouldn’t do it.

## QUICK START for the Starter Kit

1. In an ADMIN terminal:

   ```ps1
   .\init.ps1 -InitEnv -LicenseXmlPath "C:\path\to\license.xml" -AdminPassword "DesiredAdminPassword"
   ```

2. Restart your terminal and run:

   ```ps1
   .\up.ps1
   ```

3. Follow the instructions to [deploy to XM Cloud](#deploy-to-xmcloud)

4. Create Edge token and [query from edge](#query-edge)

---

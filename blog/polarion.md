---
slug: polarion-20-r1
title: Polarion ALM 20 R1 – What’s New and Noteworthy
author: Yangshun Tay
author_title: Front End Engineer @ Facebook
author_url: https://github.com/yangshun
author_image_url: https://avatars0.githubusercontent.com/u/1315101?s=400&v=4
tags: [facebook, hello, docusaurus]
---

* * * * *

OFFICIAL SOURCE: <https://blogs.sw.siemens.com/polarion/polarion-alm-20-r1-whats-new-and-noteworthy/>

A new major version of Polarion is available  --  **Polarion ALM 20 R1**.

For the last time, this major release concludes the delivery of capabilities that were previously released during the year through the  ([19.1](https://blogs.sw.siemens.com/polarion/polarion-alm-19-1-whats-new-and-noteworthy/), [19.2](https://blogs.sw.siemens.com/polarion/polarion-alm-19-2-whats-new-and-noteworthy/), [19.3](https://blogs.sw.siemens.com/polarion/polarion-alm-19-3-whats-new-and-noteworthy/)) service releases. They include:

-   **Document Baselines** ([19.2](https://blogs.sw.siemens.com/polarion/polarion-alm-19-2-whats-new-and-noteworthy/))
-   **Reuse and combine** for LiveDocs ([19.3](https://blogs.sw.siemens.com/polarion/polarion-alm-19-3-whats-new-and-noteworthy/))
-   **User Groups** for easy permissions management ([19.3](https://blogs.sw.siemens.com/polarion/polarion-alm-19-3-whats-new-and-noteworthy/))

In the Polarion 20 R1 release, we introduce additional new features, improvements, and enhancements to existing functionality, that were finalized since the last 19.3 release:

-   **Collections** -- support parallel development of specifications
-   **Connector for Jenkins** -- integrates your CI/CD pipelines into Polarion
-   **Synchronization of User Groups with LDAP** -- centralizes the user groups management
-   **New historical searching** -- reworked with a focus on performance and scalability

Collections
-----------

### What is a Collection?

**Collections** support parallel development activities, help with audit and regulatory compliance and support advanced reuse scenarios. At first glance, it may seem like **Collections** are simple containers for LiveDoc documents, but there is more to it than that.

Complex Waterfall (V-model) product development is often used in heavily regulated industries (Aerospace, Defense and Automotive to name a few), and it's not unusual to have different phases of development done by different teams. It's also not unusual for specifications to be developed concurrently or in parallel with one another.

The Polarion **Collection** concept helps projects with that concurrent workflow. It helps them to ensure they are working with the right versions of specifications, links that are created point to the correct specification versions, and the collection can be archived for historic and regulatory compliance needs.

### How to enable and create the Collections

To unlock the benefits of the new Collections feature, admins will need to add the new Collections topic into the right Navigation panel. Then it is possible to create new Collections and select which Documents, and which baselines of those Documents, belong to it.

![](https://blogs.sw.siemens.com/wp-content/uploads/sites/4/2020/04/01-collections-create-1024x563.png)

### Browsing a Collection

Once you have collected the Documents and their baselines, you can open the Collection and work in a focused interface, that shows only the Documents, links, and actions relevant to the Collection. A user can use this streamlined view to work within the Collection context without being disturbed by objects that do not belong to the Collection but still exist in Polarion.

![](https://blogs.sw.siemens.com/wp-content/uploads/sites/4/2020/04/02-collections_browse-1024x555.png)

### Linking Work Items in the Collection context

Collection also allows you to link Work Items to each other with a real-time link validation that ensures the link consistency within the Collection, i.e. you can only link Work Items from the same Collection when opening the link within the Collection context.

![](https://blogs.sw.siemens.com/wp-content/uploads/sites/4/2020/04/03-collections_link.png)

### Additional functionality of Collections

Additionally, you can also:

-   Close a Collection and lock it for further modification.
-   Configure Collection custom fields and user permissions.
-   Configure the per-project preference whether to hide or show Work Item links leading out of a Collection by default.

Note that we are not done with the Collections yet, so we will be extending the feature set further in the next releases, starting with the cross-project Collections.

Jenkins Connector
-----------------

### Polarion integration with Jenkins CI/CD

The complexity of today's and future products is hardly manageable without automation, especially when it comes to the variability of product variants and the impact on the software that needs to support all the different variants. In the software domain, one of the most popular tools for Continuous Integration/Continuous Delivery (CI/CD) is the open-source tool, Jenkins.

Polarion supports Continuous Integration/Continuous Delivery (CI/CD) technology by means of a Connector that administrators can configure to connect to, and exchange data with a remote CI/CD system. This enables Polarion to launch builds and tests that are performed by an external application (Jenkins) and to import build and test results.

![](https://blogs.sw.siemens.com/wp-content/uploads/sites/4/2020/04/4-jenkins_logo.png)

### Configuring the Jenkins connector

This connector allows Polarion to be plugged into a DevOps chain by connecting to any Jenkins server via HTTP/S with authentication via either a user password or an API Token. The connector can be configured via the Building > CI/CD Integration administration topic.

![](https://blogs.sw.siemens.com/wp-content/uploads/sites/4/2020/04/04-jenkins_configure.png)

When the connection is established, Builds can be configured. You will need to know the URL of the remote Jenkins Build, and any parameters it requires. The parameters' settings can either be a static part of the Build configuration or, if the Build is being triggered by Polarion's workflow, the values can be loaded dynamically from a custom field on a Work Item or a Test Run.

![](https://blogs.sw.siemens.com/wp-content/uploads/sites/4/2020/04/05-jenkins_configure2.png)

A Build in Jenkins represents a build, a test, or a combination of both run in a series.

### Triggering Jenkins builds from Polarion

Configured Builds can be triggered in multiple ways. The most straightforward one is to start a build manually using the Polarion Builds topic. The Builds can also be scheduled via Polarion Scheduler and run automatically. The third option to trigger the Builds is via Work Item or Test Run Workflow functions which enables you to run the Builds as a part of a status transition. This third option brings great value to the highly integrated environments where the development is closely tied to and tracked in Polarion.

### Monitoring the Jenkins builds within Polarion

When a Jenkins Build is run from Polarion it is then monitored via polling of Jenkins for current data. The Build Number and Build Status are polled from Jenkins and stored on the Build page of the Builds topic. This information can also be stored in Work Item or Test Run custom fields if the build process was triggered by a Workflow function, together with a link to the actual Polarion Build that was created when the remote Build was triggered.

![](https://blogs.sw.siemens.com/wp-content/uploads/sites/4/2020/04/06-jenkins_monitor.png)

### Accessing Build Artifacts and Test Results

By default, the set of all build artifacts are uploaded to Polarion when a Build finishes. This set can be filtered to avoid uploading unnecessary data to Polarion.

Jenkins is frequently used to run automated tests. If such tests write test results to a xUnit file, Polarion enables users to import the test results to existing Test Runs, or new Test Runs created by the import process.

UI Refresh
----------

Release 20 R1 delivers the first of a two-phase UI refresh.  Phase 1 consists of an update of colors, typography, and icons. This phase is a prerequisite for PHASE II to ensure a smoother transition for the user from current to future re-envisioned Polarion. We have also made some improvements to a number of pages in Administration. For more details about what you'll find in 20 R1, and what we have planned for the future, check out the blog post at [Sneak Preview -- Visual Refresh Polarion 20](https://blogs.sw.siemens.com/polarion/sneak-preview-visual-refresh-polarion-20/).

![](https://blogs.sw.siemens.com/wp-content/uploads/sites/4/2020/04/07-ui_rework.png)

User Groups Synchronization via LDAP
------------------------------------

We did not stop when we released the new User Groups functionality in Polarion 19.3. The 20 R1 update now allows our customers to automatically assign Users to User Groups by synchronizing them with identity provider via LDAP.

Each User Group can be linked with LDAP via an LDAP Search Filter. If this optional field in a User Group's detail is blank, then the User Group will not be synchronized with LDAP. If this field is not empty, then the LDAP synchronization will attempt to update the Users of the Group based on the LDAP query entered in this field.

![](https://blogs.sw.siemens.com/wp-content/uploads/sites/4/2020/04/08-groups_filter.png)

### Triggering LDAP synchronization via a job

 The LDAP synchronization can be triggered either manually or automatically via a job, where the job offers the possibility to adjust the synchronization by supported parameters.

### Displaying roles source in User and Roles administration

Because Roles can be assigned to Users either directly or via a User Group, it is important to know how the assignment was done. A new Source column was added to the Global Roles and Project Roles sections of the Users administration page and to the Users section of the Roles administration page. This column tells the administrator whether a Role was directly assigned or comes from one or more User Groups (and lists all the User Groups there).

![](https://blogs.sw.siemens.com/wp-content/uploads/sites/4/2020/04/09-groups_user.png)

Other Enhancements
------------------

### Jira Connector: Support for synchronization of multi-select fields

We are continuously working on improvements to our existing Connectors. Polarion 20 R1 supports the synchronization of Jira "multi-select" type fields with Polarion "Custom Multi Enum" type fields, which effectively enables a user to synchronize lists of values between the two tools.

### Configurable merge and source target for GitLab

 You can now configure both source and target branches for the GitLab merge request extension.

![](https://blogs.sw.siemens.com/wp-content/uploads/sites/4/2020/04/10-merge_request.png)

```
<extension id="GitLabExtension" label="Merge Request Panel"
   sourceBranchNameField="[name of custom field with working branch name]"
   targetBranchNameField="[name of custom field with target branch name]"/>
```

You can also hard-code the target branch using the targetBranchName parameter only.

### Extended WebService API coverage

Three new WebService calls were added to the TrackerWebService:

-   Get Attachment
-   Export Document to PDF
-   Delete Work Item

### Security Enhancements

#### Showing stack traces for application errors

System error dialogs are by default not displaying the stack traces for security reasons. If you need to display the stack traces for development and debugging, you can re-enable the stack traces via a new system configuration property **com.siemens.polarion.ui.showStackTraces=true**.

#### Revised security configuration of Apache HTTPD

We have expanded Polarion Help to better advise customers about the best security configuration for Polarion's Apache HTTPD server. We strongly recommend all customers to go through the Help topic *"Advanced security configuration"* to secure the headers and cookies of their Polarion instance. The default configuration is permissive to prevent problems during the evaluation, but production installations should be configured for the restrictive security level.

### Technology Maintenance

#### Updated Apache HTTPD and Subversion bundled with Windows distribution

In the 20 R1 release we have updated the bundled Apache HTTP server to version 2.1.41, and bundled Subversion to version 1.12.2. These changes have the following impacts:

-   After the Polarion installation, the HTTP protocol is used by default for the system user access to the Subversion. We do require setting up the SVN protocol for production use. Due to performance issues, we don't recommend using the FILE protocol anymore.
-   Apache HTTPD configuration for Windows installations now disabled support for TLS 1.0 and TLS 1.1 by default, because these TLS versions are no longer considered secure enough. All major browsers plan to stop supporting these TLS versions in the near future as well

#### Upgrading Subversion storage to the latest version

With the official support of Subversion 1.10+, we also do support and recommend migrating your production repositories to the latest repository storage format that was introduced in Subversion 1.10.

The fastest way to migrate a repository to the new format is to "pipe" the output of the **svnadmin dump** command right into the** svnadmin load** of the new repository. In our labs, we were able to migrate a production repository close to 500 GB and 4.7 million revisions in less than 15 hours.

Example command:

```
nohup  sh -c "svnadmin dump -M 2048 repo-1.9 | svnadmin load -M 2048  --no-flush-to-disk repo-1.10 > load-progress.log 2>&1" &
```

The new repository format uses a different compression algorithm, which is faster, but less efficient. Depending on the contents of the repository, its size might grow after the migration by up to tens of percent. Our tests with production repositories show that the growth is typically below 10% of the size while increasing the throughput for read and write operations by 5 -- 10%.

It is recommended to run the **svnadmin pack** command on your repository every weekend, to achieve the full benefits of the SVN:

-   Minimizing the size of the Subversion repository
-   Reducing the number of Subversion repository files to speedup backup procedures
-   Ensuring efficient caching of the Subversion data on Subversion servers and OS level

#### Support for new MS Edge

Also worth mentioning is the fact, that Polarion supports the new Chromium-based Microsoft Edge browser that is quickly gaining popularity. The old versions of MS Edge are no longer tested and supported.

Information on currently supported browsers and browser versions are now provided in the System Requirements chapters of the installation guides for Linux and Windows, and in online Help. All are published on [Siemens Doc Center](https://polarion.plm.automation.siemens.com/documentation/latest%A0).

#### Changes to bundled Maven repository

The bundled Maven repository has been changed and no longer includes any third-party libraries. As a result, calculations and builds might start contacting Maven's central repository on the Internet. If the Polarion server has no connection to the Maven's central repository then you might consider employing a Maven repository manager.

Performance and Scalability
---------------------------

Our development teams are gradually working on improving Polarion performance and scalability. In the 20 R1 version we deliver one major project that brings a number of benefits throughout almost the whole Polarion feature set.

### Reworked historical search

Polarion handles HEAD and historical data differently. Different mechanisms and different algorithms are used to search and process head and historical data. The historical searching engine has been completely reworked. Some use cases are significantly better/faster (trend charts, for example) while others have similar performance as previously. However, in all cases, the scalability of the algorithm has been improved so that the overall historical operations are now performing better, and with lower memory allocation, especially when Polarion is under load when being used by hundreds of concurrent users.

The measurable benefits of this rework include, but are not limited to:

-   Faster execution of Lucene searches in history by 90%+
-   Faster execution of SQL searches in history by 95%+
-   Faster opening of Documents & Pages in history by 95%+
-   Faster lazy-loading of Work Items in LiveDocs in case they display Linked Work Items in their presentation layout
-   Faster loading of Document compare views
-   Faster initial rendering of the trend chart widgets
-   Shortened duration of the DB History Creator job after Polarion restart to minutes

Polarion creates so-called "baseline views" to filter the raw result of historical Lucene search in order to get the correct result that only includes objects that actually exist in the specified baseline. By default, Polarion preloads and caches baseline views for the last 180 days, which ensures quick initial rendering of trend charts that span up to 6 months into the past. Additional tuning can improve the performance of the historical searches in older history at the expense of increased memory consumption.

### Configurable attachments indexing

Polarion by default indexes the content of attachment to allow searching for objects by the content of their attachments, .e.g a Work Item can be found via the content of its attached Excel sheet. However, it turns out that with specific data the attachments content index can grow substantially, without actually providing the benefit to the end-users.

For this release, we provide a more granular configuration of what attachment types are indexed for content. Also, the default list of indexed types has been reviewed, e.g. the content of archives is no longer indexed by default. To illustrate the great benefits of this small change on the data of one of our biggest customers:

-   Attachment indexing shortened from 84 to 23 minutes (-73%)
-   History indexing shortened from 32 to less than 19 hours (-42%)
-   Polarion data size on disk reduced from 812 to 91 GB (-89%)

Please refer to the Polarion Help topic "Attachment file types for indexing" for additional details.

### Faster loading of the Documents & Pages in the navigation panel

While we are planning major rework of our existing navigation panel, we still provided a way to speed up the loading of Documents & Pages in the existing navigation in case there are thousands of Documents and Live Reports in the Project. From this release, the loading of objects into the navigation can relax the permissions check, which results in 80%+ speedup. With these settings, the users may see the title of restricted objects in the navigation panel, but will not be able to open the actual object.

### Form extensions are asynchronous only

Following the option provided in the Polarion 19.3 to load the Work Item form extensions asynchronously, this option now becomes the only option. This change ensures users get the Polarion data quickly, while an external content of scripted sections of the Work Item can be processed in the background.

Notable Issue Fixes
-------------------

-   GitHubCommit cannot be found by net.sf.ehcache
-   Jira Connector: NullPointerException when synchronizing emptied description field
-   Memory leak in Web Service session and transaction management
-   Regression in 19.1: Index out of bounds error when comparing bigger table with merged cells
-   Regression in 19.3: Editable fields of referenced Work Items after refreshing lazy-loaded Document
-   Regression in 19.3: Fields recalculation fails on Lucene query hard limit
-   Regression in 19.3: Wrong Work Item created in Document when Properties sidebar is opened
-   Wrong repo or credentials in GitHub, Bitbucket Connector configuration interrupts Polarion startup

For a listing of all fixed issues in the release, see the [Resolved Issues](https://docs.plm.automation.siemens.com/content/polarion/20/help/common/en_US/graphics/fileLibrary/20_R1/resolved_workitems.html) file.

Last but not least
------------------

#### New release cycle coming in 2020

In case you've not yet heard, this is the last release of the quarterly release cycle we have followed for quite some time. We'll be moving to a new product release schedule of 2 major releases per year and more frequent hotfix releases, as requested by many of you. For more details, check out this  [Software Field Bulletin](https://solutions.industrysoftware.automation.siemens.com/view.php?si=sfb-polarion-8016388).

#### Update Information

Version 20 R1 is an update for all Polarion ALM products. It is free to all customers with a current maintenance subscription. You can download the update distribution at: <https://polarion.plm.automation.siemens.com/downloads/update>. For details, see the bundled HOW_TO_INSTALL_THIS_UPDATE.txt in the update distribution package or available on Siemens Doc Center.

#### Evaluation

If you would like to evaluate this release before updating your production installation, simply visit <https://polarion.plm.automation.siemens.com/downloads>, download the product of your choice, install it and use the built-in 30-day evaluation license.

If you have any questions or comments, please don't hesitate to contact me or your Polarion technical support contact. On behalf of our entire team, thank you for using Polarion ALM.
---

copyright:
  years: 2014, 2020
lastupdated: "2020-01-27"

keywords: Block Storage, limit increase, global quota, quota increase

subcollection: BlockStorage

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="DomainName"}
{:shortdesc: .shortdesc}
{:support: data-reuse='support'}
{:help: data-hd-content-type='help'}

# Managing storage limits
{: #managingstoragelimits}
{: help}
{: support}

By default, you can provision a combined total of 250 {{site.data.keyword.blockstorageshort}} and {{site.data.keyword.filestorage_short}} volumes globally.

If you're unsure how many volumes you have, you can list the number of your volumes by using the following `slcli` command.
```
# slcli block volume-limit
```
Example output:
```
[{'datacenterName': 'global', 'maximumAvailableCount': 250, 'provisioned Count':117}]
:............:.......................:..................:
: Datacenter : maximumAvailableCount : ProvisionedCount :
:............:.......................:..................:
:   global   :           250         :         117      :
:............:.......................:..................:
```
The API call shows the combined number of {{site.data.keyword.blockstorageshort}} and {{site.data.keyword.filestorage_short}}.
{:tip}


You can request a limit increase by submitting a support case in the [console](https://{DomainName}/unifiedsupport/cases/add){: external}. When the request is approved, you get a volume limit that is set for a specific data center.
{:shortdesc}

To request a limit increase, open a case and direct it to your sales representative.

In the case, provide the following information:

- **Ticket Subject**: Request to Increase Data Center Volume Count Storage Limit

- **What is the use case for the additional volumes request?** <br />
*For example, your answer might be something similar to a new VMware datastore, a new development and testing (dev/test) environment, an SQL database, or logging.*

- **How many extra Block volumes are needed by type, size, IOPS, and location?** <br />
*For example, your answer might be something similar to "25x Endurance 2 TB @ 4 IOPS in DAL09" or "25x Performance 4 TB @ 2 IOPS in WDC04".*

- **How many extra File volumes are needed by type, size, IOPS, and location?** <br />
*For example, your answer might be something similar to "25x Performance 20 GB @ 10 IOPS in DAL09" or "50x Endurance 2 TB @ 0.25 IOPS in SJC03".*

- **Provide an estimate of when you expect or plan to provision all of the requested volume increase.** <br />
*For example, your answer might be something similar to "90 days".*

- **Provide a 90-day forecast of expected average capacity usage of these volumes.** <br />
*For example, your answer might be something similar to "expect 25 percent to be used in 30 days, 50 percent to be used in 60 days and 75 percent to be used in 90 days".*

Respond to all questions and statements in your request. They are required for processing and approval.
{:important}

You're going to be notified of the update to your limits through the case process.

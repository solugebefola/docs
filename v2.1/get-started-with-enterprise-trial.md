---
title: Enterprise Trial –– Get Started
summary: Check out this page to get started with your CockroachDB Enterprise Trial
toc: true
license: true
---

Congratulations on starting your CockroachDB Enterprise Trial! With it, you'll not only get access to CockroachDB's core capabilities like [high availability](high-availability.html) and [`SERIALIZABLE` isolation](strong-consistency.html), but also our Enterprise-only features like distributed [`BACKUP`](backup.html) &amp; [`RESTORE`](restore.html), [geo-partitioning](partitioning.html), and [cluster visualization](enable-node-map.html).

## Install CockroachDB

If you haven't already, you'll need to [locally install](install-cockroachdb.html), [remotely deploy](manual-deployment.html), or [orchestrate](orchestration.html) CockroachDB.

## Enable Enterprise features

As the CockroachDB `root` user, open the [built-in SQL shell](use-the-built-in-sql-client.html) in insecure or secure mode, as per your CockroachDB setup. In the following example, we assume that CockroachDB is running in insecure mode.

{% include copy-clipboard.html %}
~~~ shell
$ cockroach sql --insecure
~~~

{{site.data.alerts.callout_info}}
If you've secured your deployment, you'll need to [include the flags for your certificates](create-security-certificates.html) instead of the `--insecure` flag.
{{site.data.alerts.end}}

Now, use the `SET CLUSTER SETTING` command to set the name of your organization and the license key:

{% include copy-clipboard.html %}
~~~ sql
>  SET CLUSTER SETTING cluster.organization = 'Acme Company'; SET CLUSTER SETTING enterprise.license = 'xxxxxxxxxxxx';
~~~

Then verify your organization in response to the following query:

{% include copy-clipboard.html %}
~~~ sql
>  SHOW CLUSTER SETTING cluster.organization;
~~~

## Use Enterprise features

Your cluster now has access to all of CockroachDB's enterprise features for the length of the trial:

- [`BACKUP`](backup.html) & [`RESTORE`](restore.html), which leverage your entirely cluster to create and consume consistent backups.
- [Geo-partitioning](partitioning.html) to control the physical location of your data with row-level granularity.
- [Node Maps](enable-node-map.html), which provides enhanced visuals of your cluster's nodes.
- [Use role-based access management (RBAC)](create-role.html) for simplified user management.

## Getting help

If you or your team need any help during your trial, our engineers are available on [CockroachDB Community Slack](https://cockroachdb.slack.com), [our forum](https://forum.cockroachlabs.com/), or [GitHub](https://github.com/cockroachdb/cockroach).</p>

## See also

- [Enterprise Licensing](enterprise-licensing.html)
- [`SET CLUSTER SETTING`](set-cluster-setting.html)
- [`SHOW CLUSTER SETTING`](show-cluster-setting.html)


---
title: "getSnapshot"
title_tag: "azure.compute.getSnapshot"
meta_desc: "Documentation for the azure.compute.getSnapshot function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Use this data source to access information about an existing Snapshot.


{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}





{{< example csharp >}}

```csharp
using Pulumi;
using Azure = Pulumi.Azure;

class MyStack : Stack
{
    public MyStack()
    {
        var example = Output.Create(Azure.Compute.GetSnapshot.InvokeAsync(new Azure.Compute.GetSnapshotArgs
        {
            Name = "my-snapshot",
            ResourceGroupName = "my-resource-group",
        }));
    }

}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-azure/sdk/v3/go/azure/compute"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		_, err := compute.LookupSnapshot(ctx, &compute.LookupSnapshotArgs{
			Name:              "my-snapshot",
			ResourceGroupName: "my-resource-group",
		}, nil)
		if err != nil {
			return err
		}
		return nil
	})
}
```


{{< /example >}}


{{< example python >}}

```python
import pulumi
import pulumi_azure as azure

example = azure.compute.get_snapshot(name="my-snapshot",
    resource_group_name="my-resource-group")
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as azure from "@pulumi/azure";

const example = pulumi.output(azure.compute.getSnapshot({
    name: "my-snapshot",
    resourceGroupName: "my-resource-group",
}, { async: true }));
```


{{< /example >}}





{{% /examples %}}




## Using getSnapshot {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getSnapshot<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetSnapshotArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetSnapshotResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_snapshot(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">resource_group_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetSnapshotResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupSnapshot<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">args</span><span class="p"> *</span><span class="nx">LookupSnapshotArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">LookupSnapshotResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `LookupSnapshot` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetSnapshot </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetSnapshotResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetSnapshotArgs</span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Snapshot.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_csharp">
<a href="#resourcegroupname_csharp" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the resource group the Snapshot is located in.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Snapshot.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_go">
<a href="#resourcegroupname_go" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the resource group the Snapshot is located in.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Snapshot.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_nodejs">
<a href="#resourcegroupname_nodejs" style="color: inherit; text-decoration: inherit;">resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the resource group the Snapshot is located in.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Snapshot.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resource_group_name_python">
<a href="#resource_group_name_python" style="color: inherit; text-decoration: inherit;">resource_<wbr>group_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the resource group the Snapshot is located in.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getSnapshot Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="creationoption_csharp">
<a href="#creationoption_csharp" style="color: inherit; text-decoration: inherit;">Creation<wbr>Option</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="disksizegb_csharp">
<a href="#disksizegb_csharp" style="color: inherit; text-decoration: inherit;">Disk<wbr>Size<wbr>Gb</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The size of the Snapshotted Disk in GB.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="encryptionsettings_csharp">
<a href="#encryptionsettings_csharp" style="color: inherit; text-decoration: inherit;">Encryption<wbr>Settings</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getsnapshotencryptionsetting">List&lt;Get<wbr>Snapshot<wbr>Encryption<wbr>Setting&gt;</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="id_csharp">
<a href="#id_csharp" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="ostype_csharp">
<a href="#ostype_csharp" style="color: inherit; text-decoration: inherit;">Os<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="resourcegroupname_csharp">
<a href="#resourcegroupname_csharp" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="sourceresourceid_csharp">
<a href="#sourceresourceid_csharp" style="color: inherit; text-decoration: inherit;">Source<wbr>Resource<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The reference to an existing snapshot.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="sourceuri_csharp">
<a href="#sourceuri_csharp" style="color: inherit; text-decoration: inherit;">Source<wbr>Uri</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The URI to a Managed or Unmanaged Disk.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="storageaccountid_csharp">
<a href="#storageaccountid_csharp" style="color: inherit; text-decoration: inherit;">Storage<wbr>Account<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of an storage account.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="timecreated_csharp">
<a href="#timecreated_csharp" style="color: inherit; text-decoration: inherit;">Time<wbr>Created</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="creationoption_go">
<a href="#creationoption_go" style="color: inherit; text-decoration: inherit;">Creation<wbr>Option</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="disksizegb_go">
<a href="#disksizegb_go" style="color: inherit; text-decoration: inherit;">Disk<wbr>Size<wbr>Gb</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The size of the Snapshotted Disk in GB.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="encryptionsettings_go">
<a href="#encryptionsettings_go" style="color: inherit; text-decoration: inherit;">Encryption<wbr>Settings</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getsnapshotencryptionsetting">[]Get<wbr>Snapshot<wbr>Encryption<wbr>Setting</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="id_go">
<a href="#id_go" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="ostype_go">
<a href="#ostype_go" style="color: inherit; text-decoration: inherit;">Os<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="resourcegroupname_go">
<a href="#resourcegroupname_go" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="sourceresourceid_go">
<a href="#sourceresourceid_go" style="color: inherit; text-decoration: inherit;">Source<wbr>Resource<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The reference to an existing snapshot.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="sourceuri_go">
<a href="#sourceuri_go" style="color: inherit; text-decoration: inherit;">Source<wbr>Uri</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The URI to a Managed or Unmanaged Disk.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="storageaccountid_go">
<a href="#storageaccountid_go" style="color: inherit; text-decoration: inherit;">Storage<wbr>Account<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of an storage account.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="timecreated_go">
<a href="#timecreated_go" style="color: inherit; text-decoration: inherit;">Time<wbr>Created</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="creationoption_nodejs">
<a href="#creationoption_nodejs" style="color: inherit; text-decoration: inherit;">creation<wbr>Option</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="disksizegb_nodejs">
<a href="#disksizegb_nodejs" style="color: inherit; text-decoration: inherit;">disk<wbr>Size<wbr>Gb</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The size of the Snapshotted Disk in GB.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="encryptionsettings_nodejs">
<a href="#encryptionsettings_nodejs" style="color: inherit; text-decoration: inherit;">encryption<wbr>Settings</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getsnapshotencryptionsetting">Get<wbr>Snapshot<wbr>Encryption<wbr>Setting[]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="id_nodejs">
<a href="#id_nodejs" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="ostype_nodejs">
<a href="#ostype_nodejs" style="color: inherit; text-decoration: inherit;">os<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="resourcegroupname_nodejs">
<a href="#resourcegroupname_nodejs" style="color: inherit; text-decoration: inherit;">resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="sourceresourceid_nodejs">
<a href="#sourceresourceid_nodejs" style="color: inherit; text-decoration: inherit;">source<wbr>Resource<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The reference to an existing snapshot.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="sourceuri_nodejs">
<a href="#sourceuri_nodejs" style="color: inherit; text-decoration: inherit;">source<wbr>Uri</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The URI to a Managed or Unmanaged Disk.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="storageaccountid_nodejs">
<a href="#storageaccountid_nodejs" style="color: inherit; text-decoration: inherit;">storage<wbr>Account<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of an storage account.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="timecreated_nodejs">
<a href="#timecreated_nodejs" style="color: inherit; text-decoration: inherit;">time<wbr>Created</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="creation_option_python">
<a href="#creation_option_python" style="color: inherit; text-decoration: inherit;">creation_<wbr>option</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="disk_size_gb_python">
<a href="#disk_size_gb_python" style="color: inherit; text-decoration: inherit;">disk_<wbr>size_<wbr>gb</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The size of the Snapshotted Disk in GB.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="encryption_settings_python">
<a href="#encryption_settings_python" style="color: inherit; text-decoration: inherit;">encryption_<wbr>settings</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getsnapshotencryptionsetting">Sequence[Get<wbr>Snapshot<wbr>Encryption<wbr>Setting]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="id_python">
<a href="#id_python" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="os_type_python">
<a href="#os_type_python" style="color: inherit; text-decoration: inherit;">os_<wbr>type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="resource_group_name_python">
<a href="#resource_group_name_python" style="color: inherit; text-decoration: inherit;">resource_<wbr>group_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="source_resource_id_python">
<a href="#source_resource_id_python" style="color: inherit; text-decoration: inherit;">source_<wbr>resource_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The reference to an existing snapshot.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="source_uri_python">
<a href="#source_uri_python" style="color: inherit; text-decoration: inherit;">source_<wbr>uri</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The URI to a Managed or Unmanaged Disk.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="storage_account_id_python">
<a href="#storage_account_id_python" style="color: inherit; text-decoration: inherit;">storage_<wbr>account_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of an storage account.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="time_created_python">
<a href="#time_created_python" style="color: inherit; text-decoration: inherit;">time_<wbr>created</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}




## Supporting Types


<h4 id="getsnapshotencryptionsetting">Get<wbr>Snapshot<wbr>Encryption<wbr>Setting</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="diskencryptionkeys_csharp">
<a href="#diskencryptionkeys_csharp" style="color: inherit; text-decoration: inherit;">Disk<wbr>Encryption<wbr>Keys</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getsnapshotencryptionsettingdiskencryptionkey">List&lt;Get<wbr>Snapshot<wbr>Encryption<wbr>Setting<wbr>Disk<wbr>Encryption<wbr>Key<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="enabled_csharp">
<a href="#enabled_csharp" style="color: inherit; text-decoration: inherit;">Enabled</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="keyencryptionkeys_csharp">
<a href="#keyencryptionkeys_csharp" style="color: inherit; text-decoration: inherit;">Key<wbr>Encryption<wbr>Keys</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getsnapshotencryptionsettingkeyencryptionkey">List&lt;Get<wbr>Snapshot<wbr>Encryption<wbr>Setting<wbr>Key<wbr>Encryption<wbr>Key<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="diskencryptionkeys_go">
<a href="#diskencryptionkeys_go" style="color: inherit; text-decoration: inherit;">Disk<wbr>Encryption<wbr>Keys</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getsnapshotencryptionsettingdiskencryptionkey">[]Get<wbr>Snapshot<wbr>Encryption<wbr>Setting<wbr>Disk<wbr>Encryption<wbr>Key</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="enabled_go">
<a href="#enabled_go" style="color: inherit; text-decoration: inherit;">Enabled</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="keyencryptionkeys_go">
<a href="#keyencryptionkeys_go" style="color: inherit; text-decoration: inherit;">Key<wbr>Encryption<wbr>Keys</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getsnapshotencryptionsettingkeyencryptionkey">[]Get<wbr>Snapshot<wbr>Encryption<wbr>Setting<wbr>Key<wbr>Encryption<wbr>Key</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="diskencryptionkeys_nodejs">
<a href="#diskencryptionkeys_nodejs" style="color: inherit; text-decoration: inherit;">disk<wbr>Encryption<wbr>Keys</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getsnapshotencryptionsettingdiskencryptionkey">Get<wbr>Snapshot<wbr>Encryption<wbr>Setting<wbr>Disk<wbr>Encryption<wbr>Key[]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="enabled_nodejs">
<a href="#enabled_nodejs" style="color: inherit; text-decoration: inherit;">enabled</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="keyencryptionkeys_nodejs">
<a href="#keyencryptionkeys_nodejs" style="color: inherit; text-decoration: inherit;">key<wbr>Encryption<wbr>Keys</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getsnapshotencryptionsettingkeyencryptionkey">Get<wbr>Snapshot<wbr>Encryption<wbr>Setting<wbr>Key<wbr>Encryption<wbr>Key[]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="disk_encryption_keys_python">
<a href="#disk_encryption_keys_python" style="color: inherit; text-decoration: inherit;">disk_<wbr>encryption_<wbr>keys</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getsnapshotencryptionsettingdiskencryptionkey">Sequence[Get<wbr>Snapshot<wbr>Encryption<wbr>Setting<wbr>Disk<wbr>Encryption<wbr>Key<wbr>Args]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="enabled_python">
<a href="#enabled_python" style="color: inherit; text-decoration: inherit;">enabled</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="key_encryption_keys_python">
<a href="#key_encryption_keys_python" style="color: inherit; text-decoration: inherit;">key_<wbr>encryption_<wbr>keys</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getsnapshotencryptionsettingkeyencryptionkey">Sequence[Get<wbr>Snapshot<wbr>Encryption<wbr>Setting<wbr>Key<wbr>Encryption<wbr>Key<wbr>Args]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

<h4 id="getsnapshotencryptionsettingdiskencryptionkey">Get<wbr>Snapshot<wbr>Encryption<wbr>Setting<wbr>Disk<wbr>Encryption<wbr>Key</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="secreturl_csharp">
<a href="#secreturl_csharp" style="color: inherit; text-decoration: inherit;">Secret<wbr>Url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="sourcevaultid_csharp">
<a href="#sourcevaultid_csharp" style="color: inherit; text-decoration: inherit;">Source<wbr>Vault<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="secreturl_go">
<a href="#secreturl_go" style="color: inherit; text-decoration: inherit;">Secret<wbr>Url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="sourcevaultid_go">
<a href="#sourcevaultid_go" style="color: inherit; text-decoration: inherit;">Source<wbr>Vault<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="secreturl_nodejs">
<a href="#secreturl_nodejs" style="color: inherit; text-decoration: inherit;">secret<wbr>Url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="sourcevaultid_nodejs">
<a href="#sourcevaultid_nodejs" style="color: inherit; text-decoration: inherit;">source<wbr>Vault<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="secret_url_python">
<a href="#secret_url_python" style="color: inherit; text-decoration: inherit;">secret_<wbr>url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="source_vault_id_python">
<a href="#source_vault_id_python" style="color: inherit; text-decoration: inherit;">source_<wbr>vault_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

<h4 id="getsnapshotencryptionsettingkeyencryptionkey">Get<wbr>Snapshot<wbr>Encryption<wbr>Setting<wbr>Key<wbr>Encryption<wbr>Key</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="keyurl_csharp">
<a href="#keyurl_csharp" style="color: inherit; text-decoration: inherit;">Key<wbr>Url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="sourcevaultid_csharp">
<a href="#sourcevaultid_csharp" style="color: inherit; text-decoration: inherit;">Source<wbr>Vault<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="keyurl_go">
<a href="#keyurl_go" style="color: inherit; text-decoration: inherit;">Key<wbr>Url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="sourcevaultid_go">
<a href="#sourcevaultid_go" style="color: inherit; text-decoration: inherit;">Source<wbr>Vault<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="keyurl_nodejs">
<a href="#keyurl_nodejs" style="color: inherit; text-decoration: inherit;">key<wbr>Url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="sourcevaultid_nodejs">
<a href="#sourcevaultid_nodejs" style="color: inherit; text-decoration: inherit;">source<wbr>Vault<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="key_url_python">
<a href="#key_url_python" style="color: inherit; text-decoration: inherit;">key_<wbr>url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="source_vault_id_python">
<a href="#source_vault_id_python" style="color: inherit; text-decoration: inherit;">source_<wbr>vault_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-azure">https://github.com/pulumi/pulumi-azure</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`azurerm` Terraform Provider](https://github.com/terraform-providers/terraform-provider-azurerm).{{% /md %}}</dd>
</dl>


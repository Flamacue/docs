
---
title: "getDnsZone"
title_tag: "azure.privatedns.getDnsZone"
meta_desc: "Documentation for the azure.privatedns.getDnsZone function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Use this data source to access information about an existing Private DNS Zone.


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
        var example = Output.Create(Azure.PrivateDns.GetDnsZone.InvokeAsync(new Azure.PrivateDns.GetDnsZoneArgs
        {
            Name = "contoso.internal",
            ResourceGroupName = "contoso-dns",
        }));
        this.PrivateDnsZoneId = example.Apply(example => example.Id);
    }

    [Output("privateDnsZoneId")]
    public Output<string> PrivateDnsZoneId { get; set; }
}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-azure/sdk/v3/go/azure/privatedns"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		opt0 := "contoso-dns"
		example, err := privatedns.GetDnsZone(ctx, &privatedns.GetDnsZoneArgs{
			Name:              "contoso.internal",
			ResourceGroupName: &opt0,
		}, nil)
		if err != nil {
			return err
		}
		ctx.Export("privateDnsZoneId", example.Id)
		return nil
	})
}
```


{{< /example >}}


{{< example python >}}

```python
import pulumi
import pulumi_azure as azure

example = azure.privatedns.get_dns_zone(name="contoso.internal",
    resource_group_name="contoso-dns")
pulumi.export("privateDnsZoneId", example.id)
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as azure from "@pulumi/azure";

const example = azure.privatedns.getDnsZone({
    name: "contoso.internal",
    resourceGroupName: "contoso-dns",
});
export const privateDnsZoneId = example.then(example => example.id);
```


{{< /example >}}





{{% /examples %}}




## Using getDnsZone {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getDnsZone<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetDnsZoneArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetDnsZoneResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_dns_zone(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">resource_group_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetDnsZoneResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetDnsZone<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">args</span><span class="p"> *</span><span class="nx">GetDnsZoneArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">GetDnsZoneResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `GetDnsZone` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetDnsZone </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetDnsZoneResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetDnsZoneArgs</span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
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
    <dd>{{% md %}}The name of the Private DNS Zone.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="resourcegroupname_csharp">
<a href="#resourcegroupname_csharp" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Name of the Resource Group where the Private DNS Zone exists.
If the Name of the Resource Group is not provided, the first Private DNS Zone from the list of Private
DNS Zones in your subscription that matches `name` will be returned.
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
    <dd>{{% md %}}The name of the Private DNS Zone.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="resourcegroupname_go">
<a href="#resourcegroupname_go" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Name of the Resource Group where the Private DNS Zone exists.
If the Name of the Resource Group is not provided, the first Private DNS Zone from the list of Private
DNS Zones in your subscription that matches `name` will be returned.
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
    <dd>{{% md %}}The name of the Private DNS Zone.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="resourcegroupname_nodejs">
<a href="#resourcegroupname_nodejs" style="color: inherit; text-decoration: inherit;">resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Name of the Resource Group where the Private DNS Zone exists.
If the Name of the Resource Group is not provided, the first Private DNS Zone from the list of Private
DNS Zones in your subscription that matches `name` will be returned.
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
    <dd>{{% md %}}The name of the Private DNS Zone.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="resource_group_name_python">
<a href="#resource_group_name_python" style="color: inherit; text-decoration: inherit;">resource_<wbr>group_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Name of the Resource Group where the Private DNS Zone exists.
If the Name of the Resource Group is not provided, the first Private DNS Zone from the list of Private
DNS Zones in your subscription that matches `name` will be returned.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getDnsZone Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
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
        <span id="maxnumberofrecordsets_csharp">
<a href="#maxnumberofrecordsets_csharp" style="color: inherit; text-decoration: inherit;">Max<wbr>Number<wbr>Of<wbr>Record<wbr>Sets</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Maximum number of recordsets that can be created in this Private Zone.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="maxnumberofvirtualnetworklinks_csharp">
<a href="#maxnumberofvirtualnetworklinks_csharp" style="color: inherit; text-decoration: inherit;">Max<wbr>Number<wbr>Of<wbr>Virtual<wbr>Network<wbr>Links</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Maximum number of Virtual Networks that can be linked to this Private Zone.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="maxnumberofvirtualnetworklinkswithregistration_csharp">
<a href="#maxnumberofvirtualnetworklinkswithregistration_csharp" style="color: inherit; text-decoration: inherit;">Max<wbr>Number<wbr>Of<wbr>Virtual<wbr>Network<wbr>Links<wbr>With<wbr>Registration</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Maximum number of Virtual Networks that can be linked to this Private Zone with registration enabled.
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
        <span id="numberofrecordsets_csharp">
<a href="#numberofrecordsets_csharp" style="color: inherit; text-decoration: inherit;">Number<wbr>Of<wbr>Record<wbr>Sets</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of recordsets currently in the zone.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="resourcegroupname_csharp">
<a href="#resourcegroupname_csharp" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="tags_csharp">
<a href="#tags_csharp" style="color: inherit; text-decoration: inherit;">Tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Dictionary&lt;string, string&gt;</span>
    </dt>
    <dd>{{% md %}}A mapping of tags for the zone.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
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
        <span id="maxnumberofrecordsets_go">
<a href="#maxnumberofrecordsets_go" style="color: inherit; text-decoration: inherit;">Max<wbr>Number<wbr>Of<wbr>Record<wbr>Sets</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Maximum number of recordsets that can be created in this Private Zone.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="maxnumberofvirtualnetworklinks_go">
<a href="#maxnumberofvirtualnetworklinks_go" style="color: inherit; text-decoration: inherit;">Max<wbr>Number<wbr>Of<wbr>Virtual<wbr>Network<wbr>Links</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Maximum number of Virtual Networks that can be linked to this Private Zone.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="maxnumberofvirtualnetworklinkswithregistration_go">
<a href="#maxnumberofvirtualnetworklinkswithregistration_go" style="color: inherit; text-decoration: inherit;">Max<wbr>Number<wbr>Of<wbr>Virtual<wbr>Network<wbr>Links<wbr>With<wbr>Registration</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Maximum number of Virtual Networks that can be linked to this Private Zone with registration enabled.
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
        <span id="numberofrecordsets_go">
<a href="#numberofrecordsets_go" style="color: inherit; text-decoration: inherit;">Number<wbr>Of<wbr>Record<wbr>Sets</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of recordsets currently in the zone.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="resourcegroupname_go">
<a href="#resourcegroupname_go" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="tags_go">
<a href="#tags_go" style="color: inherit; text-decoration: inherit;">Tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}A mapping of tags for the zone.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
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
        <span id="maxnumberofrecordsets_nodejs">
<a href="#maxnumberofrecordsets_nodejs" style="color: inherit; text-decoration: inherit;">max<wbr>Number<wbr>Of<wbr>Record<wbr>Sets</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Maximum number of recordsets that can be created in this Private Zone.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="maxnumberofvirtualnetworklinks_nodejs">
<a href="#maxnumberofvirtualnetworklinks_nodejs" style="color: inherit; text-decoration: inherit;">max<wbr>Number<wbr>Of<wbr>Virtual<wbr>Network<wbr>Links</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Maximum number of Virtual Networks that can be linked to this Private Zone.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="maxnumberofvirtualnetworklinkswithregistration_nodejs">
<a href="#maxnumberofvirtualnetworklinkswithregistration_nodejs" style="color: inherit; text-decoration: inherit;">max<wbr>Number<wbr>Of<wbr>Virtual<wbr>Network<wbr>Links<wbr>With<wbr>Registration</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Maximum number of Virtual Networks that can be linked to this Private Zone with registration enabled.
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
        <span id="numberofrecordsets_nodejs">
<a href="#numberofrecordsets_nodejs" style="color: inherit; text-decoration: inherit;">number<wbr>Of<wbr>Record<wbr>Sets</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of recordsets currently in the zone.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="resourcegroupname_nodejs">
<a href="#resourcegroupname_nodejs" style="color: inherit; text-decoration: inherit;">resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="tags_nodejs">
<a href="#tags_nodejs" style="color: inherit; text-decoration: inherit;">tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags for the zone.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
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
        <span id="max_number_of_record_sets_python">
<a href="#max_number_of_record_sets_python" style="color: inherit; text-decoration: inherit;">max_<wbr>number_<wbr>of_<wbr>record_<wbr>sets</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Maximum number of recordsets that can be created in this Private Zone.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="max_number_of_virtual_network_links_python">
<a href="#max_number_of_virtual_network_links_python" style="color: inherit; text-decoration: inherit;">max_<wbr>number_<wbr>of_<wbr>virtual_<wbr>network_<wbr>links</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Maximum number of Virtual Networks that can be linked to this Private Zone.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="max_number_of_virtual_network_links_with_registration_python">
<a href="#max_number_of_virtual_network_links_with_registration_python" style="color: inherit; text-decoration: inherit;">max_<wbr>number_<wbr>of_<wbr>virtual_<wbr>network_<wbr>links_<wbr>with_<wbr>registration</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Maximum number of Virtual Networks that can be linked to this Private Zone with registration enabled.
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
        <span id="number_of_record_sets_python">
<a href="#number_of_record_sets_python" style="color: inherit; text-decoration: inherit;">number_<wbr>of_<wbr>record_<wbr>sets</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of recordsets currently in the zone.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="resource_group_name_python">
<a href="#resource_group_name_python" style="color: inherit; text-decoration: inherit;">resource_<wbr>group_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="tags_python">
<a href="#tags_python" style="color: inherit; text-decoration: inherit;">tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Mapping[str, str]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags for the zone.
{{% /md %}}</dd></dl>
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


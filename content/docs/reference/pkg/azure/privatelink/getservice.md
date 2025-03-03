
---
title: "getService"
title_tag: "azure.privatelink.getService"
meta_desc: "Documentation for the azure.privatelink.getService function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Use this data source to access information about an existing Private Link Service.


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
        var example = Output.Create(Azure.PrivateLink.GetService.InvokeAsync(new Azure.PrivateLink.GetServiceArgs
        {
            Name = "myPrivateLinkService",
            ResourceGroupName = "PrivateLinkServiceRG",
        }));
        this.PrivateLinkServiceId = example.Apply(example => example.Id);
    }

    [Output("privateLinkServiceId")]
    public Output<string> PrivateLinkServiceId { get; set; }
}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-azure/sdk/v3/go/azure/privatelink"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		example, err := privatelink.GetService(ctx, &privatelink.GetServiceArgs{
			Name:              "myPrivateLinkService",
			ResourceGroupName: "PrivateLinkServiceRG",
		}, nil)
		if err != nil {
			return err
		}
		ctx.Export("privateLinkServiceId", example.Id)
		return nil
	})
}
```


{{< /example >}}


{{< example python >}}

```python
import pulumi
import pulumi_azure as azure

example = azure.privatelink.get_service(name="myPrivateLinkService",
    resource_group_name="PrivateLinkServiceRG")
pulumi.export("privateLinkServiceId", example.id)
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as azure from "@pulumi/azure";

const example = azure.privatelink.getService({
    name: "myPrivateLinkService",
    resourceGroupName: "PrivateLinkServiceRG",
});
export const privateLinkServiceId = example.then(example => example.id);
```


{{< /example >}}





{{% /examples %}}




## Using getService {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getService<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetServiceArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetServiceResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_service(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">resource_group_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetServiceResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetService<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">args</span><span class="p"> *</span><span class="nx">GetServiceArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">GetServiceResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `GetService` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetService </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetServiceResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetServiceArgs</span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
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
    <dd>{{% md %}}The name of the private link service.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_csharp">
<a href="#resourcegroupname_csharp" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource group in which the private link service resides.
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
    <dd>{{% md %}}The name of the private link service.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_go">
<a href="#resourcegroupname_go" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource group in which the private link service resides.
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
    <dd>{{% md %}}The name of the private link service.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_nodejs">
<a href="#resourcegroupname_nodejs" style="color: inherit; text-decoration: inherit;">resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource group in which the private link service resides.
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
    <dd>{{% md %}}The name of the private link service.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resource_group_name_python">
<a href="#resource_group_name_python" style="color: inherit; text-decoration: inherit;">resource_<wbr>group_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the resource group in which the private link service resides.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getService Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="alias_csharp">
<a href="#alias_csharp" style="color: inherit; text-decoration: inherit;">Alias</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The alias is a globally unique name for your private link service which Azure generates for you. Your can use this alias to request a connection to your private link service.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="autoapprovalsubscriptionids_csharp">
<a href="#autoapprovalsubscriptionids_csharp" style="color: inherit; text-decoration: inherit;">Auto<wbr>Approval<wbr>Subscription<wbr>Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}The list of subscription(s) globally unique identifiers that will be auto approved to use the private link service.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="enableproxyprotocol_csharp">
<a href="#enableproxyprotocol_csharp" style="color: inherit; text-decoration: inherit;">Enable<wbr>Proxy<wbr>Protocol</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Does the Private Link Service support the Proxy Protocol?
{{% /md %}}</dd><dt class="property-"
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
        <span id="loadbalancerfrontendipconfigurationids_csharp">
<a href="#loadbalancerfrontendipconfigurationids_csharp" style="color: inherit; text-decoration: inherit;">Load<wbr>Balancer<wbr>Frontend<wbr>Ip<wbr>Configuration<wbr>Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}The list of Standard Load Balancer(SLB) resource IDs. The Private Link service is tied to the frontend IP address of a SLB. All traffic destined for the private link service will reach the frontend of the SLB. You can configure SLB rules to direct this traffic to appropriate backend pools where your applications are running.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="location_csharp">
<a href="#location_csharp" style="color: inherit; text-decoration: inherit;">Location</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The supported Azure location where the resource exists.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of private link service NAT IP configuration.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="natipconfigurations_csharp">
<a href="#natipconfigurations_csharp" style="color: inherit; text-decoration: inherit;">Nat<wbr>Ip<wbr>Configurations</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getservicenatipconfiguration">List&lt;Get<wbr>Service<wbr>Nat<wbr>Ip<wbr>Configuration&gt;</a></span>
    </dt>
    <dd>{{% md %}}The `nat_ip_configuration` block as defined below.
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
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="visibilitysubscriptionids_csharp">
<a href="#visibilitysubscriptionids_csharp" style="color: inherit; text-decoration: inherit;">Visibility<wbr>Subscription<wbr>Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}The list of subscription(s) globally unique identifiers(GUID) that will be able to see the private link service.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="alias_go">
<a href="#alias_go" style="color: inherit; text-decoration: inherit;">Alias</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The alias is a globally unique name for your private link service which Azure generates for you. Your can use this alias to request a connection to your private link service.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="autoapprovalsubscriptionids_go">
<a href="#autoapprovalsubscriptionids_go" style="color: inherit; text-decoration: inherit;">Auto<wbr>Approval<wbr>Subscription<wbr>Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The list of subscription(s) globally unique identifiers that will be auto approved to use the private link service.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="enableproxyprotocol_go">
<a href="#enableproxyprotocol_go" style="color: inherit; text-decoration: inherit;">Enable<wbr>Proxy<wbr>Protocol</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Does the Private Link Service support the Proxy Protocol?
{{% /md %}}</dd><dt class="property-"
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
        <span id="loadbalancerfrontendipconfigurationids_go">
<a href="#loadbalancerfrontendipconfigurationids_go" style="color: inherit; text-decoration: inherit;">Load<wbr>Balancer<wbr>Frontend<wbr>Ip<wbr>Configuration<wbr>Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The list of Standard Load Balancer(SLB) resource IDs. The Private Link service is tied to the frontend IP address of a SLB. All traffic destined for the private link service will reach the frontend of the SLB. You can configure SLB rules to direct this traffic to appropriate backend pools where your applications are running.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="location_go">
<a href="#location_go" style="color: inherit; text-decoration: inherit;">Location</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The supported Azure location where the resource exists.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of private link service NAT IP configuration.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="natipconfigurations_go">
<a href="#natipconfigurations_go" style="color: inherit; text-decoration: inherit;">Nat<wbr>Ip<wbr>Configurations</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getservicenatipconfiguration">[]Get<wbr>Service<wbr>Nat<wbr>Ip<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}The `nat_ip_configuration` block as defined below.
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
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="visibilitysubscriptionids_go">
<a href="#visibilitysubscriptionids_go" style="color: inherit; text-decoration: inherit;">Visibility<wbr>Subscription<wbr>Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The list of subscription(s) globally unique identifiers(GUID) that will be able to see the private link service.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="alias_nodejs">
<a href="#alias_nodejs" style="color: inherit; text-decoration: inherit;">alias</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The alias is a globally unique name for your private link service which Azure generates for you. Your can use this alias to request a connection to your private link service.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="autoapprovalsubscriptionids_nodejs">
<a href="#autoapprovalsubscriptionids_nodejs" style="color: inherit; text-decoration: inherit;">auto<wbr>Approval<wbr>Subscription<wbr>Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The list of subscription(s) globally unique identifiers that will be auto approved to use the private link service.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="enableproxyprotocol_nodejs">
<a href="#enableproxyprotocol_nodejs" style="color: inherit; text-decoration: inherit;">enable<wbr>Proxy<wbr>Protocol</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Does the Private Link Service support the Proxy Protocol?
{{% /md %}}</dd><dt class="property-"
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
        <span id="loadbalancerfrontendipconfigurationids_nodejs">
<a href="#loadbalancerfrontendipconfigurationids_nodejs" style="color: inherit; text-decoration: inherit;">load<wbr>Balancer<wbr>Frontend<wbr>Ip<wbr>Configuration<wbr>Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The list of Standard Load Balancer(SLB) resource IDs. The Private Link service is tied to the frontend IP address of a SLB. All traffic destined for the private link service will reach the frontend of the SLB. You can configure SLB rules to direct this traffic to appropriate backend pools where your applications are running.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="location_nodejs">
<a href="#location_nodejs" style="color: inherit; text-decoration: inherit;">location</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The supported Azure location where the resource exists.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of private link service NAT IP configuration.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="natipconfigurations_nodejs">
<a href="#natipconfigurations_nodejs" style="color: inherit; text-decoration: inherit;">nat<wbr>Ip<wbr>Configurations</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getservicenatipconfiguration">Get<wbr>Service<wbr>Nat<wbr>Ip<wbr>Configuration[]</a></span>
    </dt>
    <dd>{{% md %}}The `nat_ip_configuration` block as defined below.
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
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="visibilitysubscriptionids_nodejs">
<a href="#visibilitysubscriptionids_nodejs" style="color: inherit; text-decoration: inherit;">visibility<wbr>Subscription<wbr>Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The list of subscription(s) globally unique identifiers(GUID) that will be able to see the private link service.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="alias_python">
<a href="#alias_python" style="color: inherit; text-decoration: inherit;">alias</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The alias is a globally unique name for your private link service which Azure generates for you. Your can use this alias to request a connection to your private link service.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="auto_approval_subscription_ids_python">
<a href="#auto_approval_subscription_ids_python" style="color: inherit; text-decoration: inherit;">auto_<wbr>approval_<wbr>subscription_<wbr>ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}The list of subscription(s) globally unique identifiers that will be auto approved to use the private link service.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="enable_proxy_protocol_python">
<a href="#enable_proxy_protocol_python" style="color: inherit; text-decoration: inherit;">enable_<wbr>proxy_<wbr>protocol</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Does the Private Link Service support the Proxy Protocol?
{{% /md %}}</dd><dt class="property-"
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
        <span id="load_balancer_frontend_ip_configuration_ids_python">
<a href="#load_balancer_frontend_ip_configuration_ids_python" style="color: inherit; text-decoration: inherit;">load_<wbr>balancer_<wbr>frontend_<wbr>ip_<wbr>configuration_<wbr>ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}The list of Standard Load Balancer(SLB) resource IDs. The Private Link service is tied to the frontend IP address of a SLB. All traffic destined for the private link service will reach the frontend of the SLB. You can configure SLB rules to direct this traffic to appropriate backend pools where your applications are running.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="location_python">
<a href="#location_python" style="color: inherit; text-decoration: inherit;">location</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The supported Azure location where the resource exists.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of private link service NAT IP configuration.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="nat_ip_configurations_python">
<a href="#nat_ip_configurations_python" style="color: inherit; text-decoration: inherit;">nat_<wbr>ip_<wbr>configurations</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getservicenatipconfiguration">Sequence[Get<wbr>Service<wbr>Nat<wbr>Ip<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}The `nat_ip_configuration` block as defined below.
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
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="visibility_subscription_ids_python">
<a href="#visibility_subscription_ids_python" style="color: inherit; text-decoration: inherit;">visibility_<wbr>subscription_<wbr>ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}The list of subscription(s) globally unique identifiers(GUID) that will be able to see the private link service.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## Supporting Types


<h4 id="getservicenatipconfiguration">Get<wbr>Service<wbr>Nat<wbr>Ip<wbr>Configuration</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the private link service.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="primary_csharp">
<a href="#primary_csharp" style="color: inherit; text-decoration: inherit;">Primary</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Value that indicates if the IP configuration is the primary configuration or not.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="privateipaddress_csharp">
<a href="#privateipaddress_csharp" style="color: inherit; text-decoration: inherit;">Private<wbr>Ip<wbr>Address</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The private IP address of the NAT IP configuration.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="privateipaddressversion_csharp">
<a href="#privateipaddressversion_csharp" style="color: inherit; text-decoration: inherit;">Private<wbr>Ip<wbr>Address<wbr>Version</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The version of the IP Protocol.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="subnetid_csharp">
<a href="#subnetid_csharp" style="color: inherit; text-decoration: inherit;">Subnet<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the subnet to be used by the service.
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
    <dd>{{% md %}}The name of the private link service.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="primary_go">
<a href="#primary_go" style="color: inherit; text-decoration: inherit;">Primary</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Value that indicates if the IP configuration is the primary configuration or not.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="privateipaddress_go">
<a href="#privateipaddress_go" style="color: inherit; text-decoration: inherit;">Private<wbr>Ip<wbr>Address</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The private IP address of the NAT IP configuration.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="privateipaddressversion_go">
<a href="#privateipaddressversion_go" style="color: inherit; text-decoration: inherit;">Private<wbr>Ip<wbr>Address<wbr>Version</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The version of the IP Protocol.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="subnetid_go">
<a href="#subnetid_go" style="color: inherit; text-decoration: inherit;">Subnet<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the subnet to be used by the service.
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
    <dd>{{% md %}}The name of the private link service.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="primary_nodejs">
<a href="#primary_nodejs" style="color: inherit; text-decoration: inherit;">primary</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Value that indicates if the IP configuration is the primary configuration or not.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="privateipaddress_nodejs">
<a href="#privateipaddress_nodejs" style="color: inherit; text-decoration: inherit;">private<wbr>Ip<wbr>Address</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The private IP address of the NAT IP configuration.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="privateipaddressversion_nodejs">
<a href="#privateipaddressversion_nodejs" style="color: inherit; text-decoration: inherit;">private<wbr>Ip<wbr>Address<wbr>Version</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The version of the IP Protocol.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="subnetid_nodejs">
<a href="#subnetid_nodejs" style="color: inherit; text-decoration: inherit;">subnet<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the subnet to be used by the service.
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
    <dd>{{% md %}}The name of the private link service.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="primary_python">
<a href="#primary_python" style="color: inherit; text-decoration: inherit;">primary</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Value that indicates if the IP configuration is the primary configuration or not.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="private_ip_address_python">
<a href="#private_ip_address_python" style="color: inherit; text-decoration: inherit;">private_<wbr>ip_<wbr>address</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The private IP address of the NAT IP configuration.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="private_ip_address_version_python">
<a href="#private_ip_address_version_python" style="color: inherit; text-decoration: inherit;">private_<wbr>ip_<wbr>address_<wbr>version</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The version of the IP Protocol.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="subnet_id_python">
<a href="#subnet_id_python" style="color: inherit; text-decoration: inherit;">subnet_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the subnet to be used by the service.
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


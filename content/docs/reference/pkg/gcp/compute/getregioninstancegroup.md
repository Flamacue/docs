
---
title: "getRegionInstanceGroup"
title_tag: "gcp.compute.getRegionInstanceGroup"
meta_desc: "Documentation for the gcp.compute.getRegionInstanceGroup function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Get a Compute Region Instance Group within GCE.
For more information, see [the official documentation](https://cloud.google.com/compute/docs/instance-groups/distributing-instances-with-regional-instance-groups) and [API](https://cloud.google.com/compute/docs/reference/latest/regionInstanceGroups).

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const group = pulumi.output(gcp.compute.getRegionInstanceGroup({
    name: "instance-group-name",
}, { async: true }));
```
```python
import pulumi
import pulumi_gcp as gcp

group = gcp.compute.get_region_instance_group(name="instance-group-name")
```
```csharp
using Pulumi;
using Gcp = Pulumi.Gcp;

class MyStack : Stack
{
    public MyStack()
    {
        var @group = Output.Create(Gcp.Compute.GetRegionInstanceGroup.InvokeAsync(new Gcp.Compute.GetRegionInstanceGroupArgs
        {
            Name = "instance-group-name",
        }));
    }

}
```
```go
package main

import (
	"github.com/pulumi/pulumi-gcp/sdk/v4/go/gcp/compute"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		opt0 := "instance-group-name"
		_, err := compute.GetRegionInstanceGroup(ctx, &compute.GetRegionInstanceGroupArgs{
			Name: &opt0,
		}, nil)
		if err != nil {
			return err
		}
		return nil
	})
}
```

The most common use of this datasource will be to fetch information about the instances inside regional managed instance groups, for instance:




## Using getRegionInstanceGroup {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getRegionInstanceGroup<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetRegionInstanceGroupArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetRegionInstanceGroupResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_region_instance_group(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">project</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">region</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">self_link</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetRegionInstanceGroupResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetRegionInstanceGroup<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">args</span><span class="p"> *</span><span class="nx">GetRegionInstanceGroupArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">GetRegionInstanceGroupResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `GetRegionInstanceGroup` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetRegionInstanceGroup </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetRegionInstanceGroupResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetRegionInstanceGroupArgs</span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the instance group.  One of `name` or `self_link` must be provided.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="project_csharp">
<a href="#project_csharp" style="color: inherit; text-decoration: inherit;">Project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the project in which the resource belongs.
If `self_link` is provided, this value is ignored.  If neither `self_link`
nor `project` are provided, the provider project is used.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="region_csharp">
<a href="#region_csharp" style="color: inherit; text-decoration: inherit;">Region</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The region in which the resource belongs.  If `self_link`
is provided, this value is ignored.  If neither `self_link` nor `region` are
provided, the provider region is used.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="selflink_csharp">
<a href="#selflink_csharp" style="color: inherit; text-decoration: inherit;">Self<wbr>Link</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The link to the instance group.  One of `name` or `self_link` must be provided.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the instance group.  One of `name` or `self_link` must be provided.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="project_go">
<a href="#project_go" style="color: inherit; text-decoration: inherit;">Project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the project in which the resource belongs.
If `self_link` is provided, this value is ignored.  If neither `self_link`
nor `project` are provided, the provider project is used.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="region_go">
<a href="#region_go" style="color: inherit; text-decoration: inherit;">Region</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The region in which the resource belongs.  If `self_link`
is provided, this value is ignored.  If neither `self_link` nor `region` are
provided, the provider region is used.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="selflink_go">
<a href="#selflink_go" style="color: inherit; text-decoration: inherit;">Self<wbr>Link</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The link to the instance group.  One of `name` or `self_link` must be provided.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the instance group.  One of `name` or `self_link` must be provided.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="project_nodejs">
<a href="#project_nodejs" style="color: inherit; text-decoration: inherit;">project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the project in which the resource belongs.
If `self_link` is provided, this value is ignored.  If neither `self_link`
nor `project` are provided, the provider project is used.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="region_nodejs">
<a href="#region_nodejs" style="color: inherit; text-decoration: inherit;">region</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The region in which the resource belongs.  If `self_link`
is provided, this value is ignored.  If neither `self_link` nor `region` are
provided, the provider region is used.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="selflink_nodejs">
<a href="#selflink_nodejs" style="color: inherit; text-decoration: inherit;">self<wbr>Link</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The link to the instance group.  One of `name` or `self_link` must be provided.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the instance group.  One of `name` or `self_link` must be provided.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="project_python">
<a href="#project_python" style="color: inherit; text-decoration: inherit;">project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the project in which the resource belongs.
If `self_link` is provided, this value is ignored.  If neither `self_link`
nor `project` are provided, the provider project is used.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="region_python">
<a href="#region_python" style="color: inherit; text-decoration: inherit;">region</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The region in which the resource belongs.  If `self_link`
is provided, this value is ignored.  If neither `self_link` nor `region` are
provided, the provider region is used.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="self_link_python">
<a href="#self_link_python" style="color: inherit; text-decoration: inherit;">self_<wbr>link</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The link to the instance group.  One of `name` or `self_link` must be provided.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getRegionInstanceGroup Result {#result}

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
        <span id="instances_csharp">
<a href="#instances_csharp" style="color: inherit; text-decoration: inherit;">Instances</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getregioninstancegroupinstance">List&lt;Get<wbr>Region<wbr>Instance<wbr>Group<wbr>Instance&gt;</a></span>
    </dt>
    <dd>{{% md %}}List of instances in the group, as a list of resources, each containing:
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}String port name
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="project_csharp">
<a href="#project_csharp" style="color: inherit; text-decoration: inherit;">Project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="region_csharp">
<a href="#region_csharp" style="color: inherit; text-decoration: inherit;">Region</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="selflink_csharp">
<a href="#selflink_csharp" style="color: inherit; text-decoration: inherit;">Self<wbr>Link</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="size_csharp">
<a href="#size_csharp" style="color: inherit; text-decoration: inherit;">Size</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of instances in the group.
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
        <span id="instances_go">
<a href="#instances_go" style="color: inherit; text-decoration: inherit;">Instances</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getregioninstancegroupinstance">[]Get<wbr>Region<wbr>Instance<wbr>Group<wbr>Instance</a></span>
    </dt>
    <dd>{{% md %}}List of instances in the group, as a list of resources, each containing:
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}String port name
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="project_go">
<a href="#project_go" style="color: inherit; text-decoration: inherit;">Project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="region_go">
<a href="#region_go" style="color: inherit; text-decoration: inherit;">Region</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="selflink_go">
<a href="#selflink_go" style="color: inherit; text-decoration: inherit;">Self<wbr>Link</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="size_go">
<a href="#size_go" style="color: inherit; text-decoration: inherit;">Size</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of instances in the group.
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
        <span id="instances_nodejs">
<a href="#instances_nodejs" style="color: inherit; text-decoration: inherit;">instances</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getregioninstancegroupinstance">Get<wbr>Region<wbr>Instance<wbr>Group<wbr>Instance[]</a></span>
    </dt>
    <dd>{{% md %}}List of instances in the group, as a list of resources, each containing:
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}String port name
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="project_nodejs">
<a href="#project_nodejs" style="color: inherit; text-decoration: inherit;">project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="region_nodejs">
<a href="#region_nodejs" style="color: inherit; text-decoration: inherit;">region</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="selflink_nodejs">
<a href="#selflink_nodejs" style="color: inherit; text-decoration: inherit;">self<wbr>Link</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="size_nodejs">
<a href="#size_nodejs" style="color: inherit; text-decoration: inherit;">size</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of instances in the group.
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
        <span id="instances_python">
<a href="#instances_python" style="color: inherit; text-decoration: inherit;">instances</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getregioninstancegroupinstance">Sequence[Get<wbr>Region<wbr>Instance<wbr>Group<wbr>Instance]</a></span>
    </dt>
    <dd>{{% md %}}List of instances in the group, as a list of resources, each containing:
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}String port name
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="project_python">
<a href="#project_python" style="color: inherit; text-decoration: inherit;">project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="region_python">
<a href="#region_python" style="color: inherit; text-decoration: inherit;">region</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="self_link_python">
<a href="#self_link_python" style="color: inherit; text-decoration: inherit;">self_<wbr>link</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="size_python">
<a href="#size_python" style="color: inherit; text-decoration: inherit;">size</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of instances in the group.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## Supporting Types


<h4 id="getregioninstancegroupinstance">Get<wbr>Region<wbr>Instance<wbr>Group<wbr>Instance</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="instance_csharp">
<a href="#instance_csharp" style="color: inherit; text-decoration: inherit;">Instance</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}URL to the instance.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="namedports_csharp">
<a href="#namedports_csharp" style="color: inherit; text-decoration: inherit;">Named<wbr>Ports</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getregioninstancegroupinstancenamedport">List&lt;Get<wbr>Region<wbr>Instance<wbr>Group<wbr>Instance<wbr>Named<wbr>Port<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}List of named ports in the group, as a list of resources, each containing:
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="status_csharp">
<a href="#status_csharp" style="color: inherit; text-decoration: inherit;">Status</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}String description of current state of the instance.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="instance_go">
<a href="#instance_go" style="color: inherit; text-decoration: inherit;">Instance</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}URL to the instance.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="namedports_go">
<a href="#namedports_go" style="color: inherit; text-decoration: inherit;">Named<wbr>Ports</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getregioninstancegroupinstancenamedport">[]Get<wbr>Region<wbr>Instance<wbr>Group<wbr>Instance<wbr>Named<wbr>Port</a></span>
    </dt>
    <dd>{{% md %}}List of named ports in the group, as a list of resources, each containing:
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="status_go">
<a href="#status_go" style="color: inherit; text-decoration: inherit;">Status</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}String description of current state of the instance.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="instance_nodejs">
<a href="#instance_nodejs" style="color: inherit; text-decoration: inherit;">instance</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}URL to the instance.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="namedports_nodejs">
<a href="#namedports_nodejs" style="color: inherit; text-decoration: inherit;">named<wbr>Ports</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getregioninstancegroupinstancenamedport">Get<wbr>Region<wbr>Instance<wbr>Group<wbr>Instance<wbr>Named<wbr>Port[]</a></span>
    </dt>
    <dd>{{% md %}}List of named ports in the group, as a list of resources, each containing:
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="status_nodejs">
<a href="#status_nodejs" style="color: inherit; text-decoration: inherit;">status</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}String description of current state of the instance.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="instance_python">
<a href="#instance_python" style="color: inherit; text-decoration: inherit;">instance</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}URL to the instance.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="named_ports_python">
<a href="#named_ports_python" style="color: inherit; text-decoration: inherit;">named_<wbr>ports</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getregioninstancegroupinstancenamedport">Sequence[Get<wbr>Region<wbr>Instance<wbr>Group<wbr>Instance<wbr>Named<wbr>Port<wbr>Args]</a></span>
    </dt>
    <dd>{{% md %}}List of named ports in the group, as a list of resources, each containing:
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="status_python">
<a href="#status_python" style="color: inherit; text-decoration: inherit;">status</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}String description of current state of the instance.
{{% /md %}}</dd></dl>
{{% /choosable %}}

<h4 id="getregioninstancegroupinstancenamedport">Get<wbr>Region<wbr>Instance<wbr>Group<wbr>Instance<wbr>Named<wbr>Port</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the instance group.  One of `name` or `self_link` must be provided.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="port_csharp">
<a href="#port_csharp" style="color: inherit; text-decoration: inherit;">Port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Integer port number
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
    <dd>{{% md %}}The name of the instance group.  One of `name` or `self_link` must be provided.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="port_go">
<a href="#port_go" style="color: inherit; text-decoration: inherit;">Port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Integer port number
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
    <dd>{{% md %}}The name of the instance group.  One of `name` or `self_link` must be provided.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="port_nodejs">
<a href="#port_nodejs" style="color: inherit; text-decoration: inherit;">port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Integer port number
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
    <dd>{{% md %}}The name of the instance group.  One of `name` or `self_link` must be provided.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="port_python">
<a href="#port_python" style="color: inherit; text-decoration: inherit;">port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Integer port number
{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-gcp">https://github.com/pulumi/pulumi-gcp</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`google-beta` Terraform Provider](https://github.com/hashicorp/terraform-provider-google-beta).{{% /md %}}</dd>
</dl>



---
title: "getProjectAlertGroup"
title_tag: "rancher2.getProjectAlertGroup"
meta_desc: "Documentation for the rancher2.getProjectAlertGroup function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Use this data source to retrieve information about a Rancher v2 project alert group.


{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}





{{< example csharp >}}

```csharp
using Pulumi;
using Rancher2 = Pulumi.Rancher2;

class MyStack : Stack
{
    public MyStack()
    {
        var foo = Output.Create(Rancher2.GetProjectAlertGroup.InvokeAsync(new Rancher2.GetProjectAlertGroupArgs
        {
            Name = "<project_alert_group_name>",
            ProjectId = "<project_id>",
        }));
    }

}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-rancher2/sdk/v2/go/rancher2"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		_, err := rancher2.LookupProjectAlertGroup(ctx, &rancher2.LookupProjectAlertGroupArgs{
			Name:      "<project_alert_group_name>",
			ProjectId: "<project_id>",
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
import pulumi_rancher2 as rancher2

foo = rancher2.get_project_alert_group(name="<project_alert_group_name>",
    project_id="<project_id>")
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as rancher2 from "@pulumi/rancher2";

const foo = pulumi.output(rancher2.getProjectAlertGroup({
    name: "<project_alert_group_name>",
    projectId: "<project_id>",
}, { async: true }));
```


{{< /example >}}





{{% /examples %}}




## Using getProjectAlertGroup {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getProjectAlertGroup<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetProjectAlertGroupArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetProjectAlertGroupResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_project_alert_group(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">project_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetProjectAlertGroupResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupProjectAlertGroup<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">args</span><span class="p"> *</span><span class="nx">LookupProjectAlertGroupArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">LookupProjectAlertGroupResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `LookupProjectAlertGroup` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetProjectAlertGroup </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetProjectAlertGroupResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetProjectAlertGroupArgs</span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
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
    <dd>{{% md %}}The project alert group name (string)
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="projectid_csharp">
<a href="#projectid_csharp" style="color: inherit; text-decoration: inherit;">Project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The project id where create project alert group (string)
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
    <dd>{{% md %}}The project alert group name (string)
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="projectid_go">
<a href="#projectid_go" style="color: inherit; text-decoration: inherit;">Project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The project id where create project alert group (string)
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
    <dd>{{% md %}}The project alert group name (string)
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="projectid_nodejs">
<a href="#projectid_nodejs" style="color: inherit; text-decoration: inherit;">project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The project id where create project alert group (string)
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
    <dd>{{% md %}}The project alert group name (string)
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="project_id_python">
<a href="#project_id_python" style="color: inherit; text-decoration: inherit;">project_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The project id where create project alert group (string)
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getProjectAlertGroup Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="annotations_csharp">
<a href="#annotations_csharp" style="color: inherit; text-decoration: inherit;">Annotations</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Dictionary&lt;string, object&gt;</span>
    </dt>
    <dd>{{% md %}}(Computed) The project alert group annotations (map)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="description_csharp">
<a href="#description_csharp" style="color: inherit; text-decoration: inherit;">Description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Computed) The project alert group description (string)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="groupintervalseconds_csharp">
<a href="#groupintervalseconds_csharp" style="color: inherit; text-decoration: inherit;">Group<wbr>Interval<wbr>Seconds</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}(Computed) The project alert group interval seconds. Default: `180` (int)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="groupwaitseconds_csharp">
<a href="#groupwaitseconds_csharp" style="color: inherit; text-decoration: inherit;">Group<wbr>Wait<wbr>Seconds</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}(Computed) The project alert group wait seconds. Default: `180` (int)
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
        <span id="labels_csharp">
<a href="#labels_csharp" style="color: inherit; text-decoration: inherit;">Labels</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Dictionary&lt;string, object&gt;</span>
    </dt>
    <dd>{{% md %}}(Computed) The project alert group labels (map)
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
        <span id="projectid_csharp">
<a href="#projectid_csharp" style="color: inherit; text-decoration: inherit;">Project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="recipients_csharp">
<a href="#recipients_csharp" style="color: inherit; text-decoration: inherit;">Recipients</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getprojectalertgrouprecipient">List&lt;Get<wbr>Project<wbr>Alert<wbr>Group<wbr>Recipient&gt;</a></span>
    </dt>
    <dd>{{% md %}}(Computed) The project alert group recipients (list)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="repeatintervalseconds_csharp">
<a href="#repeatintervalseconds_csharp" style="color: inherit; text-decoration: inherit;">Repeat<wbr>Interval<wbr>Seconds</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}(Computed) The project alert group wait seconds. Default: `3600` (int)
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="annotations_go">
<a href="#annotations_go" style="color: inherit; text-decoration: inherit;">Annotations</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}(Computed) The project alert group annotations (map)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="description_go">
<a href="#description_go" style="color: inherit; text-decoration: inherit;">Description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Computed) The project alert group description (string)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="groupintervalseconds_go">
<a href="#groupintervalseconds_go" style="color: inherit; text-decoration: inherit;">Group<wbr>Interval<wbr>Seconds</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}(Computed) The project alert group interval seconds. Default: `180` (int)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="groupwaitseconds_go">
<a href="#groupwaitseconds_go" style="color: inherit; text-decoration: inherit;">Group<wbr>Wait<wbr>Seconds</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}(Computed) The project alert group wait seconds. Default: `180` (int)
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
        <span id="labels_go">
<a href="#labels_go" style="color: inherit; text-decoration: inherit;">Labels</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}(Computed) The project alert group labels (map)
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
        <span id="projectid_go">
<a href="#projectid_go" style="color: inherit; text-decoration: inherit;">Project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="recipients_go">
<a href="#recipients_go" style="color: inherit; text-decoration: inherit;">Recipients</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getprojectalertgrouprecipient">[]Get<wbr>Project<wbr>Alert<wbr>Group<wbr>Recipient</a></span>
    </dt>
    <dd>{{% md %}}(Computed) The project alert group recipients (list)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="repeatintervalseconds_go">
<a href="#repeatintervalseconds_go" style="color: inherit; text-decoration: inherit;">Repeat<wbr>Interval<wbr>Seconds</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}(Computed) The project alert group wait seconds. Default: `3600` (int)
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="annotations_nodejs">
<a href="#annotations_nodejs" style="color: inherit; text-decoration: inherit;">annotations</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}</span>
    </dt>
    <dd>{{% md %}}(Computed) The project alert group annotations (map)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="description_nodejs">
<a href="#description_nodejs" style="color: inherit; text-decoration: inherit;">description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Computed) The project alert group description (string)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="groupintervalseconds_nodejs">
<a href="#groupintervalseconds_nodejs" style="color: inherit; text-decoration: inherit;">group<wbr>Interval<wbr>Seconds</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}(Computed) The project alert group interval seconds. Default: `180` (int)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="groupwaitseconds_nodejs">
<a href="#groupwaitseconds_nodejs" style="color: inherit; text-decoration: inherit;">group<wbr>Wait<wbr>Seconds</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}(Computed) The project alert group wait seconds. Default: `180` (int)
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
        <span id="labels_nodejs">
<a href="#labels_nodejs" style="color: inherit; text-decoration: inherit;">labels</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}</span>
    </dt>
    <dd>{{% md %}}(Computed) The project alert group labels (map)
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
        <span id="projectid_nodejs">
<a href="#projectid_nodejs" style="color: inherit; text-decoration: inherit;">project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="recipients_nodejs">
<a href="#recipients_nodejs" style="color: inherit; text-decoration: inherit;">recipients</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getprojectalertgrouprecipient">Get<wbr>Project<wbr>Alert<wbr>Group<wbr>Recipient[]</a></span>
    </dt>
    <dd>{{% md %}}(Computed) The project alert group recipients (list)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="repeatintervalseconds_nodejs">
<a href="#repeatintervalseconds_nodejs" style="color: inherit; text-decoration: inherit;">repeat<wbr>Interval<wbr>Seconds</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}(Computed) The project alert group wait seconds. Default: `3600` (int)
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="annotations_python">
<a href="#annotations_python" style="color: inherit; text-decoration: inherit;">annotations</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Mapping[str, Any]</span>
    </dt>
    <dd>{{% md %}}(Computed) The project alert group annotations (map)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="description_python">
<a href="#description_python" style="color: inherit; text-decoration: inherit;">description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}(Computed) The project alert group description (string)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="group_interval_seconds_python">
<a href="#group_interval_seconds_python" style="color: inherit; text-decoration: inherit;">group_<wbr>interval_<wbr>seconds</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}(Computed) The project alert group interval seconds. Default: `180` (int)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="group_wait_seconds_python">
<a href="#group_wait_seconds_python" style="color: inherit; text-decoration: inherit;">group_<wbr>wait_<wbr>seconds</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}(Computed) The project alert group wait seconds. Default: `180` (int)
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
        <span id="labels_python">
<a href="#labels_python" style="color: inherit; text-decoration: inherit;">labels</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Mapping[str, Any]</span>
    </dt>
    <dd>{{% md %}}(Computed) The project alert group labels (map)
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
        <span id="project_id_python">
<a href="#project_id_python" style="color: inherit; text-decoration: inherit;">project_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="recipients_python">
<a href="#recipients_python" style="color: inherit; text-decoration: inherit;">recipients</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getprojectalertgrouprecipient">Sequence[Get<wbr>Project<wbr>Alert<wbr>Group<wbr>Recipient]</a></span>
    </dt>
    <dd>{{% md %}}(Computed) The project alert group recipients (list)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="repeat_interval_seconds_python">
<a href="#repeat_interval_seconds_python" style="color: inherit; text-decoration: inherit;">repeat_<wbr>interval_<wbr>seconds</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}(Computed) The project alert group wait seconds. Default: `3600` (int)
{{% /md %}}</dd></dl>
{{% /choosable %}}




## Supporting Types


<h4 id="getprojectalertgrouprecipient">Get<wbr>Project<wbr>Alert<wbr>Group<wbr>Recipient</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="notifierid_csharp">
<a href="#notifierid_csharp" style="color: inherit; text-decoration: inherit;">Notifier<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="notifiertype_csharp">
<a href="#notifiertype_csharp" style="color: inherit; text-decoration: inherit;">Notifier<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="recipient_csharp">
<a href="#recipient_csharp" style="color: inherit; text-decoration: inherit;">Recipient</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="defaultrecipient_csharp">
<a href="#defaultrecipient_csharp" style="color: inherit; text-decoration: inherit;">Default<wbr>Recipient</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="notifierid_go">
<a href="#notifierid_go" style="color: inherit; text-decoration: inherit;">Notifier<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="notifiertype_go">
<a href="#notifiertype_go" style="color: inherit; text-decoration: inherit;">Notifier<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="recipient_go">
<a href="#recipient_go" style="color: inherit; text-decoration: inherit;">Recipient</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="defaultrecipient_go">
<a href="#defaultrecipient_go" style="color: inherit; text-decoration: inherit;">Default<wbr>Recipient</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="notifierid_nodejs">
<a href="#notifierid_nodejs" style="color: inherit; text-decoration: inherit;">notifier<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="notifiertype_nodejs">
<a href="#notifiertype_nodejs" style="color: inherit; text-decoration: inherit;">notifier<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="recipient_nodejs">
<a href="#recipient_nodejs" style="color: inherit; text-decoration: inherit;">recipient</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="defaultrecipient_nodejs">
<a href="#defaultrecipient_nodejs" style="color: inherit; text-decoration: inherit;">default<wbr>Recipient</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="notifier_id_python">
<a href="#notifier_id_python" style="color: inherit; text-decoration: inherit;">notifier_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="notifier_type_python">
<a href="#notifier_type_python" style="color: inherit; text-decoration: inherit;">notifier_<wbr>type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="recipient_python">
<a href="#recipient_python" style="color: inherit; text-decoration: inherit;">recipient</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="default_recipient_python">
<a href="#default_recipient_python" style="color: inherit; text-decoration: inherit;">default_<wbr>recipient</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-rancher2">https://github.com/pulumi/pulumi-rancher2</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`rancher2` Terraform Provider](https://github.com/rancher/terraform-provider-rancher2).{{% /md %}}</dd>
</dl>


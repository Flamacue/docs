
---
title: "getProjects"
title_tag: "azuredevops.Core.getProjects"
meta_desc: "Documentation for the azuredevops.Core.getProjects function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->
<p class="resource-deprecated">Deprecated: {{% md %}}azuredevops.core.getProjects has been deprecated in favor of azuredevops.getProjects{{% /md %}}</p>

Use this data source to access information about existing Projects within Azure DevOps.
## Relevant Links

- [Azure DevOps Service REST API 5.1 - Projects - Get](https://docs.microsoft.com/en-us/rest/api/azure/devops/core/projects/get?view=azure-devops-rest-5.1)


{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}





{{< example csharp >}}

```csharp
using System.Linq;
using Pulumi;
using AzureDevOps = Pulumi.AzureDevOps;

class MyStack : Stack
{
    public MyStack()
    {
        var test = Output.Create(AzureDevOps.GetProjects.InvokeAsync(new AzureDevOps.GetProjectsArgs
        {
            Name = "contoso",
            State = "wellFormed",
        }));
        this.ProjectId = test.Apply(test => test.Projects.Select(__item => __item.ProjectId).ToList());
        this.Name = test.Apply(test => test.Projects.Select(__item => __item.Name).ToList());
        this.ProjectUrl = test.Apply(test => test.Projects.Select(__item => __item.ProjectUrl).ToList());
        this.State = test.Apply(test => test.Projects.Select(__item => __item.State).ToList());
    }

    [Output("projectId")]
    public Output<string> ProjectId { get; set; }
    [Output("name")]
    public Output<string> Name { get; set; }
    [Output("projectUrl")]
    public Output<string> ProjectUrl { get; set; }
    [Output("state")]
    public Output<string> State { get; set; }
}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-azuredevops/sdk/go/azuredevops"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		opt0 := "contoso"
		opt1 := "wellFormed"
		test, err := azuredevops.GetProjects(ctx, &azuredevops.GetProjectsArgs{
			Name:  &opt0,
			State: &opt1,
		}, nil)
		if err != nil {
			return err
		}
		var splat0 []string
		for _, val0 := range test.Projects {
			splat0 = append(splat0, val0.ProjectId)
		}
		ctx.Export("projectId", splat0)
		var splat1 []string
		for _, val0 := range test.Projects {
			splat1 = append(splat1, val0.Name)
		}
		ctx.Export("name", splat1)
		var splat2 []string
		for _, val0 := range test.Projects {
			splat2 = append(splat2, val0.ProjectUrl)
		}
		ctx.Export("projectUrl", splat2)
		var splat3 []string
		for _, val0 := range test.Projects {
			splat3 = append(splat3, val0.State)
		}
		ctx.Export("state", splat3)
		return nil
	})
}
```


{{< /example >}}


{{< example python >}}

```python
import pulumi
import pulumi_azuredevops as azuredevops

test = azuredevops.get_projects(name="contoso",
    state="wellFormed")
pulumi.export("projectId", [__item.project_id for __item in test.projects])
pulumi.export("name", [__item.name for __item in test.projects])
pulumi.export("projectUrl", [__item.project_url for __item in test.projects])
pulumi.export("state", [__item.state for __item in test.projects])
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as azuredevops from "@pulumi/azuredevops";

const test = azuredevops.getProjects({
    name: "contoso",
    state: "wellFormed",
});
export const projectId = test.then(test => test.projects.map(__item => __item.projectId));
export const name = test.then(test => test.projects.map(__item => __item.name));
export const projectUrl = test.then(test => test.projects.map(__item => __item.projectUrl));
export const state = test.then(test => test.projects.map(__item => __item.state));
```


{{< /example >}}





{{% /examples %}}




## Using getProjects {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getProjects<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetProjectsArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetProjectsResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_projects(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">state</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetProjectsResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetProjects<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">args</span><span class="p"> *</span><span class="nx">GetProjectsArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">GetProjectsResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `GetProjects` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetProjects </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetProjectsResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetProjectsArgs</span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
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
    <dd>{{% md %}}Name of the Project, if not specified all projects will be returned.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_csharp">
<a href="#state_csharp" style="color: inherit; text-decoration: inherit;">State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}State of the Project, if not specified all projects will be returned. Valid values are `all`, `deleting`, `new`, `wellFormed`, `createPending`, `unchanged`,`deleted`.
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
    <dd>{{% md %}}Name of the Project, if not specified all projects will be returned.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_go">
<a href="#state_go" style="color: inherit; text-decoration: inherit;">State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}State of the Project, if not specified all projects will be returned. Valid values are `all`, `deleting`, `new`, `wellFormed`, `createPending`, `unchanged`,`deleted`.
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
    <dd>{{% md %}}Name of the Project, if not specified all projects will be returned.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_nodejs">
<a href="#state_nodejs" style="color: inherit; text-decoration: inherit;">state</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}State of the Project, if not specified all projects will be returned. Valid values are `all`, `deleting`, `new`, `wellFormed`, `createPending`, `unchanged`,`deleted`.
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
    <dd>{{% md %}}Name of the Project, if not specified all projects will be returned.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_python">
<a href="#state_python" style="color: inherit; text-decoration: inherit;">state</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}State of the Project, if not specified all projects will be returned. Valid values are `all`, `deleting`, `new`, `wellFormed`, `createPending`, `unchanged`,`deleted`.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getProjects Result {#result}

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
        <span id="projects_csharp">
<a href="#projects_csharp" style="color: inherit; text-decoration: inherit;">Projects</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getprojectsproject">List&lt;Pulumi.<wbr>Azure<wbr>Dev<wbr>Ops.<wbr>Core.<wbr>Outputs.<wbr>Get<wbr>Projects<wbr>Project&gt;</a></span>
    </dt>
    <dd>{{% md %}}A list of existing projects in your Azure DevOps Organization with details about every project which includes:
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Project name.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="state_csharp">
<a href="#state_csharp" style="color: inherit; text-decoration: inherit;">State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Project state.
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
        <span id="projects_go">
<a href="#projects_go" style="color: inherit; text-decoration: inherit;">Projects</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getprojectsproject">[]Get<wbr>Projects<wbr>Project</a></span>
    </dt>
    <dd>{{% md %}}A list of existing projects in your Azure DevOps Organization with details about every project which includes:
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Project name.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="state_go">
<a href="#state_go" style="color: inherit; text-decoration: inherit;">State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Project state.
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
        <span id="projects_nodejs">
<a href="#projects_nodejs" style="color: inherit; text-decoration: inherit;">projects</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getprojectsproject">Get<wbr>Projects<wbr>Project[]</a></span>
    </dt>
    <dd>{{% md %}}A list of existing projects in your Azure DevOps Organization with details about every project which includes:
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Project name.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="state_nodejs">
<a href="#state_nodejs" style="color: inherit; text-decoration: inherit;">state</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Project state.
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
        <span id="projects_python">
<a href="#projects_python" style="color: inherit; text-decoration: inherit;">projects</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getprojectsproject">Get<wbr>Projects<wbr>Project]</a></span>
    </dt>
    <dd>{{% md %}}A list of existing projects in your Azure DevOps Organization with details about every project which includes:
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Project name.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="state_python">
<a href="#state_python" style="color: inherit; text-decoration: inherit;">state</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Project state.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## Supporting Types


<h4 id="getprojectsproject">Get<wbr>Projects<wbr>Project</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the Project, if not specified all projects will be returned.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="projectid_csharp">
<a href="#projectid_csharp" style="color: inherit; text-decoration: inherit;">Project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Project identifier.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="projecturl_csharp">
<a href="#projecturl_csharp" style="color: inherit; text-decoration: inherit;">Project<wbr>Url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Url to the full version of the object.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="state_csharp">
<a href="#state_csharp" style="color: inherit; text-decoration: inherit;">State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}State of the Project, if not specified all projects will be returned. Valid values are `all`, `deleting`, `new`, `wellFormed`, `createPending`, `unchanged`,`deleted`.
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
    <dd>{{% md %}}Name of the Project, if not specified all projects will be returned.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="projectid_go">
<a href="#projectid_go" style="color: inherit; text-decoration: inherit;">Project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Project identifier.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="projecturl_go">
<a href="#projecturl_go" style="color: inherit; text-decoration: inherit;">Project<wbr>Url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Url to the full version of the object.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="state_go">
<a href="#state_go" style="color: inherit; text-decoration: inherit;">State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}State of the Project, if not specified all projects will be returned. Valid values are `all`, `deleting`, `new`, `wellFormed`, `createPending`, `unchanged`,`deleted`.
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
    <dd>{{% md %}}Name of the Project, if not specified all projects will be returned.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="projectid_nodejs">
<a href="#projectid_nodejs" style="color: inherit; text-decoration: inherit;">project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Project identifier.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="projecturl_nodejs">
<a href="#projecturl_nodejs" style="color: inherit; text-decoration: inherit;">project<wbr>Url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Url to the full version of the object.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="state_nodejs">
<a href="#state_nodejs" style="color: inherit; text-decoration: inherit;">state</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}State of the Project, if not specified all projects will be returned. Valid values are `all`, `deleting`, `new`, `wellFormed`, `createPending`, `unchanged`,`deleted`.
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
    <dd>{{% md %}}Name of the Project, if not specified all projects will be returned.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="project_id_python">
<a href="#project_id_python" style="color: inherit; text-decoration: inherit;">project_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Project identifier.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="project_url_python">
<a href="#project_url_python" style="color: inherit; text-decoration: inherit;">project_<wbr>url</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Url to the full version of the object.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="state_python">
<a href="#state_python" style="color: inherit; text-decoration: inherit;">state</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}State of the Project, if not specified all projects will be returned. Valid values are `all`, `deleting`, `new`, `wellFormed`, `createPending`, `unchanged`,`deleted`.
{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-azuredevops">https://github.com/pulumi/pulumi-azuredevops</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`azuredevops` Terraform Provider](https://github.com/microsoft/terraform-provider-azuredevops).{{% /md %}}</dd>
</dl>



---
title: "getPolicies"
title_tag: "alicloud.resourcemanager.getPolicies"
meta_desc: "Documentation for the alicloud.resourcemanager.getPolicies function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

This data source provides the Resource Manager Policies of the current Alibaba Cloud user.

> **NOTE:**  Available in 1.86.0+.


{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}





{{< example csharp >}}

```csharp
using Pulumi;
using AliCloud = Pulumi.AliCloud;

class MyStack : Stack
{
    public MyStack()
    {
        var example = Output.Create(AliCloud.ResourceManager.GetPolicies.InvokeAsync(new AliCloud.ResourceManager.GetPoliciesArgs
        {
            DescriptionRegex = "tftest_policy",
            NameRegex = "tftest",
            PolicyType = "Custom",
        }));
        this.FirstPolicyId = example.Apply(example => example.Policies[0].Id);
    }

    [Output("firstPolicyId")]
    public Output<string> FirstPolicyId { get; set; }
}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-alicloud/sdk/v2/go/alicloud/resourcemanager"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		opt0 := "tftest"
		opt1 := "Custom"
		example, err := resourcemanager.GetPolicies(ctx, &resourcemanager.GetPoliciesArgs{
			DescriptionRegex: "tftest_policy",
			NameRegex:        &opt0,
			PolicyType:       &opt1,
		}, nil)
		if err != nil {
			return err
		}
		ctx.Export("firstPolicyId", example.Policies[0].Id)
		return nil
	})
}
```


{{< /example >}}


{{< example python >}}

```python
import pulumi
import pulumi_alicloud as alicloud

example = alicloud.resourcemanager.get_policies(description_regex="tftest_policy",
    name_regex="tftest",
    policy_type="Custom")
pulumi.export("firstPolicyId", example.policies[0].id)
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as alicloud from "@pulumi/alicloud";

const example = pulumi.output(alicloud.resourcemanager.getPolicies({
    descriptionRegex: "tftest_policy",
    nameRegex: "tftest",
    policyType: "Custom",
}, { async: true }));

export const firstPolicyId = example.policies[0].id;
```


{{< /example >}}





{{% /examples %}}




## Using getPolicies {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getPolicies<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetPoliciesArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetPoliciesResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_policies(</span><span class="nx">ids</span><span class="p">:</span> <span class="nx">Optional[Sequence[str]]</span> = None<span class="p">, </span><span class="nx">name_regex</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">output_file</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">policy_type</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetPoliciesResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetPolicies<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">args</span><span class="p"> *</span><span class="nx">GetPoliciesArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">GetPoliciesResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `GetPolicies` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetPolicies </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetPoliciesResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetPoliciesArgs</span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="ids_csharp">
<a href="#ids_csharp" style="color: inherit; text-decoration: inherit;">Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}A list of Resource Manager Policy IDs.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="nameregex_csharp">
<a href="#nameregex_csharp" style="color: inherit; text-decoration: inherit;">Name<wbr>Regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A regex string to filter results by policy name.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="outputfile_csharp">
<a href="#outputfile_csharp" style="color: inherit; text-decoration: inherit;">Output<wbr>File</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="policytype_csharp">
<a href="#policytype_csharp" style="color: inherit; text-decoration: inherit;">Policy<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the policy. If you do not specify this parameter, the system lists all types of policies. Valid values: `Custom` and `System`.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="ids_go">
<a href="#ids_go" style="color: inherit; text-decoration: inherit;">Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of Resource Manager Policy IDs.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="nameregex_go">
<a href="#nameregex_go" style="color: inherit; text-decoration: inherit;">Name<wbr>Regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A regex string to filter results by policy name.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="outputfile_go">
<a href="#outputfile_go" style="color: inherit; text-decoration: inherit;">Output<wbr>File</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="policytype_go">
<a href="#policytype_go" style="color: inherit; text-decoration: inherit;">Policy<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the policy. If you do not specify this parameter, the system lists all types of policies. Valid values: `Custom` and `System`.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="ids_nodejs">
<a href="#ids_nodejs" style="color: inherit; text-decoration: inherit;">ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of Resource Manager Policy IDs.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="nameregex_nodejs">
<a href="#nameregex_nodejs" style="color: inherit; text-decoration: inherit;">name<wbr>Regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A regex string to filter results by policy name.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="outputfile_nodejs">
<a href="#outputfile_nodejs" style="color: inherit; text-decoration: inherit;">output<wbr>File</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="policytype_nodejs">
<a href="#policytype_nodejs" style="color: inherit; text-decoration: inherit;">policy<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the policy. If you do not specify this parameter, the system lists all types of policies. Valid values: `Custom` and `System`.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="ids_python">
<a href="#ids_python" style="color: inherit; text-decoration: inherit;">ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}A list of Resource Manager Policy IDs.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="name_regex_python">
<a href="#name_regex_python" style="color: inherit; text-decoration: inherit;">name_<wbr>regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A regex string to filter results by policy name.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="output_file_python">
<a href="#output_file_python" style="color: inherit; text-decoration: inherit;">output_<wbr>file</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="policy_type_python">
<a href="#policy_type_python" style="color: inherit; text-decoration: inherit;">policy_<wbr>type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the policy. If you do not specify this parameter, the system lists all types of policies. Valid values: `Custom` and `System`.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getPolicies Result {#result}

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
        <span id="ids_csharp">
<a href="#ids_csharp" style="color: inherit; text-decoration: inherit;">Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}A list of policy IDs.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="names_csharp">
<a href="#names_csharp" style="color: inherit; text-decoration: inherit;">Names</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}A list of policy names.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="policies_csharp">
<a href="#policies_csharp" style="color: inherit; text-decoration: inherit;">Policies</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getpoliciespolicy">List&lt;Pulumi.<wbr>Ali<wbr>Cloud.<wbr>Resource<wbr>Manager.<wbr>Outputs.<wbr>Get<wbr>Policies<wbr>Policy&gt;</a></span>
    </dt>
    <dd>{{% md %}}A list of policies. Each element contains the following attributes:
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="nameregex_csharp">
<a href="#nameregex_csharp" style="color: inherit; text-decoration: inherit;">Name<wbr>Regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="outputfile_csharp">
<a href="#outputfile_csharp" style="color: inherit; text-decoration: inherit;">Output<wbr>File</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="policytype_csharp">
<a href="#policytype_csharp" style="color: inherit; text-decoration: inherit;">Policy<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
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
        <span id="ids_go">
<a href="#ids_go" style="color: inherit; text-decoration: inherit;">Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of policy IDs.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="names_go">
<a href="#names_go" style="color: inherit; text-decoration: inherit;">Names</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of policy names.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="policies_go">
<a href="#policies_go" style="color: inherit; text-decoration: inherit;">Policies</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getpoliciespolicy">[]Get<wbr>Policies<wbr>Policy</a></span>
    </dt>
    <dd>{{% md %}}A list of policies. Each element contains the following attributes:
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="nameregex_go">
<a href="#nameregex_go" style="color: inherit; text-decoration: inherit;">Name<wbr>Regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="outputfile_go">
<a href="#outputfile_go" style="color: inherit; text-decoration: inherit;">Output<wbr>File</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="policytype_go">
<a href="#policytype_go" style="color: inherit; text-decoration: inherit;">Policy<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
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
        <span id="ids_nodejs">
<a href="#ids_nodejs" style="color: inherit; text-decoration: inherit;">ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of policy IDs.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="names_nodejs">
<a href="#names_nodejs" style="color: inherit; text-decoration: inherit;">names</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of policy names.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="policies_nodejs">
<a href="#policies_nodejs" style="color: inherit; text-decoration: inherit;">policies</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getpoliciespolicy">Get<wbr>Policies<wbr>Policy[]</a></span>
    </dt>
    <dd>{{% md %}}A list of policies. Each element contains the following attributes:
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="nameregex_nodejs">
<a href="#nameregex_nodejs" style="color: inherit; text-decoration: inherit;">name<wbr>Regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="outputfile_nodejs">
<a href="#outputfile_nodejs" style="color: inherit; text-decoration: inherit;">output<wbr>File</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="policytype_nodejs">
<a href="#policytype_nodejs" style="color: inherit; text-decoration: inherit;">policy<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
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
        <span id="ids_python">
<a href="#ids_python" style="color: inherit; text-decoration: inherit;">ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}A list of policy IDs.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="names_python">
<a href="#names_python" style="color: inherit; text-decoration: inherit;">names</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}A list of policy names.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="policies_python">
<a href="#policies_python" style="color: inherit; text-decoration: inherit;">policies</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getpoliciespolicy">Sequence[Get<wbr>Policies<wbr>Policy]</a></span>
    </dt>
    <dd>{{% md %}}A list of policies. Each element contains the following attributes:
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_regex_python">
<a href="#name_regex_python" style="color: inherit; text-decoration: inherit;">name_<wbr>regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="output_file_python">
<a href="#output_file_python" style="color: inherit; text-decoration: inherit;">output_<wbr>file</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="policy_type_python">
<a href="#policy_type_python" style="color: inherit; text-decoration: inherit;">policy_<wbr>type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}




## Supporting Types


<h4 id="getpoliciespolicy">Get<wbr>Policies<wbr>Policy</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="attachmentcount_csharp">
<a href="#attachmentcount_csharp" style="color: inherit; text-decoration: inherit;">Attachment<wbr>Count</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of times the policy is referenced.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="defaultversion_csharp">
<a href="#defaultversion_csharp" style="color: inherit; text-decoration: inherit;">Default<wbr>Version</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The default version of the policy.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="description_csharp">
<a href="#description_csharp" style="color: inherit; text-decoration: inherit;">Description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The description of the policy.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="id_csharp">
<a href="#id_csharp" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the policy.
* `policy_name`- The name of the policy.
* `policy_type`- The type of the policy.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="policyname_csharp">
<a href="#policyname_csharp" style="color: inherit; text-decoration: inherit;">Policy<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="policytype_csharp">
<a href="#policytype_csharp" style="color: inherit; text-decoration: inherit;">Policy<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the policy. If you do not specify this parameter, the system lists all types of policies. Valid values: `Custom` and `System`.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="updatedate_csharp">
<a href="#updatedate_csharp" style="color: inherit; text-decoration: inherit;">Update<wbr>Date</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The time when the policy was updated.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="attachmentcount_go">
<a href="#attachmentcount_go" style="color: inherit; text-decoration: inherit;">Attachment<wbr>Count</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of times the policy is referenced.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="defaultversion_go">
<a href="#defaultversion_go" style="color: inherit; text-decoration: inherit;">Default<wbr>Version</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The default version of the policy.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="description_go">
<a href="#description_go" style="color: inherit; text-decoration: inherit;">Description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The description of the policy.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="id_go">
<a href="#id_go" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the policy.
* `policy_name`- The name of the policy.
* `policy_type`- The type of the policy.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="policyname_go">
<a href="#policyname_go" style="color: inherit; text-decoration: inherit;">Policy<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="policytype_go">
<a href="#policytype_go" style="color: inherit; text-decoration: inherit;">Policy<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the policy. If you do not specify this parameter, the system lists all types of policies. Valid values: `Custom` and `System`.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="updatedate_go">
<a href="#updatedate_go" style="color: inherit; text-decoration: inherit;">Update<wbr>Date</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The time when the policy was updated.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="attachmentcount_nodejs">
<a href="#attachmentcount_nodejs" style="color: inherit; text-decoration: inherit;">attachment<wbr>Count</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of times the policy is referenced.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="defaultversion_nodejs">
<a href="#defaultversion_nodejs" style="color: inherit; text-decoration: inherit;">default<wbr>Version</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The default version of the policy.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="description_nodejs">
<a href="#description_nodejs" style="color: inherit; text-decoration: inherit;">description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The description of the policy.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="id_nodejs">
<a href="#id_nodejs" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the policy.
* `policy_name`- The name of the policy.
* `policy_type`- The type of the policy.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="policyname_nodejs">
<a href="#policyname_nodejs" style="color: inherit; text-decoration: inherit;">policy<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="policytype_nodejs">
<a href="#policytype_nodejs" style="color: inherit; text-decoration: inherit;">policy<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the policy. If you do not specify this parameter, the system lists all types of policies. Valid values: `Custom` and `System`.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="updatedate_nodejs">
<a href="#updatedate_nodejs" style="color: inherit; text-decoration: inherit;">update<wbr>Date</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The time when the policy was updated.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="attachment_count_python">
<a href="#attachment_count_python" style="color: inherit; text-decoration: inherit;">attachment_<wbr>count</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of times the policy is referenced.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="default_version_python">
<a href="#default_version_python" style="color: inherit; text-decoration: inherit;">default_<wbr>version</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The default version of the policy.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="description_python">
<a href="#description_python" style="color: inherit; text-decoration: inherit;">description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The description of the policy.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="id_python">
<a href="#id_python" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the policy.
* `policy_name`- The name of the policy.
* `policy_type`- The type of the policy.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="policy_name_python">
<a href="#policy_name_python" style="color: inherit; text-decoration: inherit;">policy_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="policy_type_python">
<a href="#policy_type_python" style="color: inherit; text-decoration: inherit;">policy_<wbr>type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the policy. If you do not specify this parameter, the system lists all types of policies. Valid values: `Custom` and `System`.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="update_date_python">
<a href="#update_date_python" style="color: inherit; text-decoration: inherit;">update_<wbr>date</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The time when the policy was updated.
{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-alicloud">https://github.com/pulumi/pulumi-alicloud</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`alicloud` Terraform Provider](https://github.com/aliyun/terraform-provider-alicloud).{{% /md %}}</dd>
</dl>


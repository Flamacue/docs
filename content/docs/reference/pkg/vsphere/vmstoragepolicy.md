
---
title: "VmStoragePolicy"
title_tag: "vsphere.VmStoragePolicy"
meta_desc: "Documentation for the vsphere.VmStoragePolicy resource with examples, input properties, output properties, lookup functions, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

The `vsphere.VmStoragePolicy` resource can be used to create and manage storage
policies. Using this storage policy, tag based placement rules can be created to
place a VM on a particular tagged datastore.


{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}





{{< example csharp >}}

```csharp
using Pulumi;
using VSphere = Pulumi.VSphere;

class MyStack : Stack
{
    public MyStack()
    {
        var dc = Output.Create(VSphere.GetDatacenter.InvokeAsync(new VSphere.GetDatacenterArgs
        {
            Name = "DC",
        }));
        var tagCategory = Output.Create(VSphere.GetTagCategory.InvokeAsync(new VSphere.GetTagCategoryArgs
        {
            Name = "cat1",
        }));
        var tag1 = tagCategory.Apply(tagCategory => Output.Create(VSphere.GetTag.InvokeAsync(new VSphere.GetTagArgs
        {
            Name = "tag1",
            CategoryId = tagCategory.Id,
        })));
        var tag2 = tagCategory.Apply(tagCategory => Output.Create(VSphere.GetTag.InvokeAsync(new VSphere.GetTagArgs
        {
            Name = "tag2",
            CategoryId = tagCategory.Id,
        })));
        var policyTagBasedPlacement = new VSphere.VmStoragePolicy("policyTagBasedPlacement", new VSphere.VmStoragePolicyArgs
        {
            Description = "description",
            TagRules = 
            {
                new VSphere.Inputs.VmStoragePolicyTagRuleArgs
                {
                    TagCategory = tagCategory.Apply(tagCategory => tagCategory.Name),
                    Tags = 
                    {
                        tag1.Apply(tag1 => tag1.Name),
                        tag2.Apply(tag2 => tag2.Name),
                    },
                    IncludeDatastoresWithTags = true,
                },
            },
        });
    }

}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-vsphere/sdk/v2/go/vsphere"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		opt0 := "DC"
		_, err := vsphere.LookupDatacenter(ctx, &vsphere.LookupDatacenterArgs{
			Name: &opt0,
		}, nil)
		if err != nil {
			return err
		}
		tagCategory, err := vsphere.LookupTagCategory(ctx, &vsphere.LookupTagCategoryArgs{
			Name: "cat1",
		}, nil)
		if err != nil {
			return err
		}
		tag1, err := vsphere.LookupTag(ctx, &vsphere.LookupTagArgs{
			Name:       "tag1",
			CategoryId: tagCategory.Id,
		}, nil)
		if err != nil {
			return err
		}
		tag2, err := vsphere.LookupTag(ctx, &vsphere.LookupTagArgs{
			Name:       "tag2",
			CategoryId: tagCategory.Id,
		}, nil)
		if err != nil {
			return err
		}
		_, err = vsphere.NewVmStoragePolicy(ctx, "policyTagBasedPlacement", &vsphere.VmStoragePolicyArgs{
			Description: pulumi.String("description"),
			TagRules: vsphere.VmStoragePolicyTagRuleArray{
				&vsphere.VmStoragePolicyTagRuleArgs{
					TagCategory: pulumi.String(tagCategory.Name),
					Tags: pulumi.StringArray{
						pulumi.String(tag1.Name),
						pulumi.String(tag2.Name),
					},
					IncludeDatastoresWithTags: pulumi.Bool(true),
				},
			},
		})
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
import pulumi_vsphere as vsphere

dc = vsphere.get_datacenter(name="DC")
tag_category = vsphere.get_tag_category(name="cat1")
tag1 = vsphere.get_tag(name="tag1",
    category_id=tag_category.id)
tag2 = vsphere.get_tag(name="tag2",
    category_id=tag_category.id)
policy_tag_based_placement = vsphere.VmStoragePolicy("policyTagBasedPlacement",
    description="description",
    tag_rules=[vsphere.VmStoragePolicyTagRuleArgs(
        tag_category=tag_category.name,
        tags=[
            tag1.name,
            tag2.name,
        ],
        include_datastores_with_tags=True,
    )])
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as vsphere from "@pulumi/vsphere";

const dc = vsphere.getDatacenter({
    name: "DC",
});
const tagCategory = vsphere.getTagCategory({
    name: "cat1",
});
const tag1 = tagCategory.then(tagCategory => vsphere.getTag({
    name: "tag1",
    categoryId: tagCategory.id,
}));
const tag2 = tagCategory.then(tagCategory => vsphere.getTag({
    name: "tag2",
    categoryId: tagCategory.id,
}));
const policyTagBasedPlacement = new vsphere.VmStoragePolicy("policyTagBasedPlacement", {
    description: "description",
    tagRules: [{
        tagCategory: tagCategory.then(tagCategory => tagCategory.name),
        tags: [
            tag1.then(tag1 => tag1.name),
            tag2.then(tag2 => tag2.name),
        ],
        includeDatastoresWithTags: true,
    }],
});
```


{{< /example >}}





{{% /examples %}}




## Create a VmStoragePolicy Resource {#create}
{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx">VmStoragePolicy</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">, </span><span class="nx">args</span><span class="p">:</span> <span class="nx"><a href="#inputs">VmStoragePolicyArgs</a></span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nx">VmStoragePolicy</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">, </span><span class="nx">description</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">tag_rules</span><span class="p">:</span> <span class="nx">Optional[Sequence[VmStoragePolicyTagRuleArgs]]</span> = None<span class="p">)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span><span class="nx">NewVmStoragePolicy</span><span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">, </span><span class="nx">args</span><span class="p"> </span><span class="nx"><a href="#inputs">VmStoragePolicyArgs</a></span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">VmStoragePolicy</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx">VmStoragePolicy</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">, </span><span class="nx"><a href="#inputs">VmStoragePolicyArgs</a></span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language nodejs %}}

<dl class="resources-properties"><dt
        class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>
      The unique name of the resource.
    </dd><dt
        class="property-required" title="Required">
        <span>args</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#inputs">VmStoragePolicyArgs</a></span>
    </dt>
    <dd>
      The arguments to resource properties.
    </dd><dt
        class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span>
    </dt>
    <dd>
      Bag of options to control resource&#39;s behavior.
    </dd></dl>

{{% /choosable %}}

{{% choosable language python %}}

<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>resource_name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>The unique name of the resource.</dd>
    <dt class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
        <span class="property-type">
            <a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">ResourceOptions</a>
        </span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>
{{% /choosable %}}

{{% choosable language go %}}

<dl class="resources-properties"><dt
        class="property-optional" title="Optional">
        <span>ctx</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span>
    </dt>
    <dd>
      Context object for the current deployment.
    </dd><dt
        class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>
      The unique name of the resource.
    </dd><dt
        class="property-required" title="Required">
        <span>args</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#inputs">VmStoragePolicyArgs</a></span>
    </dt>
    <dd>
      The arguments to resource properties.
    </dd><dt
        class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span>
    </dt>
    <dd>
      Bag of options to control resource&#39;s behavior.
    </dd></dl>

{{% /choosable %}}

{{% choosable language csharp %}}

<dl class="resources-properties"><dt
        class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>
      The unique name of the resource.
    </dd><dt
        class="property-required" title="Required">
        <span>args</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#inputs">VmStoragePolicyArgs</a></span>
    </dt>
    <dd>
      The arguments to resource properties.
    </dd><dt
        class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span>
    </dt>
    <dd>
      Bag of options to control resource&#39;s behavior.
    </dd></dl>

{{% /choosable %}}

## VmStoragePolicy Resource Properties {#properties}

To learn more about resource properties and how to use them, see [Inputs and Outputs]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) in the Programming Model docs.

### Inputs

The VmStoragePolicy resource accepts the following [input]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) properties:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="tagrules_csharp">
<a href="#tagrules_csharp" style="color: inherit; text-decoration: inherit;">Tag<wbr>Rules</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#vmstoragepolicytagrule">List&lt;Pulumi.<wbr>VSphere.<wbr>Inputs.<wbr>Vm<wbr>Storage<wbr>Policy<wbr>Tag<wbr>Rule<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}List of tag rules. The tag category and tags to be associated to this storage policy.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="description_csharp">
<a href="#description_csharp" style="color: inherit; text-decoration: inherit;">Description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Description of the storage policy.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the storage policy.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="tagrules_go">
<a href="#tagrules_go" style="color: inherit; text-decoration: inherit;">Tag<wbr>Rules</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#vmstoragepolicytagrule">[]Vm<wbr>Storage<wbr>Policy<wbr>Tag<wbr>Rule</a></span>
    </dt>
    <dd>{{% md %}}List of tag rules. The tag category and tags to be associated to this storage policy.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="description_go">
<a href="#description_go" style="color: inherit; text-decoration: inherit;">Description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Description of the storage policy.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the storage policy.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="tagrules_nodejs">
<a href="#tagrules_nodejs" style="color: inherit; text-decoration: inherit;">tag<wbr>Rules</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#vmstoragepolicytagrule">Vm<wbr>Storage<wbr>Policy<wbr>Tag<wbr>Rule[]</a></span>
    </dt>
    <dd>{{% md %}}List of tag rules. The tag category and tags to be associated to this storage policy.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="description_nodejs">
<a href="#description_nodejs" style="color: inherit; text-decoration: inherit;">description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Description of the storage policy.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the storage policy.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="tag_rules_python">
<a href="#tag_rules_python" style="color: inherit; text-decoration: inherit;">tag_<wbr>rules</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#vmstoragepolicytagrule">Sequence[Vm<wbr>Storage<wbr>Policy<wbr>Tag<wbr>Rule<wbr>Args]</a></span>
    </dt>
    <dd>{{% md %}}List of tag rules. The tag category and tags to be associated to this storage policy.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="description_python">
<a href="#description_python" style="color: inherit; text-decoration: inherit;">description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the storage policy.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the storage policy.
{{% /md %}}</dd></dl>
{{% /choosable %}}


### Outputs

All [input](#inputs) properties are implicitly available as output properties. Additionally, the VmStoragePolicy resource produces the following output properties:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="id_csharp">
<a href="#id_csharp" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd></dl>
{{% /choosable %}}



## Look up an Existing VmStoragePolicy Resource {#look-up}

Get an existing VmStoragePolicy resource's state with the given name, ID, and optional extra properties used to qualify the lookup.
{{< chooser language "typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">, </span><span class="nx">id</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">Input&lt;ID&gt;</a></span><span class="p">, </span><span class="nx">state</span><span class="p">?:</span> <span class="nx">VmStoragePolicyState</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">): </span><span class="nx">VmStoragePolicy</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class=nd>@staticmethod</span>
<span class="k">def </span><span class="nf">get</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">id</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">, </span><span class="nx">description</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">tag_rules</span><span class="p">:</span> <span class="nx">Optional[Sequence[VmStoragePolicyTagRuleArgs]]</span> = None<span class="p">) -&gt;</span> VmStoragePolicy</code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetVmStoragePolicy<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">, </span><span class="nx">id</span><span class="p"> </span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#IDInput">IDInput</a></span><span class="p">, </span><span class="nx">state</span><span class="p"> *</span><span class="nx">VmStoragePolicyState</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">VmStoragePolicy</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx">VmStoragePolicy</span><span class="nf"> Get</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input-1.html">Input&lt;string&gt;</a></span><span class="p"> </span><span class="nx">id<span class="p">, </span><span class="nx">VmStoragePolicyState</span><span class="p">? </span><span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language nodejs %}}

<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resulting resource.</dd>
    <dt class="property-required" title="Required">
        <span>id</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The <em>unique</em> provider ID of the resource to lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>state</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>Any extra arguments used during the lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>resource_name</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resulting resource.</dd>
    <dt class="property-required" title="Optional">
        <span>id</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The <em>unique</em> provider ID of the resource to lookup.</dd>
</dl>
{{% /choosable %}}

{{% choosable language go %}}

<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resulting resource.</dd>
    <dt class="property-required" title="Required">
        <span>id</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The <em>unique</em> provider ID of the resource to lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>state</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>Any extra arguments used during the lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

{{% choosable language csharp %}}

<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resulting resource.</dd>
    <dt class="property-required" title="Required">
        <span>id</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The <em>unique</em> provider ID of the resource to lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>state</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>Any extra arguments used during the lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

The following state arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_description_csharp">
<a href="#state_description_csharp" style="color: inherit; text-decoration: inherit;">Description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Description of the storage policy.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_name_csharp">
<a href="#state_name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the storage policy.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_tagrules_csharp">
<a href="#state_tagrules_csharp" style="color: inherit; text-decoration: inherit;">Tag<wbr>Rules</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#vmstoragepolicytagrule">List&lt;Pulumi.<wbr>VSphere.<wbr>Inputs.<wbr>Vm<wbr>Storage<wbr>Policy<wbr>Tag<wbr>Rule<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}List of tag rules. The tag category and tags to be associated to this storage policy.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_description_go">
<a href="#state_description_go" style="color: inherit; text-decoration: inherit;">Description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Description of the storage policy.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_name_go">
<a href="#state_name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the storage policy.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_tagrules_go">
<a href="#state_tagrules_go" style="color: inherit; text-decoration: inherit;">Tag<wbr>Rules</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#vmstoragepolicytagrule">[]Vm<wbr>Storage<wbr>Policy<wbr>Tag<wbr>Rule</a></span>
    </dt>
    <dd>{{% md %}}List of tag rules. The tag category and tags to be associated to this storage policy.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_description_nodejs">
<a href="#state_description_nodejs" style="color: inherit; text-decoration: inherit;">description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Description of the storage policy.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_name_nodejs">
<a href="#state_name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the storage policy.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_tagrules_nodejs">
<a href="#state_tagrules_nodejs" style="color: inherit; text-decoration: inherit;">tag<wbr>Rules</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#vmstoragepolicytagrule">Vm<wbr>Storage<wbr>Policy<wbr>Tag<wbr>Rule[]</a></span>
    </dt>
    <dd>{{% md %}}List of tag rules. The tag category and tags to be associated to this storage policy.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_description_python">
<a href="#state_description_python" style="color: inherit; text-decoration: inherit;">description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the storage policy.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_name_python">
<a href="#state_name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the storage policy.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_tag_rules_python">
<a href="#state_tag_rules_python" style="color: inherit; text-decoration: inherit;">tag_<wbr>rules</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#vmstoragepolicytagrule">Sequence[Vm<wbr>Storage<wbr>Policy<wbr>Tag<wbr>Rule<wbr>Args]</a></span>
    </dt>
    <dd>{{% md %}}List of tag rules. The tag category and tags to be associated to this storage policy.
{{% /md %}}</dd></dl>
{{% /choosable %}}






## Supporting Types



<h4 id="vmstoragepolicytagrule">Vm<wbr>Storage<wbr>Policy<wbr>Tag<wbr>Rule</h4>

{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="tagcategory_csharp">
<a href="#tagcategory_csharp" style="color: inherit; text-decoration: inherit;">Tag<wbr>Category</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the tag category.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="tags_csharp">
<a href="#tags_csharp" style="color: inherit; text-decoration: inherit;">Tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}List of Name of tags to select from the given category.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="includedatastoreswithtags_csharp">
<a href="#includedatastoreswithtags_csharp" style="color: inherit; text-decoration: inherit;">Include<wbr>Datastores<wbr>With<wbr>Tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to include datastores with the given tags or exclude. Default 
value is true i.e. include datastores with the given tags.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="tagcategory_go">
<a href="#tagcategory_go" style="color: inherit; text-decoration: inherit;">Tag<wbr>Category</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the tag category.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="tags_go">
<a href="#tags_go" style="color: inherit; text-decoration: inherit;">Tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of Name of tags to select from the given category.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="includedatastoreswithtags_go">
<a href="#includedatastoreswithtags_go" style="color: inherit; text-decoration: inherit;">Include<wbr>Datastores<wbr>With<wbr>Tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to include datastores with the given tags or exclude. Default 
value is true i.e. include datastores with the given tags.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="tagcategory_nodejs">
<a href="#tagcategory_nodejs" style="color: inherit; text-decoration: inherit;">tag<wbr>Category</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the tag category.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="tags_nodejs">
<a href="#tags_nodejs" style="color: inherit; text-decoration: inherit;">tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}List of Name of tags to select from the given category.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="includedatastoreswithtags_nodejs">
<a href="#includedatastoreswithtags_nodejs" style="color: inherit; text-decoration: inherit;">include<wbr>Datastores<wbr>With<wbr>Tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Whether to include datastores with the given tags or exclude. Default 
value is true i.e. include datastores with the given tags.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="tag_category_python">
<a href="#tag_category_python" style="color: inherit; text-decoration: inherit;">tag_<wbr>category</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the tag category.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="tags_python">
<a href="#tags_python" style="color: inherit; text-decoration: inherit;">tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}List of Name of tags to select from the given category.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="include_datastores_with_tags_python">
<a href="#include_datastores_with_tags_python" style="color: inherit; text-decoration: inherit;">include_<wbr>datastores_<wbr>with_<wbr>tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to include datastores with the given tags or exclude. Default 
value is true i.e. include datastores with the given tags.
{{% /md %}}</dd></dl>
{{% /choosable %}}


<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-vsphere">https://github.com/pulumi/pulumi-vsphere</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`vsphere` Terraform Provider](https://github.com/hashicorp/terraform-provider-vsphere).{{% /md %}}</dd>
</dl>



---
title: "Role"
title_tag: "okta.group.Role"
meta_desc: "Documentation for the okta.group.Role resource with examples, input properties, output properties, lookup functions, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Assigns Admin roles to Okta Groups.

This resource allows you to assign Okta administrator roles to Okta Groups. This resource provides a one-to-one
interface between the Okta group and the admin role.

{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}





{{< example csharp >}}

```csharp
using Pulumi;
using Okta = Pulumi.Okta;

class MyStack : Stack
{
    public MyStack()
    {
        var example = new Okta.Group.Role("example", new Okta.Group.RoleArgs
        {
            GroupId = "<group id>",
            RoleType = "READ_ONLY_ADMIN",
        });
    }

}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-okta/sdk/v2/go/okta/group"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		_, err := group.NewRole(ctx, "example", &group.RoleArgs{
			GroupId:  pulumi.String("<group id>"),
			RoleType: pulumi.String("READ_ONLY_ADMIN"),
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
import pulumi_okta as okta

example = okta.group.Role("example",
    group_id="<group id>",
    role_type="READ_ONLY_ADMIN")
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as okta from "@pulumi/okta";

const example = new okta.group.Role("example", {
    groupId: "<group id>",
    roleType: "READ_ONLY_ADMIN",
});
```


{{< /example >}}





{{% /examples %}}




## Create a Role Resource {#create}
{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx">Role</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">, </span><span class="nx">args</span><span class="p">:</span> <span class="nx"><a href="#inputs">RoleArgs</a></span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nx">Role</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">, </span><span class="nx">group_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">role_type</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">target_app_lists</span><span class="p">:</span> <span class="nx">Optional[Sequence[str]]</span> = None<span class="p">, </span><span class="nx">target_group_lists</span><span class="p">:</span> <span class="nx">Optional[Sequence[str]]</span> = None<span class="p">)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span><span class="nx">NewRole</span><span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">, </span><span class="nx">args</span><span class="p"> </span><span class="nx"><a href="#inputs">RoleArgs</a></span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">Role</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx">Role</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">, </span><span class="nx"><a href="#inputs">RoleArgs</a></span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        <span class="property-type"><a href="#inputs">RoleArgs</a></span>
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
        <span class="property-type"><a href="#inputs">RoleArgs</a></span>
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
        <span class="property-type"><a href="#inputs">RoleArgs</a></span>
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

## Role Resource Properties {#properties}

To learn more about resource properties and how to use them, see [Inputs and Outputs]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) in the Programming Model docs.

### Inputs

The Role resource accepts the following [input]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) properties:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="groupid_csharp">
<a href="#groupid_csharp" style="color: inherit; text-decoration: inherit;">Group<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of group to attach admin roles to.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="roletype_csharp">
<a href="#roletype_csharp" style="color: inherit; text-decoration: inherit;">Role<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Admin role assigned to the group. It can be any one of the following values `"SUPER_ADMIN"`
, `"ORG_ADMIN"`, `"APP_ADMIN"`, `"USER_ADMIN"`, `"HELP_DESK_ADMIN"`, `"READ_ONLY_ADMIN"`
, `"MOBILE_ADMIN"`, `"API_ACCESS_MANAGEMENT_ADMIN"`, `"REPORT_ADMIN"`, `"GROUP_MEMBERSHIP_ADMIN"`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="targetapplists_csharp">
<a href="#targetapplists_csharp" style="color: inherit; text-decoration: inherit;">Target<wbr>App<wbr>Lists</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}A list of app names (name represents set of app instances, like 'salesforce' or '
facebook'), or a combination of app name and app instance ID (like 'facebook.0oapsqQ6dv19pqyEo0g3') you would like as
the targets of the admin role.
- Only supported when used with the role type `"APP_ADMIN"`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="targetgrouplists_csharp">
<a href="#targetgrouplists_csharp" style="color: inherit; text-decoration: inherit;">Target<wbr>Group<wbr>Lists</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}A list of group IDs you would like as the targets of the admin role.
- Only supported when used with the role types: `GROUP_MEMBERSHIP_ADMIN`, `HELP_DESK_ADMIN`, or `USER_ADMIN`.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="groupid_go">
<a href="#groupid_go" style="color: inherit; text-decoration: inherit;">Group<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of group to attach admin roles to.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="roletype_go">
<a href="#roletype_go" style="color: inherit; text-decoration: inherit;">Role<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Admin role assigned to the group. It can be any one of the following values `"SUPER_ADMIN"`
, `"ORG_ADMIN"`, `"APP_ADMIN"`, `"USER_ADMIN"`, `"HELP_DESK_ADMIN"`, `"READ_ONLY_ADMIN"`
, `"MOBILE_ADMIN"`, `"API_ACCESS_MANAGEMENT_ADMIN"`, `"REPORT_ADMIN"`, `"GROUP_MEMBERSHIP_ADMIN"`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="targetapplists_go">
<a href="#targetapplists_go" style="color: inherit; text-decoration: inherit;">Target<wbr>App<wbr>Lists</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of app names (name represents set of app instances, like 'salesforce' or '
facebook'), or a combination of app name and app instance ID (like 'facebook.0oapsqQ6dv19pqyEo0g3') you would like as
the targets of the admin role.
- Only supported when used with the role type `"APP_ADMIN"`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="targetgrouplists_go">
<a href="#targetgrouplists_go" style="color: inherit; text-decoration: inherit;">Target<wbr>Group<wbr>Lists</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of group IDs you would like as the targets of the admin role.
- Only supported when used with the role types: `GROUP_MEMBERSHIP_ADMIN`, `HELP_DESK_ADMIN`, or `USER_ADMIN`.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="groupid_nodejs">
<a href="#groupid_nodejs" style="color: inherit; text-decoration: inherit;">group<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of group to attach admin roles to.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="roletype_nodejs">
<a href="#roletype_nodejs" style="color: inherit; text-decoration: inherit;">role<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Admin role assigned to the group. It can be any one of the following values `"SUPER_ADMIN"`
, `"ORG_ADMIN"`, `"APP_ADMIN"`, `"USER_ADMIN"`, `"HELP_DESK_ADMIN"`, `"READ_ONLY_ADMIN"`
, `"MOBILE_ADMIN"`, `"API_ACCESS_MANAGEMENT_ADMIN"`, `"REPORT_ADMIN"`, `"GROUP_MEMBERSHIP_ADMIN"`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="targetapplists_nodejs">
<a href="#targetapplists_nodejs" style="color: inherit; text-decoration: inherit;">target<wbr>App<wbr>Lists</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of app names (name represents set of app instances, like 'salesforce' or '
facebook'), or a combination of app name and app instance ID (like 'facebook.0oapsqQ6dv19pqyEo0g3') you would like as
the targets of the admin role.
- Only supported when used with the role type `"APP_ADMIN"`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="targetgrouplists_nodejs">
<a href="#targetgrouplists_nodejs" style="color: inherit; text-decoration: inherit;">target<wbr>Group<wbr>Lists</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of group IDs you would like as the targets of the admin role.
- Only supported when used with the role types: `GROUP_MEMBERSHIP_ADMIN`, `HELP_DESK_ADMIN`, or `USER_ADMIN`.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="group_id_python">
<a href="#group_id_python" style="color: inherit; text-decoration: inherit;">group_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of group to attach admin roles to.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="role_type_python">
<a href="#role_type_python" style="color: inherit; text-decoration: inherit;">role_<wbr>type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Admin role assigned to the group. It can be any one of the following values `"SUPER_ADMIN"`
, `"ORG_ADMIN"`, `"APP_ADMIN"`, `"USER_ADMIN"`, `"HELP_DESK_ADMIN"`, `"READ_ONLY_ADMIN"`
, `"MOBILE_ADMIN"`, `"API_ACCESS_MANAGEMENT_ADMIN"`, `"REPORT_ADMIN"`, `"GROUP_MEMBERSHIP_ADMIN"`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="target_app_lists_python">
<a href="#target_app_lists_python" style="color: inherit; text-decoration: inherit;">target_<wbr>app_<wbr>lists</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}A list of app names (name represents set of app instances, like 'salesforce' or '
facebook'), or a combination of app name and app instance ID (like 'facebook.0oapsqQ6dv19pqyEo0g3') you would like as
the targets of the admin role.
- Only supported when used with the role type `"APP_ADMIN"`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="target_group_lists_python">
<a href="#target_group_lists_python" style="color: inherit; text-decoration: inherit;">target_<wbr>group_<wbr>lists</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}A list of group IDs you would like as the targets of the admin role.
- Only supported when used with the role types: `GROUP_MEMBERSHIP_ADMIN`, `HELP_DESK_ADMIN`, or `USER_ADMIN`.
{{% /md %}}</dd></dl>
{{% /choosable %}}


### Outputs

All [input](#inputs) properties are implicitly available as output properties. Additionally, the Role resource produces the following output properties:



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



## Look up an Existing Role Resource {#look-up}

Get an existing Role resource's state with the given name, ID, and optional extra properties used to qualify the lookup.
{{< chooser language "typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">, </span><span class="nx">id</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">Input&lt;ID&gt;</a></span><span class="p">, </span><span class="nx">state</span><span class="p">?:</span> <span class="nx">RoleState</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">): </span><span class="nx">Role</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class=nd>@staticmethod</span>
<span class="k">def </span><span class="nf">get</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">id</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">, </span><span class="nx">group_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">role_type</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">target_app_lists</span><span class="p">:</span> <span class="nx">Optional[Sequence[str]]</span> = None<span class="p">, </span><span class="nx">target_group_lists</span><span class="p">:</span> <span class="nx">Optional[Sequence[str]]</span> = None<span class="p">) -&gt;</span> Role</code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetRole<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">, </span><span class="nx">id</span><span class="p"> </span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#IDInput">IDInput</a></span><span class="p">, </span><span class="nx">state</span><span class="p"> *</span><span class="nx">RoleState</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">Role</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx">Role</span><span class="nf"> Get</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input-1.html">Input&lt;string&gt;</a></span><span class="p"> </span><span class="nx">id<span class="p">, </span><span class="nx">RoleState</span><span class="p">? </span><span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        <span id="state_groupid_csharp">
<a href="#state_groupid_csharp" style="color: inherit; text-decoration: inherit;">Group<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of group to attach admin roles to.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_roletype_csharp">
<a href="#state_roletype_csharp" style="color: inherit; text-decoration: inherit;">Role<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Admin role assigned to the group. It can be any one of the following values `"SUPER_ADMIN"`
, `"ORG_ADMIN"`, `"APP_ADMIN"`, `"USER_ADMIN"`, `"HELP_DESK_ADMIN"`, `"READ_ONLY_ADMIN"`
, `"MOBILE_ADMIN"`, `"API_ACCESS_MANAGEMENT_ADMIN"`, `"REPORT_ADMIN"`, `"GROUP_MEMBERSHIP_ADMIN"`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_targetapplists_csharp">
<a href="#state_targetapplists_csharp" style="color: inherit; text-decoration: inherit;">Target<wbr>App<wbr>Lists</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}A list of app names (name represents set of app instances, like 'salesforce' or '
facebook'), or a combination of app name and app instance ID (like 'facebook.0oapsqQ6dv19pqyEo0g3') you would like as
the targets of the admin role.
- Only supported when used with the role type `"APP_ADMIN"`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_targetgrouplists_csharp">
<a href="#state_targetgrouplists_csharp" style="color: inherit; text-decoration: inherit;">Target<wbr>Group<wbr>Lists</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}A list of group IDs you would like as the targets of the admin role.
- Only supported when used with the role types: `GROUP_MEMBERSHIP_ADMIN`, `HELP_DESK_ADMIN`, or `USER_ADMIN`.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_groupid_go">
<a href="#state_groupid_go" style="color: inherit; text-decoration: inherit;">Group<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of group to attach admin roles to.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_roletype_go">
<a href="#state_roletype_go" style="color: inherit; text-decoration: inherit;">Role<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Admin role assigned to the group. It can be any one of the following values `"SUPER_ADMIN"`
, `"ORG_ADMIN"`, `"APP_ADMIN"`, `"USER_ADMIN"`, `"HELP_DESK_ADMIN"`, `"READ_ONLY_ADMIN"`
, `"MOBILE_ADMIN"`, `"API_ACCESS_MANAGEMENT_ADMIN"`, `"REPORT_ADMIN"`, `"GROUP_MEMBERSHIP_ADMIN"`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_targetapplists_go">
<a href="#state_targetapplists_go" style="color: inherit; text-decoration: inherit;">Target<wbr>App<wbr>Lists</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of app names (name represents set of app instances, like 'salesforce' or '
facebook'), or a combination of app name and app instance ID (like 'facebook.0oapsqQ6dv19pqyEo0g3') you would like as
the targets of the admin role.
- Only supported when used with the role type `"APP_ADMIN"`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_targetgrouplists_go">
<a href="#state_targetgrouplists_go" style="color: inherit; text-decoration: inherit;">Target<wbr>Group<wbr>Lists</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of group IDs you would like as the targets of the admin role.
- Only supported when used with the role types: `GROUP_MEMBERSHIP_ADMIN`, `HELP_DESK_ADMIN`, or `USER_ADMIN`.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_groupid_nodejs">
<a href="#state_groupid_nodejs" style="color: inherit; text-decoration: inherit;">group<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of group to attach admin roles to.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_roletype_nodejs">
<a href="#state_roletype_nodejs" style="color: inherit; text-decoration: inherit;">role<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Admin role assigned to the group. It can be any one of the following values `"SUPER_ADMIN"`
, `"ORG_ADMIN"`, `"APP_ADMIN"`, `"USER_ADMIN"`, `"HELP_DESK_ADMIN"`, `"READ_ONLY_ADMIN"`
, `"MOBILE_ADMIN"`, `"API_ACCESS_MANAGEMENT_ADMIN"`, `"REPORT_ADMIN"`, `"GROUP_MEMBERSHIP_ADMIN"`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_targetapplists_nodejs">
<a href="#state_targetapplists_nodejs" style="color: inherit; text-decoration: inherit;">target<wbr>App<wbr>Lists</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of app names (name represents set of app instances, like 'salesforce' or '
facebook'), or a combination of app name and app instance ID (like 'facebook.0oapsqQ6dv19pqyEo0g3') you would like as
the targets of the admin role.
- Only supported when used with the role type `"APP_ADMIN"`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_targetgrouplists_nodejs">
<a href="#state_targetgrouplists_nodejs" style="color: inherit; text-decoration: inherit;">target<wbr>Group<wbr>Lists</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of group IDs you would like as the targets of the admin role.
- Only supported when used with the role types: `GROUP_MEMBERSHIP_ADMIN`, `HELP_DESK_ADMIN`, or `USER_ADMIN`.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_group_id_python">
<a href="#state_group_id_python" style="color: inherit; text-decoration: inherit;">group_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of group to attach admin roles to.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_role_type_python">
<a href="#state_role_type_python" style="color: inherit; text-decoration: inherit;">role_<wbr>type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Admin role assigned to the group. It can be any one of the following values `"SUPER_ADMIN"`
, `"ORG_ADMIN"`, `"APP_ADMIN"`, `"USER_ADMIN"`, `"HELP_DESK_ADMIN"`, `"READ_ONLY_ADMIN"`
, `"MOBILE_ADMIN"`, `"API_ACCESS_MANAGEMENT_ADMIN"`, `"REPORT_ADMIN"`, `"GROUP_MEMBERSHIP_ADMIN"`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_target_app_lists_python">
<a href="#state_target_app_lists_python" style="color: inherit; text-decoration: inherit;">target_<wbr>app_<wbr>lists</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}A list of app names (name represents set of app instances, like 'salesforce' or '
facebook'), or a combination of app name and app instance ID (like 'facebook.0oapsqQ6dv19pqyEo0g3') you would like as
the targets of the admin role.
- Only supported when used with the role type `"APP_ADMIN"`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_target_group_lists_python">
<a href="#state_target_group_lists_python" style="color: inherit; text-decoration: inherit;">target_<wbr>group_<wbr>lists</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}A list of group IDs you would like as the targets of the admin role.
- Only supported when used with the role types: `GROUP_MEMBERSHIP_ADMIN`, `HELP_DESK_ADMIN`, or `USER_ADMIN`.
{{% /md %}}</dd></dl>
{{% /choosable %}}





## Import


Individual admin role assignment can be imported by passing the group and role assignment IDs as follows

```sh
 $ pulumi import okta:group/role:Role example <group id>/<role id>
```




<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-okta">https://github.com/pulumi/pulumi-okta</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`okta` Terraform Provider](https://github.com/oktadeveloper/terraform-provider-okta).{{% /md %}}</dd>
</dl>



---
title: "GroupMemberEntityIds"
title_tag: "vault.identity.GroupMemberEntityIds"
meta_desc: "Documentation for the vault.identity.GroupMemberEntityIds resource with examples, input properties, output properties, lookup functions, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Manages member entities for an Identity Group for Vault. The [Identity secrets engine](https://www.vaultproject.io/docs/secrets/identity/index.html) is the identity management solution for Vault.


{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}


### Exclusive Member Entities


{{< example csharp >}}

```csharp
using Pulumi;
using Vault = Pulumi.Vault;

class MyStack : Stack
{
    public MyStack()
    {
        var @internal = new Vault.Identity.Group("internal", new Vault.Identity.GroupArgs
        {
            Type = "internal",
            ExternalMemberEntityIds = true,
            Metadata = 
            {
                { "version", "2" },
            },
        });
        var user = new Vault.Identity.Entity("user", new Vault.Identity.EntityArgs
        {
        });
        var members = new Vault.Identity.GroupMemberEntityIds("members", new Vault.Identity.GroupMemberEntityIdsArgs
        {
            Exclusive = true,
            MemberEntityIds = 
            {
                user.Id,
            },
            GroupId = @internal.Id,
        });
    }

}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-vault/sdk/v3/go/vault/identity"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		internal, err := identity.NewGroup(ctx, "internal", &identity.GroupArgs{
			Type:                    pulumi.String("internal"),
			ExternalMemberEntityIds: pulumi.Bool(true),
			Metadata: pulumi.StringMap{
				"version": pulumi.String("2"),
			},
		})
		if err != nil {
			return err
		}
		user, err := identity.NewEntity(ctx, "user", nil)
		if err != nil {
			return err
		}
		_, err = identity.NewGroupMemberEntityIds(ctx, "members", &identity.GroupMemberEntityIdsArgs{
			Exclusive: pulumi.Bool(true),
			MemberEntityIds: pulumi.StringArray{
				user.ID(),
			},
			GroupId: internal.ID(),
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
import pulumi_vault as vault

internal = vault.identity.Group("internal",
    type="internal",
    external_member_entity_ids=True,
    metadata={
        "version": "2",
    })
user = vault.identity.Entity("user")
members = vault.identity.GroupMemberEntityIds("members",
    exclusive=True,
    member_entity_ids=[user.id],
    group_id=internal.id)
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as vault from "@pulumi/vault";

const internal = new vault.identity.Group("internal", {
    type: "internal",
    externalMemberEntityIds: true,
    metadata: {
        version: "2",
    },
});
const user = new vault.identity.Entity("user", {});
const members = new vault.identity.GroupMemberEntityIds("members", {
    exclusive: true,
    memberEntityIds: [user.id],
    groupId: internal.id,
});
```


{{< /example >}}




### Non-exclusive Member Entities


{{< example csharp >}}

```csharp
using Pulumi;
using Vault = Pulumi.Vault;

class MyStack : Stack
{
    public MyStack()
    {
        var @internal = new Vault.Identity.Group("internal", new Vault.Identity.GroupArgs
        {
            Type = "internal",
            ExternalMemberEntityIds = true,
            Metadata = 
            {
                { "version", "2" },
            },
        });
        var testUser = new Vault.Identity.Entity("testUser", new Vault.Identity.EntityArgs
        {
        });
        var secondTestUser = new Vault.Identity.Entity("secondTestUser", new Vault.Identity.EntityArgs
        {
        });
        var devUser = new Vault.Identity.Entity("devUser", new Vault.Identity.EntityArgs
        {
        });
        var test = new Vault.Identity.GroupMemberEntityIds("test", new Vault.Identity.GroupMemberEntityIdsArgs
        {
            MemberEntityIds = 
            {
                testUser.Id,
                secondTestUser.Id,
            },
            Exclusive = false,
            GroupId = @internal.Id,
        });
        var others = new Vault.Identity.GroupMemberEntityIds("others", new Vault.Identity.GroupMemberEntityIdsArgs
        {
            MemberEntityIds = 
            {
                devUser.Id,
            },
            Exclusive = false,
            GroupId = @internal.Id,
        });
    }

}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-vault/sdk/v3/go/vault/identity"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		internal, err := identity.NewGroup(ctx, "internal", &identity.GroupArgs{
			Type:                    pulumi.String("internal"),
			ExternalMemberEntityIds: pulumi.Bool(true),
			Metadata: pulumi.StringMap{
				"version": pulumi.String("2"),
			},
		})
		if err != nil {
			return err
		}
		testUser, err := identity.NewEntity(ctx, "testUser", nil)
		if err != nil {
			return err
		}
		secondTestUser, err := identity.NewEntity(ctx, "secondTestUser", nil)
		if err != nil {
			return err
		}
		devUser, err := identity.NewEntity(ctx, "devUser", nil)
		if err != nil {
			return err
		}
		_, err = identity.NewGroupMemberEntityIds(ctx, "test", &identity.GroupMemberEntityIdsArgs{
			MemberEntityIds: pulumi.StringArray{
				testUser.ID(),
				secondTestUser.ID(),
			},
			Exclusive: pulumi.Bool(false),
			GroupId:   internal.ID(),
		})
		if err != nil {
			return err
		}
		_, err = identity.NewGroupMemberEntityIds(ctx, "others", &identity.GroupMemberEntityIdsArgs{
			MemberEntityIds: pulumi.StringArray{
				devUser.ID(),
			},
			Exclusive: pulumi.Bool(false),
			GroupId:   internal.ID(),
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
import pulumi_vault as vault

internal = vault.identity.Group("internal",
    type="internal",
    external_member_entity_ids=True,
    metadata={
        "version": "2",
    })
test_user = vault.identity.Entity("testUser")
second_test_user = vault.identity.Entity("secondTestUser")
dev_user = vault.identity.Entity("devUser")
test = vault.identity.GroupMemberEntityIds("test",
    member_entity_ids=[
        test_user.id,
        second_test_user.id,
    ],
    exclusive=False,
    group_id=internal.id)
others = vault.identity.GroupMemberEntityIds("others",
    member_entity_ids=[dev_user.id],
    exclusive=False,
    group_id=internal.id)
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as vault from "@pulumi/vault";

const internal = new vault.identity.Group("internal", {
    type: "internal",
    externalMemberEntityIds: true,
    metadata: {
        version: "2",
    },
});
const testUser = new vault.identity.Entity("testUser", {});
const secondTestUser = new vault.identity.Entity("secondTestUser", {});
const devUser = new vault.identity.Entity("devUser", {});
const test = new vault.identity.GroupMemberEntityIds("test", {
    memberEntityIds: [
        testUser.id,
        secondTestUser.id,
    ],
    exclusive: false,
    groupId: internal.id,
});
const others = new vault.identity.GroupMemberEntityIds("others", {
    memberEntityIds: [devUser.id],
    exclusive: false,
    groupId: internal.id,
});
```


{{< /example >}}





{{% /examples %}}




## Create a GroupMemberEntityIds Resource {#create}
{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx">GroupMemberEntityIds</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">, </span><span class="nx">args</span><span class="p">:</span> <span class="nx"><a href="#inputs">GroupMemberEntityIdsArgs</a></span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nx">GroupMemberEntityIds</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">, </span><span class="nx">exclusive</span><span class="p">:</span> <span class="nx">Optional[bool]</span> = None<span class="p">, </span><span class="nx">group_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">member_entity_ids</span><span class="p">:</span> <span class="nx">Optional[Sequence[str]]</span> = None<span class="p">)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span><span class="nx">NewGroupMemberEntityIds</span><span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">, </span><span class="nx">args</span><span class="p"> </span><span class="nx"><a href="#inputs">GroupMemberEntityIdsArgs</a></span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">GroupMemberEntityIds</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx">GroupMemberEntityIds</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">, </span><span class="nx"><a href="#inputs">GroupMemberEntityIdsArgs</a></span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        <span class="property-type"><a href="#inputs">GroupMemberEntityIdsArgs</a></span>
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
        <span class="property-type"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span>
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
        <span class="property-type"><a href="#inputs">GroupMemberEntityIdsArgs</a></span>
    </dt>
    <dd>
      The arguments to resource properties.
    </dd><dt
        class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span>
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
        <span class="property-type"><a href="#inputs">GroupMemberEntityIdsArgs</a></span>
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

## GroupMemberEntityIds Resource Properties {#properties}

To learn more about resource properties and how to use them, see [Inputs and Outputs]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) in the Programming Model docs.

### Inputs

The GroupMemberEntityIds resource accepts the following [input]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) properties:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="groupid_csharp">
<a href="#groupid_csharp" style="color: inherit; text-decoration: inherit;">Group<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Group ID to assign member entities to.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="exclusive_csharp">
<a href="#exclusive_csharp" style="color: inherit; text-decoration: inherit;">Exclusive</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Defaults to `true`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="memberentityids_csharp">
<a href="#memberentityids_csharp" style="color: inherit; text-decoration: inherit;">Member<wbr>Entity<wbr>Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}List of member entities that belong to the group
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
    <dd>{{% md %}}Group ID to assign member entities to.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="exclusive_go">
<a href="#exclusive_go" style="color: inherit; text-decoration: inherit;">Exclusive</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Defaults to `true`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="memberentityids_go">
<a href="#memberentityids_go" style="color: inherit; text-decoration: inherit;">Member<wbr>Entity<wbr>Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of member entities that belong to the group
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
    <dd>{{% md %}}Group ID to assign member entities to.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="exclusive_nodejs">
<a href="#exclusive_nodejs" style="color: inherit; text-decoration: inherit;">exclusive</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Defaults to `true`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="memberentityids_nodejs">
<a href="#memberentityids_nodejs" style="color: inherit; text-decoration: inherit;">member<wbr>Entity<wbr>Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}List of member entities that belong to the group
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
    <dd>{{% md %}}Group ID to assign member entities to.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="exclusive_python">
<a href="#exclusive_python" style="color: inherit; text-decoration: inherit;">exclusive</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Defaults to `true`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="member_entity_ids_python">
<a href="#member_entity_ids_python" style="color: inherit; text-decoration: inherit;">member_<wbr>entity_<wbr>ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}List of member entities that belong to the group
{{% /md %}}</dd></dl>
{{% /choosable %}}


### Outputs

All [input](#inputs) properties are implicitly available as output properties. Additionally, the GroupMemberEntityIds resource produces the following output properties:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="groupname_csharp">
<a href="#groupname_csharp" style="color: inherit; text-decoration: inherit;">Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the group that are assigned the member entities.
{{% /md %}}</dd><dt class="property-"
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
        <span id="groupname_go">
<a href="#groupname_go" style="color: inherit; text-decoration: inherit;">Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the group that are assigned the member entities.
{{% /md %}}</dd><dt class="property-"
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
        <span id="groupname_nodejs">
<a href="#groupname_nodejs" style="color: inherit; text-decoration: inherit;">group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the group that are assigned the member entities.
{{% /md %}}</dd><dt class="property-"
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
        <span id="group_name_python">
<a href="#group_name_python" style="color: inherit; text-decoration: inherit;">group_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the group that are assigned the member entities.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="id_python">
<a href="#id_python" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd></dl>
{{% /choosable %}}



## Look up an Existing GroupMemberEntityIds Resource {#look-up}

Get an existing GroupMemberEntityIds resource's state with the given name, ID, and optional extra properties used to qualify the lookup.
{{< chooser language "typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">, </span><span class="nx">id</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">Input&lt;ID&gt;</a></span><span class="p">, </span><span class="nx">state</span><span class="p">?:</span> <span class="nx">GroupMemberEntityIdsState</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">): </span><span class="nx">GroupMemberEntityIds</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class=nd>@staticmethod</span>
<span class="k">def </span><span class="nf">get</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">id</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">, </span><span class="nx">exclusive</span><span class="p">:</span> <span class="nx">Optional[bool]</span> = None<span class="p">, </span><span class="nx">group_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">group_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">member_entity_ids</span><span class="p">:</span> <span class="nx">Optional[Sequence[str]]</span> = None<span class="p">) -&gt;</span> GroupMemberEntityIds</code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetGroupMemberEntityIds<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">, </span><span class="nx">id</span><span class="p"> </span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#IDInput">IDInput</a></span><span class="p">, </span><span class="nx">state</span><span class="p"> *</span><span class="nx">GroupMemberEntityIdsState</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">GroupMemberEntityIds</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx">GroupMemberEntityIds</span><span class="nf"> Get</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input-1.html">Input&lt;string&gt;</a></span><span class="p"> </span><span class="nx">id<span class="p">, </span><span class="nx">GroupMemberEntityIdsState</span><span class="p">? </span><span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        <span id="state_exclusive_csharp">
<a href="#state_exclusive_csharp" style="color: inherit; text-decoration: inherit;">Exclusive</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Defaults to `true`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_groupid_csharp">
<a href="#state_groupid_csharp" style="color: inherit; text-decoration: inherit;">Group<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Group ID to assign member entities to.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_groupname_csharp">
<a href="#state_groupname_csharp" style="color: inherit; text-decoration: inherit;">Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the group that are assigned the member entities.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_memberentityids_csharp">
<a href="#state_memberentityids_csharp" style="color: inherit; text-decoration: inherit;">Member<wbr>Entity<wbr>Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}List of member entities that belong to the group
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_exclusive_go">
<a href="#state_exclusive_go" style="color: inherit; text-decoration: inherit;">Exclusive</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Defaults to `true`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_groupid_go">
<a href="#state_groupid_go" style="color: inherit; text-decoration: inherit;">Group<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Group ID to assign member entities to.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_groupname_go">
<a href="#state_groupname_go" style="color: inherit; text-decoration: inherit;">Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the group that are assigned the member entities.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_memberentityids_go">
<a href="#state_memberentityids_go" style="color: inherit; text-decoration: inherit;">Member<wbr>Entity<wbr>Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of member entities that belong to the group
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_exclusive_nodejs">
<a href="#state_exclusive_nodejs" style="color: inherit; text-decoration: inherit;">exclusive</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Defaults to `true`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_groupid_nodejs">
<a href="#state_groupid_nodejs" style="color: inherit; text-decoration: inherit;">group<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Group ID to assign member entities to.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_groupname_nodejs">
<a href="#state_groupname_nodejs" style="color: inherit; text-decoration: inherit;">group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the group that are assigned the member entities.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_memberentityids_nodejs">
<a href="#state_memberentityids_nodejs" style="color: inherit; text-decoration: inherit;">member<wbr>Entity<wbr>Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}List of member entities that belong to the group
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_exclusive_python">
<a href="#state_exclusive_python" style="color: inherit; text-decoration: inherit;">exclusive</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Defaults to `true`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_group_id_python">
<a href="#state_group_id_python" style="color: inherit; text-decoration: inherit;">group_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Group ID to assign member entities to.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_group_name_python">
<a href="#state_group_name_python" style="color: inherit; text-decoration: inherit;">group_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the group that are assigned the member entities.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_member_entity_ids_python">
<a href="#state_member_entity_ids_python" style="color: inherit; text-decoration: inherit;">member_<wbr>entity_<wbr>ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}List of member entities that belong to the group
{{% /md %}}</dd></dl>
{{% /choosable %}}







<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-vault">https://github.com/pulumi/pulumi-vault</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`vault` Terraform Provider](https://github.com/hashicorp/terraform-provider-vault).{{% /md %}}</dd>
</dl>



---
title: "getScript"
title_tag: "aws.glue.getScript"
meta_desc: "Documentation for the aws.glue.getScript function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Use this data source to generate a Glue script from a Directed Acyclic Graph (DAG).




## Using getScript {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getScript<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetScriptArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetScriptResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_script(</span><span class="nx">dag_edges</span><span class="p">:</span> <span class="nx">Optional[Sequence[GetScriptDagEdgeArgs]]</span> = None<span class="p">, </span><span class="nx">dag_nodes</span><span class="p">:</span> <span class="nx">Optional[Sequence[GetScriptDagNodeArgs]]</span> = None<span class="p">, </span><span class="nx">language</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetScriptResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetScript<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">args</span><span class="p"> *</span><span class="nx">GetScriptArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">GetScriptResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `GetScript` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetScript </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetScriptResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetScriptArgs</span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="dagedges_csharp">
<a href="#dagedges_csharp" style="color: inherit; text-decoration: inherit;">Dag<wbr>Edges</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getscriptdagedge">List&lt;Get<wbr>Script<wbr>Dag<wbr>Edge<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}A list of the edges in the DAG. Defined below.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="dagnodes_csharp">
<a href="#dagnodes_csharp" style="color: inherit; text-decoration: inherit;">Dag<wbr>Nodes</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getscriptdagnode">List&lt;Get<wbr>Script<wbr>Dag<wbr>Node<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}A list of the nodes in the DAG. Defined below.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="language_csharp">
<a href="#language_csharp" style="color: inherit; text-decoration: inherit;">Language</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The programming language of the resulting code from the DAG. Defaults to `PYTHON`. Valid values are `PYTHON` and `SCALA`.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="dagedges_go">
<a href="#dagedges_go" style="color: inherit; text-decoration: inherit;">Dag<wbr>Edges</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getscriptdagedge">[]Get<wbr>Script<wbr>Dag<wbr>Edge</a></span>
    </dt>
    <dd>{{% md %}}A list of the edges in the DAG. Defined below.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="dagnodes_go">
<a href="#dagnodes_go" style="color: inherit; text-decoration: inherit;">Dag<wbr>Nodes</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getscriptdagnode">[]Get<wbr>Script<wbr>Dag<wbr>Node</a></span>
    </dt>
    <dd>{{% md %}}A list of the nodes in the DAG. Defined below.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="language_go">
<a href="#language_go" style="color: inherit; text-decoration: inherit;">Language</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The programming language of the resulting code from the DAG. Defaults to `PYTHON`. Valid values are `PYTHON` and `SCALA`.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="dagedges_nodejs">
<a href="#dagedges_nodejs" style="color: inherit; text-decoration: inherit;">dag<wbr>Edges</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getscriptdagedge">Get<wbr>Script<wbr>Dag<wbr>Edge[]</a></span>
    </dt>
    <dd>{{% md %}}A list of the edges in the DAG. Defined below.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="dagnodes_nodejs">
<a href="#dagnodes_nodejs" style="color: inherit; text-decoration: inherit;">dag<wbr>Nodes</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getscriptdagnode">Get<wbr>Script<wbr>Dag<wbr>Node[]</a></span>
    </dt>
    <dd>{{% md %}}A list of the nodes in the DAG. Defined below.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="language_nodejs">
<a href="#language_nodejs" style="color: inherit; text-decoration: inherit;">language</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The programming language of the resulting code from the DAG. Defaults to `PYTHON`. Valid values are `PYTHON` and `SCALA`.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="dag_edges_python">
<a href="#dag_edges_python" style="color: inherit; text-decoration: inherit;">dag_<wbr>edges</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getscriptdagedge">Sequence[Get<wbr>Script<wbr>Dag<wbr>Edge<wbr>Args]</a></span>
    </dt>
    <dd>{{% md %}}A list of the edges in the DAG. Defined below.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="dag_nodes_python">
<a href="#dag_nodes_python" style="color: inherit; text-decoration: inherit;">dag_<wbr>nodes</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getscriptdagnode">Sequence[Get<wbr>Script<wbr>Dag<wbr>Node<wbr>Args]</a></span>
    </dt>
    <dd>{{% md %}}A list of the nodes in the DAG. Defined below.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="language_python">
<a href="#language_python" style="color: inherit; text-decoration: inherit;">language</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The programming language of the resulting code from the DAG. Defaults to `PYTHON`. Valid values are `PYTHON` and `SCALA`.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getScript Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="dagedges_csharp">
<a href="#dagedges_csharp" style="color: inherit; text-decoration: inherit;">Dag<wbr>Edges</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getscriptdagedge">List&lt;Get<wbr>Script<wbr>Dag<wbr>Edge&gt;</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="dagnodes_csharp">
<a href="#dagnodes_csharp" style="color: inherit; text-decoration: inherit;">Dag<wbr>Nodes</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getscriptdagnode">List&lt;Get<wbr>Script<wbr>Dag<wbr>Node&gt;</a></span>
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
        <span id="pythonscript_csharp">
<a href="#pythonscript_csharp" style="color: inherit; text-decoration: inherit;">Python<wbr>Script</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Python script generated from the DAG when the `language` argument is set to `PYTHON`.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="scalacode_csharp">
<a href="#scalacode_csharp" style="color: inherit; text-decoration: inherit;">Scala<wbr>Code</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Scala code generated from the DAG when the `language` argument is set to `SCALA`.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="language_csharp">
<a href="#language_csharp" style="color: inherit; text-decoration: inherit;">Language</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="dagedges_go">
<a href="#dagedges_go" style="color: inherit; text-decoration: inherit;">Dag<wbr>Edges</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getscriptdagedge">[]Get<wbr>Script<wbr>Dag<wbr>Edge</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="dagnodes_go">
<a href="#dagnodes_go" style="color: inherit; text-decoration: inherit;">Dag<wbr>Nodes</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getscriptdagnode">[]Get<wbr>Script<wbr>Dag<wbr>Node</a></span>
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
        <span id="pythonscript_go">
<a href="#pythonscript_go" style="color: inherit; text-decoration: inherit;">Python<wbr>Script</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Python script generated from the DAG when the `language` argument is set to `PYTHON`.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="scalacode_go">
<a href="#scalacode_go" style="color: inherit; text-decoration: inherit;">Scala<wbr>Code</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Scala code generated from the DAG when the `language` argument is set to `SCALA`.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="language_go">
<a href="#language_go" style="color: inherit; text-decoration: inherit;">Language</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="dagedges_nodejs">
<a href="#dagedges_nodejs" style="color: inherit; text-decoration: inherit;">dag<wbr>Edges</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getscriptdagedge">Get<wbr>Script<wbr>Dag<wbr>Edge[]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="dagnodes_nodejs">
<a href="#dagnodes_nodejs" style="color: inherit; text-decoration: inherit;">dag<wbr>Nodes</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getscriptdagnode">Get<wbr>Script<wbr>Dag<wbr>Node[]</a></span>
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
        <span id="pythonscript_nodejs">
<a href="#pythonscript_nodejs" style="color: inherit; text-decoration: inherit;">python<wbr>Script</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Python script generated from the DAG when the `language` argument is set to `PYTHON`.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="scalacode_nodejs">
<a href="#scalacode_nodejs" style="color: inherit; text-decoration: inherit;">scala<wbr>Code</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Scala code generated from the DAG when the `language` argument is set to `SCALA`.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="language_nodejs">
<a href="#language_nodejs" style="color: inherit; text-decoration: inherit;">language</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="dag_edges_python">
<a href="#dag_edges_python" style="color: inherit; text-decoration: inherit;">dag_<wbr>edges</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getscriptdagedge">Sequence[Get<wbr>Script<wbr>Dag<wbr>Edge]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="dag_nodes_python">
<a href="#dag_nodes_python" style="color: inherit; text-decoration: inherit;">dag_<wbr>nodes</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getscriptdagnode">Sequence[Get<wbr>Script<wbr>Dag<wbr>Node]</a></span>
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
        <span id="python_script_python">
<a href="#python_script_python" style="color: inherit; text-decoration: inherit;">python_<wbr>script</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Python script generated from the DAG when the `language` argument is set to `PYTHON`.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="scala_code_python">
<a href="#scala_code_python" style="color: inherit; text-decoration: inherit;">scala_<wbr>code</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Scala code generated from the DAG when the `language` argument is set to `SCALA`.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="language_python">
<a href="#language_python" style="color: inherit; text-decoration: inherit;">language</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}




## Supporting Types


<h4 id="getscriptdagedge">Get<wbr>Script<wbr>Dag<wbr>Edge</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="source_csharp">
<a href="#source_csharp" style="color: inherit; text-decoration: inherit;">Source</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the node at which the edge starts.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="target_csharp">
<a href="#target_csharp" style="color: inherit; text-decoration: inherit;">Target</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the node at which the edge ends.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="targetparameter_csharp">
<a href="#targetparameter_csharp" style="color: inherit; text-decoration: inherit;">Target<wbr>Parameter</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The target of the edge.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="source_go">
<a href="#source_go" style="color: inherit; text-decoration: inherit;">Source</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the node at which the edge starts.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="target_go">
<a href="#target_go" style="color: inherit; text-decoration: inherit;">Target</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the node at which the edge ends.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="targetparameter_go">
<a href="#targetparameter_go" style="color: inherit; text-decoration: inherit;">Target<wbr>Parameter</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The target of the edge.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="source_nodejs">
<a href="#source_nodejs" style="color: inherit; text-decoration: inherit;">source</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the node at which the edge starts.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="target_nodejs">
<a href="#target_nodejs" style="color: inherit; text-decoration: inherit;">target</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the node at which the edge ends.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="targetparameter_nodejs">
<a href="#targetparameter_nodejs" style="color: inherit; text-decoration: inherit;">target<wbr>Parameter</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The target of the edge.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="source_python">
<a href="#source_python" style="color: inherit; text-decoration: inherit;">source</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the node at which the edge starts.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="target_python">
<a href="#target_python" style="color: inherit; text-decoration: inherit;">target</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the node at which the edge ends.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="target_parameter_python">
<a href="#target_parameter_python" style="color: inherit; text-decoration: inherit;">target_<wbr>parameter</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The target of the edge.
{{% /md %}}</dd></dl>
{{% /choosable %}}

<h4 id="getscriptdagnode">Get<wbr>Script<wbr>Dag<wbr>Node</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="args_csharp">
<a href="#args_csharp" style="color: inherit; text-decoration: inherit;">Args</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getscriptdagnodearg">List&lt;Get<wbr>Script<wbr>Dag<wbr>Node<wbr>Arg<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}Nested configuration an argument or property of a node. Defined below.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="id_csharp">
<a href="#id_csharp" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A node identifier that is unique within the node's graph.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="nodetype_csharp">
<a href="#nodetype_csharp" style="color: inherit; text-decoration: inherit;">Node<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of node this is.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="linenumber_csharp">
<a href="#linenumber_csharp" style="color: inherit; text-decoration: inherit;">Line<wbr>Number</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The line number of the node.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="args_go">
<a href="#args_go" style="color: inherit; text-decoration: inherit;">Args</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getscriptdagnodearg">[]Get<wbr>Script<wbr>Dag<wbr>Node<wbr>Arg</a></span>
    </dt>
    <dd>{{% md %}}Nested configuration an argument or property of a node. Defined below.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="id_go">
<a href="#id_go" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A node identifier that is unique within the node's graph.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="nodetype_go">
<a href="#nodetype_go" style="color: inherit; text-decoration: inherit;">Node<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of node this is.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="linenumber_go">
<a href="#linenumber_go" style="color: inherit; text-decoration: inherit;">Line<wbr>Number</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The line number of the node.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="args_nodejs">
<a href="#args_nodejs" style="color: inherit; text-decoration: inherit;">args</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getscriptdagnodearg">Get<wbr>Script<wbr>Dag<wbr>Node<wbr>Arg[]</a></span>
    </dt>
    <dd>{{% md %}}Nested configuration an argument or property of a node. Defined below.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="id_nodejs">
<a href="#id_nodejs" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A node identifier that is unique within the node's graph.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="nodetype_nodejs">
<a href="#nodetype_nodejs" style="color: inherit; text-decoration: inherit;">node<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of node this is.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="linenumber_nodejs">
<a href="#linenumber_nodejs" style="color: inherit; text-decoration: inherit;">line<wbr>Number</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The line number of the node.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="args_python">
<a href="#args_python" style="color: inherit; text-decoration: inherit;">args</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getscriptdagnodearg">Sequence[Get<wbr>Script<wbr>Dag<wbr>Node<wbr>Arg<wbr>Args]</a></span>
    </dt>
    <dd>{{% md %}}Nested configuration an argument or property of a node. Defined below.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="id_python">
<a href="#id_python" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A node identifier that is unique within the node's graph.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="node_type_python">
<a href="#node_type_python" style="color: inherit; text-decoration: inherit;">node_<wbr>type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of node this is.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="line_number_python">
<a href="#line_number_python" style="color: inherit; text-decoration: inherit;">line_<wbr>number</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The line number of the node.
{{% /md %}}</dd></dl>
{{% /choosable %}}

<h4 id="getscriptdagnodearg">Get<wbr>Script<wbr>Dag<wbr>Node<wbr>Arg</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the argument or property.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="value_csharp">
<a href="#value_csharp" style="color: inherit; text-decoration: inherit;">Value</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The value of the argument or property.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="param_csharp">
<a href="#param_csharp" style="color: inherit; text-decoration: inherit;">Param</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean if the value is used as a parameter. Defaults to `false`.
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
    <dd>{{% md %}}The name of the argument or property.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="value_go">
<a href="#value_go" style="color: inherit; text-decoration: inherit;">Value</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The value of the argument or property.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="param_go">
<a href="#param_go" style="color: inherit; text-decoration: inherit;">Param</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean if the value is used as a parameter. Defaults to `false`.
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
    <dd>{{% md %}}The name of the argument or property.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="value_nodejs">
<a href="#value_nodejs" style="color: inherit; text-decoration: inherit;">value</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The value of the argument or property.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="param_nodejs">
<a href="#param_nodejs" style="color: inherit; text-decoration: inherit;">param</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Boolean if the value is used as a parameter. Defaults to `false`.
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
    <dd>{{% md %}}The name of the argument or property.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="value_python">
<a href="#value_python" style="color: inherit; text-decoration: inherit;">value</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The value of the argument or property.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="param_python">
<a href="#param_python" style="color: inherit; text-decoration: inherit;">param</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean if the value is used as a parameter. Defaults to `false`.
{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-aws">https://github.com/pulumi/pulumi-aws</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`aws` Terraform Provider](https://github.com/terraform-providers/terraform-provider-aws).{{% /md %}}</dd>
</dl>


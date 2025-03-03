
---
title: "getTestResultFile"
title_tag: "azure-native.insights.getTestResultFile"
meta_desc: "Documentation for the azure-native.insights.getTestResultFile function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Test result.
API Version: 2020-02-10-preview.




## Using getTestResultFile {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getTestResultFile<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetTestResultFileArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetTestResultFileResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_test_result_file(</span><span class="nx">continuation_token</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">download_as</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">geo_location_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">resource_group_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">test_successful_criteria</span><span class="p">:</span> <span class="nx">Optional[bool]</span> = None<span class="p">, </span><span class="nx">time_stamp</span><span class="p">:</span> <span class="nx">Optional[int]</span> = None<span class="p">, </span><span class="nx">web_test_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetTestResultFileResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetTestResultFile<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">args</span><span class="p"> *</span><span class="nx">GetTestResultFileArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">GetTestResultFileResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `GetTestResultFile` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetTestResultFile </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetTestResultFileResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetTestResultFileArgs</span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="downloadas_csharp">
<a href="#downloadas_csharp" style="color: inherit; text-decoration: inherit;">Download<wbr>As</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The format to use when returning the webtest result.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="geolocationid_csharp">
<a href="#geolocationid_csharp" style="color: inherit; text-decoration: inherit;">Geo<wbr>Location<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The location ID where the webtest was physically run.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_csharp">
<a href="#resourcegroupname_csharp" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource group. The name is case insensitive.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="timestamp_csharp">
<a href="#timestamp_csharp" style="color: inherit; text-decoration: inherit;">Time<wbr>Stamp</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The posix (epoch) time stamp for the webtest result.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="webtestname_csharp">
<a href="#webtestname_csharp" style="color: inherit; text-decoration: inherit;">Web<wbr>Test<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Application Insights webtest resource.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="continuationtoken_csharp">
<a href="#continuationtoken_csharp" style="color: inherit; text-decoration: inherit;">Continuation<wbr>Token</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The continuation token.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="testsuccessfulcriteria_csharp">
<a href="#testsuccessfulcriteria_csharp" style="color: inherit; text-decoration: inherit;">Test<wbr>Successful<wbr>Criteria</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}The success state criteria for the webtest result.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="downloadas_go">
<a href="#downloadas_go" style="color: inherit; text-decoration: inherit;">Download<wbr>As</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The format to use when returning the webtest result.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="geolocationid_go">
<a href="#geolocationid_go" style="color: inherit; text-decoration: inherit;">Geo<wbr>Location<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The location ID where the webtest was physically run.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_go">
<a href="#resourcegroupname_go" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource group. The name is case insensitive.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="timestamp_go">
<a href="#timestamp_go" style="color: inherit; text-decoration: inherit;">Time<wbr>Stamp</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The posix (epoch) time stamp for the webtest result.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="webtestname_go">
<a href="#webtestname_go" style="color: inherit; text-decoration: inherit;">Web<wbr>Test<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Application Insights webtest resource.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="continuationtoken_go">
<a href="#continuationtoken_go" style="color: inherit; text-decoration: inherit;">Continuation<wbr>Token</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The continuation token.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="testsuccessfulcriteria_go">
<a href="#testsuccessfulcriteria_go" style="color: inherit; text-decoration: inherit;">Test<wbr>Successful<wbr>Criteria</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}The success state criteria for the webtest result.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="downloadas_nodejs">
<a href="#downloadas_nodejs" style="color: inherit; text-decoration: inherit;">download<wbr>As</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The format to use when returning the webtest result.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="geolocationid_nodejs">
<a href="#geolocationid_nodejs" style="color: inherit; text-decoration: inherit;">geo<wbr>Location<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The location ID where the webtest was physically run.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_nodejs">
<a href="#resourcegroupname_nodejs" style="color: inherit; text-decoration: inherit;">resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource group. The name is case insensitive.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="timestamp_nodejs">
<a href="#timestamp_nodejs" style="color: inherit; text-decoration: inherit;">time<wbr>Stamp</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The posix (epoch) time stamp for the webtest result.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="webtestname_nodejs">
<a href="#webtestname_nodejs" style="color: inherit; text-decoration: inherit;">web<wbr>Test<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Application Insights webtest resource.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="continuationtoken_nodejs">
<a href="#continuationtoken_nodejs" style="color: inherit; text-decoration: inherit;">continuation<wbr>Token</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The continuation token.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="testsuccessfulcriteria_nodejs">
<a href="#testsuccessfulcriteria_nodejs" style="color: inherit; text-decoration: inherit;">test<wbr>Successful<wbr>Criteria</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}The success state criteria for the webtest result.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="download_as_python">
<a href="#download_as_python" style="color: inherit; text-decoration: inherit;">download_<wbr>as</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The format to use when returning the webtest result.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="geo_location_id_python">
<a href="#geo_location_id_python" style="color: inherit; text-decoration: inherit;">geo_<wbr>location_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The location ID where the webtest was physically run.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resource_group_name_python">
<a href="#resource_group_name_python" style="color: inherit; text-decoration: inherit;">resource_<wbr>group_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the resource group. The name is case insensitive.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="time_stamp_python">
<a href="#time_stamp_python" style="color: inherit; text-decoration: inherit;">time_<wbr>stamp</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The posix (epoch) time stamp for the webtest result.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="web_test_name_python">
<a href="#web_test_name_python" style="color: inherit; text-decoration: inherit;">web_<wbr>test_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Application Insights webtest resource.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="continuation_token_python">
<a href="#continuation_token_python" style="color: inherit; text-decoration: inherit;">continuation_<wbr>token</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The continuation token.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="test_successful_criteria_python">
<a href="#test_successful_criteria_python" style="color: inherit; text-decoration: inherit;">test_<wbr>successful_<wbr>criteria</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}The success state criteria for the webtest result.{{% /md %}}</dd></dl>
{{% /choosable %}}




## getTestResultFile Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="data_csharp">
<a href="#data_csharp" style="color: inherit; text-decoration: inherit;">Data</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}File contents.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="nextlink_csharp">
<a href="#nextlink_csharp" style="color: inherit; text-decoration: inherit;">Next<wbr>Link</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The URI that can be used to request the next section of the result file in the event the file is too large for a single request.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="data_go">
<a href="#data_go" style="color: inherit; text-decoration: inherit;">Data</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}File contents.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="nextlink_go">
<a href="#nextlink_go" style="color: inherit; text-decoration: inherit;">Next<wbr>Link</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The URI that can be used to request the next section of the result file in the event the file is too large for a single request.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="data_nodejs">
<a href="#data_nodejs" style="color: inherit; text-decoration: inherit;">data</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}File contents.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="nextlink_nodejs">
<a href="#nextlink_nodejs" style="color: inherit; text-decoration: inherit;">next<wbr>Link</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The URI that can be used to request the next section of the result file in the event the file is too large for a single request.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="data_python">
<a href="#data_python" style="color: inherit; text-decoration: inherit;">data</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}File contents.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="next_link_python">
<a href="#next_link_python" style="color: inherit; text-decoration: inherit;">next_<wbr>link</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The URI that can be used to request the next section of the result file in the event the file is too large for a single request.{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-azure-native">https://github.com/pulumi/pulumi-azure-native</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
</dl>


## Get feed of all stages

```shell
$ curl 'https://ci.example.com/go/api/pipelines/mypipeline/stages.xml' \
      -u 'username:password'
```

> The above command returns XML structured like this:

```http
HTTP/1.1 200 OK
Content-Type: application/xml; charset=utf-8
```

```xml
<feed xmlns="http://www.w3.org/2005/Atom" xmlns:go="http://www.thoughtworks-studios.com/ns/go">
    <title><![CDATA[mypipeline]]></title>
    <id>https://ci.example.com/go/api/pipelines/mypipeline/stages.xml</id>
    <author>
        <name>Go</name>
    </author>
    <updated>2015-07-13T10:59:49+05:30</updated>
    <link rel="self" href="https://ci.example.com/go/api/pipelines/mypipeline/stages.xml"/>
        <link rel="next" href="https://ci.example.com/go/api/pipelines/mypipeline/stages.xml?before=6"/>

        <entry>
            <title><![CDATA[mypipeline(2) stage defaultStage(1) Cancelled]]></title>
            <updated>2015-07-10T12:00:04+05:30</updated>
            <id>https://ci.example.com/go/pipelines/mypipeline/2/defaultStage/1</id>

            <author>
                <name><![CDATA[Pick E Reader <pick.e.reader@example.com>]]></name>
            </author>

            <link title="defaultStage Stage Detail" href="https://ci.example.com/go/api/stages/2.xml" rel="alternate" type="application/vnd.go+xml"/>
            <link title="defaultStage Stage Detail" href="https://ci.example.com/go/pipelines/mypipeline/2/defaultStage/1" rel="alternate" type="text/html"/>
            <link title="mypipeline Pipeline Detail" href="https://ci.example.com/go/api/pipelines/mypipeline/2.xml" rel="http://www.thoughtworks-studios.com/ns/relations/go/pipeline" type="application/vnd.go+xml"/>
            <link title="mypipeline Pipeline Detail" href="https://ci.example.com/go/pipelines/mypipeline/2/defaultStage/1/pipeline" rel="http://www.thoughtworks-studios.com/ns/relations/go/pipeline" type="text/html"/>

            <category scheme="http://www.thoughtworks-studios.com/ns/categories/go" term="stage" label="Stage" />
            <category scheme="http://www.thoughtworks-studios.com/ns/categories/go" term="completed" label="Completed" />
            <category scheme="http://www.thoughtworks-studios.com/ns/categories/go" term="cancelled" label="Cancelled" />
        </entry>
        <entry>
            <title><![CDATA[mypipeline(1) stage defaultStage(1) Passed]]></title>
            <updated>2015-07-10T11:57:22+05:30</updated>
            <id>https://ci.example.com/go/pipelines/mypipeline/1/defaultStage/1</id>

            <author>
                <name><![CDATA[Pick E Reader <pick.e.reader@example.com>]]></name>
            </author>

            <link title="defaultStage Stage Detail" href="https://ci.example.com/go/api/stages/1.xml" rel="alternate" type="application/vnd.go+xml"/>
            <link title="defaultStage Stage Detail" href="https://ci.example.com/go/pipelines/mypipeline/1/defaultStage/1" rel="alternate" type="text/html"/>
            <link title="mypipeline Pipeline Detail" href="https://ci.example.com/go/api/pipelines/mypipeline/1.xml" rel="http://www.thoughtworks-studios.com/ns/relations/go/pipeline" type="application/vnd.go+xml"/>
            <link title="mypipeline Pipeline Detail" href="https://ci.example.com/go/pipelines/mypipeline/1/defaultStage/1/pipeline" rel="http://www.thoughtworks-studios.com/ns/relations/go/pipeline" type="text/html"/>

            <category scheme="http://www.thoughtworks-studios.com/ns/categories/go" term="stage" label="Stage" />
            <category scheme="http://www.thoughtworks-studios.com/ns/categories/go" term="completed" label="Completed" />
            <category scheme="http://www.thoughtworks-studios.com/ns/categories/go" term="passed" label="Passed" />
        </entry>
</feed>
```

Gets feed of all stages for the specified pipeline with links to the pipeline and stage details.

### HTTP Request

`GET /go/api/pipelines/:pipeline_name/stages.xml`

### Returns

An array of feed of stages.

## Get pipeline

```shell
$ curl 'https://ci.example.com/go/api/pipelines/mypipeline/1.xml' \
      -u 'username:password'
```

> The above command returns XML structured like this:

```http
HTTP/1.1 200 OK
Content-Type: application/xml; charset=utf-8
```

```xml
<pipeline name="mypipeline" counter="1" label="1">
  <link rel="self" href="https://ci.example.com/go/api/pipelines/mypipeline/1.xml"/>
  <id><![CDATA[urn:x-go.studios.thoughtworks.com:job-id:mypipeline:1]]></id>
  <scheduleTime>2015-07-10T11:55:18+05:30</scheduleTime>
  <materials>
    <material materialUri="https://ci.example.com/go/api/materials/405.xml" type="GitMaterial" url="URL: https://github.com/gocd/gocd" branch="master">
      <modifications>
        <changeset changesetUri="https://ci.example.com/go/api/materials/405/changeset/c194b49db102b705ebc13e604e490ae13ac92d96.xml">
          <user><![CDATA[Pick E Reader <pick.e.reader@example.com>]]></user>
          <checkinTime>2015-06-22T12:50:13+05:30</checkinTime>
          <revision><![CDATA[c194b49db102b705ebc13e604e490ae13ac92d96]]></revision>
          <message><![CDATA[Update README]]></message>
          <file name="README" action="modified"/>
        </changeset>
      </modifications>
    </material>
  </materials>
  <stages>
    <stage href="https://ci.example.com/go/api/stages/1.xml"/>
  </stages>
  <approvedBy><![CDATA[changes]]></approvedBy>
</pipeline>
```

Gets XML representation of pipeline.

### HTTP Request

`GET /go/api/pipelines/:pipeline_name/:pipeline_id.xml`

### Returns

A pipeline object.

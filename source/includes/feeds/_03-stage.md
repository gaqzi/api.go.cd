## Get stage

```shell
$ curl 'https://ci.example.com/go/api/stages/2.xml' \
      -u 'username:password'
```

> The above command returns XML structured like this:

```http
HTTP/1.1 200 OK
Content-Type: application/xml; charset=utf-8
```

```xml
<stage name="defaultStage" counter="1">
  <link rel="self" href="https://ci.example.com/go/api/stages/2.xml"/>
  <id><![CDATA[urn:x-go.studios.thoughtworks.com:stage-id:mypipeline:2:defaultStage:1]]></id>
  <pipeline name="mypipeline" counter="2" label="2" href="https://ci.example.com/go/api/pipelines/mypipeline/2.xml"/>
  <updated>2015-07-10T12:00:04+05:30</updated>
  <result>Cancelled</result>
  <state>Completed</state>
  <approvedBy><![CDATA[admin]]></approvedBy>
  <jobs>
    <job href="https://ci.example.com/go/api/jobs/2.xml"/>
  </jobs>
</stage>
```

Gets XML representation of stage.

### HTTP Request

`GET /go/api/stages/:stage_id.xml`

**Alternate APIs**

`GET /go/pipelines/:pipeline:name/:pipeline_counter/:stage_name/:stage_counter.xml`

 or

`GET /go/pipelines/:pipeline:name/:pipeline_label/:stage_name/:stage_counter.xml`


### Returns

A stage object.

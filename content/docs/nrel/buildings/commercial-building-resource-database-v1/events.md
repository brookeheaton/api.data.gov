---
title: Commercial Building Resource Events
summary: Upcoming and/or past events added to the Commercial Building Resource Database.
url: GET /api/commercial-building-resources/v1/events
disqus: true

---

# {{title}} <span class="url">({{url}})</span>
{{summary}}

<ul id="toc"></ul>

## Request URL

<pre>GET /api/commercial-building-resources/events<em>.format?parameters</em></pre>

## Request Parameters

<table border="0" cellpadding="0" cellspacing="0" class="doc-parameters">
  <thead>
    <tr>
      <th class="doc-parameters-name" scope="col">Parameter</th>
      <th class="doc-parameters-required" scope="col">Required</th>
      <th class="doc-parameters-value" scope="col">Value</th>
      <th class="doc-parameters-description" scope="col">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th class="doc-parameter-name" scope="row">format</th>
      <td class="doc-parameter-required">Yes</td>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> string
        </div>
        <div class="doc-parameter-value-field">
          <strong>Default:</strong> None
        </div>
        <div class="doc-parameter-value-field">
          <strong>Options:</strong> <em>json</em>, <em>jsonp</em>, <em>xml</em>
        </div>
      </td>
      <td class="doc-parameter-description">
        <p>The output response format. Jsonp format is identical to json format, with the addition that it supports the callback parameter for jsonp requests.</p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">api_key</th>
      <td class="doc-parameter-required">Yes</td>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> string
        </div>
        <div class="doc-parameter-value-field">
          <strong>Default:</strong> None
        </div>
      </td>
      <td class="doc-parameter-description">
        <p>Your developer API key. See <a href="/docs/api-key/">API keys</a> for more information.</p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">portal</th>
      <td class="doc-parameter-required">No</td>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> integer
        </div>
        <div class="doc-parameter-value-field">
          <strong>Default:</strong> None
        </div>
      </td>
      <td class="doc-parameter-description">
        <p>Unique integer representing the term from the Portal vocabulary <span>to filter results on.</span></p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">scope</th>
      <td class="doc-parameter-required">No</td>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> string
        </div>
        <div class="doc-parameter-value-field">
          <strong>Default:</strong> None
        </div>
        <div class="doc-parameter-value-field">
          <strong>Options:</strong> <em>upcoming</em>, <em>past</em>
        </div>
      </td>
      <td class="doc-parameter-description">
        <p>List events relative to current Date and Time.</p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">callback</th>
      <td class="doc-parameter-required">No</td>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> string
        </div>
        <div class="doc-parameter-value-field">
          <strong>Default:</strong> None
        </div>
      </td>
      <td class="doc-parameter-description">
        <p>For jsonp format, the callback parameter is used to support jsonp requests.</p>
      </td>
    </tr>
  </tbody>
</table>

## Response Fields

*The top-level structure of response is different for JSON vs XML format requests. The XML format responds with a single array **result** of resource items. The JSON format responds with a hash. Each key in the JSON response hash is a nid value, and each value is a resource item. The fields for individual resource items are consistent for JSON and XML format, and described below. For more specfics, see Examples below.*

### Resource Response Fields

<table border="0" cellpadding="0" cellspacing="0" class="doc-parameters">
  <thead>
    <tr>
      <th class="doc-parameters-name" scope="col">Field</th>
      <th class="doc-parameters-value" scope="col">Value</th>
      <th class="doc-parameters-description" scope="col">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th class="doc-parameter-name" scope="row">vid</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> integer
        </div>
        <div class="doc-parameter-value-field"></div>
      </td>
      <td class="doc-parameter-description">
        <p>Version ID of resource. If a new version of the resouce is published, the vid will change while the nid is constant.</p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">title</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> string
        </div>
      </td>
      <td class="doc-parameter-description">
        <p>Title text.</p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">nid</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> integer
        </div>
      </td>
      <td class="doc-parameter-description">
        <p>Unique integer identifier for resource. This does not change when new versions are published (see vid).</p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">created</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> integer
        </div>
      </td>
      <td class="doc-parameter-description">
        <p>Timestamp when resource was created in Unix epoch time.</p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">changed</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> integer
        </div>
      </td>
      <td class="doc-parameter-description">
        <p>Timestamp when resource was last updated in Unix epoch time.</p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">rdf_mapping</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> object
        </div>
      </td>
      <td class="doc-parameter-description">
        <p>Resource Description Framework (RDF) metadata.</p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">body</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> array
        </div>
      </td>
      <td class="doc-parameter-description">
        <p>Array of objects containing copy for resource. See Body Response Fields.</p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">field_event_type</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> object
        </div>
      </td>
      <td class="doc-parameter-description">
        <p><span>Applicable only for Event content (see type). Array containing exactly one term.</span> See Term Response Fields.</p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">field_collections</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> object
        </div>
      </td>
      <td class="doc-parameter-description">
        <p><span>Array of terms in the Vocabulary. See Term Response Fields.</span></p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">field_topics</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> object
        </div>
      </td>
      <td class="doc-parameter-description">
        <p><span>Array of terms in the Vocabulary. See Term Response Fields.</span></p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">field_construction_types</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> object
        </div>
      </td>
      <td class="doc-parameter-description">
        <p><span>Array of terms in the Vocabulary. See Term Response Fields.</span></p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">field_building_types</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> object
        </div>
      </td>
      <td class="doc-parameter-description">
        <p><span>Array of terms in the Vocabulary. See Term Response Fields.</span></p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">field_phases_of_delivery</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> object
        </div>
      </td>
      <td class="doc-parameter-description">
        <p><span>Array of terms in the Vocabulary. See Term Response Fields.</span></p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">field_audience_types</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> object
        </div>
      </td>
      <td class="doc-parameter-description">
        <p><span>Array of terms in the Vocabulary. See Term Response Fields.</span></p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">field_keywords</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> object
        </div>
      </td>
      <td class="doc-parameter-description">
        <p><span>Array of terms in the Vocabulary. See Term Response Fields.</span></p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">field_event_date</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> object
        </div>
      </td>
      <td class="doc-parameter-description">
        <p>The start and end time of Event. See DateTime Response Fields.</p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">field_location</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> object
        </div>
      </td>
      <td class="doc-parameter-description">
        <p>See Location Response fields.</p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">field_location_alternative</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> string
        </div>
      </td>
      <td class="doc-parameter-description">
        <p>Simple string description of location, provided when full Location cannot be.</p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">field_sponsor_name</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> string
        </div>
      </td>
      <td class="doc-parameter-description">
        <p>Name of Event sponsor (if available).</p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">field_website_url</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> string
        </div>
      </td>
      <td class="doc-parameter-description">
        <p>Url of event website, if available.</p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">field_logo</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> string
        </div>
      </td>
      <td class="doc-parameter-description">
        <p>Url of logo for Event sponsor, if available.</p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">field_registration_url</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> string
        </div>
      </td>
      <td class="doc-parameter-description">
        <p>Url to register for Event, if available.</p>
      </td>
    </tr>
  </tbody>
</table>

### Body Response Fields

<table border="0" cellpadding="0" cellspacing="0" class="doc-parameters">
  <thead>
    <tr>
      <th class="doc-parameters-name" scope="col">Field</th>
      <th class="doc-parameters-value" scope="col">Value</th>
      <th class="doc-parameters-description" scope="col">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th class="doc-parameter-name" scope="row">value</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> string
        </div>
        <div class="doc-parameter-value-field"></div>
      </td>
      <td class="doc-parameter-description">
        <p>Text for resource body without html tags.</p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">summary</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> string
        </div>
      </td>
      <td class="doc-parameter-description">
        <p>Text for resource summary without html tags.</p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">safe_value</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> string
        </div>
        <div class="doc-parameter-value-field"></div>
      </td>
      <td class="doc-parameter-description">
        <p>Text for Resource body with escaped html tags.</p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">safe_summary</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> string
        </div>
        <div class="doc-parameter-value-field"></div>
      </td>
      <td class="doc-parameter-description">
        <p>Text for Resource summary with escaped html tags.</p>
      </td>
    </tr>
  </tbody>
</table>

### Term Response Fields

<table border="0" cellpadding="0" cellspacing="0" class="doc-parameters">
  <thead>
    <tr>
      <th class="doc-parameters-name" scope="col">Field</th>
      <th class="doc-parameters-value" scope="col">Value</th>
      <th class="doc-parameters-description" scope="col">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th class="doc-parameter-name" scope="row">tid</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> integer
        </div>
        <div class="doc-parameter-value-field"></div>
      </td>
      <td class="doc-parameter-description">
        <p>Unique id of the vocabulary term.</p>
      </td>
    </tr>
  </tbody>
</table>

### DateTime Response Fields

<table border="0" cellpadding="0" cellspacing="0" class="doc-parameters">
  <thead>
    <tr>
      <th class="doc-parameters-name" scope="col">Field</th>
      <th class="doc-parameters-value" scope="col">Value</th>
      <th class="doc-parameters-description" scope="col">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th class="doc-parameter-name" scope="row">value</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> DateTime
        </div>
        <div class="doc-parameter-value-field"></div>
      </td>
      <td class="doc-parameter-description">
        <p>The start date and time of Event, in timezone.</p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">value2</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> DateTime
        </div>
        <div class="doc-parameter-value-field"></div>
      </td>
      <td class="doc-parameter-description">
        <p>The end date and time of Event, in timezone.</p>
      </td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">timezone</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> String
        </div>
        <div class="doc-parameter-value-field"></div>
      </td>
      <td class="doc-parameter-description">
        <p>The timezone of the event.</p>
      </td>
    </tr>
  </tbody>
</table>

### Location Response Fields

<table border="0" cellpadding="0" cellspacing="0" class="doc-parameters">
  <thead>
    <tr>
      <th class="doc-parameters-name" scope="col">Field</th>
      <th class="doc-parameters-value" scope="col">Value</th>
      <th class="doc-parameters-description" scope="col">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th class="doc-parameter-name" scope="row">Country</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> string
        </div>
        <div class="doc-parameter-value-field"></div>
      </td>
      <td class="doc-parameter-description"></td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">Locality</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> string
        </div>
        <div class="doc-parameter-value-field"></div>
      </td>
      <td class="doc-parameter-description"></td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">Postal Code</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> integer
        </div>
        <div class="doc-parameter-value-field"></div>
      </td>
      <td class="doc-parameter-description"></td>
    </tr>
    <tr>
      <th class="doc-parameter-name" scope="row">Premise</th>
      <td class="doc-parameter-value">
        <div class="doc-parameter-value-field">
          <strong>Type:</strong> string
        </div>
        <div class="doc-parameter-value-field"></div>
      </td>
      <td class="doc-parameter-description"></td>
    </tr>
  </tbody>
</table>

## Examples

### JSON Output Format

<pre>GET <a href="http://api.data.gov/nrel/commercial-building-resources/v1/events.json?portal=6&amp;api_key=DEMO_KEY">/api/commercial-building-resources/v1/events.json?portal=6&amp;api_key=DEMO_KEY</a></pre>

```json
{
  "18":{
    "vid":"51",
    "title":"Wireless Metering Challenge Webinar",
    "nid":"18",
    "created":"1366404303",
    "changed":"1371062531",
    "rdf_mapping":{
      "rdftype":[
        "sioc:Item",
        "foaf:Document"
      ],
      "title":{
        "predicates":[
          "dc:title"
        ]
      },
      "created":{
        "predicates":[
          "dc:date",
          "dc:created"
        ],
        "datatype":"xsd:dateTime",
        "callback":"date_iso8601"
      },
      "changed":{
        "predicates":[
          "dc:modified"
        ],
        "datatype":"xsd:dateTime",
        "callback":"date_iso8601"
      },
      "body":{
        "predicates":[
          "content:encoded"
        ]
      },
      "uid":{
        "predicates":[
          "sioc:has_creator"
        ],
        "type":"rel"
      },
      "name":{
        "predicates":[
          "foaf:name"
        ]
      },
      "comment_count":{
        "predicates":[
          "sioc:num_replies"
        ],
        "datatype":"xsd:integer"
      },
      "last_activity":{
        "predicates":[
          "sioc:last_activity_date"
        ],
        "datatype":"xsd:dateTime",
        "callback":"date_iso8601"
      }
    },
    "body":{
      "und":[
        {
          "value":"<strong>Time:</strong> Tuesday, April 30, 2013, 2:00-4:00 p.m. ET/11:00 a.m.-1:00 p.m. PT\r\n\r\n<strong>Presenter: </strong>The Department of Energy\u2019s Building Technologies Office\r\n\r\n<strong>Overview: </strong>The U.S. Department of Energy\u2019s Building Technologies Office announced plans to issue a new <A HREF=\"http://www1.eere.energy.gov/buildings/commercial/bba_wireless_metering.html\">Wireless Metering Challenge</A> to spur the development of low cost electric metering devices that can serve growing interest in panel level sub metering being seen throughout the commercial sector. \r\n\r\nKey features of the challenge specification include a low cost target, essential requirements for electrical energy measurement, and wireless data transmission to an onsite collection point. Draft specifications for the wireless metering device are now <A HREF=\"http://apps1.eere.energy.gov/buildings/publications/pdfs/alliances/wireless_energy_meter_specification_draft.pdf\">available for review</A>. \r\n\r\nBuilding owners, managers, manufacturers and other interested parties are invited to <A HREF=\"http://apps1.eere.energy.gov/buildings/publications/pdfs/alliances/wireless_energy_meter_specification_draft.pdf\">review and comment</A> on the draft specification by April 23, 2013. All comments and feedback should be submitted to wireless.meter@ee.doe.gov. The specification will be revised based on stakeholder feedback. \r\n\r\nThis webinar will present the revised specification and address any further questions.\r\n\r\n<strong>Target Audience:</strong> The primary audience for this webinar is the commercial sector, manufacturers and federal agencies. \r\n\r\n",
          "summary":"",
          "format":"filtered_html",
          "safe_value":"<p><strong>Time:</strong> Tuesday, April 30, 2013, 2:00-4:00 p.m. ET/11:00 a.m.-1:00 p.m. PT</p>\n<p><strong>Presenter: </strong>The Department of Energy\u2019s Building Technologies Office</p>\n<p><strong>Overview: </strong>The U.S. Department of Energy\u2019s Building Technologies Office announced plans to issue a new <a href=\"http://www1.eere.energy.gov/buildings/commercial/bba_wireless_metering.html\">Wireless Metering Challenge</a> to spur the development of low cost electric metering devices that can serve growing interest in panel level sub metering being seen throughout the commercial sector. </p>\n<p>Key features of the challenge specification include a low cost target, essential requirements for electrical energy measurement, and wireless data transmission to an onsite collection point. Draft specifications for the wireless metering device are now <a href=\"http://apps1.eere.energy.gov/buildings/publications/pdfs/alliances/wireless_energy_meter_specification_draft.pdf\">available for review</a>. </p>\n<p>Building owners, managers, manufacturers and other interested parties are invited to <a href=\"http://apps1.eere.energy.gov/buildings/publications/pdfs/alliances/wireless_energy_meter_specification_draft.pdf\">review and comment</a> on the draft specification by April 23, 2013. All comments and feedback should be submitted to <a href=\"mailto:wireless.meter@ee.doe.gov\">wireless.meter@ee.doe.gov</a>. The specification will be revised based on stakeholder feedback. </p>\n<p>This webinar will present the revised specification and address any further questions.</p>\n<p><strong>Target Audience:</strong> The primary audience for this webinar is the commercial sector, manufacturers and federal agencies.</p>\n",
          "safe_summary":""
        }
      ]
    },
    "field_event_type":{
      "und":[
        {
          "tid":"1"
        }
      ]
    },
    "field_collections":[

    ],
    "field_portal_tags":{
      "und":[
        {
          "tid":"6"
        }
      ]
    },
    "field_topics":{
      "und":[
        {
          "tid":"29"
        },
        {
          "tid":"32"
        },
        {
          "tid":"33"
        },
        {
          "tid":"48"
        },
        {
          "tid":"45"
        }
      ]
    },
    "field_keywords":{
      "und":[
        {
          "tid":"205"
        },
        {
          "tid":"206"
        },
        {
          "tid":"207"
        },
        {
          "tid":"208"
        },
        {
          "tid":"209"
        }
      ]
    },
    "field_event_date":{
      "und":[
        {
          "value":"2013-04-30 18:00:00",
          "value2":"2013-04-30 20:00:00",
          "timezone":"America/New_York",
          "offset":"-14400",
          "offset2":"-14400",
          "rrule":null,
          "timezone_db":"UTC",
          "date_type":"datetime"
        }
      ]
    },
    "field_location":{
      "und":[
        {
          "country":"US",
          "administrative_area":"",
          "sub_administrative_area":null,
          "locality":"",
          "dependent_locality":null,
          "postal_code":"",
          "thoroughfare":"",
          "premise":"",
          "sub_premise":null,
          "organisation_name":null,
          "name_line":null,
          "first_name":null,
          "last_name":null,
          "data":null
        }
      ]
    },
    "field_location_alternative":[

    ],
    "field_sponsor_name":{
      "und":[
        {
          "value":"FEMP",
          "format":null,
          "safe_value":"FEMP"
        }
      ]
    },
    "field_website_url":[

    ],
    "field_logo":[

    ],
    "field_registration_url":{
      "und":[
        {
          "url":"http://apps1.eere.energy.gov/femp/training/course_detail_live.cfm/CourseDateId=537",
          "title":null,
          "attributes":[

          ]
        }
      ]
    },
    "field_audience_types":{
      "und":[
        {
          "tid":"86"
        },
        {
          "tid":"87"
        },
        {
          "tid":"89"
        },
        {
          "tid":"90"
        },
        {
          "tid":"95"
        }
      ]
    },
    "field_building_types":[

    ],
    "field_radioactivity":[

    ]
  },
  ...
}
```

### XML Output Format

<pre>GET /api/commercial-building-resources/v1/events.xml?portal=6&api_key=DEMO_KEY</pre>

## Rate Limits

[Standard rate limits](/docs/rate-limits) apply. No more than 1,000 requests may be made in any hour. No more than 10,000 requests may be made in any day.

## Errors

[Standard errors](/docs/errors) may be returned.

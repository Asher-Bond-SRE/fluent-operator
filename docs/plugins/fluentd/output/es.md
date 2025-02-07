# ElasticsearchCommon

Elasticsearch defines the parameters for out_es output plugin


| Field | Description | Scheme |
| ----- | ----------- | ------ |
| host | The hostname of your Elasticsearch node (default: localhost). | *string |
| port | The port number of your Elasticsearch node (default: 9200). | *uint32 |
| hosts | Hosts defines a list of hosts if you want to connect to more than one Elasticsearch nodes | *string |
| scheme | Specify https if your Elasticsearch endpoint supports SSL (default: http). | *string |
| path | Path defines the REST API endpoint of Elasticsearch to post write requests (default: nil). | *string |
| cloudId | Authenticate towards Elastic Cloud using CloudId. If set, cloudAuth must be set as well and host, port, user and password are ignored. | *[plugins.Secret](../secret.md) |
| cloudAuth | Authenticate towards Elastic Cloud using cloudAuth. | *[plugins.Secret](../secret.md) |
| user | Optional, The login credentials to connect to Elasticsearch | *[plugins.Secret](../secret.md) |
| password | Optional, The login credentials to connect to Elasticsearch | *[plugins.Secret](../secret.md) |
| sslVerify | Optional, Force certificate validation | *bool |
| caFile | Optional, Absolute path to CA certificate file | *string |
| clientCert | Optional, Absolute path to client Certificate file | *string |
| clientKey | Optional, Absolute path to client private Key file | *string |
| clientKeyPassword | Optional, password for ClientKey file | *[plugins.Secret](../secret.md) |
| templateOverwrite | Optional, Always update the template, even if it already exists (default: false) | *bool |
| maxRetryPuttingTemplate | Optional, You can specify times of retry putting template (default: 10) | *uint32 |
| failOnPuttingTemplateRetryExceeded | Optional, Indicates whether to fail when max_retry_putting_template is exceeded. If you have multiple output plugin, you could use this property to do not fail on fluentd statup (default: false) | *bool |
| reconnectOnError | Optional, Indicates that the plugin should reset connection on any error (reconnect on next send) (default: false) | *bool |
| reloadAfter | Optional, When ReloadConnections true, this is the integer number of operations after which the plugin will reload the connections. The default value is 10000. | *uint32 |
| reloadConnections | Optional, Automatically reload connection after 10000 documents (default: true) | *bool |
| reloadOnFailure | Optional, Indicates that the elasticsearch-transport will try to reload the nodes addresses if there is a failure while making the request, this can be useful to quickly remove a dead node from the list of addresses (default: false) | *bool |
| requestTimeout | Optional, HTTP Timeout (default: 5) | *string |
| snifferClassName | Optional, Provide a different sniffer class name | *string |
| suppressTypeName | Optional, Suppress '[types removal]' warnings on elasticsearch 7.x | *bool |
| enableIlm | Optional, Enable Index Lifecycle Management (ILM) | *bool |
| ilmPolicyId | Optional, Specify ILM policy id | *string |
| ilmPolicy | Optional, Specify ILM policy contents as Hash | *string |
| ilmPolicyOverride | Optional, Specify whether overwriting ilm policy or not | *bool |
| logEs400Reason | Optional, Enable logging of 400 reason without enabling debug log level | *bool |
# Elasticsearch




| Field | Description | Scheme |
| ----- | ----------- | ------ |
| indexName | IndexName defines the placeholder syntax of Fluentd plugin API. See https://docs.fluentd.org/configuration/buffer-section. | *string |
| logstashFormat | If true, Fluentd uses the conventional index name format logstash-%Y.%m.%d (default: false). This option supersedes the index_name option. | *bool |
| logstashPrefix | LogstashPrefix defines the logstash prefix index name to write events when logstash_format is true (default: logstash). | *string |
# ElasticsearchDataStream




| Field | Description | Scheme |
| ----- | ----------- | ------ |
| dataStreamName | You can specify Elasticsearch data stream name by this parameter. This parameter is mandatory for elasticsearch_data_stream | *string |
| dataStreamTemplateName | Optional, You can specify an existing matching index template for the data stream. If not present, it creates a new matching index template | *string |
| dataStreamTemplateUseIndexPatternsWildcard | Optional, Specify whether index patterns should include a wildcard (*) when creating an index template. This is particularly useful to prevent errors in scenarios where index templates are generated automatically, and multiple services with distinct suffixes are in use | *bool |
| dataStreamIlmName | Optional, You can specify the name of an existing ILM policy, which will be applied to the data stream. If not present, it creates a new ILM default policy (unless data_stream_template_name is defined, in that case the ILM will be set to the one specified in the matching index template) | *string |
| dataStreamIlmPolicy | Optional, You can specify the ILM policy contents as hash. If not present, it will apply the ILM default policy | *string |
| dataStreamIlmPolicyOverwrite | Optional, Specify whether the data stream ILM policy should be overwritten | *bool |

# Fluentd Meraki
This configuration file takes the Meraki Syslog Events and converts them to structure data using Fluentd. The data can then be ingested in elasticsearch for dashboards etc...

To configure Meraki Syslog:
[https://documentation.meraki.com/zGeneral_Administration/Monitoring_and_Reporting/Syslog_Server_Overview_and_Configuration](https://documentation.meraki.com/zGeneral_Administration/Monitoring_and_Reporting/Syslog_Server_Overview_and_Configuration)

## Example Output
These are JSON outputs from Kibana.

### Flows
```json
{
  "_index": "logstash-2017.07.02",
  "_type": "fluentd",
  "_id": "AV0EqCMv3mPW9dgx11GL",
  "_score": null,
  "_source": {
    "host": "ap_office",
    "event": "flows",
    "action": "allow",
    "ipv4_src_addr": "192.168.1.67",
    "ipv4_dst_addr": "192.168.1.3",
    "mac": "XX:XX:XX:XX:XX:XX",
    "meraki_protocol": "udp",
    "l4_src_port": "60611",
    "l4_dst_port": "53",
    "tag": "meraki.flows",
    "@timestamp": "2017-07-02T11:53:40-07:00"
  },
  "fields": {
    "@timestamp": [
      1499021620000
    ]
  },
  "sort": [
    1499021620000
  ]
}
```

### URL (HTTP)
```json
{
  "_index": "logstash-2017.07.02",
  "_type": "fluentd",
  "_id": "AV0EwttZ3mPW9dgx17yv",
  "_score": null,
  "_source": {
    "host": "ap_office",
    "event": "urls",
    "ipv4_src_addr": "192.168.1.67",
    "l4_src_port": "58656",
    "ipv4_dst_addr": "192.168.1.30",
    "l4_dst_port": "80",
    "mac_addr": "XX:XX:XX:XX:XX:XX",
    "useragent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_5) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.36",
    "method": "POST",
    "url": "http://home-kibana1.home.lan/elasticsearch/_msearch?timeout=0&ignore_unavailable=true&preference=1499021195717",
    "tag": "meraki.urls",
    "@timestamp": "2017-07-02T12:22:50-07:00"
  },
  "fields": {
    "@timestamp": [
      1499023370000
    ]
  },
  "sort": [
    1499023370000
  ]
}
```

### URL (HTTPS)
```json
{
  "_index": "logstash-2017.07.02",
  "_type": "fluentd",
  "_id": "AV0EqDL_3mPW9dgx11Hg",
  "_score": null,
  "_source": {
    "host": "ap_office",
    "event": "urls",
    "ipv4_src_addr": "192.168.1.67",
    "l4_src_port": "58332",
    "ipv4_dst_addr": "192.30.253.125",
    "l4_dst_port": "443",
    "mac_addr": "XX:XX:XX:XX:XX:XX",
    "method": "UNKNOWN",
    "url": "https://live.github.com/...",
    "tag": "meraki.urls",
    "@timestamp": "2017-07-02T11:53:40-07:00"
  },
  "fields": {
    "@timestamp": [
      1499021620000
    ]
  },
  "sort": [
    1499021620000
  ]
}
```

### Events (Multiple DHCP detected)
```json
{
  "_index": "logstash-2017.07.02",
  "_type": "fluentd",
  "_id": "AV0EwRG03mPW9dgx17j7",
  "_score": null,
  "_source": {
    "host": "ap_livingroom",
    "event": "events",
    "event_type": "multiple_dhcp_servers_detected",
    "event_vap": "1",
    "event_original_server_ip": "192.168.1.2",
    "event_original_server_mac": "XX:XX:XX:XX:XX:XX",
    "event_server_ip": "192.168.1.3",
    "event_server_mac": "XX:XX:XX:XX:XX:XX",
    "tag": "meraki.events",
    "@timestamp": "2017-07-02T12:20:29-07:00"
  },
  "fields": {
    "@timestamp": [
      1499023229000
    ]
  },
  "sort": [
    1499023229000
  ]
}
```

### Events (Association)
```json
{
  "_index": "logstash-2017.07.02",
  "_type": "fluentd",
  "_id": "AV0EwRG03mPW9dgx17j5",
  "_score": null,
  "_source": {
    "host": "ap_livingroom",
    "event": "events",
    "event_type": "association",
    "event_radio": "1",
    "event_vap": "1",
    "client_mac": "XX:XX:XX:XX:XX:XX",
    "client_ip": "192.168.1.85",
    "channel": "161",
    "rssi": "28",
    "aid": "850598500",
    "tag": "meraki.events",
    "@timestamp": "2017-07-02T12:20:25-07:00"
  },
  "fields": {
    "@timestamp": [
      1499023225000
    ]
  },
  "sort": [
    1499023225000
  ]
}
```

### Events (Disassociation)
```json
{
  "_index": "logstash-2017.07.02",
  "_type": "fluentd",
  "_id": "AV0EwRG03mPW9dgx17j4",
  "_score": null,
  "_source": {
    "host": "ap_livingroom",
    "event": "events",
    "event_type": "disassociation",
    "event_radio": "1",
    "event_vap": "1",
    "client_mac": "XX:XX:XX:XX:XX:XX",
    "channel": "161",
    "reason": "8",
    "instigator": "1",
    "duration": "15397.262894605",
    "auth_neg_dur": "0.659793815",
    "last_auth_ago": "15396.603100790",
    "is_wpa": "1",
    "event_full_conn": "5.628241175",
    "event_ip_resp": "5.628241175",
    "event_ip_src": "192.168.1.85",
    "tag": "meraki.events",
    "@timestamp": "2017-07-02T12:20:25-07:00"
  },
  "fields": {
    "@timestamp": [
      1499023225000
    ]
  },
  "sort": [
    1499023225000
  ]
}
```

### Events (WPA Auth)
```json
{
  "_index": "logstash-2017.07.02",
  "_type": "fluentd",
  "_id": "AV0EvWLH3mPW9dgx160X",
  "_score": null,
  "_source": {
    "host": "ap_livingroom",
    "event": "events",
    "event_type": "wpa_auth",
    "event_radio": "0",
    "event_vap": "0",
    "client_mac": "XX:XX:XX:XX:XX:XX",
    "client_ip": "192.168.1.40",
    "aid": "634438691",
    "tag": "meraki.events",
    "@timestamp": "2017-07-02T12:16:19-07:00"
  },
  "fields": {
    "@timestamp": [
      1499022979000
    ]
  },
  "sort": [
    1499022979000
  ]
}
```
### Events (WPA DE-Auth)
```json
{
  "_index": "logstash-2017.07.02",
  "_type": "fluentd",
  "_id": "AV0ErtuM3mPW9dgx13Wd",
  "_score": null,
  "_source": {
    "host": "ap_livingroom",
    "event": "events",
    "event_type": "wpa_deauth",
    "event_radio": "0",
    "event_vap": "0",
    "client_mac": "XX:XX:XX:XX:XX:XX",
    "client_ip": "192.168.1.40",
    "aid": "549425231",
    "tag": "meraki.events",
    "@timestamp": "2017-07-02T12:00:20-07:00"
  },
  "fields": {
    "@timestamp": [
      1499022020000
    ]
  },
  "sort": [
    1499022020000
  ]
}
```

### Air Marshall Events (SSID spoofing detected)
```json
{
  "_index": "logstash-2017.07.02",
  "_type": "fluentd",
  "_id": "AV0ExLCt3mPW9dgx18EH",
  "_score": null,
  "_source": {
    "host": "ap_livingroom",
    "event": "airmarshal_events",
    "event_type": "ssid_spoofing_detected",
    "ssid": "my-ssid",
    "vap": "6",
    "bssid": "FF:FF:FF:FF:FF:FF",
    "src_mac": "XX:XX:XX:XX:XX:XX",
    "dst_mac": "FF:FF:FF:FF:FF:FF",
    "channel": "1",
    "rssi": "18",
    "fc_type": "0",
    "fc_subtype": "4",
    "tag": "meraki.airmarshal",
    "@timestamp": "2017-07-02T12:24:10-07:00"
  },
  "fields": {
    "@timestamp": [
      1499023450000
    ]
  },
  "sort": [
    1499023450000
  ]
}
```

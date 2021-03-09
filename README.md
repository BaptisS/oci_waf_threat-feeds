# oci_waf_threat-feeds




1.1.2- Copy and Paste (CTRL+SHIFT+’V’) the command below in your Cloud Shell session : 

(Replace ‘ocid1.waaspolicy.oc1..aaaaaaaaxxxxxxxxxxx’ by your WAF Policy OCID - copied in the previous step.)


```
export wafpolid=ocid1.waaspolicy.oc1..aaaaaaaaxxxxxxxxxxx

oci waas threat-feed list --waas-policy-id $wafpolid --all | jq -r '.[]'>/tmp/threat-feeds.json
sed -i 's/OFF/BLOCK/g' /tmp/threat-feeds.json
sed -i '$d' /tmp/threat-feeds.json
oci waas threat-feed update --waas-policy-id $wafpol01 --threat-feeds file:///tmp/threat-feeds.json
```



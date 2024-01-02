# NETCONF USING SSH

1. NETCONF using SSH to the devices(terminal).
```
ssh -p 830 cisco@csr1kv -s netconf
```
2. devices terminal will show up

"IT WILL SHOW YOU NETCONF CAPABILITY THE DEVICES IS CAPABLE"
example:
```
<hello xmlns="urn:ietf:params:xml:ns:netconf:base:1.0">
<capabilities>
<capability>urn:ietf:params:netconf:base:1.0</capability>
<capability>urn:ietf:params:netconf:base:1.1</capability>
```
3. we need to respond with message hello.
when inputing this no need to enter go get for it work. just copy paste it
```
<?xml version="1.0" encoding="UTF-8"?>
<hello xmlns="urn:ietf:params:xml:ns:netconf:base:1.0">
  <capabilities>
    <capability>urn:ietf:params:netconf:base:1.0</capability>
  </capabilities>
</hello>]]>]]>
```

4. after hello message now we need to send get message.
```
<rpc message-id="101" xmlns="urn:ietf:params:xml:ns:netconf:base:1.0">
  <get>
    <filter type="subtree">
      <netconf-state xmlns= "urn:ietf:params:xml:ns:yang:ietf-netconf-monitoring">
        <schemas/>
      </netconf-state>
    </filter>
  </get>
</rpc>]]>]]>
```

the devices will repond the rpc. copy the respond and take a look into it.


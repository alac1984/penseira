04/01/2023 11:46

Status: #walkthrough 

Tags: [[Bizagi]] [[Bizagi's SOA Layer]] [[SOAPUi]]

`saveEntity` is a POST request made for `http://[your_host]/[your_bizagi_project]/WebServices/EntityManagerSOA.asmx` endpoint.  A raw requisition is showed below:

```http

POST http://desktop-98fs2r0/p4pro_model_basic/WebServices/EntityManagerSOA.asmx HTTP/1.1
Accept-Encoding: gzip,deflate
Content-Type: text/xml;charset=UTF-8
SOAPAction: "http://tempuri.org/getEntities"
Content-Length: 509
Host: desktop-98fs2r0
Connection: Keep-Alive
User-Agent: Apache-HttpClient/4.5.5 (Java/16.0.1)
```

You have to send an XML like this in the body:

```xml

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:tem="http://tempuri.org/">
   <soapenv:Header/>
   <soapenv:Body>
      <tem:saveEntity>
         <!--Optional:-->
         <tem:entityInfo>
            <BizAgiWSParam>
               <Entities>
                  <Compras key="7">
                     <DataAprovacao>2022-12-13T10:10:00.000</DataAprovacao>
                  </Compras>
               </Entities>
            </BizAgiWSParam>
         </tem:entityInfo>
      </tem:saveEntity>
   </soapenv:Body>
</soapenv:Envelope>

```

In that example, `<Compras key="7">` is the name (not display name) of an Entity (master, parameter, system or stakeholder). `<DataAprovacao>` is the display name of an attribute we want to set in that particular entity.

After sending, we will receive a response like below:

```http
HTTP/1.1 200 OK
Cache-Control: no-cache, no-store
Pragma: no-cache
Content-Type: text/xml; charset=utf-8
Expires: -1
Vary: Accept-Encoding
Access-Control-Allow-Origin: *
X-Frame-Options: SAMEORIGIN
X-UA-Compatible: IE=Edge,chrome=IE8
Date: Wed, 04 Jan 2023 15:23:47 GMT
```

And a XML body like this:

```xml

<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
   <soap:Body>
      <saveEntityResponse xmlns="http://tempuri.org/">
         <saveEntityResult>
            <Entities xmlns="">
               <Compras>7</Compras>
            </Entities>
         </saveEntityResult>
      </saveEntityResponse>
   </soap:Body>
</soap:Envelope>
```


---
# References

https://help.bizagi.com/bpm-suite/en/saveentityasstring.htm
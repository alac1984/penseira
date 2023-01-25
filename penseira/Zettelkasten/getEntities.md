04/01/2023 11:29

Tags: [[Bizagi]] [[Bizagi's SOA Layer]] [[SOAPUi]]

`getEntities` is a POST request made for `http://[your_host]/[your_bizagi_project]/WebServices/EntityManagerSOA.asmx` endpoint.  A raw requisition is showed below:

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
      <tem:getEntities>
         <!--Optional:-->
         <tem:entitiesInfo>
             <BizAgiWSParam>
		      <EntityData>           
			    <EntityName>Compras</EntityName>
			    <Filters>idCompras = 3</Filters>
			 </EntityData>
		  </BizAgiWSParam>
         </tem:entitiesInfo>
      </tem:getEntities>
   </soapenv:Body>
</soapenv:Envelope>
```

In that example, `<EntityName>` is the name (not display name) of an Entity (master, parameter, system or stakeholder). `<Filters>` node work exactly as a WHERE clause in SQL. An requisition like that will give a response like this:

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
Date: Wed, 04 Jan 2023 15:24:28 GMT
```

And a XML body like this:

```xml

<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
   <soap:Body>
      <getEntitiesResponse xmlns="http://tempuri.org/">
         <getEntitiesResult>
            <BizAgiWSResponse xmlns="">
               <Entities>
                  <Compras key="3">
                     <DataSolicitacao>2022-12-12T00:00:00</DataSolicitacao>
                     <DataCompra>2022-12-12T00:00:00</DataCompra>
                     <Observacoes>Compramos</Observacoes>
                  </Compras>
               </Entities>
            </BizAgiWSResponse>
         </getEntitiesResult>
      </getEntitiesResponse>
   </soap:Body>
</soap:Envelope>
```

---
# References

https://help.bizagi.com/bpm-suite/en/getentitiesasstring.htm
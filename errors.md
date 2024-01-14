# Cannot create a secure XMLInputFactory
## Error stack
```bash
java.lang.RuntimeException: Cannot create a secure XMLInputFactory
		at org.apache.cxf.staxutils.StaxUtils.createXMLInputFactory(StaxUtils.java:323)
		at org.apache.cxf.staxutils.StaxUtils.getXMLInputFactory(StaxUtils.java:273)
		at org.apache.cxf.staxutils.StaxUtils.createXMLStreamReader(StaxUtils.java:1702)
		at org.apache.cxf.interceptor.StaxInInterceptor.handleMessage(StaxInInterceptor.java:123)
		at org.apache.cxf.phase.PhaseInterceptorChain.doIntercept(PhaseInterceptorChain.java:308)
		at org.apache.cxf.transport.ChainInitiationObserver.onMessage(ChainInitiationObserver.java:121)
		at org.apache.cxf.transport.http.AbstractHTTPDestination.invoke(AbstractHTTPDestination.java:254)
		at org.apache.cxf.transport.servlet.ServletController.invokeDestination(ServletController.java:234)
```

## Cause
The conflict between stax api libraries - check the dependencies and remove old libraries

# The given SOAPAction Unknown does not match an operation
## Error stack
```bash
org.apache.cxf.interceptor.Fault: The given SOAPAction Unknown does not match an operation.
		at org.apache.cxf.binding.soap.interceptor.SoapActionInInterceptor$SoapActionInAttemptTwoInterceptor.handleMessage(SoapActionInInterceptor.java:258)
		at org.apache.cxf.binding.soap.interceptor.SoapActionInInterceptor$SoapActionInAttemptTwoInterceptor.handleMessage(SoapActionInInterceptor.java:236)
		at org.apache.cxf.phase.PhaseInterceptorChain.doIntercept(PhaseInterceptorChain.java:308)
		at org.apache.cxf.transport.ChainInitiationObserver.onMessage(ChainInitiationObserver.java:121)
		at org.apache.cxf.transport.http.AbstractHTTPDestination.invoke(AbstractHTTPDestination.java:254)
		at org.apache.cxf.transport.servlet.ServletController.invokeDestination(ServletController.java:234)
		at org.apache.cxf.transport.servlet.ServletController.invoke(ServletController.java:208)
		at org.apache.cxf.transport.servlet.ServletController.invoke(ServletController.java:160)
```
## Cause
SOAPAction header is wrong - check the Action attribute of the operation in WSDL and correct the SOAPAction header.
```xml
<wsdl:operation name="request">
  <soap:operation soapAction="myAction" style="document"/>
  <wsdl:input name="request">
    <soap:body use="literal"/>
  </wsdl:input>
  <wsdl:output name="requestResponse">
    <soap:body use="literal"/>
  </wsdl:output>
</wsdl:operation>
```
```javascript
SOAPAction: myAction
```

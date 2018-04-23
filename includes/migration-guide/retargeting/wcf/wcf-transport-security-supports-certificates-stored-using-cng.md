### <a name="wcf-transport-security-supports-certificates-stored-using-cng"></a>Seguridad de transporte WCF es compatible con los certificados almacenados con CNG

|   |   |
|---|---|
|Detalles|A partir de las aplicaciones que tienen como destino .NET Framework 4.6.2, seguridad de transporte WCF admite certificados almacenados mediante la biblioteca de Windows Cryptography (CNG). Esta compatibilidad está limitada a los certificados con una clave pública que tengan un exponente con una longitud no superior a 32 bits. Cuando una aplicación tiene como destino .NET Framework 4.6.2, esta característica está activada de forma predeterminada. En versiones anteriores de .NET Framework, el intento de usar X509 certificados con un CSG proveedor de almacenamiento de claves produce una excepción.|
|Sugerencia|Aplicaciones de destino es .NET Framework 4.6.1 y versiones anterior pero se ejecutan en .NET Framework 4.6.2 pueden habilitar la compatibilidad para los certificados CNG agregando la siguiente línea a la <code>&lt;runtime&gt;</code> sección del archivo app.config o web.config:<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableCngCertificates=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Esto también puede realizarse mediante programación con el siguiente código:<pre><code class="language-cs">private const string DisableCngCertificates = @&quot;Switch.System.ServiceModel.DisableCngCertificate&quot;;&#13;&#10;AppContext.SetSwitch(disableCngCertificates, false);&#13;&#10;</code></pre><pre><code class="language-vb">Const DisableCngCertificates As String = &quot;Switch.System.ServiceModel.DisableCngCertificates&quot;&#13;&#10;AppContext.SetSwitch(disableCngCertificates, False)&#13;&#10;</code></pre>Tenga en cuenta que, debido a este cambio, cualquier código erróneo de control de excepciones que dependa del intento de iniciar una comunicación segura con un certificado CNG dejará de ejecutarse.|
|Ámbito|Secundaria|
|Versión|4.6.2|
|Tipo|Redestinación|

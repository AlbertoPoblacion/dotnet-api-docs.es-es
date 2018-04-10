### <a name="httprequestcontentencoding-property-prohibits-utf7"></a>La propiedad HttpRequest.ContentEncoding prohíbe UTF7

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.5, codificación UTF-7 está prohibido en <xref:System.Web.HttpRequest?displayProperty=name>s' cuerpos. Los datos de las aplicaciones que dependen de los datos de entrada UTF-7 no se descodificarán correctamente en algunos casos.|
|Sugerencia|Idealmente, las aplicaciones deben actualizarse para que no use la codificación en UTF-7 <xref:System.Web.HttpRequest?displayProperty=name>s. También es posible restaurar el comportamiento heredado usando el atributo <code>aspnet:AllowUtf7RequestContentEncoding</code> del elemento [appSettings](https://msdn.microsoft.com/library/hh975440(v=vs.110).aspx).|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|


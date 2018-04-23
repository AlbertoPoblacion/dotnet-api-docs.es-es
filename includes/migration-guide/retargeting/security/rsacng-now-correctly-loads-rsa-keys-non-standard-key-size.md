### <a name="rsacng-now-correctly-loads-rsa-keys-of-non-standard-key-size"></a>RSACng ahora carga correctamente las claves RSA del tamaño de clave no estándar

|   |   |
|---|---|
|Detalles|En las versiones de .NET Framework anteriores a 4.6.2, los clientes con tamaños de clave no estándares para los certificados RSA son no se puede tener acceso a esas claves a través de la <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=name> y <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=name> métodos de extensión.  A <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> con el mensaje &quot;no se admite el tamaño de clave solicitado&quot; se produce. En .NET Framework 4.6.2 se ha solucionado este problema. De forma similar, <xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)> y <xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)> ahora trabajar con los tamaños de clave no estándares sin producir <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>s.|
|Sugerencia|Si no hay ninguna lógica que se basa en el comportamiento anterior de control de excepciones donde un <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> se produce cuando se usan los tamaños de clave no estándares, considere la posibilidad de quitar la lógica.|
|Ámbito|Borde|
|Versión|4.6.2|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType></li></ul>|

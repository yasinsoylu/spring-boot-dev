# 6-) Spring Boot Application Properties Custom
Spring Boot projesi geliştirilirken **application_properties** dosyası yalnızca konfigürasyon veya ayarlama için değil aynı zamanda Custom Properties tanımlamak için de kullanılabilir.
**application_properties** içerisinde proje adımız, actuator servisi için endpoint sağlayıcımız, security için endpoint exluce edişimiz vs. tanımlanmaktadır. Ancak en altta yer alan koyu yazılı alan ile custom variables da tanımlanabilir.
#
#### Custom Fields
```
# My Custom Properties Area
dad.name=Yasin
pet.name=Leo
```
Tanımlanan bu değişkenler ise basitçe get edilebilir. 
```
@Value("${dad.name}")
private String dadName;

@Value("${pet.name}")
private String petName;
```
Bu şekilde @Value("${attribute}") kullanarak değeri get edebiliyoruz. 
#
Ek olarak **application_properties** dosyası içerisine farklı tanımlamalar da sağlanabilir. Loglanma yönetmi, log dosyası path tanımı, http tanımları vs.
```
# HTTP Props
server.port=9548
server.servlet.context-path=/app
```
Bu şekilde http tanımı yapılarak default olan port değeri özelleştirilebilir ve context-path belirlenerek her endpoint'i bunun altından sağlayabiliriz.
>![](/attachment/Clipboard_2025-03-14-14-51-29.png)

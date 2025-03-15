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
#### HTTP Props
Ek olarak **application_properties** dosyası içerisine farklı tanımlamalar da sağlanabilir. Loglanma yönetmi, log dosyası path tanımı, http tanımları vs.
```
# HTTP Props
server.port=9548
server.servlet.context-path=/app
```
Bu şekilde http tanımı yapılarak default olan port değeri özelleştirilebilir ve context-path belirlenerek her endpoint'i bunun altından sağlayabiliriz.
>![](/attachment/Clipboard_2025-03-14-14-51-29.png)
#
#### Actuator Props
Aynı zamanda Actuator için de ayarlamalar sağlanabilmektedir. Önceki yazılarımızda olduğu gibi include ve exclude edilecek methodalar belirtilebilir. 
Ayrıca actuator için default base end point'i (/actuator) değiştirilebilir.
```
management.endpoints.web.base-path=/mypath
```
>![](/attachment/Clipboard_2025-03-15-11-46-26.png)

Böylece default olan /actuator yerine /mypath gibi istediğimiz bir değer ataması yapabiliriz
#
#### Security Props
Security ayarlarında default olarak username = user ataması mevcuttur ve password için spring projemiz ayağa kalkarken üretilen token kullanılır.
Ancak bunu biz tanımlayarak özelleştirebiliriz.
```
# Spring security:
spring.security.user.name=admin
spring.security.user.password=topsecret
```
>![](/attachment/Clipboard_2025-03-15-11-56-04.png)

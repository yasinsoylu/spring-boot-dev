# 4-) Spring Boot Security for Actuator Endpoints
Mevcut düzende en son wildcard kullanımı ile * tanımlaması sağlanarak spring'e ait 14 tane endpoint ayağa kalkmıştır. Ancak security sağlanması için bir işlem yapılmamıştı. 

Bu aşamada security adımları yer almaktadır. 

  #### Security Dependecy
**Pom.xml** içerisine security dependecy eklenir.
```
  <dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-security</artifactId>
  </dependency>
```
>![](/attachment/Clipboard_2025-03-14-14-40-09.png)

Spring projesi her seferinde ayağa kalkarken Basic Auth kullanımı için default "user" kullanıcısına bir password oluşturur. Bu şifreyi loglardan takip edebiliriz.

>![](/attachment/Clipboard_2025-03-14-14-40-27.png)

**Note: Actuator tarafından sağlanan /actuator/health endpointi hariç kalan tüm özel ve default endpointler kilitlenmektedir.**
#
Bu şekilde artık bizim actuator ile istek attığımız endpointlerimiz health haricinde login olunmasını zorunlu kılmıştır.
>![](/attachment/Clipboard_2025-03-14-14-41-00.png)
#
Aynı şekilde postman'den de istek atarken **Basic Auth** seçilerek token yardımı ile istek atılabilir.
>![](/attachment/Clipboard_2025-03-14-14-46-08.png)

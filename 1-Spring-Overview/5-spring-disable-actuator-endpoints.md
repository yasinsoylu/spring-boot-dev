# 5-) Spring Boot Disable Actuator Endpoints
Spring Boot projemizde bir endpoint'i disable etmek için **Application_properties** içerisine actuator tarafından bize sağlanan ve disable etmek istediğimiz endpointleri belirtiyoruz.
```
management.endpoints.web.exposure.exclude=beans,health
```
>![](/1-Spring-Overview/attachment/Clipboard_2025-03-14-14-48-20.png)

Böylece ilgili endpointler 404 olarak dönmektedir. Bu kapsamda ulaşılmasını istemediğimiz endpointler için exclude olarak belirtebiliriz.
>![](/1-Spring-Overview/attachment/Clipboard_2025-03-14-14-48-30.png)

# 3-) Spring Boot Actuator
Spring Boot'un ekstra geliştirme yapmaya gerek kalmadan bizlere sunabildiği bazı endpointler vardır. Bu endpointler ile projenin sağlığını, belirlenen bilgilerini, beans kullanımını, mapping kullanımını vs. json formatta get edebiliriz.

Actuator kullanımı için gerekli aşamalar:
1. **Pom.xml** içerisine spring-boot-starter-actuator eklenir:
   ```
   	<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-actuator</artifactId>
		</dependency>
   ```
   >![](/1-Spring-Overview/attachment/Clipboard_2025-03-14-14-20-28.png)

2. Application properties içerisine kullanılacak spring actuator hizmetleri belirlenir;
   ```
    Springboot Actuator:
    management.endpoints.web.exposure.include=health,info
    management.info.env.enabled=true
   ```
   >![](/1-Spring-Overview/attachment/Clipboard_2025-03-14-14-22-45.png)

   **Hint:** Eğer ki **management.endpoints.web.exposure.include=*** olarak tanımlanırsa, wildcard kullanımı ile * işareti 14 default endpointi hizmete açar.  
#
### /actuator/health endpointi:
>![](/1-Spring-Overview/attachment/Clipboard_2025-03-14-14-33-09.png)
#
### /actuator/ifno endpointi:
Info endpointi default olarak {} olarak boş json döner. Bunun sebebi ***application_properties*** altında info dağılımı sağlanmadığı içindir.
***application_properties*** altına info. ile başlayarak gerekli tüm tanımlamaları ve endopoint'in return değerini biz belirleyeceğiz. Örnek aşağıda yer almaktadır;

```
# /info endpoint values can define as info.yourvalues... After that they will be display json format:
info.person.name=Yasin
info.person.surname=Soylu
info.person.birthdate=1999
info.pet.name=Leo
info.pet.type=Cat
info.pet.birthdate=2020
```

>![](/1-Spring-Overview/attachment/Clipboard_2025-03-14-14-29-48.png)
#
### /actuator/* endpointi:
Projede Security Ayarları ile beraber kontrollü şekilde endpoint ayarlaması için management.endpoints.web.exposure.include=* tanımlaması sağlanır.

Bu sayede /actuator/beans, /actuator/mappings, /actuator/threaddump gibi endpointler de açılır. Ancak bu endpoint sonuçları çok fazla proje açığı içerebileceği için bir sonraki yazıda yer alan security ayarları ile kontrol sağlanabilir.

>![](/1-Spring-Overview/attachment/Clipboard_2025-03-14-14-32-07.png)

>![](/1-Spring-Overview/attachment/Clipboard_2025-03-14-14-32-20.png)

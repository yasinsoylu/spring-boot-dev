# 2-)  Spring Projesi Auto Reload
Spring projesi geliştirme sürecinde her kod değişikliğinden sonra tüm servisi kapatıp tekrar açmak yerine auto reload işlevi kazandırılarak zaman ve efor açısından daha efektiflik sağlanabilir.


Öncelikli olarak pom.xml içerisine dependecy olarak devtools eklenir:

```
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-devtools</artifactId>
		</dependency>
```
![](/1-Spring-Overview/attachment/Clipboard_2025-03-14-14-17-56.png)

Ardından Intellij'in kendi ayarlarında yer alan iki checkbox işaretlenmelidir.

1. Settings > Build, Execution, Deployment > Complier > "Build Project Automatically"
2. Settings > Advanced Settings > "Allow auto-make to start even if developed application is currently running"

pom.xml ve gerekli ayarlar sağlanınca servis ayakta olduğu zamanlarda da kaynak kodda yapılan değişiklikler için auto reload işlemi sağlanır. 

# Java #

## SWITCHING JAVA VERSION (WINDOWS) ##
install [scoop](https://scoop.sh), see guide for [Windows installation](https://www.cyberithub.com/how-to-install-scoop-on-windows-10-using-few-easy-steps/)

```
scoop bucket add java
scoop install [java-package]
scoop reset [java-package]
```
```
scoop bucket add java
scoop install openjdk21
scoop reset openjdk21
```

## Gradle ##
running Spring Boot app


```
gradle build
gradle bootRun
```

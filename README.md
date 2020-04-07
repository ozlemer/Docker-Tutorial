# Docker-Tutorial
Bu repoda docker'a başlangıç olarak temel komutlara değinilecektir.
Öncelikle kurulum ve gereken paketler vs için oldukça faydalı ve açıklayıcı bir şekilde dökümante edilmiş olan [docker'ın sitesini](https://docs.docker.com/get-started/)  ziyaret edebilirsiniz.
## Kısaca Kavramlar
**Container:** Konteynerler, bir geliştiricinin bir uygulamayı, kütüphaneler ve diğer bağımlılıklar gibi ihtiyaç duyduğu tüm parçalarla paketlemesini ve tek bir paket olarak göndermesini sağlar
**Image:** Uygulamanızın altyapısında çalışan gerekli işletim sistemi kütüphanelerinin bulunduğu bir yapıdır. 
![GitHub Logo](/docker_images/dockercomponents.svg)
Format: ![Alt Text](url)
**Docker file:** Bir image'i build etmek için talimatları içeren bir text dosyasıdır. 
(docker file görseli gelecek)
https://docs.docker.com/engine/reference/builder/#environment-replacement
## Temel Komutlar
- yardım alma komutu
```
$ docker images --help
```
- konu ile ilgili mevcut *image*leri arama
```
$ docker search <subject_name>
```
- *image* indirme
```
$ docker pull <image_name>
```
- *image*in özel versiyonunu indirme
```
$ docker pull <image_name:tag>
```
- *image*leri listeler
```
$ docker images
```
- *container*ları listeler
```
$ docker ps
```
- *f* parametresi filtre anlamına gelmektedir, *dangling* ise herhangi bir *image*in herhangi bir *container*la ilişkili olduğunu ifade eder
```
$ docker images -f "dangling=false"
```
- *image* hakkındaki tüm detayları öğrenmek için
```
$ docker inspect <image_name>
```
- *container* silme
```
$ docker rmi <container_name|ID>
```
- *container* koşturma
```
$ docker run <image_name> or <container_name>
```
- *it* parametresi interactive mode anlamına gelir, böylelikle containerın içine gireriz ve *bash* ile container için bir shell başlatmış oluruz. Opsiyonel olarak container'a *name* parametresiyle isim verebilirsiniz.
Bu şekilde bir **image**den bir **container** yaratmış oluruz.
```
$ docker run -- name <container_name> -it <image_name> bash
```
- image localde mevcut değil ise önce çeker sonra çalıştırır
```
$ docker run <image_name>
```
- *container*ı başlatır
```
$ docker start <container_name|ID>
```
- *container* durdurma  
```
$ docker stop <container_name|ID>
```
- *container*ın kullandığı sistem kaynaklarını görmek için
```
$ docker stats <container_name|ID>
```
- *container* terminalde çalışmaya başlar, *interactive mode*da çalışmaya başlar
```
$ docker attach <container_name|ID>
```
- çalışan *container*ı öldürme
```
$ docker kill <container_name|ID>
```
- *image* geçmişini görme
```
$ docker history <image_name>
```

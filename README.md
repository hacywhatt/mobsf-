# mobsf

MOBSF KURULUM

MobSF’e https://github.com/MobSF/Mobile-Security-Framework-MobSF adresinden erişebilirsiniz.

Kurulumu terminal üzerinden yapmak isterseniz;


sudo apt update -y && sudo apt install docker -y

docker pull opensecurity/mobile-security-framework-mobsf:latest

docker run -it -p 8000:8000  --name mobsf opensecurity/mobile-security-framework-mobsf 

ya da 

docker run -it --rm -p 8000:8000 opensecurity/mobile-security-framework-mobsf:latest

lokal ip adresinize port forwarding yaptığınız portu ekleyerek gidin ve mobsf'in çalıştığını göreceksiniz.

upload and analiz kısmına testi yapılacak .apk dosyası sürükleyip static analize başlayabilirsiniz. Unutmayın önce static analiz yapmadan dinamik analiz yaptıramazsınız.

giriş bilgileri default olarak mobsf:mobsf 

![image](https://github.com/user-attachments/assets/f92bbf1f-1ce6-4c06-b3b3-62b244c81844)


karşınıza aşağıdaki şekilde bilgiler çıkacak, bu kısımda yapılacak tek şey bize verilen bilgileri inceleyip dokümantasyona aktarmak.
![image](https://github.com/user-attachments/assets/77219635-d9d9-4718-94de-57735c8ed6cb)



Dinamik analiz

incelemek isterseniz dinamik analiz mimarisi;

![image](https://github.com/user-attachments/assets/648d79ee-9e63-4c88-a35d-ced5773e1ffb)

static analiz bittikten sonra dynamic analyzer'e basın, karşınıza android ve ios için iki farklı seçenek çıkıyor. ios tarafını şirketteki cihaz üzerinden yaptığımız için işimiz sadece android ile.
![image](https://github.com/user-attachments/assets/990a2ab3-7aaa-4027-9fe4-8b65bb597814)

dinamik analizi yapmak için Genymotion Android VM , Android Emulator AVD ve Corellium Android VM kullanabilirsiniz. Kullanacağınız sanal cihazların mobsf ile de uyumlu olmasına dikkat edin.
![image](https://github.com/user-attachments/assets/e6678964-0a0c-49e0-b255-5a9b5d4d867b)


ben Genymotion kullandığım için bunun üzerinden anlatıyorum ve samsung galaxy s6 11.0 mobsf ile uyumlu ve diğer cihazlara nazaran daha stabil geldiği için bunu tercih ediyorum. uyumlu olan başka bir cihaz ile devam edebilirsiniz.  
![image](https://github.com/user-attachments/assets/a513a37d-54a3-45d3-ad52-5b73f5d89d7e)

başlattığınızda üstünde ip adresi ve portu yazıyor. öncesinde ping atarak cihazların birbirini gördüğünden emin olun, eğer görmüyorlarsa ağ ayarlarınızı değiştirin.
![image](https://github.com/user-attachments/assets/c5e75392-9406-4a29-a504-24c217758c1a)

aşağıdaki komutla mobsf'i tekrar başlatın. 
![image](https://github.com/user-attachments/assets/45ed1b56-2649-433b-9922-7d7195c2ce6b)

apps available kısmında uygulama görünuyor. start diyoruz.
![image](https://github.com/user-attachments/assets/eaff985b-05ba-4abe-9ee2-9ef046de51cf)

gelecek olan arayüz aşağıdaki şekilde
![image](https://github.com/user-attachments/assets/6d1eae79-ca65-44c7-bc2c-df992a9770e8)


gerekli parametreleri seçip spawn and inject dediğinizde sanal cihazda uygulama otomatik olarak başlatılır. bu kısımdaki farklı parametreleri deneyerek ve arayüzdeki TLS/SSL security tester, activity tester gibi kısımları kullanarak mobil sızma testlerini gerçekleştirebilirisiniz. 
![image](https://github.com/user-attachments/assets/a5a5b432-3a18-4bae-9168-e79a4c04fa99)

generate report dediğinizde raporu size hazırlar, biraz uzun sürebilir. 



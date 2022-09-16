Nmap, ağ tarama ve zafiyet tespiti için kullanılan açık kaynaklı bir araçtır. Bu araç birçok sisteme yönelik taramaları gerçekleştirerek esnek, hızlı ve anlamlı bir şekilde sonuç üretmektedir. Sistemlerin açık olup olmadığını, açık olan sistemlerin portlarını durumları, hangi servislerin çalıştığı ve kullanılan işletim sistemi gibi birçok bilgiyi verebilmektedir. Nmap ile tespit edilen servislerin güvenlik açığı barındırıp barındırmadığı ve kullanılan servisler hakkında bilgi elde edilebilir. Ayrıca içerisinde barındırmış olduğu scriptler ile hedef sisteme yönelik tarama gerçekleştirildiğinde hedef sistem hakkında detaylı bilgi ve güvenlik açığı olup olmamasına yönelik sonuç üretmektedir. Nmap aracı, alanının en iyi araçları arasında yer almaktadır.

# **NMAP TARAMA AŞAMALARI**

Nmap uygulaması kullanılarak taramanın başarılı bir şekilde sonuçlanması için belirli aşamalar takip edilerek tarama işlemleri yapılmalıdır.

# **Tarama Öncesi Scriptlerin Kullanılması**

Nmap aracı, taranacak ağ hakkında bilgi toplamak için scriptler barındırır. Örneğin, ağ servislerinden bilgi almak için broadcast sorgularını kullanan dhcp-discover ve broadcast-dns-service-discover gibi scriptler kullanılmaktadır.

# **Hedef Numaralandırma**

Nmap, hedef numaralandırma işlemlerinde DNS, IP adresleri, CIDR değerleri gibi host belirteçlerini tespit etmektedir. Hedef hostları belirlemek için –iR parametresi kullanılabilir.

# **Host Keşif İşlemleri**

Nmap’te host keşif işlemleri genellikle bir makinenin aktif olup olmadığını tespit etmek için yapılmaktadır. Nmap varsayılan olarak önce host keşfi yapar ve sonra port taramasına başlar. Eğer port taraması yapmadan sadece host keşif işlemi yapılmak isteniyorsa –sn parametresi kullanılır. Host keşif işleminin yapılması istenmiyorsa –Pn parametresi kullanılabilir. –Pn parametresinin kullanılması ile hostlara ping atılmaz. Böylelikle host keşfi yapılmaz.

# **Reverse-DNS Resolution**

Nmap, ping taraması ile tarayıp belirlediği aktif makinelere yönelik Reverse-DNS çözümleme işlemi gerçekleştirilmektedir. Reverse-DNS çözümlemesi, –R parametresi ile yapılır. Normal şartlarda yalnızca açık makinelere yapılır.

# **Port Taraması**

Port taraması, Nmap aracının ana işlevlerinden biridir. Aktif olan bir sistemin portlarına istek atarak, portların açık veya kapalı olma durumunu tespit eder.

# **Versiyon Tespiti**

Tespit edilen açık portlarda hangi servisin çalıştığının tespiti için kullanılır. Nmap aracı içerisinde barındırmış olduğu problar ve 6500’den fazla servis imzası ile portlarda bulunan servisleri karşılaştırıp tespit etmektedir. Bu işlem –sV parametresi kullanılarak gerçekleştirilmektedir.

# **İşletim Sistemi Tespiti**

Nmap ile açık olan makinelere yönelik işletim sistemi tespiti yapılmaktadır. Nmap içerisinde bulunan bir veritabanında işletim sistemlerinin yanıtları bulunmaktadır. Nmap oluşturmuş olduğu probları makinelere göndererek makinelerden gelen yanıtları veritabanında bulunan yanıtlarla karşılaştırılmaktadır. Böylelikle kullanılan işletim sistemi bilgisi elde edilmektedir. Nmap aracı üzerinde bu işlem –O parametresi kullanılarak gerçekleştirilmektedir.

# **Traceroute İşlemi**

Nmap, –traceroute parametresi ile her hedef için paketlerin hangi yoldan geçtiğini tespit edebilir.

# **Script Taraması**

Nmap içerisinde, Nmap Script Engine(NSE) adı verilen bir yapı bulunmaktadır. Bu yapı içerisinde birçok script bulunur. Bu scriptler kullanılarak hedefe yönelik bilgi toplama ve güvenlik açığı tespit etme gibi birçok işlem gerçekleştirilebilmektedir. NSE, lua programlama dili ve ağ üzerinde bilgi toplama için tasarlanmış standart bir kütüphane tarafından desteklenmektedir. Bu scriptler genellikle tespit edilen her host üzerinde bulunan her bir port için bir kere çalıştırılmaktadır. –script veya -sC parametreleri kullanarak Nmap üzerindeki script’ler çalıştırılabilir.

# **Çıktı Alma**

Nmap, tarama işlemleri sonucunda elde ettiği bilgileri ekrana basar. Bu sonuçlar farklı dosya formatlarında kaydedilebilir.

# **Nmap Kurulumu**

# **Linux (Debian/Ubuntu) Ortamı**

Terminal’de “sudo apt-get install nmap” komutu çalıştırıldığında Nmap yüklenmeye başlayacaktır. Ayrıca nmap, sitesinden .rpm veya .deb uzantılı setup dosyaları indirilerek kurulabilir.

Şekil 2.1.1 – Linux Ortamında Kurulum

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap2.1.1.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap2.1.1.png)

Şekil 2.1.1’de gösterildiği gibi “sudo apt-get install nmap” komutu ile kolay bir şekilde kurulum gerçekleştirilebilir.

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap2.1.2.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap2.1.2.png)

### **Windows Ortamı**

Nmap aracının Windows ortamındaki kurulumunu sağlamak için https://nmap.org/download.html uzantılı sayfasından aşağıda gösterileceği gibi indirme işlemi gerçekleştirilecektir.

Şekil 2.2.1 – Windows Ortamı için İndirme İşlemi

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap2.2.1.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap2.2.1.png)

Daha sonra indirilen .exe uzantılı nmap setup’ı yönetici olarak çalıştırılmaktadır.

Şekil 2.2.2 – Windows Kurulum Gösterimi

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap2.2.2.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap2.2.2.png)

Kurulum işlemi bittikten sonra **Program Files(x86)\Nmap** dizinin altındaki **nmap.exe** uygulaması çalıştırılabilir. Ayrıca bu kurulumla birlikte Nmap’in grafik kullanıcı arayüzlü hali olan **zenmap** uygulaması da yüklenecektir.

Şekil 2.2.3 – Command Prompt Ekranında Nmap

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap2.2.3.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap2.2.3.png)

Şekil 2.2.3’te Command Prompt ekranı üzerinde nmap.exe çalıştırılmıştır.

Şekil 2.2.4 – Windows Ortamında ZenMap Uygulamasının Çalıştırılması

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap2.2.4.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap2.2.4.png)

Şekil 2.2.3 ve Şekil 2.2.4’te gösterildiği gibi Nmap ve Zenmap araçları Linux ortamında da mevcuttur. Terminal üzerinden **nmap** ve **zenmap** komutu çalıştırılarak görüntülenebilir.

# **Host Keşif İşlemleri**

Host keşfi, ağda bulunan sistemlere ping atılarak gerçekleştirilir. Fakat bu işlemler geniş ağlara yönelik yapıldığında veya var olan ağ üzerinde ICMP paketlerine yönelik cevap vermeyen bazı makineler olduğunda farklı yöntemler kullanılarak host keşfi yapılabilir. Hedef ağ üzerinde ping atmadan tarama işlemleri gerçekleştirilebilir. Ayrıca TCP, SYN/ACK, UDP gibi problar isteğe bağlı olarak kullanılabilir. Bu probların amacı, türüne göre problar gönderildikten sonra, alınan yanıt doğrultusunda verilen IP adresine sahip makinenin gerçekten açık olup olmadığını tespit etmektir.

# **Hedef Hostları ve Ağları Belirlemek**

Hedef hostları belirlemek için Nmap’e hedef ağın IP adresi veya Hostname bilgisi girilmelidir. Bir IP adresinin yerine IP adresi aralığı verilebilir. Ayrıca, Nmap uygulaması CIDR adreslemeyi desteklemektedir. CIDR, ip adresinden veya hostname’den sonra gelen /24, /18 vb. değerlerdir. Bu değerler sonucunda Nmap uygulaması kendi içerisinde bunun işlemlerini yaparak kaç hostun taranması gerektiğini hesaplayıp otomatik olarak tarama işlemini gerçekleştirmektedir. Örneğin, 192.168.10.0/24 IP adresini girdiğimizde 256 tane hostu taramaktadır. Ayrıca hostname adını belirterek tarama aynı şekile gerçekleştirilmektedir. Örneğin, priviasecurity.com/24 diyerek de bir tarama başlatılabilir.

Şekil 3.1 – Örnek Host Keşif Sorgusu

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.1.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.1.png)

Şekil 3.1’de gösterildiği gibi nmap uygulaması üzerinden bir IP aralığı verilmektedir. Bu tarama sonucunda verilen IP aralığında da tarama gerçekleştirilmektedir.

# **IP Listesi Belirtmek**

Bu tür tarama işlemleri genellikle geniş ağ taramalarında gerçekleştirilmektedir. Verilen yüzlerce veya binlerce IP adresini bir dosyaya kaydettikten sonra –iL parametresi kullanılarak tarama işlemleri başlatılabilir.

Şekil 3.1.1 – Nmap Uygulaması ile Liste Taraması Gerçekleştirmek

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.1.1.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.1.1.png)

Şekil 3.1.1’de gösterildiği gibi nmap komutundan sonra –iL parametresi kullanılarak içerisinde IP adresleri bulunan bir dosya belirtilir ve tarama işlemi gerçekleştirilir.

**Rastgele Hedef Seçmek**

Nmap aracı ile rastgele IP adresilerinin taranması için –iR parametresi kullanılarak yapılmaktadır.

**Kapsam Dışı Hedefleri Belirlemek**

Genellikle gözden kaçan durumlardan biri olan kapsam dışı hedefleri belirleme işlemleri, riskli işlemleri önlemektedir. Tarama yapılacak ağda, taranması istenmeyen IP adresleri –exclude parametresi ile belirtilir. Birçok IP adresi olduğu durumlarda, IP adresleri bir dosyaya kaydedildikten sonra **–excludefile** parametresi ile bu işlemler gerçekleştirilmektedir.

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.1.3.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.1.3.png)

Şekil 3.1.3’de gösterildiği gibi **–exclude** parametresinden sonra belirtilen IP adresleri tarama dışında tutulmaktadır. Ayrıca taranması istenmeyen IP adresleri birden fazla olduğunda **–excludefile** parametresi kullanılabilir.

Şekil 3.14’te, taranacak bir ağdaki IP adreslerinin listelenmesi için –sL parametresi kullanılır.

Şekil 3.1.4 – Nmap ile -sL Parametresinin Kullanılması

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.1.4.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.1.4.png)

Eğer birbirinden farklı hedeflerin IP adresleri veya hostnameleri taranmak istenirse IP adresleri arasında boşluk bırakılarak tarama işlemi gerçekleştirilebilir. Şekil 3.1.5’de gösterilmiştir.

Şekil 3.1.5 – Nmap ile Farklı Hedeflerin Bir Anda Taranması

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.1.5.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.1.5.png)

# **Hedef Kuruluşun IP Adresinin Bulunması**

Genellikle bir taramadan önce ana domain bilgisi verilmektedir. Verilen domain adresinin IP bilgileri üzerinden tarama işlemleri gerçekleştirilebilir.

### **DNS Bilgilerinin Elde Edilmesi**

DNS’in birincil amacı, domain adlarını IP adreslerine çözümlemektir. Bu nedenle DNS bilgilerini araştırılması gerekmektedir. Şekil 3.2.1’de gösterilmiştir.

Şekil 3.2.1 – DNS Kayıt Türlerinin Sorgulanması

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.2.1.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.2.1.png)

Şekil 3.2.1’de gösterildiği gibi linux ortamında DNS kayıt türlerinin öğrenilmesi için host yardımcı uygulaması kullanılarak nameserver’lar hakkında bilgi elde edilmektedir. Ayrıca zone transferi ile ilgili işlemler Şekil 3.2.2’de gösterilmektedir.

Şekil 3.2.2 – Zone Transfer İşleminin Kontrolü

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.2.2.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.2.2.png)

Şekil 3.2.2 ‘de gösterildiği gibi zone transfer işleminin başarılı veya hatalı olduğu gösterilmektedir. Bir domainin IP adresi var olan kapsam içerisinde var mı yok mu gibi işlemleri öğrenmek için DNS çözümlemesi, traceroute ve ilgili IP adres kayıtları için whois kullanılmaktadır.

Şekil 3.2.3 – Nmap ile Traceroute Kullanımı

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.2.3.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.2.3.png)

Şekil 3.2.3’te gösterildiği gibi hedef domaine yönelik tarama gerçekleştirildiğinde –tracetoute parametresi kullanılarak hedef IP adresine kadarki ara IP adresileri gösterilecektir. Ayrıca bir IP adresini kullanarak bilgi toplama işlemi Şekil 3.2.4’te de gösterilmektedir.

Şekil 3.2.4 – Hedef Hakkında Bilgi Toplama

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.2.4.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.2.4.png)

Şekil 3.2.4’te gösterildiği gibi whois ile hedef IP adresi hakkında bilgiler getirmektedir.

# **DNS Çözümlemesi**

Host keşiflerinde DNS çözümlemesi işleminin kullanılması büyük önem taşımaktadır. Nmap, host keşif problarına yanıt veren her IP adresi için DNS çözümlemesi gerçekleştirmektedir. DNS çözümlemesini kontrol etme işleminde 4 parametre kullanılmaktadır. Bu parametreler aşağıdaki gibidir:

**(-n) Parametresi:** Nmap uygulamasının bulduğu IP adreslerine yönelik Reverse DNS çözümlemesi yapmamasını sağlamaktadır. Bu parameter genellikle tarama süresini azaltmaktadır.

**(-R) Parametresi:** Nmap uygulamasının elde ettiği bütün IP adreslerine yönelik Reverse DNS çözümlemesi yapmasını sağlamaktadır. Varsayılan olarak Reverse DNS çözümlemesi yalnızca açık hostlara karşı gerçekleştirilmektedir.

**(–system-dns) Parametresi:** Nmap uygulaması, varsayılan olarak makinemizde yapılandırılmış name server’lara sorgu gönderip yanıtları dinleyerek IP adreslerini çözümlemektedir. Performansı arttırmak için birçok istek parallel olarak yapılmaktadır. Bunun yerine ise bu parameter kullanılmaktadır. –system-dns parametresi IPv6 için kullanılmaktadır.

**(–dns-server) Parametresi:** Nmap uygulaması, varsayılan olarak DNS sunucuları resolv.conf(Unix) dosyasından veya registry(Win32)’den belirtmektedir. Birden çok DNS sunucusu kullanıldığında daha hızlıdır. İstekler internetteki özyinelemeli DNS sunucusundan hemen hemen ayrılabileceği için gizliliği de arttırabilmektedir.

Şekil 3.3’te DNS çözümlemesine yönelik uygulanmıştır.

Şekil 3.3 – Nmap ile –system-dns Parametresinin Kullanılması

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.3.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.3.png)

Şekil 3.3’te gösterildiği gibi DNS çözümleme işlemi gerçekleştirilmiştir. Yukarıda belirtilen parametreler kullanılarak sonuçlar elde edilmiştir.

# **Host Keşif Kontrolleri**

Host keşif kontrollerinde kullanılan parametreler sonucunda, hedeflerin açık/kapalı olma durumu tespit edilebilir. Makinelere gönderilen probların yanıtlarının kontrol edilmesi gerekmektedir.

### **Liste Taraması (-sL)**

Hedef IP adreslerinin kontrolünü sağlamak amacıyla kullanılır. Hedef makinelere herhangi bir paket gönderilmeden belirtilen ağ üzerindeki hostların listelenmesini sağlayan bir host keşif şeklidir.

Şekil 3.4.1 – Nmap ile Liste Taramasının Gerçekleştirilmesi

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.4.1.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.4.1.png)

Şekil 3.4.1’de gösterildiği gibi –sL parametresi ile liste taraması gerçekleştirilmektedir. Ayrıca –Pn parametresi kullanılarak ping tarama yapıp taramadaki işlevselliğin devam etmesi sağlanılacaktır.

Bir ön liste taraması, hangi hedeflerin tarandığını doğrulamaya yardımcı olmaktadır. Gelişmiş bir liste taramasının nedenlerinden biri gizliliktir. Bazı durumlar IDS sistemlerin tetiklenmesine neden olmaktadır. Liste taraması bu tür tetiklenmelere sebep vermeden hangi makinelerin hedef makine olacağı konusunda bilgi sağlamaktadır. Hedeflerin Reverse DNS çözümleme isteklerini fark etmeleri durumunda –dns-server parametresini kullanarak isimsiz özyinelemeli DNS sunucuları arasında geçiş yapılabilmektedir.

# **Port Taramasını Devre Dışı Bırakmak (-sn)**

Nmap, bir ağ üzerinde aktif hostların hızlı bir şekilde tespit edilmesi için –sn parametresini kullanır. Tespit edilen hostların IP adresleri belirtilmektedir. Bu işleme “ping scan” denir. Port taraması gerçekleştirmeden Nmap uygulamasının içerisindeki scriptlerden ve traceroute problarından faydalanılmaktadır. Ping Scan, liste taramasına göre daha aktif bir tarama türüdür. Bu tarama türü ile hedeflerin IP adresleri ve hostname bilgileri elde edilir. Şekil 3.4.2’de Nmap ile ping taraması gösterilmektedir.

Şekil 3.4.2 – Nmap Uygulaması ile Ping Scan İşlemi

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.4.2.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.4.2.png)

Şekil 3.4.2’de –sn parametresi kullanılarak ping taraması gerçekleştirilmiştir. Ekran görüntüsünde görüldüğü gibi port taraması yapılmamıştır.

# **Ping Devre Dışı Bırakmak (-Pn)**

Nmap uygulaması ile pingsiz tarama gerçekleştirilmesi, host keşfinin yapılmasının istenmemesi anlamına gelmektedir. Bir ağdaki bütün makineleri sırasıyla diğer işlemlere tabi tutulmaktadır. Host keşfi atlanılmaktadır. Bir ağda verilen IP adresleri üzeride host keşfi yapıldığında pingsiz taramaya göre zaman kaybı meydana gelecektir. Ayrıca nmap ile –Pn parametresi kullanıldığında pingsiz tarama işlemleri gerçekleştirilmektedir. Şekil 3.4.4’te gösterilmiştir.

### **Bazı Parametreler**

**(–disable-arp-ping) Parametresi:** Genellikle host keşfinde ARP paketleri gönderilip alınan yanıtlar doğrultusunda hostun aktif olup olmadığı tespit edilmektedir. Bu seçenek, bir yönlendiricinin bütün ARP isteklerine özel olarak yanıt verdiği ve hedefin ARP taraması yapılıyormuş gibi görünmesini sağlayan ağlarda kullanılmaktadır. Varsayılan ARP taramasını devre dışı bırakmaktadır. Şekil 3.4.4’te gösterilmektedir.

Şekil 3.4.4 – Nmap ile ARP ve ND Ping Taramasını Pasif Tutarak Tarama

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.4.4.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.4.4.png)

**(–resolve-all) Parametresi:** Bir hostname hedefi birden fazla adrese çözümlenirse, hepsi taranmaktadır. Varsayılan olan, yalnızca ilk çözülen adresi taramaktır.

**(–traceroute) Parametresi:** Hedefe ulaşması en uygun portu ve protokolü belirlemek için tarama sonuçlarından gelen bilgileri kullanarak tarama sonrasında gerçekleştirilmektedir. Bağlantı taramaları (-sT) ve boşta taramalar (-sl) dışındaki bütün tarama türleriyle çalışmaktadır. Traceroute, ICMP zamanını aşmak için tarayıcı ve hedef host arasındaki ara atlama noktalarından aşılmış mesajları almak için düşük TTL (yaşam süresi) sürüme sahip paketler göndererek çalışmaktadır. Standart traceroute uygulamaları 1 TTL ile başlayıp hedef hosta ulaşana kadar arttırmaktadır. Bu TTL işlemleri, Nmap uygulaması üzerinde geriye doğru yapıldığında sürecin hızlandırılması için akıllı önbellek algoritması kullanılmıştır.

# **Host Keşif Teknikleri**

Genellikle bir ğ üzerinde bulunan makinelerin aktif olup olmadığını tespit edilmek açacıyla makinelere ICMP echo isteği gönderilmektedir. Daha sonra yapılan istek sonucunda bir yanıt alınmaktadır. Alınan yanıt sonucunda makinenin aktif veya pasif olduğu tespit edilmektedir. Güvenlik duvarları bu istekleri nadiren engellemektedir. Bundan dolayı host keşif çalışmaları için kullanılan bir tekniktir. Şekil 3.5’de –sn –PE parametreleri ICMP ping taramasını belirtmektedir. –R parametresi ise tüm makinelere yönelik reverse DNS çözümlemesi yapmasını istemektedir.

Şekil 3.5 – Nmap Host Keşif Teknikleri

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.5.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.5.png)

### **TCP SYN Ping**

- PS parametresi kullanılarak, SYN bayraklı boş bir TCP paketi gönderilmektedir. Varsayılan olarak 80. port hedef alınmaktadır. Bu bayrak uzak bir sistem ile bağlantı kurulmak istendiğini göstermektedir. Port açık olursa SYN/ACK paketiyle yanıt verilecektir. Üç el sıkışma tamamlayıp bir ACK paketi yerine RST paketini göndererek bağlantıyı düşürecektir. Alınan RST ve SYN/ACK yanıtları makinenin açık olduğunu belirtmektedir.

Şekil 3.5.1 – TCP SYN probu ile host keşfi

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.5.1.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.5.1.png)

### **TCP ACK Ping**

- PA parametresi kullanılarak gerçekleştirilen bir host keşif tekniğidir. SYN ping’e benzemektedir. Tek fark bayrakların değişik olmasıdır. Hedef sisteme ACK bayraklı TCP paketi gönderilir. Eğer hedef sistem açıksa RST paketi ile yanıt verir. 80. port hedef alınarak yapılmaktadır. –PS parametresi ile yapılan taramalar engellendiğinde kullanılmaktadır.

Şekil 3.5.2 – Nmap ile TCP ACK Ping tekniğinin kullanımı

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.5.2.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.5.2.png)

# **UDP Ping**

UDP paketleri kullanılarak sistemlerin aktif olup olmadığı tespit edilir. –PU parametresi kullanılarak gerçekleştirilmektedir. –PS ve –PA parametreleri ile aynı formattadır. Varsayılan olak 40. Ve 125. Portlar kullanılmaktadır. Genellikle gönderilen paketler boştur. Fakat 53. Ve 161. Portlar genel bağlantı noktaları olduğu için özel payload gönderilmektedir. **–data-length** parametresi, tüm portlar için ratsgele payload göndermektedir. Bu tarama türünün en önemli avantajı güvenlik duvarını atlatması ve TCP portlarını tarayan filtreleri olmasıdır.

### **ICMP Ping Türleri**

Nmap, host keşiflerinde ICMP paketlerini kullanır. Hedef hostlara ICMP type 8 (Echo isteği) gönderip ICMP type 0(Echo yanıtı) beklemektedir. Fakat birçok güvenlik duvarı bu isteği engellemektedir. -PE parametresi kullanılarak ICMP echo isteği gerçekleştirilir. Bu işlem ICMP ping sorgusu olarak bilinmektedir. Ayrıca açık hostların keşfi zaman damgası ve adres damgası üzerinden de tespit edilebilmektedir. Bu işlemler –PP ve –PM parametreleri kullanılarak gerçekleştirilir.

Şekil 3.5.4 – ICMP Ping Türleri ile Tarama Gerçekleştirilmesi

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.5.4.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.5.4.png)

### **IP Protocol Ping**

IP paketlerinin içerisindeki IP başlığında belirtilen protokol numarası ile yapılan bir tarama türüdür. Herhangi bir protokol belirtilmediği zaman ICMP, IGMP, IP-inIP protokolleri için birden fazla IP paketi gönderilmektedir. Bu yöntemde kullanılan prob ile aynı protokolü kullanan yanıtlar üzerinde veya hedef hosta yönelik erişilemediğini belirten ICMP paketlerine bakılarak bir makinenin çalışıp çalışılmadığı tespit edilmektedir.

# **ARP Ping**

En yaygın kullanılan taramalardan biridir. Bu tarama işlemi –PR parametresi kullanılarak gerçekleştirilir. Bu tarama ham bir IP paketi gönderilerek gerçekleştirilmektedir. Böylece hedef IP adresine karşılık gelen makinenin fiziksel adresi tespit edilir.

Şekil 3.5.6 – Çevrimdışı hedefe yönelik IP Pİng Taraması ve ARP Ping Taraması

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.5.6.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.5.6.png)

Şekil 3.5.6’da gösterildiği gibi tarama örnekleri gerçekleştirilmiştir. Bu tarama örneğinin ilkinde **–send-ip** parametresi kullanılmasıyla, yerel ağ olmasına rağmen IP seviyesinde paketler gönderilmektedir. İlk örnek 3.09 saniye sürmüştür. Yalnızca bir hedefe yönelik yapılan bir tarama olduğu için taramanın sonuçlanması kısa sürmüştür. Fakat kurumsal bir yerel ağdaki makine sayısının fazlalığı bu süreyi arttırmaktadır. İşletim sistemi hosttan vazgeçmediği için bir saniye arayla üç ARP isteği göndermektedir. İkinci örnekte ise ARP taraması 0.47 saniyede gerçekleştirilmiştir. Ağ yöneticileri normal şartlarda ping paketlerini engellemektedir. Fakat ARP istekleri veya yanıtları genellikle engellenmemektedir. Ayrıca bu taramalar gerçekleştirildiğinde **–spoof-mac** parametresini kullanılarak tarama yapan makinenin MAC adresi gizlenebilmektedir.

# **SCTP INIT Ping**

Bu tarama türü –PY kullanılarak gerçekleştirilmektedir. Bu parametre kullanılarak içerisinde INIT öbeği bulunan bit SCTP paketi gönderilmektedir. Varsayılan olarak 80. portu hedef almaktadır. Örnek olarak “–PY22,80” gibi bir parametre ile 22. ve 80. portlar ile bağlantı kurulacaktır. Portlar açık ise INIT-ACK yanıtı dönmektedir. Nmap, bu yanıta işlevsel bir SCTP paketi göndermek yerine ABORT yanıtını vererek bağlantıyı bitirmektedir. Böylece bu iki yanıt ile hedef makine üzerindeki portların açık olduğu tespit edilmektedir.

# **Host Keşif Stratejileri**

Nmap aracı, host keşiflerini daha iyi şekilde tespitinin sağlanması için belirli parametreleri kullanmaktadır. Bu parametreler host keşiflerinde kullanıcının yapmak istediği tarama türlerine göre kullanılmaktadır. Bu parametreler aşağıda belirtilmiştir.

**(-v/–verbose) Parametresi**

Nmap aracında bulunan bu parametre, tarama sonucunda gelen çıktının ayrıntılı bir şekilde gelmesini sağlamaktadır. Bu doğrultuda host hakkında ek bilgiler verilmektedir.

Şekil 3.6.1 – Verbose Parametresinin Kullanımı

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.6.1.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.6.1.png)

**(–source-port <port no>) Parametresi**

Firewall yöneticileri, DNS ve FTP portlarını açık tutmak için firewall üzerinden özel kurallar oluşturmaktadır. Fakat firewall bypass işlemlerinden biri de source port manipülasyon işlemidir.

**(–data-length <length>) Parametresi**

Bu parametre ile her pakete rastgele olarak veri eklenmektedir. Ayrıca TCP, UDP ve ICMP gibi tarama türleriyle birlikte kullanılabilmektedir. Birçok IDS sistemini atlatmak için kullanılan yöntemlerden biridir. Örneğin, data değeri 56 olan bir echo istek paketine rastgele olarak 32 değeri atanırsa, IDS sistemi paketin bir Windows işletim sistemine sahip bir makineden geldiğini işaretler. Fakat gelen istek paketindeki gerçek data değerinin 56 olması isteğin bir Linux işletim sistemine sahip makineden geldiğini gösterebilir.

Şekil 3.6.3 – (–data-length) Parametresinin Kullanımı

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.6.3.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.6.3.png)

**(–ttl <value>) Parametresi**

Giden TTL değerinin ayarlanması, IPv4 düzeyindeki ping taramalarında kullanılmaktadır. Yapılan taramanın yerel ağ sınırları içerisinde yapılmasını sağlamayı hedeflemektedir. Giden –ttl değeri azaltılarak, herhangi bir döngü ile karşılaşıldığında yönlendirici CPU’sunun işlem yükünün azaltılması hedeflenmektedir.

Şekil 3.6.4 – TTL Parametresinin Kullanımı

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.6.4.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.6.4.png)

### **Hazır Zamanlama Parametreleri**

Ping taramasını hızlandırıp sonuçların alınmasına yönelik yapılmış bir parametre düzenlemesidir. –T parametresi ile kullanılır. Hazır zamanlama şablonları, **paranoid(0), sneaky(1), polite(2), normal(3), aggressive(4) ve insane(5)** olarak 6 tanedir.

Şekil 3.6.5 – Zamanlama Parametresinin Kullanılması

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.6.5.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.6.5.png)

**(–max/min-parallelism <value>) Parametreleri**

Yapılan taramalarda taranacak makinelerin paralel bir şekilde taramasını sağlamak için düzenlenmiş bir parametredir. Parametreyi kullanarak <value> değeri olarak makine sayısı belirtilmektedir.

**(–min/max/initial-rtt-timeout <time>) Parametreleri**

Bu parametreler, Nmap aracının yaptığı istek sonucunda gelecek yanıt paketinin ne kadar bekleyeceğini kontrol etmektedir.

### **Çıktı Parametreleri**

- oA, -oN, -oG, -oX vb. parametrelerden oluşur. Örneğin, -oX parametresinin kullanılması ile Nmap çıktıları XML formatında oluşturulur.

**(–randomize-hosts) Parametresi**

Ağda bir tarama yapılırken, –randomize-hosts parametresinin kullanılması taramayı belirginsizleştirir. Bu yöntem IDS ve IPS sistemlerinden kaçınmak için kullanılır. Nmap, varsayılan olarak bir ağdaki makineleri ardışık olarak tarar. Bazı IDS ve IPS sistemleri ise, yapılan taramayı tespit edip engelleyebilir.

**(–reason) Parametresi**

Varsayılan taramalar sonucunda gelen çıktıda hedef portun çalışır durumda olup olmadığını göstermektedir. Bu parametre ile nmap taramasında hedef makinesinin hangi keşif testlerine yanıt verdiğini açıklamaktadır. Nmap çalışma sırasında yanıt paketi olarak bir ICMP echo paketi yanıtı rapor edilebilir. Fakat ikinci bir tarama sonucunda önce bir RST paketi alınabilir ve Nmap aracının bunu bildirmesine neden olabilir. Bundan dolayı detaylı olarak hedef makinenin ne tür yanıtlar verip vermediğini görebilmek için bu parametrenin kullanılması fayda sağlamaktadır.

Şekil 3.6.10 – Reason Parametresinin Kullanılması

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.6.10.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.6.10.png)

**(–packet-trace) Parametresi**

Nmap, –packet-trace parametresini kullanarak tarama süresince neler yapıldığını detaylı olarak gösterir. –packet-trace parametresi, Sıra numaraları, TTL değerleri ve TCP bayrakları gibi ayrıntılar dâhil olmak üzere, alınan ve gönderilen her paketin gösterilmesini sağlar.

**(-D <decoy1, decoy2,,,) Parametresi**

Decoy olarak tanımlanan IP adresleri, saldırgan IP adresini gizlemek için kullanılan sahte IP adresleri olarak tanımlanabilir. Resim 3.6.12’deki saldırgan IP adresi, 192.168.16.163’tür. Fakat, -D parametresi ile verilen 192.168.16.138, 192.168.16.2 gibi sahte IP adresleri kullanılarak saldırgan IP ile tarama yapılmıştır. Böylelikle ağı izleyen yetkililerin saldırganı tespit etmesi zorlaşır.

Şekil 3.6.12 – Decoy Parametresinin Kullanıması

![https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.6.12.png](https://www.priviasecurity.com/wp-content/uploads/2020/01/nmap3.6.12.png)

**(-6) Parametresi**

Taramalarda ipv4 adresi yerine ipv6 kullanmayı sağlar.

**(-S <source IP address>, -e <sending device name>) Parametreleri**

Kaynak IP adresini ve gönderen cihazın adını belirterek yapılan tarama türleridir.

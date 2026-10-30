GrassFX Proje Bilgileri ve Söz Dizimi Analizi

---

1. Genel Bilgiler ve Sürüm Geçmişi  
- Proje İlişkisi: GrassFX, GrassProject bünyesinde olan alt projedir.  
- Amaç: Kolayca grafik arayüz ve program yazabilmek.  
- Desteklenen İşletim Sistemi: GNU/Linux.  
- Programlama Dili: C

Sürüm Geçmişi

- GrassFX 0.01: 17 Eylül 2026  
- GrassFX 0.02: 20 Eylül 2026  
- GrassFX 0.03: 27 Eylül 2026  
- GrassFX 0.1: 18 Ekim 2026  
- GrassFX 0.2: 30 Ekim 2026

---

2. Kurallar ve Söz Dizimi Yapısı

Kurallar

- Yazım Biçimi: Snake\_case kullanılır.  
- Kütüphane İsmi: Mutlaka sıralamanın en başında yer alır.  
- Özellik: En sonda bulunur.  
- Eylem: Mutlaka özelliğin solunda yer alır.  
- Anlaşılabilirlik: Fonksiyonlar anlaşılır olmalıdır.  
- Özelliksiz Durum: Eğer özelliğe gerek kalmıyorsa sonda eylem olabilir (özelliksiz olarak).  
- Genel Fonksiyonlar: Kütüphane ismi ve eylem içerebilir.

Söz Dizimi ve Fonksiyon Açıklaması

Örnek fonksiyon: gfx\_object\_add\_button(Evas\_Object \*parent);

Öğe Analizi

- gfx: Kütüphane  
- object: Nesne  
- add: Eylem  
- button: Özellik  
- Evas\_Object \*parent: Parametre

# 

# **GrassFX Kütüphanesi Dokümantasyonu**

Bu doküman, EFL (Enlightenment Foundation Libraries) tabanlı **GrassFX** soyutlama katmanının tüm fonksiyon imzalarını, anlamlarını ve parametre detaylarını içermektedir.  
---

## **1\. Ortak ve Genel Fonksiyonlar (Common Functions)**

| Dönüş Tipi | Fonksiyon Prototipi | İşlevi (Ne İşe Yarar?) | Parametreler ve Alabileceği Değerler |
| :---- | :---- | :---- | :---- |
| `void` | `gfx_init(int argc, char **argv)` | GrassFX kütüphanesini ve temel bağımlılıklarını ilklendirir, komut satırı argümanlarını ayrıştırır. | ***argc:*** Komut satırı argüman sayısı (\>= 0). ***argv:*** Komut satırı argüman dizisi (*NULL* veya *char\*\** dizisi). |
| `void` | `gfx_run(void)` | Ana grafik arayüz olay döngüsünü başlatır ve uygulama sonlanana kadar engeller. | *Parametre almaz.* |
| `void` | `gfx_exit(void)` | Çalışan grafik döngüsünden çıkış sinyali verir ve uygulamayı sonlandırma sürecini başlatır. | *Parametre almaz.* |
| `void` | `gfx_shutdown(void)` | Kütüphaneyi kapatır ve ayrılan tüm sistem kaynaklarını temizler. | *Parametre almaz.* |

---

## **2\. Pencere Yönetimi (Window Functions)**

| Dönüş Tipi | Fonksiyon Prototipi | İşlevi (Ne İşe Yarar?) | Parametreler ve Alabileceği Değerler |
| :---- | :---- | :---- | :---- |
| `Evas_Object *` | `gfx_object_add_feature_window(const char *name, const char *title)` | Önceden tanımlı temel özelliklerle donatılmış yeni bir ana uygulama penceresi oluşturur. | ***name:*** Dahili tanımlayıcı (boş olmayan geçerli *string* dizgisi). ***title:*** Pencere başlığı metni (geçerli *string* veya boş *string*). |
| `Evas_Object *` | `gfx_object_add_standard_window(Evas_Object *parent, const char *name, Elm_Win_Type type)` | Belirtilen pencere tipinde standart bir Elementary pencere nesnesi yaratır. | ***parent:*** Ebeveyn pencere göstericisi (*Evas\_Object\** veya bağımsız pencere için *NULL*). ***name:*** Pencere adı (geçerli *string*). ***type:*** Pencere türü (*ELM\_WIN\_BASIC*, *ELM\_WIN\_DIALOG* vb. *Elm\_Win\_Type* enum değerleri). |
| `void` | `gfx_window_set_title(Evas_Object *object, const char *title)` | Pencerenin başlık çubuğunda görünecek başlık metnini günceller. | ***object:*** Geçerli pencere nesnesi (*Evas\_Object\**). ***title:*** Görüntülenecek başlık dizgisi (*const char\** veya *NULL*). |
| `void` | `gfx_window_set_autodel(Evas_Object *object, Eina_Bool autodel)` | Pencere kapatıldığında nesnenin otomatik olarak bellekten silinmesini ayarlar. | ***object:*** Geçerli pencere nesnesi (*Evas\_Object\**). ***autodel:*** Otomatik silinme bayrağı (*EINA\_TRUE* veya *EINA\_FALSE*). |
| `void` | `gfx_window_set_center(Evas_Object *object, Eina_Bool h, Eina_Bool v)` | Pencereyi ekranda yatayda ve/veya dikeyde tam merkeze hizalar. | ***object:*** Geçerli pencere nesnesi (*Evas\_Object\**). ***h:*** Yatayda ortalama (*EINA\_TRUE/EINA\_FALSE*). ***v:*** Dikeyde ortalama (*EINA\_TRUE/EINA\_FALSE*). |
| `void` | `gfx_window_set_minsize(Evas_Object *object, int w, int h)` | Pencerenin alabileceği asgari piksel boyutlarını sınırlar. | ***object:*** Geçerli pencere nesnesi (*Evas\_Object\**). ***w:*** Asgari genişlik (piksel, \>= 0). ***h:*** Asgari yükseklik (piksel, \>= 0). |
| `void` | `gfx_window_set_fullscreen(Evas_Object *object, Eina_Bool full)` | Pencereyi tam ekran durumuna geçirir veya tam ekrandan çıkarır. | ***object:*** Geçerli pencere nesnesi (*Evas\_Object\**). ***full:*** Tam ekran durumu (*EINA\_TRUE* açar, *EINA\_FALSE* kapatır). |
| `void` | `gfx_window_set_active(Evas_Object *object)` | Pencereyi sistem düzeyinde aktif pencere yapar ve klavye/fare odağını ona taşır. | ***object:*** Aktif yapılacak pencere nesnesi (*Evas\_Object\**). |
| `void` | `gfx_window_set_iconified(Evas_Object *object, Eina_Bool iconified)` | Pencereyi simge durumuna küçültür (minimize) veya simge durumundan çıkartır. | ***object:*** Geçerli pencere nesnesi (*Evas\_Object\**). ***iconified:*** Küçültme durumu (*EINA\_TRUE* simge durumuna alır, *EINA\_FALSE* geri yükler). |
| `void` | `gfx_window_set_sticky(Evas_Object *object, Eina_Bool sticky)` | Pencerenin tüm sanal masaüstlerinde sabit olarak görünmesini sağlar. | ***object:*** Geçerli pencere nesnesi (*Evas\_Object\**). ***sticky:*** Sabit kalma durumu (*EINA\_TRUE* sabitler, *EINA\_FALSE* tek masaüstüne bağlar). |
| `void` | `gfx_window_proportion_scale(Evas_Object *object, Evas_Object *subobject)` | Alt nesneyi pencere en-boy oranına göre orantılı olarak yeniden ölçeklendirir. | ***object:*** Ebeveyn pencere (*Evas\_Object\**). ***subobject:*** Ölçeklenecek alt bileşen (*Evas\_Object\**). |
| `void` | `gfx_window_set_autohide(Evas_Object *object, Eina_Bool autohide)` | Kapatma olayı geldiğinde pencerenin yok edilmeyip sadece gizlenmesini sağlar. | ***object:*** Geçerli pencere nesnesi (*Evas\_Object\**). ***autohide:*** Otomatik gizleme bayrağı (*EINA\_TRUE* veya *EINA\_FALSE*). |
| `void` | `gfx_window_set_borderless(Evas_Object *object, Eina_Bool borderless)` | Pencerenin kenarlıklarını ve başlık çubuğunu gizler veya görünür kılar. | ***object:*** Geçerli pencere nesnesi (*Evas\_Object\**). ***borderless:*** Kenarlıksız pencere tercihi (*EINA\_TRUE* kenarlıksız, *EINA\_FALSE* standart çerçeveli). |
| `Eina_Bool` | `gfx_window_get_borderless(const Evas_Object *object)` | Pencerenin kenarlıksız modda olup olmadığını sorgular. | ***object:*** İncelenecek pencere (*const Evas\_Object\**). |
| `void` | `gfx_window_set_shaped(Evas_Object *object, Eina_Bool shaped)` | Pencerenin piksellerine göre özel şekilli (transparan boşluklu) çizilmesini ayarlar. | ***object:*** Geçerli pencere nesnesi (*Evas\_Object\**). ***shaped:*** Şekilli pencere modu (*EINA\_TRUE/EINA\_FALSE*). |
| `Eina_Bool` | `gfx_window_get_shaped(const Evas_Object *object)` | Pencerenin şekilli (shaped) modda olup olmadığını döndürür. | ***object:*** İncelenecek pencere (*const Evas\_Object\**). |
| `void` | `gfx_window_set_alpha(Evas_Object *object, Eina_Bool alpha)` | Pencere kanvası için alfa kanalı şeffaflık desteğini etkinleştirir veya kapatır. | ***object:*** Geçerli pencere nesnesi (*Evas\_Object\**). ***alpha:*** Alfa kanalı aktifliği (*EINA\_TRUE* şeffaflığı açar, *EINA\_FALSE* kapatır). |
| `Eina_Bool` | `gfx_window_get_alpha(const Evas_Object *object)` | Pencerenin alfa kanalı şeffaflığının açık olup olmadığını döndürür. | ***object:*** İncelenecek pencere (*const Evas\_Object\**). |

---

## **3\. Widget Ekleme Fonksiyonları (Widget Addition Functions)**

Bu gruptaki tüm fonksiyonlar verilen ebeveyn (`parent`) üzerine ilgili arayüz bileşenini ekleyip nesne işaretçisini döndürür:

| Dönüş Tipi | Fonksiyon Prototipi | İşlevi (Ne İşe Yarar?) | Parametreler ve Alabileceği Değerler |
| :---- | :---- | :---- | :---- |
| `Evas_Object *` | `gfx_object_add_button(Evas_Object *parent)` | Tıklanabilir standart bir arayüz butonu oluşturur ve nesne işaretçisini döndürür. | ***parent:*** Düğmenin ekleneceği ebeveyn nesne (geçerli *Evas\_Object\**). |
| `Evas_Object *` | `gfx_object_add_checkbutton(Evas_Object *parent)` | İki durumlu (seçili/seçili değil) onay kutusu bileşeni oluşturur. | ***parent:*** Bileşenin ekleneceği ebeveyn nesne (geçerli *Evas\_Object\**). |
| `Evas_Object *` | `gfx_object_add_radiobutton(Evas_Object *parent)` | Tekli seçim sunan radyo düğmesi bileşeni oluşturur. | ***parent:*** Bileşenin ekleneceği ebeveyn nesne (geçerli *Evas\_Object\**). |
| `Evas_Object *` | `gfx_object_add_entry(Evas_Object *parent)` | Kullanıcının yazı girebileceği metin giriş alanı oluşturur. | ***parent:*** Bileşenin ekleneceği ebeveyn nesne (geçerli *Evas\_Object\**). |
| `Evas_Object *` | `gfx_object_add_slider(Evas_Object *parent)` | Belirli bir aralıkta kaydırma ile sayısal değer seçimi sağlayan kaydırma çubuğu oluşturur. | ***parent:*** Bileşenin ekleneceği ebeveyn nesne (geçerli *Evas\_Object\**). |
| `Evas_Object *` | `gfx_object_add_spinner(Evas_Object *parent)` | Artırma/azaltma butonlarıyla sayısal değer seçimi sağlayan sayaç (spinner) bileşeni oluşturur. | ***parent:*** Bileşenin ekleneceği ebeveyn nesne (geçerli *Evas\_Object\**). |
| `Evas_Object *` | `gfx_object_add_combobox(Evas_Object *parent)` | Açılır liste kutusu (combo box) bileşeni oluşturur. | ***parent:*** Bileşenin ekleneceği ebeveyn nesne (geçerli *Evas\_Object\**). |
| `Evas_Object *` | `gfx_object_add_label(Evas_Object *parent)` | Biçimlendirilmiş veya düz metin görüntülemeye yarayan etiket bileşeni oluşturur. | ***parent:*** Bileşenin ekleneceği ebeveyn nesne (geçerli *Evas\_Object\**). |
| `Evas_Object *` | `gfx_object_add_icon(Evas_Object *parent)` | Sistem temasına uygun standart ikon nesnesi oluşturur. | ***parent:*** Bileşenin ekleneceği ebeveyn nesne (geçerli *Evas\_Object\**). |
| `Evas_Object *` | `gfx_object_add_image(Evas_Object *parent)` | Resim dosyalarını yükleyip görüntülemeye uygun görsel bileşeni oluşturur. | ***parent:*** Bileşenin ekleneceği ebeveyn nesne (geçerli *Evas\_Object\**). |
| `Evas_Object *` | `gfx_object_add_progressbar(Evas_Object *parent)` | Süreç/işlem ilerleme durumunu gösteren ilerleme çubuğu bileşeni oluşturur. | ***parent:*** Bileşenin ekleneceği ebeveyn nesne (geçerli *Evas\_Object\**). |
| `Evas_Object *` | `gfx_object_add_bubble(Evas_Object *parent)` | Konuşma/bilgi balonu biçiminde arayüz kapsayıcısı oluşturur. | ***parent:*** Bileşenin ekleneceği ebeveyn nesne (geçerli *Evas\_Object\**). |
| `Evas_Object *` | `gfx_object_add_clock(Evas_Object *parent)` | Canlı saat ve zamanı gösteren saat bileşeni oluşturur. | ***parent:*** Bileşenin ekleneceği ebeveyn nesne (geçerli *Evas\_Object\**). |
| `Evas_Object *` | `gfx_object_add_calendar(Evas_Object *parent)` | Tarih seçimi ve takvim görünümü sağlayan takvim bileşeni oluşturur. | ***parent:*** Bileşenin ekleneceği ebeveyn nesne (geçerli *Evas\_Object\**). |
| `Evas_Object *` | `gfx_object_add_separator(Evas_Object *parent)` | Bileşenler arasında dikey veya yatay görsel bölme çizgisi (ayraç) ekler. | ***parent:*** Bileşenin ekleneceği ebeveyn nesne (geçerli *Evas\_Object\**). |
| `Evas_Object *` | `gfx_object_add_popup(Evas_Object *parent)` | Kullanıcı etkileşimi için bildirim/uyarı modal penceresi (popup) oluşturur. | ***parent:*** Bileşenin ekleneceği ebeveyn nesne (geçerli *Evas\_Object\**). |

---

## **4\. Konteyner ve Düzen Fonksiyonları (Box, Grid, Table, Scroller, Frame)**

### **Box Fonksiyonları**

| Dönüş Tipi | Fonksiyon Prototipi | İşlevi (Ne İşe Yarar?) | Parametreler ve Alabileceği Değerler |
| :---- | :---- | :---- | :---- |
| `Evas_Object *` | `gfx_object_add_box(Evas_Object *parent)` | İçerisine eklenen elemanları tek bir doğrultuda düzenleyen kutu kapsayıcısı yaratır. | **parent:** Ebeveyn nesne göstericisi (geçerli Evas\_Object\*). |
| `void` | `gfx_box_set_horizontal(Evas_Object *object, Eina_Bool horizontal)` | Kutunun yerleşim doğrultusunu yatay veya dikey olarak yapılandırır. | **object:** Kutu nesnesi (Evas\_Object\*). **horizontal:** Yerleşim yönü (EINA\_TRUE yatay, EINA\_FALSE dikey). |
| `Eina_Bool` | `gfx_box_get_horizontal(const Evas_Object *object)` | Kutunun yatay dizilimde olup olmadığını sorgular. | **object:** Kutu nesnesi (const Evas\_Object\*). |
| `void` | `gfx_box_pack_start(Evas_Object *object, Evas_Object *child)` | Alt nesneyi kutunun en başına ekler. | **object:** Hedef kutu (Evas\_Object\*). **child:** Eklenecek alt bileşen (Evas\_Object\*). |
| `void` | `gfx_box_pack_end(Evas_Object *object, Evas_Object *child)` | Alt nesneyi kutunun en sonuna ekler. | **object:** Hedef kutu (Evas\_Object\*). **child:** Eklenecek alt bileşen (Evas\_Object\*). |
| `void` | `gfx_box_pack_before(Evas_Object *object, Evas_Object *child, Evas_Object *before)` | Alt nesneyi kutu içinde belirli bir nesnenin hemen önüne yerleştirir. | **object:** Hedef kutu (Evas\_Object\*). **child:** Eklenecek nesne (Evas\_Object\*). **before:** Kutu içindeki referans nesne (Evas\_Object\*). |
| `void` | `gfx_box_pack_after(Evas_Object *object, Evas_Object *child, Evas_Object *after)` | Alt nesneyi kutu içinde belirli bir nesnenin hemen ardına yerleştirir. | **object:** Hedef kutu (Evas\_Object\*). **child:** Eklenecek nesne (Evas\_Object\*). **after:** Kutu içindeki referans nesne (Evas\_Object\*). |
| `void` | `gfx_box_unpack(Evas_Object *object, Evas_Object *child)` | Belirtilen alt nesneyi kutudan çıkarır ancak bellekten silmez. | **object:** Hedef kutu (Evas\_Object\*). **child:** Çıkarılacak alt nesne (Evas\_Object\*). |
| `void` | `gfx_box_unpack_all(Evas_Object *object)` | Kutu içindeki tüm alt bileşenleri serbest bırakarak kutudan çıkartır. | **object:** Boşaltılacak kutu (Evas\_Object\*). |
| `void` | `gfx_box_set_homogeneous(Evas_Object *object, Eina_Bool homogeneous)` | Kutu içindeki tüm elemanların eşit boyutta alan kaplamasını zorlar veya serbest bırakır. | **object:** Kutu nesnesi (Evas\_Object\*). **homogeneous:** Homojen dağılım bayrağı (EINA\_TRUE eşit alan, EINA\_FALSE dinamik). |
| `Eina_Bool` | `gfx_box_get_homogeneous(Evas_Object *object)` | Kutunun homojen yerleşim modunda olup olmadığını sorgular. | **object:** Kutu nesnesi (Evas\_Object\*). |
| `void` | `gfx_box_set_padding(Evas_Object *object, Evas_Coord horizontal, Evas_Coord vertical)` | Kutu içindeki elemanların arasındaki yatay ve dikey boşluk mesafelerini ayarlar. | **object:** Kutu nesnesi (Evas\_Object\*). **horizontal:** Yatay boşluk pikseli (Evas\_Coord, \>= 0). **vertical:** Dikey boşluk pikseli (Evas\_Coord, \>= 0). |
| `void` | `gfx_box_get_padding(Evas_Object *object, Evas_Coord *horizontal, Evas_Coord *vertical)` | Kutunun mevcut elemanlar arası boşluk değerlerini okur. | **object:** Kutu nesnesi (Evas\_Object\*). **horizontal:** Yatay boşluğu alacak gösterici (Evas\_Coord\* veya NULL). **vertical:** Dikey boşluğu alacak gösterici (Evas\_Coord\* veya NULL). |
| `void` | `gfx_box_set_align(Evas_Object *object, double horizontal, double vertical)` | Kutunun içindeki öğelerin kutu alanı içerisindeki genel hizalama oranını ayarlar. | **object:** Kutu nesnesi (Evas\_Object\*). **horizontal:** Yatay hizalama oranı (0.0 sol, 0.5 orta, 1.0 sağ). **vertical:** Dikey hizalama oranı (0.0 üst, 0.5 orta, 1.0 alt). |
| `void` | `gfx_box_get_align(Evas_Object *object, double *horizontal, double *vertical)` | Kutunun hizalama katsayılarını okur. | **object:** Kutu nesnesi (Evas\_Object\*). **horizontal:** Yatay hizalama göstericisi (double\* veya NULL). **vertical:** Dikey hizalama göstericisi (double\* veya NULL). |
| `Eina_List *` | `gfx_box_get_children(const Evas_Object *object)` | Kutunun içinde barındırdığı tüm alt bileşenlerin bağlı listesini döndürür. | **object:** Kutu nesnesi (const Evas\_Object\*). |

### **Grid Fonksiyonları**

| Dönüş Tipi | Fonksiyon Prototipi | İşlevi (Ne İşe Yarar?) | Parametreler ve Alabileceği Değerler |
| :---- | :---- | :---- | :---- |
| `Evas_Object *` | `gfx_object_add_grid(Evas_Object *parent)` | Sanal koordinat ızgarası tabanlı yerleşim kapsayıcısı oluşturur. | **parent:** Ebeveyn nesne göstericisi (geçerli Evas\_Object\*). |
| `void` | `gfx_grid_set_size(Evas_Object *object, int w, int h)` | Izgaranın sanal çözünürlük koordinat sınırlarını belirler (örneğin 100x100). | **object:** Izgara nesnesi (Evas\_Object\*). **w:** Sanal genişlik birimi (int \> 0, standart 100). **h:** Sanal yükseklik birimi (int \> 0, standart 100). |
| `void` | `gfx_grid_get_size(const Evas_Object *object, int *w, int *h)` | Izgaranın tanımlı sanal boyutlarını okur. | **object:** Izgara nesnesi (const Evas\_Object\*). **w, h:** Boyutları alacak tamsayı göstericileri (int\* veya NULL). |
| `void` | `gfx_grid_add_pack(Evas_Object *object, Evas_Object *subobject, int x, int y, int w, int h)` | Alt nesneyi ızgaraya ekler ve sanal koordinat/boyutlarını tanımlar. | **object:** Izgara nesnesi (Evas\_Object\*). **subobject:** Eklenecek nesne (Evas\_Object\*). **x, y:** Başlangıç sanal koordinatları (0 ile grid\_w/h arası int). **w, h:** Kaplayacağı sanal genişlik ve yükseklik (\> 0). |
| `void` | `gfx_grid_unpack(Evas_Object *object, Evas_Object *subobject)` | Alt nesneyi ızgaradan çıkarır. | **object:** Izgara nesnesi (Evas\_Object\*). **subobject:** Çıkarılacak nesne (Evas\_Object\*). |
| `void` | `gfx_grid_set_pack(Evas_Object *subobject, Evas_Coord x, Evas_Coord y, Evas_Coord w, Evas_Coord h)` | Daha önce ızgaraya eklenmiş bir alt nesnenin sanal yerleşimini günceller. | **subobject:** Izgaraya bağlı alt nesne (Evas\_Object\*). **x, y:** Yeni sanal koordinatlar (Evas\_Coord). **w, h:** Yeni sanal boyutlar (Evas\_Coord \> 0). |
| `void` | `gfx_grid_get_pack(Evas_Object *subobject, Evas_Coord *x, Evas_Coord *y, Evas_Coord *w, Evas_Coord *h)` | Izgara altındaki bir nesnenin mevcut sanal koordinat ve boyutlarını döndürür. | **subobject:** Alt nesne (Evas\_Object\*). **x, y, w, h:** Değerleri alacak koordinat göstericileri (Evas\_Coord\* veya NULL). |
| `Eina_List *` | `gfx_grid_get_children(const Evas_Object *object)` | Izgaraya bağlı alt bileşenlerin bağlı listesini döndürür. | **object:** Izgara nesnesi (const Evas\_Object\*). |
| `void` | `gfx_grid_clear(Evas_Object *object, Eina_Bool clear)` | Izgara içerisindeki alt nesneleri çıkarır ve isteğe bağlı olarak bellekten siler. | **object:** Izgara nesnesi (Evas\_Object\*). **clear:** Nesneleri bellekten silme tercihi (EINA\_TRUE nesneleri yok eder, EINA\_FALSE yalnızca boşaltır). |

### **Table Fonksiyonları**

| Dönüş Tipi | Fonksiyon Prototipi | İşlevi (Ne İşe Yarar?) | Parametreler ve Alabileceği Değerler |
| :---- | :---- | :---- | :---- |
| `Evas_Object *` | `gfx_object_add_table(Evas_Object *parent)` | Satır ve sütun matrisi şeklinde yerleşim sunan tablo kapsayıcısı oluşturur. | **parent:** Ebeveyn nesne göstericisi (geçerli Evas\_Object\*). |
| `void` | `gfx_table_set_align(Evas_Object *object, double horizontal, double vertical)` | Tablonun ebeveyni içindeki yatay ve dikey hizalama oranlarını ayarlar. | **object:** Tablo nesnesi (Evas\_Object\*). **horizontal:** Yatay hizalama oranı (0.0 \- 1.0 arası double). **vertical:** Dikey hizalama oranı (0.0 \- 1.0 arası double). |
| `void` | `gfx_table_get_align(const Evas_Object *object, double *horizontal, double *vertical)` | Tablonun hizalama oranlarını döndürür. | **object:** Tablo nesnesi (const Evas\_Object\*). **horizontal, vertical:** Değerleri alacak double göstericileri (double\* veya NULL). |
| `Evas_Object *` | `gfx_table_get_child(const Evas_Object *object, int col, int row)` | Belirli bir sütun ve satır kesişiminde bulunan alt nesneyi döndürür. | **object:** Tablo nesnesi (const Evas\_Object\*). **col:** Sütun indeksi (int \>= 0). **row:** Satır indeksi (int \>= 0). |
| `void` | `gfx_table_clear(Evas_Object *object, Eina_Bool clear)` | Tablo içindeki tüm elemanları çıkartır ve isteğe bağlı olarak siler. | **object:** Tablo nesnesi (Evas\_Object\*). **clear:** Bellekten silme durumu (EINA\_TRUE nesneleri yok eder, EINA\_FALSE sadece tablodan çıkarır). |
| `void` | `gfx_table_set_homogeneous(Evas_Object *object, Eina_Bool homogeneous)` | Tüm tablo hücrelerinin aynı genişlik ve yükseklikte olmasını zorlar veya serbest bırakır. | **object:** Tablo nesnesi (Evas\_Object\*). **homogeneous:** Homojen mod bayrağı (EINA\_TRUE veya EINA\_FALSE). |
| `Eina_Bool` | `gfx_table_get_homogeneous(const Evas_Object *object)` | Tablonun homojen hücre yapısında olup olmadığını sorgular. | **object:** Tablo nesnesi (const Evas\_Object\*). |
| `void` | `gfx_table_pack(Evas_Object *object, Evas_Object *subobject, int col, int row, int colspan, int rowspan)` | Alt nesneyi tablonun belirtilen sütun ve satırına hücre birleştirme desteğiyle ekler. | **object:** Tablo nesnesi (Evas\_Object\*). **subobject:** Eklenecek nesne (Evas\_Object\*). **col, row:** Başlangıç sütun ve satır indeksleri (\>= 0 int). **colspan, rowspan:** Kaplayacağı sütun ve satır sayısı (\>= 1 int). |
| `void` | `gfx_table_set_pack(Evas_Object *subobject, int col, int row, int colspan, int rowspan)` | Tablodaki bir elemanın hücre konumunu ve kapladığı hücre alanını günceller. | **subobject:** Tablo alt nesnesi (Evas\_Object\*). **col, row:** Yeni sütun ve satır (\>= 0 int). **colspan, rowspan:** Yeni hücre yayılım sayıları (\>= 1 int). |
| `void` | `gfx_table_get_pack(Evas_Object *subobject, int *col, int *row, int *colspan, int *rowspan)` | Tablo alt nesnesinin hücre konumu ve birleşim boyutlarını okur. | **subobject:** Alt nesne (Evas\_Object\*). **col, row, colspan, rowspan:** Değerleri alacak tamsayı işaretçileri (int\* veya NULL). |
| `void` | `gfx_table_set_padding(Evas_Object *object, Evas_Coord horizontal, Evas_Coord vertical)` | Tablo hücreleri arasındaki yatay ve dikey boşlukları ayarlar. | **object:** Tablo nesnesi (Evas\_Object\*). **horizontal:** Yatay aralık (Evas\_Coord \>= 0). **vertical:** Dikey aralık (Evas\_Coord \>= 0). |
| `void` | `gfx_table_get_padding(Evas_Object *object, Evas_Coord *horizontal, Evas_Coord *vertical)` | Tablonun hücre boşluklarını okur. | **object:** Tablo nesnesi (Evas\_Object\*). **horizontal, vertical:** Boşlukları alacak göstericiler (Evas\_Coord\* veya NULL). |
| `void` | `gfx_table_unpack(Evas_Object *object, Evas_Object *subobject)` | Alt nesneyi tablodan çıkartır. | **object:** Tablo nesnesi (Evas\_Object\*). **subobject:** Çıkarılacak nesne (Evas\_Object\*). |

### **Scroller Fonksiyonları**

| Dönüş Tipi | Fonksiyon Prototipi | İşlevi (Ne İşe Yarar?) | Parametreler ve Alabileceği Değerler |
| :---- | :---- | :---- | :---- |
| `Evas_Object *` | `gfx_object_add_scroller(Evas_Object *parent)` | Görünüm alanını aşan içerikleri kaydırmayı sağlayan kaydırıcı nesnesi oluşturur. | **parent:** Ebeveyn nesne göstericisi (geçerli Evas\_Object\*). |
| `void` | `gfx_scroller_set_policy(Evas_Object *object, Elm_Scroller_Policy policy_h, Elm_Scroller_Policy policy_v)` | Yatay ve dikey kaydırma çubuklarının görünme kurallarını (politikalarını) belirler. | **object:** Kaydırıcı nesnesi (Evas\_Object\*). **policy\_h, policy\_v:** Kaydırma çubuğu modu (ELM\_SCROLLER\_POLICY\_AUTO, ALWAYS, OFF vb. Elm\_Scroller\_Policy değerleri). |
| `void` | `gfx_scroller_get_policy(const Evas_Object *object, Elm_Scroller_Policy *policy_h, Elm_Scroller_Policy *policy_v)` | Kaydırıcının mevcut çubuk görünüm politikalarını okur. | **object:** Kaydırıcı nesnesi (const Evas\_Object\*). **policy\_h, policy\_v:** Değerleri alacak göstericiler (Elm\_Scroller\_Policy\* veya NULL). |
| `void` | `gfx_scroller_set_region(Evas_Object *object, Evas_Coord x, Evas_Coord y, Evas_Coord w, Evas_Coord h)` | Kaydırıcıyı doğrudan belirli bir koordinat ve boyut alanına odaklar/kaydırır. | **object:** Kaydırıcı nesnesi (Evas\_Object\*). **x, y:** Hedef koordinatlar (Evas\_Coord \>= 0). **w, h:** Hedef genişlik ve yükseklik (Evas\_Coord \> 0). |
| `void` | `gfx_scroller_get_region(const Evas_Object *object, Evas_Coord *x, Evas_Coord *y, Evas_Coord *w, Evas_Coord *h)` | Şu anda görünür olan içerik bölgesinin koordinat ve boyutlarını döndürür. | **object:** Kaydırıcı nesnesi (const Evas\_Object\*). **x, y, w, h:** Koordinat ve boyut göstericileri (Evas\_Coord\* veya NULL). |
| `void` | `gfx_scroller_get_position(const Evas_Object *object, Evas_Coord *x, Evas_Coord *y)` | Geçerli kaydırma ofset noktasını piksel cinsinden okur. | **object:** Kaydırıcı nesnesi (const Evas\_Object\*). **x, y:** Konumu alacak göstericiler (Evas\_Coord\* veya NULL). |
| `void` | `gfx_scroller_set_pagesize(Evas_Object *object, Evas_Coord w, Evas_Coord h)` | Sayfalı (paging) kaydırma modu için sayfa genişlik ve yükseklik adımlarını tanımlar. | **object:** Kaydırıcı nesnesi (Evas\_Object\*). **w, h:** Sayfa piksel boyutları (Evas\_Coord \>= 0). |
| `void` | `gfx_scroller_get_pagesize(const Evas_Object *object, Evas_Coord *w, Evas_Coord *h)` | Tanımlanmış sayfa boyutlarını okur. | **object:** Kaydırıcı nesnesi (const Evas\_Object\*). **w, h:** Sayfa boyutlarını alacak göstericiler (Evas\_Coord\* veya NULL). |
| `void` | `gfx_scroller_get_currentpage(const Evas_Object *object, int *hp, int *vp)` | Aktif olarak görüntülenen yatay ve dikey sayfa indeks numaralarını verir. | **object:** Kaydırıcı nesnesi (const Evas\_Object\*). **hp, vp:** Sayfa numaralarını alacak göstericiler (\>= 0 int\* veya NULL). |
| `void` | `gfx_scroller_show_page(Evas_Object *object, int hp, int vp)` | Kaydırıcıyı belirtilen sayfa indeksine otomatik olarak kaydırır. | **object:** Kaydırıcı nesnesi (Evas\_Object\*). **hp, vp:** Hedef sayfa indeksleri (\>= 0 int). |
| `void` | `gfx_scroller_set_bounce(Evas_Object *object, Eina_Bool h_bounce, Eina_Bool v_bounce)` | Sona ulaşıldığında esneme/yaylanma (bounce) animasyonunu yatay/dikey olarak açar veya kapatır. | **object:** Kaydırıcı nesnesi (Evas\_Object\*). **h\_bounce, v\_bounce:** Yaylanma efekti durumları (EINA\_TRUE açık, EINA\_FALSE kapalı). |
| `void` | `gfx_scroller_get_bounce(const Evas_Object *object, Eina_Bool *h_bounce, Eina_Bool *v_bounce)` | Esneme efektinin aktiflik durumlarını okur. | **object:** Kaydırıcı nesnesi (const Evas\_Object\*). **h\_bounce, v\_bounce:** Değerleri alacak bayrak göstericileri (Eina\_Bool\* veya NULL). |

### **Frame Fonksiyonları**

| Dönüş Tipi | Fonksiyon Prototipi | İşlevi (Ne İşe Yarar?) | Parametreler ve Alabileceği Değerler |
| :---- | :---- | :---- | :---- |
| `Evas_Object *` | `gfx_object_add_frame(Evas_Object *parent)` | Etrafında başlığı ve kenarlığı olan dekoratif çerçeve (frame) bileşeni oluşturur. | **parent:** Ebeveyn nesne göstericisi (geçerli Evas\_Object\*). |
| `void` | `gfx_frame_set_autocollapse(Evas_Object *object, Eina_Bool autocollapse)` | Başlığa tıklandığında çerçevenin otomatik katlanıp açılmasını ayarlar. | **object:** Çerçeve nesnesi (Evas\_Object\*). **autocollapse:** Otomatik katlanma durumu (EINA\_TRUE aktif, EINA\_FALSE devre dışı). |
| `Eina_Bool` | `gfx_frame_get_autocollapse(const Evas_Object *object)` | Çerçevenin otomatik katlanma modunda olup olmadığını sorgular. | **object:** Çerçeve nesnesi (const Evas\_Object\*). |
| `void` | `gfx_frame_set_collapse(Evas_Object *object, Eina_Bool collapse)` | Çerçeveyi programatik olarak anında daraltır/kapatır veya genişletir. | **object:** Çerçeve nesnesi (Evas\_Object\*). **collapse:** Daralma bayrağı (EINA\_TRUE daraltır, EINA\_FALSE açar). |
| `Eina_Bool` | `gfx_frame_get_collapse(const Evas_Object *object)` | Çerçevenin şu anda daraltılmış olup olmadığını döndürür. | **object:** Çerçeve nesnesi (const Evas\_Object\*). |

---

## **5\. Nesne ve Durum Yönetimi (Object Management & State)**

| Dönüş Tipi | Fonksiyon Prototipi | İşlevi (Ne İşe Yarar?) | Parametreler ve Alabileceği Değerler |
| :---- | :---- | :---- | :---- |
| `void` | `gfx_object_set_text(Evas_Object *object, const char *text)` | Herhangi bir UI nesnesinin varsayılan metin içeriğini ayarlar. | **object:** Hedef nesne (Evas\_Object\*). **text:** Ayarlanacak metin dizgisi (const char\* veya NULL). |
| `const char *` | `gfx_object_get_text(const Evas_Object *object)` | Nesnenin mevcut varsayılan metin içeriğini döndürür. | **object:** İncelenecek nesne (const Evas\_Object\*). |
| `void` | `gfx_object_set_content(Evas_Object *object, Evas_Object *content)` | Kapsayıcı nesnenin ana içerik alanına başka bir nesneyi bağlar. | **object:** Kapsayıcı nesne (Evas\_Object\*). **content:** İçerik nesnesi (Evas\_Object\* veya boşaltmak için NULL). |
| `Evas_Object *` | `gfx_object_get_content(const Evas_Object *object)` | Kapsayıcı nesnenin ana içeriğinde yer alan nesneyi döndürür. | **object:** Kapsayıcı nesne (const Evas\_Object\*). |
| `void` | `gfx_image_set_file(Evas_Object *object, const char *file, const char *group)` | Görsel nesnesine diskteki bir resim veya edje dosyasını atar. | **object:** Görsel nesnesi (Evas\_Object\*). **file:** Dosya yolu (geçerli dosya yolu dizgisi). **group:** Edje grup adı (const char\* veya standart resimler için NULL). |
| `void` | `gfx_icon_set_standard(Evas_Object *object, const char *name)` | İkon nesnesine sistem/freedesktop standart ikon adını atar. | **object:** İkon nesnesi (Evas\_Object\*). **name:** Standart ikon adı (örn: "home", "folder", "close" vb.). |
| `void` | `gfx_object_set_parttext(Evas_Object *object, const char *part, const char *text)` | Nesnenin Edje teması içindeki belirli bir adlandırılmış parçasına metin yazar. | **object:** Hedef nesne (Evas\_Object\*). **part:** Parça adı (örn: "elm.text", "elm.guide" vb.). **text:** Atanacak metin (const char\* veya NULL). |
| `void` | `gfx_object_set_partcontent(Evas_Object *object, const char *part, Evas_Object *content)` | Nesnenin belirli bir adlandırılmış parçasına (swallow part) alt nesne yerleştirir. | **object:** Hedef nesne (Evas\_Object\*). **part:** Parça adı (örn: "elm.swallow.icon", "elm.swallow.content"). **content:** Yerleştirilecek nesne (Evas\_Object\* veya boşaltmak için NULL). |
| `void` | `gfx_set_policy(unsigned int policy, int value)` | Elementary genel kütüphane davranış kurallarını (çıkış davranışı vb.) yapılandırır. | **policy:** Politika türü (ELM\_POLICY\_QUIT vb. unsigned int). **value:** Politika değeri (ELM\_POLICY\_QUIT\_NONE, ELM\_POLICY\_QUIT\_LAST\_WINDOW\_CLOSED vb. int). |
| `void` | `gfx_object_set_disabled(Evas_Object *object, Eina_Bool disabled)` | Bileşeni kullanıcı etkileşimine kapatır (devre dışı bırakır) veya yeniden etkinleştirir. | **object:** Hedef nesne (Evas\_Object\*). **disabled:** Kilitli olma durumu (EINA\_TRUE devre dışı bırakır, EINA\_FALSE etkinleştirir). |

### **Entry ve State Fonksiyonları**

| Dönüş Tipi | Fonksiyon Prototipi | İşlevi (Ne İşe Yarar?) | Parametreler ve Alabileceği Değerler |
| :---- | :---- | :---- | :---- |
| `void` | `gfx_entry_set_text(Evas_Object *object, const char *text)` | Metin giriş kutusunun (entry) içerdiği yazıyı günceller. | **object:** Entry nesnesi (Evas\_Object\*). **text:** Giriş alanına yazılacak metin (const char\* veya NULL). |
| `const char *` | `gfx_entry_get_text(const Evas_Object *object)` | Metin giriş kutusundaki mevcut metni döndürür. | **object:** Entry nesnesi (const Evas\_Object\*). |
| `void` | `gfx_entry_set_singleline(Evas_Object *object, Eina_Bool single_line)` | Giriş kutusunu tek satırlı moda ayarlar veya çok satırlı girişe izin verir. | **object:** Entry nesnesi (Evas\_Object\*). **single\_line:** Tek satır bayrağı (EINA\_TRUE tek satır, EINA\_FALSE çok satır). |
| `void` | `gfx_entry_set_password(Evas_Object *object, Eina_Bool password)` | Karakterleri yıldız veya nokta şeklinde maskeleyerek parola gizleme modunu açar. | **object:** Entry nesnesi (Evas\_Object\*). **password:** Parola modu (EINA\_TRUE gizler, EINA\_FALSE açık gösterir). |
| `void` | `gfx_check_set_state(Evas_Object *object, Eina_Bool checked)` | Onay kutusunun (check) işaretli olma durumunu değiştirir. | **object:** Check nesnesi (Evas\_Object\*). **checked:** İşaret durumu (EINA\_TRUE seçili, EINA\_FALSE seçilmemiş). |
| `Eina_Bool` | `gfx_check_get_state(const Evas_Object *object)` | Onay kutusunun seçili olup olmadığını döndürür. | **object:** Check nesnesi (const Evas\_Object\*). |
| `void` | `gfx_radio_set_statevalue(Evas_Object *object, int value)` | Radyo düğmesinin seçildiğinde temsil edeceği tamsayı değerini belirler. | **object:** Radio nesnesi (Evas\_Object\*). **value:** Düğmeye özgü sayısal kimlik/durum (int). |
| `void` | `gfx_radio_set_value(Evas_Object *object, int value)` | Radyo grubunun mevcut seçili değerini belirtilen değere ayarlar. | **object:** Radio nesnesi (Evas\_Object\*). **value:** Seçilecek durum değeri (int). |
| `int` | `gfx_radio_get_value(const Evas_Object *object)` | Radyo grubunda o an seçili olan radyo düğmesinin durum değerini döndürür. | **object:** Radio nesnesi (const Evas\_Object\*). |
| `void` | `gfx_radio_add_group(Evas_Object *object, Evas_Object *group)` | Bir radyo butonunu başka bir radyo butonunun oluşturduğu mantıksal gruba bağlar. | **object:** Gruba katılacak radyo nesnesi (Evas\_Object\*). **group:** Grubun lider radyo nesnesi (Evas\_Object\*). |
| `void` | `gfx_radio_set_pointervalue(Evas_Object *object, int *valuep)` | Radyo seçim değerini doğrudan bir C tamsayı değişken adresine bağlar (bağlantılı bellek güncellemesi). | **object:** Radio nesnesi (Evas\_Object\*). **valuep:** Değerin senkronize tutulacağı bellek adresi (int\* veya NULL). |
| `void` | `gfx_slider_set_minmax(Evas_Object *object, double min, double max)` | Kaydırma çubuğunun seçebileceği asgari ve azami sınır değerlerini tanımlar. | **object:** Slider nesnesi (Evas\_Object\*). **min, max:** Sınır değerleri (double, min \< max koşuluyla). |
| `void` | `gfx_slider_set_unitformat(Evas_Object *object, const char *format)` | Kaydırıcının üzerinde gösterilen değerin metin formatlama biçimini belirler. | **object:** Slider nesnesi (Evas\_Object\*). **format:** Printf uyumlu format dizgesi (örn: "%1.2f %%", "%d" vb.). |
| `void` | `gfx_slider_set_value(Evas_Object *object, double value)` | Kaydırıcının o anki sayısal değerini ve gösterge pozisyonunu günceller. | **object:** Slider nesnesi (Evas\_Object\*). **value:** Ayarlanacak değer (min ile max arasında double). |
| `double` | `gfx_slider_get_value(const Evas_Object *object)` | Kaydırıcının mevcut seçili değerini döndürür. | **object:** Slider nesnesi (const Evas\_Object\*). |

### **Genlist Fonksiyonları**

| Dönüş Tipi | Fonksiyon Prototipi | İşlevi (Ne İşe Yarar?) | Parametreler ve Alabileceği Değerler |
| :---- | :---- | :---- | :---- |
| `Elm_Object_Item *` | `gfx_genlist_add_item(Evas_Object *object, const Elm_Genlist_Item_Class *itc, const void *data, Elm_Object_Item *parent, Elm_Genlist_Item_Type type, Evas_Smart_Cb func, const void *func_data)` | Genlist (jenerik liste) bileşenine dinamik içerikli yeni bir liste elemanı ekler. | **object:** Genlist nesnesi (Evas\_Object\*). **itc:** Öğe sınıf tanımı (const Elm\_Genlist\_Item\_Class\*). **data:** Öğeye bağlanacak özel veri göstericisi (const void\* veya NULL). **parent:** Ağaç yapısı için ebeveyn öğe (Elm\_Object\_Item\* veya kök için NULL). **type:** Öğe türü (ELM\_GENLIST\_ITEM\_NONE, TREE, GROUP vb. Elm\_Genlist\_Item\_Type). **func:** Seçilme geri çağırım fonksiyonu (Evas\_Smart\_Cb veya NULL). **func\_data:** Geri çağırıma iletilecek veri (const void\* veya NULL). |
| `void` | `gfx_genlist_clear(Evas_Object *object)` | Listedeki tüm elemanları bellekten temizler ve listeyi boşaltır. | **object:** Genlist nesnesi (Evas\_Object\*). |
| `Elm_Genlist_Item_Class *` | `gfx_genlist_add_itemclass(void)` | Yeni bir Genlist öğe sınıfı yapısı tahsis eder ve bellekte ilklendirir. | *Parametre almaz.* |
| `void` | `gfx_genlist_free_itemclass(Elm_Genlist_Item_Class *itemclass)` | Daha önce tahsis edilmiş öğe sınıfı yapısını bellekten serbest bırakır. | **itemclass:** Serbest bırakılacak öğe sınıfı göstericisi (Elm\_Genlist\_Item\_Class\*). |

### **Background Fonksiyonları**

| Dönüş Tipi | Fonksiyon Prototipi | İşlevi (Ne İşe Yarar?) | Parametreler ve Alabileceği Değerler |
| :---- | :---- | :---- | :---- |
| `Evas_Object *` | `gfx_object_add_background(Evas_Object *parent)` | Pencereler veya kutular için renkli veya resimli arkaplan (background) bileşeni oluşturur. | **parent:** Ebeveyn nesne göstericisi (geçerli Evas\_Object\*). |
| `void` | `gfx_background_set_file(Evas_Object *object, const char *file, const char *group)` | Arkaplan olarak kullanılacak resim veya Edje tema dosyasını yükler. | **object:** Arkaplan nesnesi (Evas\_Object\*). **file:** Dosya yolu (const char\*). **group:** Edje grup adı (const char\* veya düz resimler için NULL). |
| `void` | `gfx_background_get_file(const Evas_Object *object, const char **file, const char **group)` | Arkaplanda kullanılan dosya yolu ve grup adını döndürür. | **object:** Arkaplan nesnesi (const Evas\_Object\*). **file, group:** Değerleri alacak string gösterici adresleri (const char\*\* veya NULL). |
| `void` | `gfx_background_set_option(Evas_Object *object, Elm_Bg_Option option)` | Arkaplan resminin nasıl yerleşeceğini (döşeme, merkezleme, ölçekleme vb.) belirler. | **object:** Arkaplan nesnesi (Evas\_Object\*). **option:** Yerleşim modu (ELM\_BG\_OPTION\_CENTER, SCALE, STRETCH, TILE vb. Elm\_Bg\_Option). |
| `Elm_Bg_Option` | `gfx_background_get_option(const Evas_Object *object)` | Arkaplan resminin mevcut yerleşim/ölçekleme seçeneğini döndürür. | **object:** Arkaplan nesnesi (const Evas\_Object\*). |
| `void` | `gfx_background_set_color(Evas_Object *object, int r, int g, int b)` | Arkaplan nesnesine düz RGB dolgu rengi atar. | **object:** Arkaplan nesnesi (Evas\_Object\*). **r, g, b:** Kırmızı, yeşil, mavi renk değerleri (her biri 0 \- 255 arası tamsayı). |
| `void` | `gfx_background_get_color(const Evas_Object *object, int *r, int *g, int *b)` | Arkaplan nesnesinin mevcut RGB renk bileşenlerini okur. | **object:** Arkaplan nesnesi (const Evas\_Object\*). **r, g, b:** Değerleri alacak tamsayı göstericileri (int\* veya NULL). |
| `void` | `gfx_background_set_loadsize(Evas_Object *object, int w, int h)` | Performans ve bellek optimizasyonu için resmin belleğe hangi çözünürlükte yükleneceğini ayarlar. | **object:** Arkaplan nesnesi (Evas\_Object\*). **w, h:** Yükleme genişlik ve yüksekliği (piksel int \>= 0). |

### **Menu Fonksiyonları**

| Dönüş Tipi | Fonksiyon Prototipi | İşlevi (Ne İşe Yarar?) | Parametreler ve Alabileceği Değerler |
| :---- | :---- | :---- | :---- |
| `Evas_Object *` | `gfx_object_add_menu(Evas_Object *parent)` | Açılır menü (popup/context menu) kapsayıcı nesnesi yaratır. | **parent:** Ebeveyn nesne göstericisi (geçerli Evas\_Object\*). |
| `Elm_Object_Item *` | `gfx_menu_add_item(Evas_Object *object, Elm_Object_Item *parent, const char *icon, const char *label, Evas_Smart_Cb func, const void *data)` | Menüye veya bir alt menüye tıklanabilir yeni bir öğe ekler. | **object:** Menü nesnesi (Evas\_Object\*). **parent:** Alt menü öğesi (Elm\_Object\_Item\* veya ana menü için NULL). **icon:** İkon adı (const char\* veya NULL). **label:** Görüntülenecek metin (const char\*). **func:** Tıklama callback fonksiyonu (Evas\_Smart\_Cb veya NULL). **data:** Callbacak iletilecek veri (const void\* veya NULL). |
| `void` | `gfx_menu_add_separator(Evas_Object *object, Elm_Object_Item *parent)` | Menü öğeleri arasına yatay bir ayraç çizgisi ekler. | **object:** Menü nesnesi (Evas\_Object\*). **parent:** Ayracın ekleneceği alt menü öğesi (Elm\_Object\_Item\* veya kök için NULL). |
| `Elm_Object_Item *` | `gfx_menu_add_submenu(Evas_Object *object, Elm_Object_Item *parent, const char *icon, const char *label)` | Üzerine gelindiğinde yana doğru açılan alt menü (submenu) dalı oluşturur. | **object:** Menü nesnesi (Evas\_Object\*). **parent:** Ebeveyn menü öğesi (Elm\_Object\_Item\* veya kök için NULL). **icon:** İkon adı (const char\* veya NULL). **label:** Alt menü başlığı (const char\*). |
| `void` | `gfx_menu_move(Evas_Object *object, Evas_Coord x, Evas_Coord y)` | Menüyü ekranda belirtilen piksel koordinatlarına taşır/konumlandırır. | **object:** Menü nesnesi (Evas\_Object\*). **x, y:** Hedef ekran piksel koordinatları (Evas\_Coord). |
| `void` | `gfx_menu_close(Evas_Object *object)` | Açık olan menüyü kapatır ve ekrandan gizler. | **object:** Menü nesnesi (Evas\_Object\*). |
| `Elm_Object_Item *` | `gfx_menu_get_selected(const Evas_Object *object)` | Menüde o an seçilmiş olan aktif öğeyi döndürür. | **object:** Menü nesnesi (const Evas\_Object\*). |
| `const Eina_List *` | `gfx_menu_get_items(const Evas_Object *object)` | Menünün kök seviyesindeki tüm öğelerin bağlı listesini döndürür. | **object:** Menü nesnesi (const Evas\_Object\*). |
| `Evas_Object *` | `gfx_menu_get_itemobject(const Elm_Object_Item *item)` | Menü öğesine ait alttaki temel Evas\_Object grafik nesnesini döndürür. | **item:** İlgili menü öğesi göstericisi (const Elm\_Object\_Item\*). |
| `void` | `gfx_menu_set_itemselected(Elm_Object_Item *item, Eina_Bool selected)` | Menü öğesinin seçili (vurgulanmış) olma durumunu ayarlar. | **item:** Menü öğesi (Elm\_Object\_Item\*). **selected:** Seçilme durumu (EINA\_TRUE veya EINA\_FALSE). |
| `Eina_Bool` | `gfx_menu_get_itemdisabled(const Elm_Object_Item *item)` | Menü öğesinin devre dışı bırakılmış olup olmadığını sorgular. | **item:** Menü öğesi (const Elm\_Object\_Item\*). |
| `void` | `gfx_menu_set_itemicon(Elm_Object_Item *item, const char *icon)` | Menü öğesinin solunda gösterilen ikon görselini değiştirir. | **item:** Menü öğesi (Elm\_Object\_Item\*). **icon:** İkon adı veya dosya yolu (const char\* veya kaldırmak için NULL). |
| `const char *` | `gfx_menu_get_itemicon(const Elm_Object_Item *item)` | Menü öğesinin ikon adını döndürür. | **item:** Menü öğesi (const Elm\_Object\_Item\*). |
| `void` | `gfx_menu_set_itemlabel(Elm_Object_Item *item, const char *label)` | Menü öğesinin metin etiketini günceller. | **item:** Menü öğesi (Elm\_Object\_Item\*). **label:** Yeni metin (const char\* veya NULL). |
| `const char *` | `gfx_menu_get_itemlabel(const Elm_Object_Item *item)` | Menü öğesinin metin etiketini döndürür. | **item:** Menü öğesi (const Elm\_Object\_Item\*). |
| `Eina_Bool` | `gfx_menu_get_itemselected(const Elm_Object_Item *item)` | Menü öğesinin seçili olup olmadığını kontrol eder. | **item:** Menü öğesi (const Elm\_Object\_Item\*). |
| `Elm_Object_Item *` | `gfx_menu_get_itemparent(const Elm_Object_Item *item)` | Bir alt menü öğesinin bağlı olduğu üst ebeveyn menü öğesini döndürür. | **item:** Menü öğesi (const Elm\_Object\_Item\*). |
| `const Eina_List *` | `gfx_menu_get_subitems(const Elm_Object_Item *item)` | Bir menü öğesinin altındaki tüm alt öğelerin (subitems) listesini döndürür. | **item:** Menü öğesi (const Elm\_Object\_Item\*). |
| `void` | `gfx_menu_del_item(Elm_Object_Item *item)` | Belirtilen menü öğesini menüden kaldırır ve bellekten siler. | **item:** Silinecek menü öğesi (Elm\_Object\_Item\*). |

---

## **6\. Evas Kanvas ve Grafik Fonksiyonları (Evas Functions)**

| Dönüş Tipi | Fonksiyon Prototipi | İşlevi (Ne İşe Yarar?) | Parametreler ve Alabileceği Değerler |
| :---- | :---- | :---- | :---- |
| `Evas *` | `gfx_object_get_evas(const Evas_Object *object)` | Nesnenin bağlı bulunduğu ana Evas çizim tuvali (canvas) işaretçisini döndürür. | **object:** Grafik nesnesi (const Evas\_Object\*). |
| `void` | `gfx_object_show(Evas_Object *object)` | Grafik nesnesini görünür yapar ve ekranda çizilmesini sağlar. | **object:** Gösterilecek nesne (Evas\_Object\*). |
| `void` | `gfx_object_hide(Evas_Object *object)` | Grafik nesnesini gizler (çizimini durdurur). | **object:** Gizlenecek nesne (Evas\_Object\*). |
| `void` | `gfx_object_del(Evas_Object *object)` | Nesneyi kanvastan kaldırır ve bellek kaynaklarını serbest bırakarak yok eder. | **object:** Silinecek nesne (Evas\_Object\*). |
| `void` | `gfx_object_raise(Evas_Object *object)` | Nesneyi katman hiyerarşisinde (Z-order) bir üst veya en ön seviyeye yükseltir. | **object:** Yükseltilecek nesne (Evas\_Object\*). |
| `void` | `gfx_object_lower(Evas_Object *object)` | Nesneyi katman hiyerarşisinde arkaya/alta indirir. | **object:** Alta indirilecek nesne (Evas\_Object\*). |
| `void` | `gfx_object_set_size_hintweight(Evas_Object *object, double x, double y)` | Konteynerler içindeyken nesnenin fazladan alanı paylaşma ağırlığını (expansion weight) belirler. | **object:** Hedef nesne (Evas\_Object\*). **x, y:** Genişleme ağırlığı (0.0 sabit boyut, 1.0 tam genişleme veya EVAS\_HINT\_EXPAND). |
| `void` | `gfx_object_set_size_hintalign(Evas_Object *object, double x, double y)` | Konteyner hücresi içindeki hizalama ve doldurma davranış ipucunu belirler. | **object:** Hedef nesne (Evas\_Object\*). **x, y:** Hizalama oranı (0.0 sol/üst, 0.5 orta, 1.0 sağ/alt, \-1.0 veya EVAS\_HINT\_FILL alanı doldurma). |
| `void` | `gfx_object_move(Evas_Object *object, Evas_Coord x, Evas_Coord y)` | Nesneyi kanvas üzerindeki mutlak piksel koordinatlarına taşır. | **object:** Taşınacak nesne (Evas\_Object\*). **x, y:** Ekran koordinatları (Evas\_Coord). |
| `void` | `gfx_object_resize(Evas_Object *object, Evas_Coord w, Evas_Coord h)` | Nesnenin piksel genişlik ve yükseklik boyutlarını ayarlar. | **object:** Nesne (Evas\_Object\*). **w, h:** Genişlik ve yükseklik (Evas\_Coord \>= 0). |
| `void` | `gfx_object_get_geometry(Evas_Object *object, Evas_Coord *x, Evas_Coord *y, Evas_Coord *w, Evas_Coord *h)` | Nesnenin mutlak koordinatlarını ve piksel boyutlarını tek seferde okur. | **object:** Hedef nesne (Evas\_Object\*). **x, y, w, h:** Değerleri alacak koordinat göstericileri (Evas\_Coord\* veya NULL). |
| `void` | `gfx_object_set_color(Evas_Object *object, int r, int g, int b, int a)` | Nesneye önceden çarpılmış (premultiplied) RGBA rengi ve şeffaflığı atar. | **object:** Renklendirilecek nesne (Evas\_Object\*). **r, g, b, a:** Renk ve alfa bileşenleri (her biri 0 \- 255 arası tamsayı; r, g, b \<= a). |
| `void` | `gfx_object_get_color(const Evas_Object *object, int *r, int *g, int *b, int *a)` | Nesnenin mevcut RGBA renk ve alfa değerlerini okur. | **object:** İncelenecek nesne (const Evas\_Object\*). **r, g, b, a:** Değerleri alacak göstericiler (int\* veya NULL). |
| `void` | `gfx_object_set_minsize(Evas_Object *object, Evas_Coord w, Evas_Coord h)` | Konteyner yerleşim motoruna nesnenin en az bu piksel boyutlarında tutulması gerektiğini bildirir. | **object:** Hedef nesne (Evas\_Object\*). **w, h:** Asgari boyutlar (Evas\_Coord \>= 0). |
| `void` | `gfx_object_set_maxsize(Evas_Object *object, Evas_Coord w, Evas_Coord h)` | Konteyner motoruna nesnenin bu piksel boyutlarından daha büyük çizilmemesi gerektiğini bildirir. | **object:** Hedef nesne (Evas\_Object\*). **w, h:** Azami boyutlar (Evas\_Coord \>= 0 veya sınırsız için \-1). |
| `Evas_Object *` | `gfx_object_add_rectangle(Evas *canvas)` | Doğrudan Evas kanvası üzerinde renkli bir temel dikdörtgen ilkel şekli oluşturur. | **canvas:** Çizim tuvali göstericisi (geçerli Evas\*). |
| `Evas_Object *` | `gfx_object_add_rawimage(Evas *canvas)` | Doğrudan Evas seviyesinde ham resim nesnesi tahsis eder. | **canvas:** Çizim tuvali göstericisi (geçerli Evas\*). |
| `Evas_Object *` | `gfx_object_add_text(Evas *canvas)` | Evas kanvası üzerinde tek satırlı yalın metin nesnesi oluşturur. | **canvas:** Çizim tuvali göstericisi (geçerli Evas\*). |
| `Evas_Object *` | `gfx_object_add_textblock(Evas *canvas)` | Gelişmiş biçimlendirmeli ve çok satırlı metin bloğu (textblock) nesnesi oluşturur. | **canvas:** Çizim tuvali göstericisi (geçerli Evas\*). |
| `void` | `gfx_object_set_imagefile(Evas_Object *object, const char *file, const char *key)` | Evas ham resim nesnesine dosya yolu ve anahtar atayarak görseli bağlar. | **object:** Evas resim nesnesi (Evas\_Object\*). **file:** Dosya yolu (const char\*). **key:** Dosya içi anahtar/grup (const char\* veya NULL). |
| `void` | `gfx_object_set_imagefilled(Evas_Object *object, Eina_Bool filled)` | Resmin nesne sınırlarına göre otomatik dolgu (stretch/fill) yapmasını sağlar. | **object:** Evas resim nesnesi (Evas\_Object\*). **filled:** Otomatik dolgu bayrağı (EINA\_TRUE açık, EINA\_FALSE kapalı). |
| `void` | `gfx_object_set_textfont(Evas_Object *object, const char *font, Evas_Font_Size size)` | Evas metin nesnesinin font ailesini ve punto boyutunu ayarlar. | **object:** Metin nesnesi (Evas\_Object\*). **font:** Font ailesi adı (örn: "Sans", "Arial"). **size:** Yazı punto boyutu (Evas\_Font\_Size \> 0). |
| `void` | `gfx_object_set_rawtext(Evas_Object *object, const char *text)` | Evas metin nesnesinin ekranda göstereceği ham metni ayarlar. | **object:** Metin nesnesi (Evas\_Object\*). **text:** Görüntülenecek ham dize (const char\* veya NULL). |
| `void` | `gfx_object_add_eventcallback(Evas_Object *object, Evas_Callback_Type type, Evas_Event_Cb func, const void *data)` | Nesneye düşük seviyeli Evas giriş olayları (fare tıklaması, hareket, tuş vb.) için dinleyici bağlar. | **object:** Hedef nesne (Evas\_Object\*). **type:** Olay tipi (EVAS\_CALLBACK\_MOUSE\_DOWN, MOUSE\_UP, KEY\_DOWN vb. Evas\_Callback\_Type). **func:** Olay çağırım fonksiyonu (Evas\_Event\_Cb). **data:** Fonksiyona aktarılacak kullanıcı verisi (const void\* veya NULL). |
| `void` | `gfx_object_add_smartcallback(Evas_Object *object, const char *event, Evas_Smart_Cb func, const void *data)` | Widget seviyesindeki yüksek seviye akıllı olaylara (örneğin "clicked", "changed") dinleyici ekler. | **object:** Hedef widget nesnesi (Evas\_Object\*). **event:** Akıllı sinyal adı (örn: "clicked", "selected", "changed"). **func:** Geri çağırım fonksiyonu (Evas\_Smart\_Cb). **data:** Aktarılacak kullanıcı verisi (const void\* veya NULL). |
| `void` | `gfx_object_set_focus(Evas_Object *object, Eina_Bool focus)` | Nesneye klavye odağını verir veya nesneden odağı kaldırır. | **object:** Hedef nesne (Evas\_Object\*). **focus:** Odak durumu (EINA\_TRUE odaklanır, EINA\_FALSE odağı bırakır). |
| `void` | `gfx_object_set_clip(Evas_Object *object, Evas_Object *clip)` | Nesnenin görünürlük ve alfa sınırlarını maskeleyici (clip) başka bir nesne ile sınırlandırır. | **object:** Maskelenecek nesne (Evas\_Object\*). **clip:** Maske nesnesi (genellikle bir dikdörtgen, Evas\_Object\*). |
| `void` | `gfx_object_unset_clip(Evas_Object *object)` | Nesne üzerindeki maskelemeyi (clip) kaldırarak orijinal sınırlarına döndürür. | **object:** Maskesi kaldırılacak nesne (Evas\_Object\*). |

---

## **7\. Ecore Sistem ve Olay Döngüsü (Ecore Functions)**

* 

| Dönüş Tipi | Fonksiyon Prototipi | İşlevi (Ne İşe Yarar?) | Parametreler ve Alabileceği Değerler |
| :---- | :---- | :---- | :---- |
| `int` | `gfx_ecore_init(void)` | Ecore sistem olay döngüsünü ve zamanlayıcı modüllerini başlatır (referans sayacı döndürür). | *Parametre almaz.* |
| `int` | `gfx_ecore_shutdown(void)` | Ecore modülünü kapatır ve sistem kaynaklarını temizler. | *Parametre almaz.* |
| `void` | `gfx_start_mainloop(void)` | Ecore ana döngüsünü başlatarak olayları işlemeye başlar. | *Parametre almaz.* |
| `void` | `gfx_quit_mainloop(void)` | Ecore ana döngüsünü durdurur ve akışın dönmesini sağlar. | *Parametre almaz.* |
| `double` | `gfx_get_looptime(void)` | Ana döngünün mevcut iterasyon başlangıç zaman damgasını saniye cinsinden döndürür. | *Parametre almaz.* |
| `Ecore_Timer *` | `gfx_add_timer(double in, Ecore_Task_Cb func, const void *data)` | Belirtilen saniye aralığında periyodik olarak tetiklenen bir zamanlayıcı kaydeder. | **in:** Tetiklenme aralığı (saniye cinsinden double, \> 0.0). **func:** Çağrılacak görev fonksiyonu (Ecore\_Task\_Cb). **data:** Göreve aktarılacak kullanıcı verisi (const void\* veya NULL). |
| `void *` | `gfx_del_timer(Ecore_Timer *timer)` | Çalışan bir zamanlayıcıyı iptal eder ve siler; bağlı kullanıcı verisini döndürür. | **timer:** Silinecek zamanlayıcı nesnesi (geçerli Ecore\_Timer\*). |
| `void` | `gfx_timer_set_interval(Ecore_Timer *timer, double in)` | Mevcut bir zamanlayıcının periyot süresini günceller. | **timer:** Zamanlayıcı nesnesi (Ecore\_Timer\*). **in:** Yeni aralık süresi (saniye double, \> 0.0). |
| `Ecore_Idler *` | `gfx_add_idler(Ecore_Task_Cb func, const void *data)` | Ana döngüde işlenecek başka bir olay kalmadığında (boşta/idle anında) çalışacak görev kaydeder. | **func:** Boşta çağrılacak görev fonksiyonu (Ecore\_Task\_Cb). **data:** Kullanıcı verisi (const void\* veya NULL). |
| `void *` | `gfx_del_idler(Ecore_Idler *idler)` | Kayıtlı bir idler görevini siler ve verisini döndürür. | **idler:** Silinecek görev nesnesi (Ecore\_Idler\*). |
| `Ecore_Poller *` | `gfx_add_poller(Ecore_Poller_Type type, int interval, Ecore_Task_Cb func, const void *data)` | Sistem durumunu belirli kene (tick) frekanslarında yoklayan bir poller kaydeder. | **type:** Yoklama türü (ECORE\_POLLER\_CORE vb. Ecore\_Poller\_Type). **interval:** Kene frekansı (1, 2, 4, 8 gibi 2'nin üssü int \>= 1). **func:** Çağrılacak fonksiyon (Ecore\_Task\_Cb). **data:** Kullanıcı verisi (const void\* veya NULL). |
| `void *` | `gfx_del_poller(Ecore_Poller *poller)` | Kayıtlı bir poller nesnesini kaldırır ve verisini döndürür. | **poller:** Silinecek poller nesnesi (Ecore\_Poller\*). |
| `Ecore_Thread *` | `gfx_run_thread(Ecore_Thread_Cb func_heavy, Ecore_Thread_Cb func_end, Ecore_Thread_Cb func_cancel, const void *data)` | Arayüzü dondurmamak için ağır hesaplamaları arka plan iş parçacığında çalıştırır. | **func\_heavy:** Arka plan iş fonksiyonu (Ecore\_Thread\_Cb). **func\_end:** İşlem bitince ana iş parçacığında çağrılacak fonksiyon (Ecore\_Thread\_Cb veya NULL). **func\_cancel:** İptal durumunda çağrılacak fonksiyon (Ecore\_Thread\_Cb veya NULL). **data:** İş parçacığına aktarılacak veri (const void\* veya NULL). |
| `Ecore_Thread *` | `gfx_thread_run_feedback(Ecore_Thread_Heavy_Cb func_heavy, Ecore_Thread_Notify_Cb func_notify, Ecore_Thread_Cb func_end, Ecore_Thread_Cb func_cancel, const void *data, Eina_Bool try_no_queue)` | Çalışırken ana iş parçacığına ara ilerleme bildirimleri (feedback) gönderebilen arka plan iş parçacığı başlatır. | **func\_heavy:** Ağır iş fonksiyonu (Ecore\_Thread\_Heavy\_Cb). **func\_notify:** Bildirim sinyali fonksiyonu (Ecore\_Thread\_Notify\_Cb veya NULL). **func\_end:** Bitiş fonksiyonu (Ecore\_Thread\_Cb veya NULL). **func\_cancel:** İptal fonksiyonu (Ecore\_Thread\_Cb veya NULL). **data:** Paylaşılan veri (const void\* veya NULL). **try\_no\_queue:** Sıraya sokmadan anında çalıştırma tercihi (EINA\_TRUE veya EINA\_FALSE). |
| `Ecore_Exe *` | `gfx_execute_run(const char *exe_cmd, const void *data)` | İşletim sistemi düzeyinde harici bir program/kabuk komutu çalıştırır. | **exe\_cmd:** Çalıştırılacak komut dizesi (geçerli string). **data:** Sürece bağlanacak veri (const void\* veya NULL). |
| `int` | `gfx_execute_terminate(Ecore_Exe *exe)` | Çalışan harici alt sürece nazik sonlandırma sinyali (SIGTERM) gönderir. | **exe:** Süreç nesnesi (geçerli Ecore\_Exe\*). |
| `int` | `gfx_execute_kill(Ecore_Exe *exe)` | Çalışan harici alt süreci zorla öldürme sinyali (SIGKILL) ile anında sonlandırır. | **exe:** Süreç nesnesi (geçerli Ecore\_Exe\*). |
| `Ecore_Fd_Handler *` | `gfx_add_fdhandler(int fd, Ecore_Fd_Handler_Flags flags, Ecore_Fd_Cb func, const void *data, Ecore_Fd_Cb buf_func, const void *buf_data)` | Dosya tanımlayıcısını (soket, dosya, pipe) ana döngüde I/O olayları için dinlemeye alır. | **fd:** Dosya tanımlayıcısı (geçerli tamsayı \>= 0). **flags:** İzleme bayrakları (ECORE\_FD\_READ, WRITE, ERROR vb. Ecore\_Fd\_Handler\_Flags). **func:** I/O olay fonksiyonu (Ecore\_Fd\_Cb). **data, buf\_func, buf\_data:** Ek callback ve kullanıcı verileri (uygun göstericiler veya NULL). |
| `Ecore_Event_Handler *` | `gfx_add_eventhandler(int type, Ecore_Event_Cb func, const void *data)` | Sistem veya özel bir Ecore olay türünü yakalamak için olay işleyici kaydeder. | **type:** Olay tipi kimliği (int \> 0, ecore\_event\_type\_new() ile üretilen değer). **func:** Olay yakalandığında çağrılacak işleyici (Ecore\_Event\_Cb). **data:** Kullanıcı verisi (const void\* veya NULL). |

* 

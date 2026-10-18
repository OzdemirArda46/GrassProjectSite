# EFL Soyutlama Katmanı (gfx) \- Eksiksiz Dökümantasyon

## 1\. Genel ve Çekirdek Fonksiyonlar (General Functions)

* **`int gfx_init(int argc, char **argv)`**: Elementary ve Ecore kütüphanelerini başlatır.  
* **`int gfx_run(void)`**: Ana uygulama döngüsünü (`elm_run`) başlatır.  
* **`int gfx_exit(void)`**: Ecore ana döngüsünü kapatır ve Elementary'den çıkar.  
* **`int gfx_shutdown(void)`**: Elementary ve Ecore kütüphanelerini kapatır, kaynakları temizler.

## 2\. Pencere Fonksiyonları (Window Functions)

* **`Evas_Object *gfx_object_add_feature_window(const char *name, const char *title)`**: Standart özelliklere sahip yeni bir pencere oluşturur.  
* **`Evas_Object *gfx_object_add_standard_window(Evas_Object *parent, const char *name, Elm_Win_Type type)`**: Belirtilen ebeveyn ve tipte standart bir pencere ekler.  
* **`int gfx_window_set_title(Evas_Object *object, const char *title)`**: Pencerenin başlığını ayarlar.  
* **`int gfx_window_set_autodel(Evas_Object *object, Eina_Bool autodel)`**: Pencere kapatıldığında otomatik silinme seçeneğini ayarlar.  
* **`int gfx_window_set_center(Evas_Object *object, Eina_Bool h, Eina_Bool v)`**: Pencereyi ekranda yatay ve/veya dikey olarak ortalar.  
* **`int gfx_window_set_minsize(Evas_Object *object, int w, int h)`**: Pencerenin alabileceği minimum boyutları belirler.  
* **`int gfx_window_set_fullscreen(Evas_Object *object, Eina_Bool full)`**: Pencereyi tam ekran moduna geçirir veya çıkarır.  
* **`int gfx_window_set_active(Evas_Object *object)`**: Pencereyi aktif/odaklanmış duruma getirir.  
* **`int gfx_window_set_iconified(Evas_Object *object, Eina_Bool iconified)`**: Pencereyi simge durumuna küçültür veya geri yükler.  
* **`int gfx_window_set_sticky(Evas_Object *object, Eina_Bool sticky)`**: Pencereyi tüm sanal masaüstlerinde sabit/görünür yapar.  
* **`int gfx_window_proportion_scale(Evas_Object *object, Evas_Object *subobject)`**: Pencereye otomatik ölçeklenen/yeniden boyutlandırılan alt nesne ekler.  
* **`void gfx_window_set_autohide(Evas_Object *object, Eina_Bool autohide)`**: Kapatma tuşuna basıldığında pencerenin silinmeyip gizlenmesini sağlar.

## 3\. Bileşen Ekleme Fonksiyonları (Widget Addition Functions)

* **`Evas_Object *gfx_object_add_button(Evas_Object *parent)`**: Buton bileşeni ekler.  
* **`Evas_Object *gfx_object_add_checkbutton(Evas_Object *parent)`**: Onay kutusu (check) bileşeni ekler.  
* **`Evas_Object *gfx_object_add_radiobutton(Evas_Object *parent)`**: Seçenek (radyo) butonu ekler.  
* **`Evas_Object *gfx_object_add_entry(Evas_Object *parent)`**: Metin giriş alanı (entry) ekler.  
* **`Evas_Object *gfx_object_add_slider(Evas_Object *parent)`**: Kaydırıcı (slider) bileşeni ekler.  
* **`Evas_Object *gfx_object_add_spinner(Evas_Object *parent)`**: Sayısal değer artırma/azaltma bileşeni (spinner) ekler.  
* **`Evas_Object *gfx_object_add_combobox(Evas_Object *parent)`**: Açılır liste (combobox) bileşeni ekler.  
* **`Evas_Object *gfx_object_add_label(Evas_Object *parent)`**: Metin etiketi (label) ekler.  
* **`Evas_Object *gfx_object_add_icon(Evas_Object *parent)`**: İkon bileşeni ekler.  
* **`Evas_Object *gfx_object_add_image(Evas_Object *parent)`**: Resim gösterim bileşeni ekler.  
* **`Evas_Object *gfx_object_add_progressbar(Evas_Object *parent)`**: İlerleme çubuğu (progress bar) ekler.  
* **`Evas_Object *gfx_object_add_bubble(Evas_Object *parent)`**: Baloncuk mesaj bileşeni ekler.  
* **`Evas_Object *gfx_object_add_clock(Evas_Object *parent)`**: Saat bileşeni ekler.  
* **`Evas_Object *gfx_object_add_calendar(Evas_Object *parent)`**: Takvim bileşeni ekler.  
* **`Evas_Object *gfx_object_add_separator(Evas_Object *parent)`**: Ayırıcı çizgi ekler.  
* **`Evas_Object *gfx_object_add_popup(Evas_Object *parent)`**: Açılır bildirim/pencere (popup) bileşeni ekler.

## 4\. Kutu Düzeni Fonksiyonları (Box Functions)

* **`Evas_Object *gfx_object_add_box(Evas_Object *parent)`**: Kutu (box) düzeni konteyneri ekler.  
* **`void gfx_box_set_horizontal(Evas_Object *object, Eina_Bool horizontal)`**: Kutunun yönünü yatay veya dikey olarak ayarlar.  
* **`Eina_Bool gfx_box_get_horizontal(const Evas_Object *object)`**: Kutunun yatay olup olmadığını döndürür.  
* **`void gfx_box_pack_start(Evas_Object *object, Evas_Object *child)`**: Elemanı kutunun başına ekler.  
* **`void gfx_box_pack_end(Evas_Object *object, Evas_Object *child)`**: Elemanı kutunun sonuna ekler.  
* **`void gfx_box_pack_before(Evas_Object *object, Evas_Object *child, Evas_Object *before)`**: Elemanı belirtilen başka bir elemandan hemen önce kutuya yerleştirir.  
* **`void gfx_box_pack_after(Evas_Object *object, Evas_Object *child, Evas_Object *after)`**: Elemanı belirtilen başka bir elemandan hemen sonra kutuya yerleştirir.  
* **`void gfx_box_unpack(Evas_Object *object, Evas_Object *child)`**: Elemanı kutudan çıkarır.  
* **`void gfx_box_unpack_all(Evas_Object *object)`**: Kutudaki tüm elemanları paketten çıkarır.  
* **`void gfx_box_set_homogeneous(Evas_Object *object, Eina_Bool homogeneous)`**: Kutu içindeki tüm elemanların eşit boyutta olmasını ayarlar.  
* **`Eina_Bool gfx_box_get_homogeneous(Evas_Object *object)`**: Kutunun homojen boyutta olup olmadığını döndürür.  
* **`void gfx_box_set_padding(Evas_Object *object, Evas_Coord horizontal, Evas_Coord vertical)`**: Elemanlar arası yatay ve dikey boşlukları (padding) ayarlar.  
* **`void gfx_box_get_padding(Evas_Object *object, Evas_Coord *horizontal, Evas_Coord *vertical)`**: Elemanlar arası iç boşluk değerlerini alır.  
* **`void gfx_box_set_align(Evas_Object *object, double horizontal, double vertical)`**: Kutu içeriğinin genel hizalamasını ayarlar.  
* **`void gfx_box_get_align(Evas_Object *object, double *horizontal, double *vertical)`**: Kutu içeriğinin hizalama değerlerini alır.  
* **`Eina_List *gfx_box_get_children(const Evas_Object *object)`**: Kutunun içerdiği tüm alt elemanların listesini döndürür.

## 5\. Izgara Düzeni Fonksiyonları (Grid Functions)

* **`Evas_Object *gfx_object_add_grid(Evas_Object *parent)`**: Izgara (grid) düzeni ekler.  
* **`void gfx_grid_set_size(Evas_Object *object, int w, int h)`**: Izgaranın sanal Genişlik ve Yükseklik boyutunu ayarlar.  
* **`void gfx_grid_get_size(const Evas_Object *object, int *w, int *h)`**: Izgaranın sanal boyut değerlerini alır.  
* **`void gfx_grid_add_pack(Evas_Object *object, Evas_Object *subobject, int x, int y, int w, int h)`**: Alt nesneyi belirtilen koordinat ve boyutlarda ızgaraya ekler.  
* **`void gfx_grid_unpack(Evas_Object *object, Evas_Object *subobject)`**: Alt nesneyi ızgaradan çıkarır.  
* **`void gfx_grid_set_pack(Evas_Object *subobject, Evas_Coord x, Evas_Coord y, Evas_Coord w, Evas_Coord h)`**: Izgaradaki bir alt nesnenin konum ve boyutunu günceller.  
* **`void gfx_grid_get_pack(Evas_Object *subobject, Evas_Coord *x, Evas_Coord *y, Evas_Coord *w, Evas_Coord *h)`**: Alt nesnenin ızgaradaki konum ve boyut bilgilerini alır.  
* **`Eina_List *gfx_grid_get_children(const Evas_Object *object)`**: Izgaradaki tüm elemanların listesini döndürür.  
* **`void gfx_grid_clear(Evas_Object *object, Eina_Bool clear)`**: Izgaradaki tüm nesneleri temizler/kaldırır.

## 6\. Tablo Düzeni Fonksiyonları (Table Functions)

* **`Evas_Object *gfx_object_add_table(Evas_Object *parent)`**: Tablo düzeni (table) ekler.  
* **`void gfx_table_set_align(Evas_Object *object, double horizontal, double vertical)`**: Tablonun genel hizalamasını ayarlar.  
* **`void gfx_table_get_align(const Evas_Object *object, double *horizontal, double *vertical)`**: Tablonun hizalama değerlerini alır.  
* **`Evas_Object *gfx_table_get_child(const Evas_Object *object, int col, int row)`**: Belirtilen sütun ve satırdaki alt nesneyi döndürür.  
* **`void gfx_table_clear(Evas_Object *object, Eina_Bool clear)`**: Tablodaki tüm elemanları temizler.  
* **`void gfx_table_set_homogeneous(Evas_Object *object, Eina_Bool homogeneous)`**: Tablo hücrelerinin eşit boyutta olmasını ayarlar.  
* **`Eina_Bool gfx_table_get_homogeneous(const Evas_Object *object)`**: Tablonun homojen hücre yapısında olup olmadığını döndürür.  
* **`void gfx_table_pack(Evas_Object *object, Evas_Object *subobject, int col, int row, int colspan, int rowspan)`**: Alt nesneyi belirtilen sütun, satır ve hücre yayılımı (span) ile tabloya yerleştirir.  
* **`void gfx_table_set_pack(Evas_Object *subobject, int col, int row, int colspan, int rowspan)`**: Tablodaki alt nesnenin hücre konumunu ve yayılımını günceller.  
* **`void gfx_table_get_pack(Evas_Object *subobject, int *col, int *row, int *colspan, int *rowspan)`**: Alt nesnenin tablodaki hücre yerleşim bilgilerini alır.  
* **`void gfx_table_set_padding(Evas_Object *object, Evas_Coord horizontal, Evas_Coord vertical)`**: Tablo hücreleri arasındaki yatay ve dikey boşlukları ayarlar.  
* **`void gfx_table_get_padding(Evas_Object *object, Evas_Coord *horizontal, Evas_Coord *vertical)`**: Tablo hücre boşluk değerlerini alır.  
* **`void gfx_table_unpack(Evas_Object *object, Evas_Object *subobject)`**: Alt nesneyi tablodan çıkarır.

## 7\. Kaydırma Alanı Fonksiyonları (Scroller Functions)

* **`Evas_Object *gfx_object_add_scroller(Evas_Object *parent)`**: Kaydırılabilir alan (scroller) ekler.  
* **`void gfx_scroller_set_policy(Evas_Object *object, Elm_Scroller_Policy policy_h, Elm_Scroller_Policy policy_v)`**: Yatay ve dikey kaydırma çubuğu görünürlük politikalarını ayarlar.  
* **`void gfx_scroller_get_policy(const Evas_Object *object, Elm_Scroller_Policy *policy_h, Elm_Scroller_Policy *policy_v)`**: Kaydırma çubuğu politikalarını alır.  
* **`void gfx_scroller_set_region(Evas_Object *object, Evas_Coord x, Evas_Coord y, Evas_Coord w, Evas_Coord h)`**: Kaydırma alanında görüntülenecek bölgeyi ayarlar.  
* **`void gfx_scroller_get_region(const Evas_Object *object, Evas_Coord *x, Evas_Coord *y, Evas_Coord *w, Evas_Coord *h)`**: Görünür bölge koordinat ve boyutlarını alır.  
* **`void gfx_scroller_get_position(const Evas_Object *object, Evas_Coord *x, Evas_Coord *y)`**: Mevcut kaydırma konumunu alır.  
* **`void gfx_scroller_set_pagesize(Evas_Object *object, Evas_Coord w, Evas_Coord h)`**: Sayfa bazlı kaydırma için sayfa boyutunu ayarlar.  
* **`void gfx_scroller_get_pagesize(const Evas_Object *object, Evas_Coord *w, Evas_Coord *h)`**: Sayfa boyutu değerlerini alır.  
* **`void gfx_scroller_get_currentpage(const Evas_Object *object, int *hp, int *vp)`**: Mevcut aktif yatay ve dikey sayfa indekslerini alır.  
* **`void gfx_scroller_show_page(Evas_Object *object, int hp, int vp)`**: Belirtilen indeksteki sayfaya kaydırır.  
* **`void gfx_scroller_set_bounce(Evas_Object *object, Eina_Bool h_bounce, Eina_Bool v_bounce)`**: Kaydırma sınırlarına ulaşıldığında esneme/zıplama (bounce) efektini ayarlar.  
* **`void gfx_scroller_get_bounce(const Evas_Object *object, Eina_Bool *h_bounce, Eina_Bool *v_bounce)`**: Esneme efekti durumunu alır.

## 8\. Çerçeve Fonksiyonları (Frame Functions)

* **`Evas_Object *gfx_object_add_frame(Evas_Object *parent)`**: Çerçeve (frame) konteyneri ekler.  
* **`void gfx_frame_set_autocollapse(Evas_Object *object, Eina_Bool autocollapse)`**: Çerçevenin otomatik katlanma/kapanma özelliğini ayarlar.  
* **`Eina_Bool gfx_frame_get_autocollapse(const Evas_Object *object)`**: Otomatik katlanma özelliğinin açık olup olmadığını döndürür.  
* **`void gfx_frame_set_collapse(Evas_Object *object, Eina_Bool collapse)`**: Çerçeveyi katlar (daraltır) veya açar.  
* **`Eina_Bool gfx_frame_get_collapse(const Evas_Object *object)`**: Çerçevenin katlanmış durumda olup olmadığını döndürür.

## 9\. Nesne Yönetimi Fonksiyonları (Object Management Functions)

* **`void gfx_object_set_text(Evas_Object *object, const char *text)`**: Nesnenin ana metin içeriğini ayarlar.  
* **`const char *gfx_object_get_text(const Evas_Object *object)`**: Nesnenin metin içeriğini döndürür.  
* **`void gfx_object_set_content(Evas_Object *object, Evas_Object *content)`**: Nesnenin ana içerik bölgesine başka bir nesne yerleştirir.  
* **`Evas_Object *gfx_object_get_content(const Evas_Object *object)`**: Nesnenin ana içerik nesnesini döndürür.  
* **`Eina_Bool gfx_image_set_file(Evas_Object *object, const char *file, const char *group)`**: Resim bileşenine dosya veya gruptan resim yükler.  
* **`Eina_Bool gfx_icon_set_standard(Evas_Object *object, const char *name)`**: İkon nesnesine freedesktop/sistem standardında ikon ismi atar.  
* **`void gfx_object_set_parttext(Evas_Object *object, const char *part, const char *text)`**: Nesnenin belirli bir parçasına (part) metin atar.  
* **`void gfx_object_set_partcontent(Evas_Object *object, const char *part, Evas_Object *content)`**: Nesnenin belirli bir parçasına başka bir içerik nesnesi yerleştirir.  
* **`Eina_Bool gfx_set_policy(unsigned int policy, int value)`**: Genel Elementary ilkesini/politikasını ayarlar.  
* **`void gfx_object_set_disabled(Evas_Object *object, Eina_Bool disabled)`**: Nesneyi devre dışı bırakır (pasifleştirir) veya etkinleştirir.

## 10\. Girdi ve Durum Fonksiyonları (Entry and State Functions)

* **`void gfx_entry_set_text(Evas_Object *object, const char *text)`**: Metin giriş alanının içeriğini ayarlar.  
* **`const char *gfx_entry_get_text(const Evas_Object *object)`**: Metin giriş alanındaki yazıyı alır.  
* **`void gfx_entry_set_singleline(Evas_Object *object, Eina_Bool single_line)`**: Giriş alanını tek satırlı veya çok satırlı yapar.  
* **`void gfx_entry_set_password(Evas_Object *object, Eina_Bool password)`**: Giriş alanını parola moduna (gizli karakterler) alır.  
* **`void gfx_check_set_state(Evas_Object *object, Eina_Bool checked)`**: Onay kutusunun seçili durumunu ayarlar.  
* **`Eina_Bool gfx_check_get_state(const Evas_Object *object)`**: Onay kutusunun seçili olup olmadığını döndürür.  
* **`void gfx_radio_set_statevalue(Evas_Object *object, int value)`**: Radyo butonunun temsil ettiği durum değerini ayarlar.  
* **`void gfx_radio_set_value(Evas_Object *object, int value)`**: Radyo grubunun aktif durum değerini ayarlar.  
* **`int gfx_radio_get_value(const Evas_Object *object)`**: Seçili radyo butonunun değerini almaktadır.  
* **`void gfx_radio_add_group(Evas_Object *object, Evas_Object *group)`**: Radyo butonunu bir radyo grubuna ekler.  
* **`void gfx_slider_set_minmax(Evas_Object *object, double min, double max)`**: Kaydırıcının minimum ve maksimum değerlerini ayarlar.  
* **`void gfx_slider_set_unitformat(Evas_Object *object, const char *format)`**: Kaydırıcı değerinin ekrandaki birim biçimini (örn. "%1.2f") ayarlar.  
* **`void gfx_slider_set_value(Evas_Object *object, double value)`**: Kaydırıcının mevcut değerini ayarlar.  
* **`double gfx_slider_get_value(const Evas_Object *object)`**: Kaydırıcının mevcut değerini döndürür.

## 11\. Genel Liste Fonksiyonları (Genlist Functions)

* **`Elm_Object_Item *gfx_genlist_add_item(Evas_Object *object, const Elm_Genlist_Item_Class *itemclass, const void *data, Elm_Object_Item *parent, Elm_Genlist_Item_Type flags, Evas_Smart_Cb function, const void *function_data)`**: Genlist bileşenine yeni bir eleman ekler.  
* **`void gfx_genlist_clear(Evas_Object *object)`**: Genlist içindeki tüm elemanları temizler.  
* **`Elm_Genlist_Item_Class *gfx_genlist_add_itemclass(void)`**: Yeni bir Genlist eleman sınıfı oluşturur.  
* **`void gfx_genlist_free_itemclass(Elm_Genlist_Item_Class *itemclass)`**: Oluşturulan eleman sınıfını bellekten serbest bırakır.

## 12\. Arka Plan Fonksiyonları (Background Functions)

* **`Evas_Object *gfx_object_add_background(Evas_Object *parent)`**: Arka plan (bg) bileşeni ekler.  
* **`Eina_Bool gfx_background_set_file(Evas_Object *object, const char *file, const char *group)`**: Arka plana resim/Edje dosyası atar.  
* **`void gfx_background_get_file(const Evas_Object *object, const char **file, const char **group)`**: Arka plan dosya ve grup bilgilerini alır.  
* **`void gfx_background_set_option(Evas_Object *object, Elm_Bg_Option option)`**: Arka plan resminin yerleşim seçeneğini (döşeme, ölçekleme, ortalama vb.) ayarlar.  
* **`Elm_Bg_Option gfx_background_get_option(const Evas_Object *object)`**: Arka plan yerleşim seçeneğini döndürür.  
* **`void gfx_background_set_color(Evas_Object *object, int r, int g, int b)`**: Düz renk arka plan için RGB değerlerini ayarlar.  
* **`void gfx_background_get_color(const Evas_Object *object, int *r, int *g, int *b)`**: Arka plan renk değerlerini alır.  
* **`void gfx_background_set_loadsize(Evas_Object *object, int w, int h)`**: Arka plan resminin yükleme boyutunu sınırlayarak bellek tasarrufu sağlar.

## 13\. Evas Tuval ve Temel Nesne Fonksiyonları (Canvas and Basic Object Management)

* **`Evas *gfx_object_get_evas(const Evas_Object *object)`**: Nesnenin bağlı olduğu Evas tuvalini (canvas) döndürür.  
* **`void gfx_object_show(Evas_Object *object)`**: Nesneyi görünür yapar.  
* **`void gfx_object_hide(Evas_Object *object)`**: Nesneyi gizler.  
* **`void gfx_object_del(Evas_Object *object)`**: Nesneyi tuvalden ve bellekten siler.  
* **`void gfx_object_raise(Evas_Object *object)`**: Nesneyi katman sırasında öne/üst seviyeye çıkarır.  
* **`void gfx_object_lower(Evas_Object *object)`**: Nesneyi katman sırasında arkaya/alt seviyeye indirir.  
* **`void gfx_object_set_size_hintweight(Evas_Object *object, double x, double y)`**: Nesnenin genişleme/ağırlık ipucunu (size hint weight) ayarlar.  
* **`void gfx_object_set_size_hintalign(Evas_Object *object, double x, double y)`**: Nesnenin hizalama ipucunu (size hint align) ayarlar.

## 14\. Geometri, Konum ve Renk Fonksiyonları (Geometry, Position and Color)

* **`void gfx_object_move(Evas_Object *object, Evas_Coord x, Evas_Coord y)`**: Nesneyi belirtilen (X, Y) koordinatlarına taşır.  
* **`void gfx_object_resize(Evas_Object *object, Evas_Coord w, Evas_Coord h)`**: Nesnenin genişlik ve yüksekliğini değiştirir.  
* **`void gfx_object_get_geometry(Evas_Object *object, Evas_Coord *x, Evas_Coord *y, Evas_Coord *w, Evas_Coord *h)`**: Nesnenin konum ve boyut bilgilerini alır.  
* **`void gfx_object_set_color(Evas_Object *object, int r, int g, int b, int a)`**: Nesne rengini ve şeffaflığını (RGBA \- premapplied) ayarlar.  
* **`void gfx_object_get_color(const Evas_Object *object, int *r, int *g, int *b, int *a)`**: Nesnenin renk ve şeffaflık değerlerini alır.

## 15\. Evas Nesne Oluşturma Fonksiyonları (Object Creation / Factory)

* **`Evas_Object *gfx_object_add_rectangle(Evas *canvas)`**: Tuval üzerinde ham bir dikdörtgen (rectangle) nesnesi oluşturur.  
* **`Evas_Object *gfx_object_add_rawimage(Evas *canvas)`**: Tuval üzerinde ham bir Evas resim (image) nesnesi oluşturur.  
* **`Evas_Object *gfx_object_add_text(Evas *canvas)`**: Tuval üzerinde ham dize metin (text) nesnesi oluşturur.  
* **`Evas_Object *gfx_object_add_textblock(Evas *canvas)`**: Tuval üzerinde biçimlendirilmiş metin bloğu (textblock) nesnesi oluşturur.

## 16\. Evas Resim Fonksiyonları (Image Operations)

* **`void gfx_object_set_imagefile(Evas_Object *object, const char *file, const char *key)`**: Evas resim nesnesine dosya yolu ve anahtar (key) ile resim atar.  
* **`void gfx_object_set_imagefilled(Evas_Object *object, Eina_Bool filled)`**: Resmin nesne alanını tamamen dolduracak şekilde otomatik ölçeklenmesini ayarlar.  
* **`void gfx_object_set_imagesize(Evas_Object *object, int w, int h)`**: Resmin piksel veri boyutunu manuel olarak ayarlar.  
* **`void gfx_object_get_imagesize(Evas_Object *object, int *w, int *h)`**: Resmin piksel boyut değerlerini alır.

## 17\. Evas Metin Fonksiyonları (Text Operations)

* **`Eina_Bool gfx_object_set_textfont(Evas_Object *object, const char *font, Evas_Font_Size size)`**: Metin nesnesinin yazı tipini ve punto boyutunu ayarlar.  
* **`void gfx_object_set_rawtext(Evas_Object *object, const char *text)`**: Ham Evas metin nesnesinin yazısını ayarlar.  
* **`const char *gfx_object_get_rawtext(const Evas_Object *object)`**: Ham Evas metin nesnesinin yazısını alır.  
* **`Eina_Bool gfx_object_set_textblockmarkup(Evas_Object *object, const char *text)`**: Textblock nesnesine markup/HTML benzeri biçimlendirilmiş metin atar.

## 18\. Olaylar ve Etkileşim Fonksiyonları (Events and Interaction)

* **`void gfx_object_add_eventcallback(Evas_Object *object, Evas_Callback_Type type, Evas_Object_Event_Cb func, const void *data)`**: Nesneye Evas seviyesinde (tıklama, fare hareketi vb.) olay geri çağırımı (callback) ekler.  
* **`void gfx_object_add_smartcallback(Evas_Object *object, const char *event, Evas_Smart_Cb func, const void *data)`**: Akıllı bileşene (Elementary seviyesinde "clicked", "changed" vb.) olay geri çağırımı ekler.  
* **`void gfx_object_set_focus(Evas_Object *object, Eina_Bool focus)`**: Nesneye klavye odağı (focus) verir veya odağı kaldırır.

## 19\. Kırpma ve Maskeleme Fonksiyonları (Cropping / Masking)

* **`void gfx_object_set_clip(Evas_Object *object, Evas_Object *clip)`**: Nesneyi başka bir nesnenin (örneğin dikdörtgen) sınırları ile kırpar/maskeler.  
* **`void gfx_object_unset_clip(Evas_Object *object)`**: Nesne üzerindeki kırpıcı/maske bağını kaldırır.

## 20\. Ecore Başlatma ve Kapatma Fonksiyonları (Ecore Initialization & Shutdown)

* **`int gfx_ecore_init(void)`**: Ecore modülünü bağımsız olarak başlatır.  
* **`int gfx_ecore_shutdown(void)`**: Ecore modülünü kapatır ve kaynakları serbest bırakır.

## 21\. Ecore Ana Döngü Fonksiyonları (Main Loop Functions)

* **`void gfx_start_mainloop(void)`**: Ecore ana olay döngüsünü başlatır.  
* **`void gfx_quit_mainloop(void)`**: Ecore ana olay döngüsünü durdurur/sonlandırır.  
* **`double gfx_get_looptime(void)`**: Ana döngünün mevcut zaman damgasını (saniye cinsinden double) alır.

## 22\. Zamanlayıcı Fonksiyonları (Timer Functions)

* **`Ecore_Timer *gfx_add_timer(double in_seconds, Ecore_Task_Cb func, const void *data)`**: Periyodik olarak çalışacak yeni bir zamanlayıcı ekler.  
* **`void gfx_del_timer(Ecore_Timer *timer)`**: Zamanlayıcıyı siler ve iptal eder.  
* **`void gfx_timer_set_interval(Ecore_Timer *timer, double in_seconds)`**: Zamanlayıcının çalışma aralığını günceller.  
* **`double gfx_timer_get_interval(const Ecore_Timer *timer)`**: Zamanlayıcının çalışma aralığını saniye cinsinden döndürür.  
* **`void gfx_timer_delay(Ecore_Timer *timer, double add)`**: Zamanlayıcının bir sonraki tetiklenmesini belirtilen saniye kadar erteler.  
* **`void gfx_timer_freeze(Ecore_Timer *timer)`**: Zamanlayıcıyı geçici olarak dondurur/durdurur.  
* **`void gfx_timer_thaw(Ecore_Timer *timer)`**: Dondurulmuş zamanlayıcıyı yeniden başlatır.

## 23\. Ecore Boşta Durum Fonksiyonları (Idler Functions)

* **`Ecore_Idler *gfx_add_idler(Ecore_Task_Cb func, const void *data)`**: Sistem boşta kaldığında (idle) çalışacak görev ekler.  
* **`void *gfx_del_idler(Ecore_Idler *idler)`**: Boşta durum görevini kaldırır.

## 24\. Ecore Yoklama Fonksiyonları (Poller Functions)

* **`Ecore_Poller *gfx_add_poller(Ecore_Poller_Type type, int interval, Ecore_Task_Cb func, const void *data)`**: Düzenli aralıklarla yoklama yapan bir poller ekler.  
* **`void *gfx_del_poller(Ecore_Poller *poller)`**: Yoklama görevini kaldırır.

## 25\. İş Parçacığı Fonksiyonları (Thread Functions)

* **`Ecore_Thread *gfx_run_thread(Ecore_Thread_Cb func_blocking, Ecore_Thread_Cb func_end, Ecore_Thread_Cb func_cancel, const void *data)`**: Arka planda engelleyici (blocking) iş parçacığı çalıştırır.  
* **`Ecore_Thread *gfx_thread_run_feedback(Ecore_Thread_Cb func_heavy, Ecore_Thread_Notify_Cb func_notify, Ecore_Thread_Cb func_end, Ecore_Thread_Cb func_cancel, const void *data, Eina_Bool try_no_queue)`**: Arka planda çalışan ve ana iş parçacığına geri bildirim (notify) gönderebilen iş parçacığı çalıştırır.  
* **`Eina_Bool gfx_thread_cancel(Ecore_Thread *th)`**: Çalışan iş parçacığına iptal sinyali gönderir.  
* **`void gfx_thread_add_localdata(Ecore_Thread *th, const char *key, void *value, Eina_Free_Cb cb, Eina_Bool direct)`**: İş parçacığına yerel veri bağlar.

## 26\. İşlem Çalıştırma Fonksiyonları (Process Execution Functions)

* **`Ecore_Exe *gfx_execute_run(const char *exe_command, const void *data)`**: Harici sistem komutunu arka planda çalıştırır.  
* **`Ecore_Exe *gfx_execute_run_cb(const char *exe_command, Ecore_Exe_Cb func, const void *data)`**: Harici komutu çalıştırır ve işlem ile iletişim kurar.  
* **`void gfx_execute_terminate(Ecore_Exe *exe)`**: Çalışan harici işleme SIGTERM sinyali göndererek sonlandırır.  
* **`void gfx_execute_kill(Ecore_Exe *exe)`**: Çalışan harici işleme SIGKILL sinyali göndererek zorla öldürür.  
* **`pid_t gfx_execute_get_pid(const Ecore_Exe *exe)`**: Harici işlemin süreç kimliğini (PID) döndürür.  
* **`void gfx_execute_free(Ecore_Exe *exe)`**: İşlem nesnesi tutacağını serbest bırakır.

## 27\. Dosya Tanımlayıcı İşleyici Fonksiyonları (File Descriptor Handler Functions)

* **`Ecore_Fd_Handler *gfx_add_fdhandler(int fd, Ecore_Fd_Handler_Flags flags, Ecore_Fd_Cb func, const void *data, Ecore_Fd_Cb bufd_func, const void *bufd_data)`**: Dosya tanımlayıcısını (socket, pipe vb.) dinleyen bir okuma/yazma işleyicisi ekler.  
* **`void *gfx_del_fdhandler(Ecore_Fd_Handler *fd_handler)`**: Dosya tanımlayıcısı işleyicisini kaldırır.

## 28\. Olay İşleyici Fonksiyonları (Event Handler Functions)

* **`Ecore_Event_Handler *gfx_add_eventhandler(int type, Ecore_Event_Handler_Cb func, const void *data)`**: Belirli bir Ecore olay türünü dinleyen olay işleyici ekler.

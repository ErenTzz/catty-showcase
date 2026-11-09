[← Vitrine dön](../README.tr.md) · [English](engineering.md)

# Catty teknik incelemesi

Catty, oturumlar arasında durumunu koruyan bir bakım merkeziyle kısa arcade oyunlarını bir araya getiriyor. Temel tasarım sorusu, her etkinliğin kendi kontrol ve kurallarına sahip olmasını sağlarken ödül ve kedi ilerlemesini sahneler arasında nasıl ortak tutacağımdı.

```mermaid
flowchart LR
    Hub["Kedi bakım merkezi"] --> Care["Bakım etkinlikleri"]
    Hub --> Arcade["Arcade mini oyunları"]
    Care --> Progress["Ortak ödül ve ilerleme"]
    Arcade --> Progress
    Progress --> Hub
    Progress --> Save["Yerel kayıt"]
    Hub --> Save
```

## Dokunuşları banyo ilerlemesine dönüştürmek

Banyo etkinliğinde oyuncu sırayla üç araç kullanıyor. Her dokunmatik hareket, kedinin bir bölgesinde yapılan işlemin kapsama oranını artırıyor. Oturum, kullanılan aracın o aşamaya ait olup olmadığını ve hareketin aktif bir bölgede gerçekleşip gerçekleşmediğini kontrol ediyor. Kapsama oranı aşamanın ne zaman tamamlandığını belirliyor. Görsel katman oturum değiştikçe kir, köpük, su ve ilerlemeyi ekrana yansıtıyor.

Kapsama hesabını görsel sunumdan ayırmak, tamamlama kurallarını koruyarak efektleri değiştirmeyi mümkün kılıyor. Ödül son aşama bittikten sonra alınabiliyor ve oturum ödülün daha önce alınıp alınmadığını takip ediyor. [Banyo demosunu izle.](../media/bath-gameplay.gif)

## Mini oyun ödüllerini bakım merkezine taşımak

Her mini oyun kendi oyun alanını, girişlerini ve skorunu yönetiyor. Oyun sırasında biriken altın ve deneyim puanı takip ediliyor ve sonuç akışında ortak ilerlemeye aktarılıyor. Bakım merkezi, her mini oyunun skoru nasıl hesapladığını bilmeden bu bakiyeleri kullanabiliyor. Mobilde oyuncu oturum devam ederken uygulamayı arka plana alabileceği veya sahneden çıkabileceği için bu geçişler de kayıt akışının parçası.

Dokunarak uçma ve platform sahneleri, engel çiftlerini ve platformları nesne havuzlarıyla yeniden kullanıyor. Aktif oyun alanı daha fazla nesneye ihtiyaç duyduğunda havuzlar büyüyebiliyor. Ödül akışı ve nesne üretimi birbirinden bağımsız olarak ayarlanabiliyor.

## Eylemleri oyun içinde öğretmek

Öğretici, yapılandırılabilir adımlardan oluşuyor. Bir adım diyalog gösterebiliyor, bir kontrolü vurgulayabiliyor veya oyun içi bir olayı bekleyebiliyor. Oyuncu ilgili eylemi yapana kadar yönlendirme görünür kalıyor. Tamamlanan adımlar yerel olarak kaydediliyor.

Diyalog yerleşimi, vurgulanan kontrolün ekrandaki konumunu ve boyutunu kullanıyor. Bu değişiklik, tablette diyalog kartının oyuncudan seçmesi istenen mama tarifini kapattığı bir durumu giderdi. Yerleşim değişiklikten sonra telefon ve tablet görünümlerinde kontrol edildi.

## Kedi durumunu oturumlar arasında korumak

Oyuncu başka bir uygulamaya geçtiğinde bakım döngüsünün tutarlı kalması gerekiyor. Catty, arka plana geçerken kedinin ihtiyaçlarını kaydediyor ve durumu geri yüklerken geçen süreyi hesaba katıyor. Mağaza, envanter ve bakım etkinlikleri sabun ve kum gibi malzemelerin kalan kullanım sayısını aynı kayıttan okuyor. Böylece mağaza bir paket ekleyebiliyor, bakım etkinliği ise paketten bir kullanım harcıyor.

Odaya özel sandıklar, oda özelleştirmesini ilerleme sistemine bağlıyor. Sandık tanımları her odanın ödüllerini belirliyor ve açılış animasyonu seçilen ödülü gösteriyor. Editör kontrolleri oda ödüllerini ve ödül seçimi davranışını kapsıyor.

## Mevcut Unity arayüzünü yerelleştirmek

Catty İngilizce, Türkçe, Almanca, İspanyolca ve Fransızcayı destekliyor. Arayüz etiketleri çeviri tablolarından geliyor. Görev ödülü etiketleri gibi oyun sırasında oluşturulan metinler yerelleştirilmiş şablonları kullanıyor. Taşıma aracı, sahne ve prefablardaki değişiklikleri uygulamadan önce önizleyerek mevcut bağlantıları ve çevirileri gözden geçirmeyi sağlıyor. Doğrulama kontrolleri dil tablolarından metin okumayı, prefab kalıtımını ve oyun sırasında dil değiştirmeyi kapsıyor.

## Bağlantı değişikliklerini ve ödüllü reklamları yönetmek

Bağlantı takibi, internet kesildiğinde veya geri geldiğinde mini oyun seçim arayüzünü güncelliyor. Ödüllü reklamların oyunu duraklatmak, sonucu işlemek ve oyuna dönmek için ayrı bir akışı var. Bu akış, onaylanmış ödülü reklamın kapatılması ya da yükleme veya gösterim hatasından ayırıyor. Enerji yenileme ve mini oyun ödülünü katlama gibi isteğe bağlı işlemler bu ayrımı kullanıyor.

## Android için mevsimsel içeriği paketlemek

Etkin mevsimsel tema birden fazla sahne, prefab ve animasyonun görsellerini değiştiriyor. Tüm değişimleri oyun çalışırken çözmek, yedek görselleri de paket bağımlılığı olarak tutacaktı. Başlangıçta seçilen tema için derleme adımı görsel referanslarını önceden çözüyor, çalışma anında hâlâ gereken eşleştirmeleri koruyor ve artık kullanılmayan sprite atlaslarını paket dışında bırakıyor. Araç, değişikliklerden önce düzenlenebilir varlıkları yedekliyor ve derleme sonrasında veya kurtarma sırasında geri yüklüyor.

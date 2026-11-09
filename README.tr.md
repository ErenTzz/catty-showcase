<div align="center">

[English](README.md) · [Türkçe](README.tr.md)

# Catty: Virtual Cat&Mini Games

**Unity ve C# ile geliştirdiğim Android sanal evcil hayvan oyunu.**

Kedinin bakımını yap, kısa arcade oyunları oyna ve kazandığın kaynaklarla kedinin ihtiyaçlarını karşıla veya yeni odalar aç.

[**Google Play'de oyna**](https://play.google.com/store/apps/details?id=com.thehookgames.catty) · [**Oynanış demosu**](#oynanış-demosu) · [**Teknik inceleme**](docs/engineering.tr.md)

<img src="media/care.jpg" alt="Catty'nin odası ve bakım arayüzü" width="225" /> <img src="media/mini-game.jpg" alt="Yün engeller ve altın içeren dokunarak uçma oyunu" width="225" /> <img src="media/rooms.jpg" alt="Sera odasında Catty" width="225" />

</div>

## Rolüm

Ben **Eren Toksöz**, Catty'nin Unity geliştiricisiyim. C# ile oynanış, mobil arayüz ve dokunmatik etkileşim, ilerleme ve kayıt akışları, öğretici ve Android yayını üzerinde çalıştım. Oyun Google Play'de **theHookGames** adıyla yayımlanıyor.

## Oynanış demosu

<table>
<tr>
<td width="42%" align="center"><a href="media/bath-gameplay.gif"><img src="media/bath-gameplay.gif" width="260" alt="Oyuncunun Catty'yi sabunladığı, duruladığı ve kuruladığı oynanış demosu" /></a></td>
<td valign="top">

**Banyo · 20 saniyelik oynanış kurgusu**

Oyuncu Catty'yi sırasıyla sabunluyor, duruluyor ve kuruluyor. Dokunuşlar ekrandaki kir, köpük ve suyu değiştiriyor. İlerleme göstergesi, oyuncuya ne zaman araç değiştireceğini gösteriyor.

Banyo, ana döngünün bir parçası. Oyuncular Catty'nin odasında bakımını yapıyor, mini oyunlarla kaynak kazanıyor ve ödülleri bakım veya oda özelleştirmesi için kullanıyor.

</td>
</tr>
</table>

## Teknik özellikler

| Alan | Geliştirdiğim sistem |
| --- | --- |
| Dokunmatik oynanış | Temizlenen alanı görsel efektlerden ayrı takip eden çok aşamalı banyo sistemi. Her aşama kendi aracını kabul ediyor ve tamamlanan bir oturum bir kez ödül verebiliyor. |
| Arcade mini oyunları | Dokunarak uçma, platform, eşya toplama ve Paw Tap için ayrı sahneler. Kayan engeller ve platformlar nesne havuzlarından yeniden kullanılıyor. |
| İlerleme | Mini oyun sonuçları ortak altın ve deneyim sistemini besliyor. Yerel kayıtlar kedinin durumunu, bakım malzemelerini ve öğretici ilerlemesini oturumlar arasında saklıyor. |
| Öğretici ve mobil arayüz | Yapılandırılabilir öğretici adımları, ilerlemeden önce ilgili oyun olayını bekliyor. Vurgular ve diyaloglar oyuncuyu ilgili kontrollere yönlendiriyor. Yerleşim telefon ve tablet ekran oranlarında kontrol edildi. |

Banyo etkileşimi, ödül akışı ve öğreticinin tasarım kararları [teknik incelemede](docs/engineering.tr.md) yer alıyor.

## Oyundan diğer görseller

<div align="center">

<a href="media/progression.jpg"><img src="media/progression.jpg" width="160" alt="Catty'nin seviye atlama animasyonu" /></a>
<a href="media/platforming.jpg"><img src="media/platforming.jpg" width="160" alt="Bulutlarda geçen platform oyunu" /></a>
<a href="media/chests.jpg"><img src="media/chests.jpg" width="160" alt="Sandık ödül ekranı" /></a>
<a href="media/shop.jpg"><img src="media/shop.jpg" width="160" alt="Oda özelleştirme mağazası" /></a>

</div>

Mağaza görselleri [Google Play sayfasından](https://play.google.com/store/apps/details?id=com.thehookgames.catty) alınmıştır. Bu portfolyo deposu oynanış medyası ve teknik inceleme içerir. Unity projesi özel depoda tutulur.

**Eren Toksöz** · [GitHub profili](https://github.com/ErenTzz)

##### 1- İlk olarak, node uygulaması için bağımlılıkları kurmalısınız:

<pre>
npm i
</pre>

##### 2- index.js dosyasını açmanız ve aşağıdaki bölüme Discord üzerinde oluşturduğunuz webhook URL'sini girmeniz gerekmektedir:

<pre>
const Hook = new webhook.Webhook("WEBHOOK ADRESİNİZ") // Örnek: https://discord.com/api/webhooks/WEBHOOK_ID/WEBHOOK_TOKEN
</pre>

##### 3- Ghost CMS tabanlı kurmuş olduğunuz sitenin, rss bağlantısını aşağıya girmelisiniz:

<pre>
const rssUrl = "https://www.siteadresi.com/rss"; // Örnek: https://www.ise.town/rss
</pre>

##### 4- Yazmış olduğunuz yazıda bir resim yok ise aşağıda belirteceğiniz resim gözükecektir.

<pre>
const defaultImg = 'varsayılan resim adresi'; // Örnek: https://www.ise.town/content/images/2023/04/town.png
</pre>

##### 5- Ne kadar sürede bir kontrol sağlanacağını milisaniye cinsinden belirtmelisiniz.:

<pre>
const timeOut = 20000;
</pre>

##### 6- Webhook'unuzun göndereceği mesajın nasıl görüneceğini ayarlamak için aşağıdaki alanı kendinize göre düzenlemelisiniz:
<pre>
  const msg = new webhook.MessageBuilder()
    .setName('Webhook Adı') // Oluşturduğunuz Webhook'un adı
    .setColor('#f1e05a') // Mesajın rengi
    .setTitle(newEntries[0].title) // Mesajın başlığı
    .addField('', newEntries[0].contentSnippet.substring(0, 120) + "...") // İçeriğin özeti
    .setFooter("Author: " + newEntries[0].creator + " - Release Time: " + formattedDate + " " + formattedTime) // Alt kısım ile ilgili ayarlar
    .setImage(imgSrc) // Resim bağlantısı
    .setURL(newEntries[0].link); // Yazının adresi
  Hook.send(msg); // Mesaj gönderiyoruz
</pre>

##### 7- Tüm ayarlamaları yaptığımıza göre uygulamamızı başlatabiliriz:

<pre>
node index.js
</pre>

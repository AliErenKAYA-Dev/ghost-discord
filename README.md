# ghost-discord

###### 1- After opening the index.js file, you need to enter the webhook URL you created on Discord in the section below:

``const Hook = new webhook.Webhook("YOUR WEBHOOK URL") // Example: https://discord.com/api/webhooks/WEBHOOK_ID/WEBHOOK_TOKEN``

###### 2- You should add the RSS feed URL of your site.

``const rssUrl = "https://www.siteurl.com/rss"; // Example: https://www.ise.town/rss``

###### 3- If the written article does not contain an image, add the default image to be displayed.

``const defaultImg = 'default img url'; // Example: https://www.ise.town/content/images/2023/04/town.png``

###### 4- The time interval for checking should be entered in milliseconds.

``const timeOut = 20000;``

###### 5- We determine how your webhook will appear when sending a message.
``
const msg = new webhook.MessageBuilder()

  .setName('Webhook Name') // Your webhook name
  
  .setColor('#f1e05a') // Message color
  
  .setTitle(newEntries[0].title) // Message Title
  .addField('', newEntries[0].contentSnippet.substring(0, 120) + "...") // We adding new field for short content
  .setFooter("Author: " + newEntries[0].creator + " - Datetime: " + formattedDate + " " + formattedTime) // Setting footer
  .setImage(imgSrc) // Image url
  .setURL(newEntries[0].link); // Post url
Hook.send(msg); // We sending a message
``

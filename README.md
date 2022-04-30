# gas-form-mail-and-upload

## メール送信

```js
function sendMail( e ) {

  // https://www.yukibnb.com/entry/form_responses

  var itemResponses = e.response.getItemResponses();

  for( var i = 0; i < itemResponses.length; i++ ) {
    console.log(itemResponses[0].getItem().getTitle());
    console.log(itemResponses[0].getResponse());
  }

  var email = e.response.getRespondentEmail();
  console.log(email);

  var mail_text = "【メールアドレス】\n" + email + "\n";

  mail_text += "【" + itemResponses[0].getItem().getTitle() + "】\n" + itemResponses[0].getResponse() + "\n";
  
  GmailApp.sendEmail(
    "メールアドレス",
    "件名",
    mail_text + "\n"

  );
  
}
```

![image](https://user-images.githubusercontent.com/1501327/166095827-3963db32-cd52-4ffb-af09-37ebe41a6828.png)\
![image](https://user-images.githubusercontent.com/1501327/166095881-3456dcb2-d87b-43a6-bdc4-bfb7b667c569.png)


<br><br>


## ファイルアップロード

### スクリプトを使う場合は、Chrome V8 ランタイムを有効にする をオフにしてください

![image](https://user-images.githubusercontent.com/1501327/166095739-a306758f-bbfd-43d8-9f4e-43b733f47a46.png)


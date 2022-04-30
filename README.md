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

![image](https://user-images.githubusercontent.com/1501327/166095621-e61aab0b-38a2-46dc-ae66-8b559fdb1bd9.png)


## ファイルアップロード

### スクリプトを使う場合は、Chrome V8 ランタイムを有効にする をオフにしてください

![image](https://user-images.githubusercontent.com/1501327/166095739-a306758f-bbfd-43d8-9f4e-43b733f47a46.png)


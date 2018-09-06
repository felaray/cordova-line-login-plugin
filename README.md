# cordova-line-login-plugin
LineSDKを使用してLINEログインを簡単に実装するためのcordovaプラグイン。　　

機能はログイン、ログアウト、アクセストークンの取得・検証・リフレッシュを行う。使用しているLineSDKのバージョンは以下のとおり。  

iOS：4.1.1

Android：4.0.8  

組み込みまでの流れは以下の通り  
「LINE BUSINESS CENTER」からLINEログインに対応したビジネスアカウントを作成。Application TypeはNATIVE_APPを選択。

### ios
1. 「LINE DEVELOPERS」より「iOS Bundle ID」「iOS Scheme」を設定。
1. 当プラグインをインストール。
1. xcodeの「Capabilities」より「Keychain Sharing」をONに設定。
1. プログラムの実装

```
例)
iOS Bundle ID : com.example.sample
iOS Scheme : line3rdp.com.example.sample
```

### android
1. 「LINE DEVELOPERS」より「Android Package Name」「Android Package Signature」「Android Scheme」を設定。
1. 当プラグインをインストール。
1. プログラムの実装

```
例)  
Android Package Name : com.example.sample
Android Package Signature : 11:22:33:44:55:66:77:88:99:aa:bb:cc:dd:ee:ff:gg:hh:ii:jj:kk
Android Scheme : com.example.sample://
```

## Installation
    cordova plugin add https://github.com/nrikiji/cordova-line-login-plugin.git --variable LINE_CHANNEL_ID={your_line_channel_id}

## Supported Platforms
- iOS
- Android

## Example



Cordova Example
```
deviceReady: function () {
        this.receivedEvent('deviceready');
        lineLogin.initialize({ channel_id: "xxxxxxx" });
        lineLogin.login({},
            function (result) {
                console.log(result);
                alert("Welcome "+result.displayName);
                // {userID:12345, displayName:'user name', pictureURL:'thumbnail url'}
            }, function (error) {
                //-1
                console.log(error);
            });
    }
```



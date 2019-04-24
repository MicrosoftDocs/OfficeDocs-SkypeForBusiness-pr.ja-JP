---
title: Windows Phone 版 Skype for Business のインストールおよびテスト
ms.reviewer: ''
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 54289bbe-97e7-44bf-8611-4e740fc5b998
description: '概要: をインストールし、Windows Phone にビジネス用の Skype をテストする方法を説明します。'
ms.openlocfilehash: f944b5d80928bd1454893dedc3bb4d56ba2d3033
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214862"
---
# <a name="install-and-test-skype-for-business-for-windows-phone"></a>Install and test Skype for Business for Windows Phone
 
**の概要:** インストールし、Windows Phone にビジネス用の Skype をテストする方法について説明します。
  
ビジネスの Windows Phone アプリケーションの Skype では、ビジネス プレゼンス、インスタント メッセージング (IM)、および音声とビデオ Windows モバイル デバイスへの呼び出しに Skype が表示されます。 Lync 2013 を使用しているユーザーの場合、ユーザー設定に応じて、アプリが自動的に更新されるか、手動で更新するよう求めるメッセージが表示されます。 新規ユーザーを[Windows Phone マーケットプ レース](https://go.microsoft.com/fwlink/p/?linkid=231901)からダウンロードできます。 ビジネスの Windows Phone アプリケーションの Skype をできるは、Windows Phone 8.1 およびそれ以降でだけです。
  
アプリをダウンロードするのには、組織内のユーザーを案内する、前に、お客様の環境に適切に統合されているかどうかを確認するのには次のテストを実行します。 
  
## <a name="install-skype-for-business-windows-phone-81"></a>ビジネス Windows Phone 8.1 の Skype をインストールします。

1. [Windows Phone 8 を中心的な更新](https://www.windowsphone.com/en-us/how-to/wp8/update-central)を Windows Phone 8.1 に、電話を更新するを参照します。
    
2. 、電話からは、**ストア**では、に移動し、 **Skype のビジネス**を検索します。
    
3. [**インストール**] をタップします。 
    
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Skype for Business に初めてサインインする

1. [ **Start** ] 画面を表示、インストールされているアプリケーション、Windows Phone のビジネス、Skype の検索を開くには、アプリケーション アイコンをタップし、読み取りのまま。
    
2. サインイン用アドレス (たとえば、user@domain.com) とパスワードを入力し、**完了**の順にタップします。
    
     場合によっては、ユーザー名とサインイン アドレスを両方とも入力する必要があります。 ユーザー名では、組織のネットワークへのサインインに使用する user@domain.com またはドメイン \ ユーザー名のいずれかです。
    
3. [**カスタマー エクスペリエンス向上プログラム**] 画面で、[**参加**] をタップしてアプリの問題と使用状況に関する匿名データを Microsoft に送信するか、参加しない場合は [**いいえ**] をタップします。
    
4. [**勤務先電話への着信を逃さない**] 画面で、携帯電話番号を国、地域番号も含めて入力します。 Windows Phone のビジネス用の Skype が、オーディオまたはビデオの呼び出しを行うには、Wi-fi または携帯電話データ ネットワークを使用できないを自動的にこの番号と呼ばれ、呼び出しのオーディオ部分に接続して行います。
    
5. **次へ**] をタップし、通知し、電話帳のアクセスの設定を確認します。
    
   - **プッシュ通知**新しい IM またはコールを受信したときにアラートを取得します。 通常**の**(推奨)。
    
     > [!IMPORTANT]
     > この設定をオフにするにしない通知 IMs、呼び出し、またはビジネスの Windows Phone のアラートには、他の Skype のアプリケーションがアクティブになっていない限り。 
  
   - **電話帳へのアクセスを許可します。** Windows Phone のビジネス用の Skype の連絡先を検索する場合は、携帯電話の連絡先を検索します。
    
6. **次回**Windows Phone のビジネス用の Skype の使用を開始する] をタップします。
    
    [サインインのヘルプが必要ですか。](https://support.office.com/article/6b827683-ad55-471a-bd4b-3d4ec098bf75)
    
## <a name="verify-mobile-client-installation"></a>モバイル クライアント インストールを検証する

クライアントを構成するし、正常にサインインすると、モバイル デバイスの Windows Phone のビジネスについて、Skype のインストールが正常に機能していることを確認するのには次のテストを使用します。
  
### <a name="search-for-a-contact-in-the-corporate-directory"></a>会社のディレクトリにある連絡先の検索

1. 連絡先一覧で、[**検索**] をタップします。
    
2. グローバル アドレス一覧にだけ含まれる連絡先を検索します。
    
3. 連絡先名が検索結果に表示されることを確認します。
    
### <a name="test-instant-messaging-and-presence"></a>インスタント メッセージングおよびプレゼンスのテスト

1. 連絡先リストで、連絡先をタップします。
    
2. 連絡先のカードでは、[インスタント メッセージング (IM)] をタップします ![Skype for Business のインスタント メッセージングのアイコン](../../media/90f8d5fa-7968-4ef7-bf5b-dddf9b893905.png)アイコン。
    
3. IM ウィンドウが表示されていて、IM の入力と送信が可能であることを確認します。
    
### <a name="test-dial-out-conferencing"></a>ダイヤルアウト会議のテスト

1. Outlook では、ビジネス会議のため、Skype のスケジュールを設定します。
    
2. Windows Phone で、会議の招待状を開きます。
    
3. 参加する会議のリンクをクリックします。
    
4. 会議サービスからの通話に応答し、会議のオーディオに接続していることを確認します。
    
### <a name="test-push-notifications"></a>プッシュ通知のテスト

1. このテスト用に異なる 2 つのユーザー アカウントを選択します。 
    
2. ユーザーの Windows Phone の上でにサインインする Skype ビジネスの Windows Phone のユーザー A のアカウント。
    
3. デバイスで別のアプリケーションを開きます。
    
4. デスクトップ クライアントなど、別のクライアントにユーザー B のアカウントを使用してビジネスの Skype にサインインします。
    
5. IM をユーザー B からユーザー A に送信します。
    
6. IM 通知がユーザー A のモバイル デバイス上に表示されていることを確認します。
    
## <a name="remove-skype-for-business-from-your-windows-phone"></a>ビジネスのため、Windows Phone から Skype を削除します。

モバイル デバイスから、Windows Phone のビジネス アプリケーションの Skype を削除します。 
  
1. 起動画面から、アプリケーション一覧をスワイプして表示します。 
    
2. タップし、Windows Phone のビジネス アプリケーションでは、Skype を押したままとし、[**アンインストール**] を選択します。
    



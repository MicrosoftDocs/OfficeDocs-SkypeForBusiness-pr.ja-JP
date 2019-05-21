---
title: Windows Phone 版 Skype for Business のインストールおよびテスト
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 54289bbe-97e7-44bf-8611-4e740fc5b998
description: '概要: Skype for Business を Windows Phone にインストールしてテストする方法について説明します。'
ms.openlocfilehash: 2796f1664ec20142bd8f9399830836c8c284ac67
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278285"
---
# <a name="install-and-test-skype-for-business-for-windows-phone"></a>Install and test Skype for Business for Windows Phone
 
**概要:** Windows Phone で Skype for Business をインストールしてテストする方法について説明します。
  
Skype for Business for Windows Phone アプリでは、Skype for Business のプレゼンス、インスタントメッセージング (IM)、音声およびビデオ通話を Windows モバイルデバイスで利用できます。 Lync 2013 を使用しているユーザーの場合、ユーザー設定に応じて、アプリが自動的に更新されるか、手動で更新するよう求めるメッセージが表示されます。 新しいユーザーは、 [Windows Phone Marketplace](https://go.microsoft.com/fwlink/p/?linkid=231901)からダウンロードできます。 Windows Phone 版 Skype for Business アプリは、Windows Phone 8.1 以降でのみ利用できます。
  
組織内のユーザーにアプリをダウンロードするように指示する前に、次のテストを実行して、環境に適切に統合されていることを確認します。 
  
## <a name="install-skype-for-business-windows-phone-81"></a>Skype for Business Windows Phone 8.1 をインストールする

1. 電話を Windows Phone 8.1 に更新するには、 [Windows phone 8 更新プログラムの中央](https://www.windowsphone.com/en-us/how-to/wp8/update-central)に移動します。
    
2. お使いの携帯電話から**ストア**に移動して、 **Skype for business**を検索します。
    
3. [**インストール**] をタップします。 
    
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Skype for Business に初めてサインインする

1. [**スタート**] 画面で、左にスワイプしてインストールされているアプリを表示し、Skype for Business For Windows Phone を検索して、アイコンをタップしてアプリを開きます。
    
2. サインインアドレス (user@domain.com など) とパスワードを入力して、[**完了**] をタップします。
    
     場合によっては、ユーザー名とサインイン アドレスを両方とも入力する必要があります。 ユーザー名は、組織のネットワークにサインインするために使用する user@domain.com または domain\username のどちらかです。
    
3. [**カスタマー エクスペリエンス向上プログラム**] 画面で、[**参加**] をタップしてアプリの問題と使用状況に関する匿名データを Microsoft に送信するか、参加しない場合は [**いいえ**] をタップします。
    
4. [**勤務先電話への着信を逃さない**] 画面で、携帯電話番号を国、地域番号も含めて入力します。 Skype for Business for Windows Phone では、Wi-fi または携帯電話のデータネットワークを使って音声通話やビデオ通話を行うことができない場合、この番号で自動的に呼び出され、通話の音声部分に接続されます。
    
5. **[次へ**] をタップして、通知と電話帳のアクセス設定を確認します。
    
   - **プッシュ通知**新しい IM または通話を受信したときに通知を受け取ります。 通常**** は (推奨)
    
     > [!IMPORTANT]
     > この設定をオフにした場合は、アプリがアクティブでない限り、Im、通話、または Windows Phone の通知に関するその他の Skype for Business について通知されません。 
  
   - **電話帳へのアクセスを許可する**Skype for Business for Windows Phone で連絡先を検索するときに、携帯電話で連絡先を検索します。
    
6. **[次へ**] をタップして、Skype for Business For Windows Phone の使用を開始します。
    
    [サインインのヘルプ](https://support.office.com/article/6b827683-ad55-471a-bd4b-3d4ec098bf75)
    
## <a name="verify-mobile-client-installation"></a>モバイル クライアント インストールを検証する

クライアントを構成して正常にサインインしたら、次のテストを行って、お使いのモバイルデバイスで Skype for Business for Windows Phone が正常にインストールされていることを確認します。
  
### <a name="search-for-a-contact-in-the-corporate-directory"></a>会社のディレクトリにある連絡先の検索

1. 連絡先一覧で、[**検索**] をタップします。
    
2. グローバル アドレス一覧にだけ含まれる連絡先を検索します。
    
3. 連絡先名が検索結果に表示されることを確認します。
    
### <a name="test-instant-messaging-and-presence"></a>インスタント メッセージングおよびプレゼンスのテスト

1. 連絡先リストで、連絡先をタップします。
    
2. 連絡先カードで、インスタントメッセージング (IM) をタップします。 ![Skype for Business のインスタント メッセージングのアイコン](../../media/90f8d5fa-7968-4ef7-bf5b-dddf9b893905.png)最小化.
    
3. IM ウィンドウが表示されていて、IM の入力と送信が可能であることを確認します。
    
### <a name="test-dial-out-conferencing"></a>ダイヤルアウト会議のテスト

1. Outlook で、Skype for Business 会議をスケジュールします。
    
2. Windows Phone で、会議の招待状を開きます。
    
3. 参加する会議のリンクをクリックします。
    
4. 会議サービスからの通話に応答し、会議のオーディオに接続していることを確認します。
    
### <a name="test-push-notifications"></a>プッシュ通知のテスト

1. このテスト用に異なる 2 つのユーザー アカウントを選択します。 
    
2. ユーザー A の Windows Phone で、ユーザー A のアカウントを使って Windows Phone 用の Skype for Business にサインインします。
    
3. デバイスで別のアプリケーションを開きます。
    
4. デスクトップクライアントなどの別のクライアントで、ユーザー B のアカウントを使用して Skype for Business にサインインします。
    
5. IM をユーザー B からユーザー A に送信します。
    
6. ユーザー A のモバイルデバイスに IM 通知が表示されることを確認します。
    
## <a name="remove-skype-for-business-from-your-windows-phone"></a>Windows Phone から Skype for Business を削除する

Skype for Business for Windows Phone アプリをモバイルデバイスから削除するには、次の操作を行います。 
  
1. 起動画面から、アプリケーション一覧をスワイプして表示します。 
    
2. Skype for Business for Windows Phone アプリケーションをタップして押し続け、[**アンインストール**] を選択します。
    



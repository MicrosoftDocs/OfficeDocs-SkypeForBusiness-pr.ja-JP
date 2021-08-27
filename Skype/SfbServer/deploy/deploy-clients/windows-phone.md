---
title: インストールとテストのSkype for Business for Windows Phone
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 54289bbe-97e7-44bf-8611-4e740fc5b998
description: '概要: デバイスにインストールしてテストするSkype for BusinessをWindows Phone。'
ms.openlocfilehash: f912c1f5bd3c0bd5f8c3cc553c64ee3b7850f63e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618153"
---
# <a name="install-and-test-skype-for-business-for-windows-phone"></a>インストールとテストのSkype for Business for Windows Phone
 
**概要:** デバイスにインストールしてテストする方法Skype for BusinessをWindows Phone。
  
このSkype for Business for Windows Phoneアプリは、Skype for Business、インスタント メッセージング (IM)、音声およびビデオ通話をモバイル デバイスWindowsします。 Lync 2013 を使用しているユーザーは、更新されたアプリを自動的に取得するか、ユーザー設定に応じて手動で更新するように求めるメッセージを表示します。 新しいユーザーは、マーケットプレースから[Windows Phoneできます](https://go.microsoft.com/fwlink/p/?linkid=231901)。 アプリSkype for Business for Windows Phoneは、8.1 以降Windows Phoneでのみ使用できます。
  
組織内のユーザーにアプリのダウンロードを指示する前に、次のテストを実行して、環境に適切に統合されていることを確認します。 
  
## <a name="install-skype-for-business-windows-phone-81"></a>8.1 Skype for Business Windows Phoneインストールする

1. [8.1 Windows Phone更新の](https://www.windowsphone.com/en-us/how-to/wp8/update-central)中央を参照して、電話を 8.1 Windows Phone更新します。
    
2. お使いの携帯電話から、[ストア] に **移動し**、[ストア] を **Skype for Business。**
    
3. [インストール **] をタップします**。 
    
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>初めてSkype for Businessにサインインする

1. [スタート **] 画面で**、左にスワイプしてインストールされているアプリを表示し、Skype for Business for Windows Phoneを検索し、アイコンをタップしてアプリを開きます。
    
2. サインイン アドレス (たとえば、user@domain.com) とパスワードを入力し、[完了] をタップ **します**。
    
     ユーザー名とサインイン アドレスの両方を要求されることがあります。 ユーザー名は、組織のネットワークへのサインインに使用する名前で、user@domain.com\username のいずれかです。
    
3. [カスタマー **エクスペリエンス向上プログラム] 画面** で、[参加] をタップして、アプリの問題と使用状況に関する匿名データを Microsoft に送信するか、参加しない場合は感謝なしをタップします。 
    
4. [仕事 **の呼び出しを見逃す必要** はありません] 画面で、国と地域のコードを含む携帯電話番号を入力します。 Skype for Business for Windows Phone Wi-Fi または携帯電話データ ネットワークを使用してオーディオまたはビデオ通話を行えない場合、この番号で自動的に呼び出され、通話のオーディオ部分に接続されます。
    
5. [ **次へ]** をタップし、通知と電話帳のアクセス設定を確認します。
    
   - **プッシュ通知** 新しい IM または通話を受信すると、アラートを受け取る。 通常は **オン** (推奨)。
    
     > [!IMPORTANT]
     > この設定をオフにした場合、アプリがアクティブな場合をSkype for Business for Windows Phone、その他の通知は通知されません。 
  
   - **電話帳へのアクセスを許可する** 携帯電話で連絡先を検索するときに、携帯電話の連絡先を検索Skype for Business for Windows Phone。
    
6. [**次へ] を** タップして、Skype for Business for Windows Phone。
    
    [サインインのヘルプ](https://support.office.com/article/6b827683-ad55-471a-bd4b-3d4ec098bf75)
    
## <a name="verify-mobile-client-installation"></a>モバイル クライアントのインストールを確認する

クライアントの構成とサインインが正常に完了したら、次のテストを使用して、モバイル デバイスで Skype for Business for Windows Phoneのインストールが正しく動作しているのを確認します。
  
### <a name="search-for-a-contact-in-the-corporate-directory"></a>会社のディレクトリにある連絡先の検索

1. [連絡先] リストで、[検索] を **タップします**。
    
2. グローバル アドレス一覧にのみ存在する連絡先を検索します。
    
3. 連絡先名が検索結果に表示されることを確認します。
    
### <a name="test-instant-messaging-and-presence"></a>インスタント メッセージングとプレゼンスのテスト

1. 連絡先一覧で、連絡先をタップします。
    
2. 連絡先カードで、インスタント メッセージング (IM) をタップします。 ![インスタント メッセージングのアイコン (Skype for Business](../../media/90f8d5fa-7968-4ef7-bf5b-dddf9b893905.png)選択します。
    
3. IM ウィンドウが表示され、IM を入力して送信できると確認します。
    
### <a name="test-dial-out-conferencing"></a>ダイヤルアウト会議のテスト

1. [Outlook] で、会議をスケジュールSkype for Businessします。
    
2. 会議出席Windows Phone会議出席依頼を開きます。
    
3. 参加する会議のリンクをクリックします。
    
4. 会議サービスからの通話に応答し、会議オーディオに接続されていることを確認します。
    
### <a name="test-push-notifications"></a>プッシュ通知のテスト

1. このテストでは、2 つの異なるユーザー アカウントを選択します。 
    
2. ユーザー A のアカウントWindows Phone、ユーザー A のSkype for Business for Windows Phoneにサインインします。
    
3. デバイスで別のアプリケーションを開きます。
    
4. デスクトップ クライアントなどの別のクライアントで、ユーザー B のSkype for Businessにサインインします。
    
5. IM をユーザー B からユーザー A に送信します。
    
6. ユーザー A のモバイル デバイスに IM 通知が表示されるのを確認します。
    
## <a name="remove-skype-for-business-from-your-windows-phone"></a>自分のSkype for Businessから削除Windows Phone

モバイル デバイスからSkype for Business for Windows Phoneアプリを削除するには、次の方法を実行します。 
  
1. スタート画面からスワイプして、アプリケーションの一覧を表示します。 
    
2. アプリケーションをタップして保持Skype for Business for Windows Phoneし、[アンインストール] を **選択します**。
    



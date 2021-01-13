---
title: Skype for Business for Windows Phone のインストールとテスト
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 54289bbe-97e7-44bf-8611-4e740fc5b998
description: '概要: Windows Phone に Skype for Business をインストールしてテストする方法について学習します。'
ms.openlocfilehash: 8323231f67e8aca87d3670cfee1a2137f0dd6c21
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812717"
---
# <a name="install-and-test-skype-for-business-for-windows-phone"></a>Skype for Business for Windows Phone のインストールとテスト
 
**概要:** Windows Phone に Skype for Business をインストールしてテストする方法について学習します。
  
Skype for Business for Windows Phone アプリは、Skype for Business のプレゼンス、インスタント メッセージング (IM)、音声通話とビデオ通話を Windows モバイル デバイスに提供します。 Lync 2013 を使用しているユーザーは、更新されたアプリを自動的に取得するか、ユーザー設定に応じて手動で更新するように求めるメッセージが表示されます。 新しいユーザーは [、Windows Phone Marketplace からダウンロードできます](https://go.microsoft.com/fwlink/p/?linkid=231901)。 Skype for Business for Windows Phone アプリは、Windows Phone 8.1 以降でのみ利用できます。
  
組織内のユーザーにアプリのダウンロードを指示する前に、次のテストを実行して、環境に正しく統合されていることを確認する必要があります。 
  
## <a name="install-skype-for-business-windows-phone-81"></a>Skype for Business Windows Phone 8.1 のインストール

1. Windows [Phone 8 更新プログラムの中央を](https://www.windowsphone.com/en-us/how-to/wp8/update-central) 参照して、電話を Windows Phone 8.1 に更新します。
    
2. From your phone, go to the **Store,** and search for **Skype for Business**.
    
3. [インストール **] をタップします**。 
    
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>初めて Skype for Business にサインインする

1. スタート画面 **で** 左にスワイプしてインストール済みアプリを表示し、Skype for Business for Windows Phone を検索し、アイコンをタップしてアプリを開きます。
    
2. サインイン アドレス (たとえば、user@domain.com) とパスワードを入力し、[完了] をタップ **します**。
    
     ユーザー名とサインイン アドレスの両方を要求されることがあります。 ユーザー名は、組織のネットワークにサインインするために使用する名前で、user@domain.com\username のいずれかです。
    
3. [カスタマー **エクスペリエンス向上** プログラム] 画面で、[参加] をタップしてアプリの問題と使用状況に関する匿名データを Microsoft に送信します。参加しない場合は[いいえ] をタップします。
    
4. [ **Never Miss Your Work Calls] 画面** で、国と地域コードを含む携帯電話番号を入力します。 Skype for Business for Windows Phone が Wi-Fi または携帯データ ネットワークを使用して音声通話やビデオ通話を行えなできない場合、この番号で自動的に呼び出され、通話のオーディオ部分に接続されます。
    
5. [ **次へ]** をタップし、通知と電話帳のアクセス設定を確認します。
    
   - **プッシュ通知** 新しい IM または通話を受け取った場合に警告を受け取る。 通常は **オン** (推奨)。
    
     > [!IMPORTANT]
     > この設定をオフにした場合、アプリがアクティブな場合を使用しない限り、VM、通話、その他の Skype for Business for Windows Phone のアラートは通知されません。 
  
   - **電話帳へのアクセスを許可する** Skype for Business for Windows Phone で連絡先を検索するときに、携帯電話の連絡先を検索します。
    
6. [ **次へ]** をタップして、Skype for Business for Windows Phone の使用を開始します。
    
    [サインインのヘルプ](https://support.office.com/article/6b827683-ad55-471a-bd4b-3d4ec098bf75)
    
## <a name="verify-mobile-client-installation"></a>モバイル クライアントのインストールを確認する

クライアントを構成して正常にサインインしたら、次のテストを使用して、Skype for Business for Windows Phone のインストールがモバイル デバイスで正しく動作しているのを確認します。
  
### <a name="search-for-a-contact-in-the-corporate-directory"></a>会社のディレクトリにある連絡先の検索

1. 連絡先リストで、[検索] を **タップします**。
    
2. グローバル アドレス一覧にのみ存在する連絡先を検索します。
    
3. 連絡先名が検索結果に表示されることを確認します。
    
### <a name="test-instant-messaging-and-presence"></a>インスタント メッセージングとプレゼンスのテスト

1. 連絡先一覧で、連絡先をタップします。
    
2. 連絡先カードで、インスタント メッセージング (IM) をタップします。 ![Skype for Business のインスタント メッセージングのアイコン](../../media/90f8d5fa-7968-4ef7-bf5b-dddf9b893905.png)選択します。
    
3. IM ウィンドウが表示され、IM を入力して送信できると確認します。
    
### <a name="test-dial-out-conferencing"></a>ダイヤルアウト会議のテスト

1. Outlook で、Skype for Business 会議をスケジュールします。
    
2. Windows Phone で、会議出席依頼を開きます。
    
3. 参加する会議のリンクをクリックします。
    
4. 会議サービスからの通話に応答し、会議の音声に接続されていることを確認します。
    
### <a name="test-push-notifications"></a>プッシュ通知のテスト

1. このテストには、2 つの異なるユーザー アカウントを選択します。 
    
2. ユーザー A の Windows Phone で、ユーザー A のアカウントで Skype for Business for Windows Phone にサインインします。
    
3. デバイスで別のアプリケーションを開きます。
    
4. デスクトップ クライアントなどの別のクライアントで、ユーザー B のアカウントで Skype for Business にサインインします。
    
5. IM をユーザー B からユーザー A に送信します。
    
6. ユーザー A のモバイル デバイスに IM 通知が表示されるのを確認します。
    
## <a name="remove-skype-for-business-from-your-windows-phone"></a>Windows Phone から Skype for Business を削除する

モバイル デバイスから Skype for Business for Windows Phone アプリを削除するには: 
  
1. スタート画面からスワイプしてアプリケーションの一覧を表示します。 
    
2. Tap and hold the Skype for Business for Windows Phone application, and then select **Uninstall**.
    



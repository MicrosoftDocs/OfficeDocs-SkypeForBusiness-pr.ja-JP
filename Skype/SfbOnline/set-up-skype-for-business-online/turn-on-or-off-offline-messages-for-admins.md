---
title: "管理者のオンまたはオフ オフライン メッセージを有効にします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "連絡先が PowerShell を使用してサインインしていないときでも、ビジネスのインスタント メッセージの Skype を送信する方法について説明します。"
ms.openlocfilehash: d75e710f5df8de05dbaba483f11f3e2a1fb4594b
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>管理者のオンまたはオフ オフライン メッセージを有効にします。

サインインしていない場合でも、連絡先に Im をビジネス用 Skype を送信できます。この機能には、そこに到達する試行されていることを確認、連絡先ことができます。メッセージを送信する前に他のユーザーがオンラインになるまで待つ必要はありません。 
  
オフラインのメッセージの場合に知っておく重要です。
  
- オフラインのメッセージは、ユーザーのメールボックスの整理されません。
    
- オフラインのメッセージは、ユーザーのメールボックスに送信され、ユーザーが skype for Business ログインしたときに通知されます。
    
- **不可]**または [**発表中**にメッセージの受信者の状態を設定している場合、受信者の Skype から for Business クライアント送信される不在着信したメッセージが届きます。
    
詳細については、 [Skype for Business で使用がオフラインでメッセージ](http://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)を参照してください。
  
## <a name="to-get-you-started"></a>使い始めるときに

### 

 **3.0 以降のバージョンの Windows PowerShell が実行していることを確認します。**
  
1. 3.0 以降のバージョンが実行していることを確認する: **[スタート] メニュー** > **Windows PowerShell**します。
    
2. **Windows PowerShell**のウィンドウで_ホストの取得_を入力して、バージョンを確認してください。
    
3. バージョン 3.0 以降をお持ちでない場合は、ダウンロードして、Windows PowerShell への更新プログラムをインストールする必要があります。[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)をダウンロードして 4.0 への Windows PowerShell を更新するを参照してください。表示されたら、お使いのコンピューターを再起動します。
    
4. Skype for Business Online できるようにする Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成するのには、Windows PowerShell モジュールをインストールする必要もします。このモジュールでは、64 ビット版コンピューターにのみサポートされているが、 [Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)では、Microsoft ダウンロード センターからダウンロードできます。求められた場合は、お使いのコンピューターを再起動します。
    
さらに詳しく調べ必要がある場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスへの接続](https://technet.microsoft.com/EN-US/library/dn568015.aspx)を参照してください。
  
### 

 **Windows PowerShell セッションを開始します。**
  
1. **[スタート] メニュー**から > **Windows PowerShell**します。
    
2. **Windows PowerShell**ウィンドウで、実行して、Office 365 の組織に接続します。
    
    > [!NOTE]
    > Skype for Business Online の Windows PowerShell モジュールに使用する**インポート モジュール**の最初のレコード] コマンドの実行にのみがあります。
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

詳細については、Windows PowerShell を開始する場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」または「 [Skype for Business Online Windows PowerShell を使用してへ接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)を参照してください。
  
## <a name="turning-on-or-off-offline-im"></a>またはオフラインで IM をオフにします。

> [!NOTE]
> オフライン メッセージ**だけ**クイック実行の Skype for Business クライアントの最新バージョンで利用できる、以前のクイック実行の Skype for Business を使用または、*.msi ファイルは、Skype for Business クライアントのインストールに使用したときに使用できません。
  
オフラインでのメッセージが、組織内のユーザー設定_EnableIMAutoArchiving_オフラインでメッセージを送信を有効または無効にする`True`または`False`します。既定では、この設定は`True`します。
  
非表示] に**設定 CsClientPolicy**コマンドレットを使用して、実行します。
  
```
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

有効またはユーザーのオフライン メッセージ送信メッセージ オフラインを無効にする] に設定されて_EnableIMAutoArchiving_ `True`または`False`します。既定では、この設定は`True`します。既存のポリシーを使用したり、次の例のように作成できます。
  
> 
  ```
  New-CsClientPolicy -Identity OfflineIM
  ```

> 
  ```
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  ```

> 
  ```
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細を知りたいとしていますか。

- Windows powershell となるはすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で Office 365 と Skype for Business Online の複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 の管理に Windows PowerShell を使用する理由 6 つの理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。
    
  - [Windows PowerShell で Office 365 を管理する最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell を使用して、Skype for Business Online の管理するには](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>関連トピック
[Skype for Business Online をセットアップします。](set-up-skype-for-business-online.md)

[ビジネス ユーザー向けの Skype Skype の連絡先を追加できるようにします。](let-skype-for-business-users-add-skype-contacts.md)

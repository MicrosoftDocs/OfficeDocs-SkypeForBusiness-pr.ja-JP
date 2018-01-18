---
title: "オフライン メッセージの有効化と無効化 (管理者向け)"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell.
ms.openlocfilehash: 2210f7f0acb2609b7557afe781bbb4349d76c73f
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>オフライン メッセージの有効化と無効化 (管理者向け)

[] サインインしていない連絡先にも Skype for Business で IM を送信できるようになりました。これにより、連絡しようとしていることを相手に知らせることができます。相手がオンラインでなくても、メッセージを送ることができます。 
  
オフライン メッセージでは、次のことに注意する必要があります。
  
- オフライン メッセージはユーザーの受信箱にアーカイブされません。
    
- オフライン メッセージがユーザーの受信箱に送信され、ユーザーが Skype for Business にログインすると、受信が通知されます。
    
- メッセージ受信者のステータスが [ **応答不可**] または [ **プレゼンテーション中**] に設定されている場合は、受信者の Skype for Business クライアントから不在着信メッセージが送られます。
    
詳細については、「[Skype for Business でオフライン メッセージを使う](http://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)」をご覧ください。
  
## <a name="to-get-you-started"></a>使用するには、次のようにします。

### 

 **Windows PowerShell バージョン 3.0 以降を実行していることを確認する**
  
1. 3.0 以降のバージョンを実行することを確認するのには: **[スタート] メニュー** > **Windows PowerShell**。
    
2. [ **Windows PowerShell**] ウィンドウに「 _Get-Host_」と入力して、バージョンを確認します。
    
3. バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。
    
4. Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。
    
詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」を参照してください。
  
### 

 **Windows PowerShell セッションを開始する**
  
1. **[スタート] メニュー**の [ > **Windows PowerShell**。
    
2. [ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。
    
    > [!NOTE]
    > Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。
  
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

Windows PowerShell を開始する方法の詳細を設定する場合は、 [1 つの Windows PowerShell のウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)か、 [Windows PowerShell を使用して、オンライン ビジネスの Skype への接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)を参照してください。
  
## <a name="turning-on-or-off-offline-im"></a>オフライン IM の有効化と無効化

> [!NOTE]
> オフライン メッセージは、最新バージョンのクイック実行 Skype for Business クライアントで **のみ** 使用できます。旧バージョンのクイック実行 Skype for Business を使用している場合や *.msi ファイルを使用して Skype for Business クライアントをインストールした場合は、使用できません。
  
オフライン メッセージが、組織内のユーザーに_EnableIMAutoArchiving_を設定するオフラインのメッセージを送信を有効または無効にする`True`または`False`。既定では、この設定は、 `True`。
  
この設定をオフにするには、 **Set-CsClientPolicy** コマンドレットを使用して、実行します。
  
```
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

_EnableIMAutoArchiving_を設定するを有効にするか、ユーザーのオフライン メッセージの送信メッセージをオフラインを無効にする、`True`または`False`。 既定では、この設定は、 `True`。 既存のポリシーを使用したり、次の例のような 1 つを作成できます。
  
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

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>関連トピック
[Skype for Business Online のセットアップ](set-up-skype-for-business-online.md)

[Skype 連絡先を追加、ビジネス ・ ユーザーの Skype を使用します。](let-skype-for-business-users-add-skype-contacts.md)

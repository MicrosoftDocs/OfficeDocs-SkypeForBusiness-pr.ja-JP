---
title: 組織のクライアント ポリシーをセットアップする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
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
description: クライアント ポリシーはユーザーが利用できる Skype for Business Online の機能を決めるのに役立ちます。たとえば、一部のユーザーにファイルを転送する権限を与えて、他のユーザーに対してはその権限を与えないようにする場合が考えられます。
ms.openlocfilehash: 93dcef25119527bce25c1155dc7c8c05ac6fe78d
ms.sourcegitcommit: dbef8028cb7f8c6366e0fdb34f5f2e2a30d8c32a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "19500637"
---
# <a name="set-up-client-policies-for-your-organization"></a>組織のクライアント ポリシーをセットアップする

[] クライアント ポリシーはユーザーが利用できる Skype for Business Online の機能を決めるのに役立ちます。たとえば、一部のユーザーにファイルを転送する権限を与えて、他のユーザーに対してはその権限を与えないようにする場合が考えられます。
  
クライアント ポリシー設定はポリシーが作成されるときに構成できます。また、**Set-CsClientPolicy **コマンドレットを使用して既存のポリシーの設定を変更できます。
  
## <a name="set-your-client-policies"></a>クライアント ポリシーを設定する

> [!NOTE]
> Skype for Business Online のすべてのクライアント ポリシー設定では、Windows PowerShell を使用する必要があります。 **Skype for Business 管理センター** を **使用することはできません**。 
  
### <a name="verify-and-start-windows-powershell"></a>Windows PowerShell を検証および開始する

- **Windows PowerShell バージョン 3.0 以降を実行していることを確認する**
    
1. 3.0 以降のバージョンが実行されていることを確認する場合: **[スタート] メニュー** > **[Windows PowerShell]**。
    
2. [ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。
    
3. バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。
    
4. Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。
    
    詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」を参照してください。
    
- **Windows PowerShell セッションを開始する**
    
1. [**スタート メニュー**]  >  [**Windows PowerShell**] を開きます。
    
2. [ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。
    
    > [!NOTE]
    > Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  Windows PowerShell の起動方法の詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」または「[Windows PowerShell を使用した Skype for Business への接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)」を参照してください。
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>絵文字、プレゼンスの通知を無効にして、インスタントメッセージ (IM) の保存を防止する

- これらの設定のために新しいポリシーを作成するには、次を実行します。
    
> 
  ```
  New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
  ```

  詳細については、 [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) コマンドレットをご覧ください。
    
- 作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
  ```

  詳細については、[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) コマンドレットをご覧ください。
    
ポリシーを作成済みの場合は、[Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) コマンドレットを使用して既存のポリシーに対する変更を行ってから、[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) コマンドレットを使用して設定をユーザーに適用します。
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>URL またはハイパーリンクを有効にしてインスタントメッセージ (IM) でクリックできる状態にする

- これらの設定のために新しいポリシーを作成するには、次を実行します。
    
> 
  ```
  New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
  ```

  詳細については、 [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) コマンドレットをご覧ください。
    
- 作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
  ```

  詳細については、[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) コマンドレットをご覧ください。
    
ポリシーを作成済みの場合は、[Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) コマンドレットを使用して既存のポリシーに対する変更を行ってから、[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) コマンドレットを使用して設定をユーザーに適用します。
  
### <a name="prevent-showing-recent-contacts"></a>最近の連絡先を表示しないようにする

- これらの設定のために新しいポリシーを作成するには、次を実行します。
> 
  ```
  New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
  ```

  詳細については、 [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) コマンドレットをご覧ください。
    
- Amos Marble に作成した新しいポリシーを付与するには、次を実行します。
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
  ```

  詳細については、[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) コマンドレットをご覧ください。
    
  ポリシーを作成済みの場合は、[Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) コマンドレットを使用して既存のポリシーに対する変更を行ってから、[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) コマンドレットを使用して設定をユーザーに適用します。
  
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

- Windows PowerShell では、ユーザーの管理と、ユーザーに許可すること、禁止することをすべて操作できます。 Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell を使用する必要がある理由 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>関連トピック
[カスタム外部アクセス ポリシーを作成する](create-custom-external-access-policies.md)

[ポイント ツー ポイントのファイル転送をブロックする](block-point-to-point-file-transfers.md)

[組織の電話会議ポリシーをセットアップする](set-up-conferencing-policies-for-your-organization.md)

  
 
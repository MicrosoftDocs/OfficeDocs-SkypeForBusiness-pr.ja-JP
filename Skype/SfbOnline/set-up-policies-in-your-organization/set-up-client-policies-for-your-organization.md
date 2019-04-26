---
title: 組織のクライアント ポリシーをセットアップする
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: クライアント ポリシーはユーザーが利用できる Skype for Business Online の機能を決めるのに役立ちます。たとえば、一部のユーザーにファイルを転送する権限を与えて、他のユーザーに対してはその権限を与えないようにする場合が考えられます。
ms.openlocfilehash: 33623e43ed6e7db6edd8af14e042ae798c9c8cd1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32237500"
---
# <a name="set-up-client-policies-for-your-organization"></a>組織のクライアント ポリシーをセットアップする

[] クライアント ポリシーはユーザーが利用できる Skype for Business Online の機能を決めるのに役立ちます。たとえば、一部のユーザーにファイルを転送する権限を与えて、他のユーザーに対してはその権限を与えないようにする場合が考えられます。
  
ポリシーを作成すると、時にクライアントのポリシー設定を構成することができます。 または既存のポリシーの設定を変更するのには、**セット CsClientPolicy**コマンドレットを使用することができます。
  
## <a name="set-your-client-policies"></a>クライアント ポリシーを設定する

> [!NOTE]
> Skype for Business Online のすべてのクライアント ポリシー設定では、Windows PowerShell を使用する必要があります。 **Skype for Business 管理センター** を **使用することはできません**。 
  
### <a name="verify-and-start-windows-powershell"></a>Windows PowerShell を検証および開始する

- **Windows PowerShell バージョン 3.0 以降を実行していることを確認する**
    
1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
    
2. [ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。
    
3. バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。
    
4. Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。
    
    詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」を参照してください。
    
- **Windows PowerShell セッションを開始する**
    
1. From the **Start Menu** > **Windows PowerShell**.
    
2. [ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。
    
    > [!NOTE]
    > Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   Windows PowerShell を開始する方法の詳細を設定する場合は、 [1 つの Windows PowerShell のウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)か、 [Windows PowerShell には、コンピューターの設定](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)を参照してください。
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>絵文字、プレゼンスの通知を無効にして、インスタントメッセージ (IM) の保存を防止する

- これらの設定のために新しいポリシーを作成するには、次を実行します。
    
> 
>   ```
>   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
>   ```

  [新規 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx)コマンドレットの詳細を参照してください。
    
- 作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。
    
> 
>   ```
>   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
>   ```

  [許可 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx)コマンドレットの詳細を参照してください。
    
ポリシーを既に作成した場合は、[セット CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx)コマンドレットを使用して既存のポリシーに変更を加えるし、[許可 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx)コマンドレットを使用して設定をユーザーに適用します。
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>URL またはハイパーリンクを有効にしてインスタントメッセージ (IM) でクリックできる状態にする

- これらの設定のために新しいポリシーを作成するには、次を実行します。
    
> 
>   ```
>   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
>   ```

  [新規 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx)コマンドレットの詳細を参照してください。
    
- 作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。
    
> 
>   ```
>   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
>   ```

  [許可 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx)コマンドレットの詳細を参照してください。
    
ポリシーを既に作成した場合は、[セット CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx)コマンドレットを使用して既存のポリシーに変更を加えるし、[許可 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx)コマンドレットを使用して設定をユーザーに適用します。
  
### <a name="prevent-showing-recent-contacts"></a>最近の連絡先を表示しないようにする

- これらの設定のために新しいポリシーを作成するには、次を実行します。
  > 
  > ```
  > New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
  > ```

  [新規 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx)コマンドレットの詳細を参照してください。
    
- Amos Marble に作成した新しいポリシーを付与するには、次を実行します。
  > 
  > ```
  > Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
  > ```

  [許可 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx)コマンドレットの詳細を参照してください。
    
  ポリシーを既に作成した場合は、[セット CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx)コマンドレットを使用して既存のポリシーに変更を加えるし、[許可 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx)コマンドレットを使用して設定をユーザーに適用します。
  
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

- Windows PowerShell は、ユーザーを管理するユーザーを許可または許可されません。 Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>関連トピック
[カスタム外部アクセス ポリシーを作成する](create-custom-external-access-policies.md)

[ブロック ポイント ツー ポイントのファイルの転送](block-point-to-point-file-transfers.md)

[組織内の会議ポリシーを設定します](set-up-conferencing-policies-for-your-organization.md)

  
 

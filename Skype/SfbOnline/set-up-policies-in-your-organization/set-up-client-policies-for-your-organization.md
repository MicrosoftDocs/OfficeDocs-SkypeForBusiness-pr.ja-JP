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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: クライアント ポリシーはユーザーが利用できる Skype for Business Online の機能を決めるのに役立ちます。たとえば、一部のユーザーにファイルを転送する権限を与えて、他のユーザーに対してはその権限を与えないようにする場合が考えられます。
ms.openlocfilehash: 3a7dd7a2840a4e94abe88c472e6dc5b0e1720704
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814356"
---
# <a name="set-up-client-policies-for-your-organization"></a>組織のクライアント ポリシーをセットアップする

[] クライアント ポリシーはユーザーが利用できる Skype for Business Online の機能を決めるのに役立ちます。たとえば、一部のユーザーにファイルを転送する権限を与えて、他のユーザーに対してはその権限を与えないようにする場合が考えられます。
  
クライアントポリシー設定はポリシーが作成されるときに構成することができます。また、 **Set-CsClientPolicy** コマンドレットを使用して、既存のポリシーの設定を変更することもできます。
  
## <a name="set-your-client-policies"></a>クライアント ポリシーを設定する

> [!NOTE]
> Skype for Business Online のすべてのクライアント ポリシー設定では、Windows PowerShell を使用する必要があります。 **Skype for Business 管理センター** を **使用することはできません**。 
  
### <a name="verify-and-start-windows-powershell"></a>Windows PowerShell を検証および開始する

- **Windows PowerShell バージョン 3.0 以降を実行していることを確認する**
    
    1. 3.0 以降のバージョンが実行されていることを確認する場合: **[スタート] メニュー** > **[Windows PowerShell]**。
        
    2. [ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。
        
    3. バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。 Windows PowerShell をバージョン4.0 にダウンロードして更新するには、「 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 」を参照してください。 メッセージが表示されたら、コンピューターを再起動します。
        
    4. また、Skype for Business Online に接続するリモート Windows PowerShell セッションを作成できるようにする、Teams 用の Windows PowerShell モジュールをインストールする必要があります。 
    
    詳細については、「 [単一の Windows PowerShell ウィンドウですべての Microsoft 365 または Office 365 サービスに接続する](https://technet.microsoft.com/library/dn568015.aspx)」を参照してください。
    
- **Windows PowerShell セッションを開始する**
    
    1. From the **Start Menu** > **Windows PowerShell**.
        
    2. **Windows PowerShell**ウィンドウで、次を実行して Microsoft 365 または Office 365 に接続します。
    
    > [!NOTE]
    > Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。
    >
    > 最新の [Teams PowerShell パブリックリリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)を使用している場合は、Skype For Business Online Connector をインストールする必要はありません。

       ```powershell
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session 
       ```
Windows PowerShell の起動の詳細については、「 [1 つの Windows powershell ウィンドウですべての Microsoft 365 または Office 365 サービスに接続](https://technet.microsoft.com/library/dn568015.aspx) する」または「 [windows powershell 用のコンピューターをセットアップ](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)する」を参照してください。
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>絵文字、プレゼンスの通知を無効にして、インスタントメッセージ (IM) の保存を防止する

- これらの設定のために新しいポリシーを作成するには、次を実行します。
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  詳細については、「 [新しい-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) コマンドレット」を参照してください。
    
- 作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  詳細については、「 [Grant Clientpolicy](https://technet.microsoft.com/library/mt779152.aspx) コマンドレット」を参照してください。
    
既にポリシーを作成している場合は、 [Set-csclientpolicy](https://technet.microsoft.com/library/mt779153.aspx) コマンドレットを使用して既存のポリシーに変更を加え、[ [権限の付与] クライアントポリシー](https://technet.microsoft.com/library/mt779152.aspx) コマンドレットを使用して、ユーザーに設定を適用することができます。
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>URL またはハイパーリンクを有効にしてインスタントメッセージ (IM) でクリックできる状態にする

- これらの設定のために新しいポリシーを作成するには、次を実行します。
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  詳細については、「 [新しい-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) コマンドレット」を参照してください。
    
- 作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  詳細については、「 [Grant Clientpolicy](https://technet.microsoft.com/library/mt779152.aspx) コマンドレット」を参照してください。
    
既にポリシーを作成している場合は、 [Set-csclientpolicy](https://technet.microsoft.com/library/mt779153.aspx) コマンドレットを使用して既存のポリシーに変更を加え、[ [権限の付与] クライアントポリシー](https://technet.microsoft.com/library/mt779152.aspx) コマンドレットを使用して、ユーザーに設定を適用することができます。
  
### <a name="prevent-showing-recent-contacts"></a>最近の連絡先を表示しないようにする

- これらの設定のために新しいポリシーを作成するには、次を実行します。
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  詳細については、「 [新しい-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) コマンドレット」を参照してください。
    
- Amos Marble に作成した新しいポリシーを付与するには、次を実行します。
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  詳細については、「 [Grant Clientpolicy](https://technet.microsoft.com/library/mt779152.aspx) コマンドレット」を参照してください。
    
  既にポリシーを作成している場合は、 [Set-csclientpolicy](https://technet.microsoft.com/library/mt779153.aspx) コマンドレットを使用して既存のポリシーに変更を加え、[ [権限の付与] クライアントポリシー](https://technet.microsoft.com/library/mt779152.aspx) コマンドレットを使用して、ユーザーに設定を適用することができます。
  
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

- Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。 Windows PowerShell を使用すると、複数のタスクがある場合に、1つの管理ポイントを使用して、Microsoft 365 または Office 365 と Skype for Business Online を管理することができます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell を使用して Microsoft 365 または Office 365 を管理する6つの理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、多くのユーザーについて同時に設定を変更する場合など、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を高めることができます。 次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell を使用して Microsoft 365 または Office 365 を管理するのに最適な方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>関連トピック
[カスタム外部アクセス ポリシーを作成する](create-custom-external-access-policies.md)

[ポイントツーポイントファイル転送をブロックする](block-point-to-point-file-transfers.md)

[組織内の会議ポリシーをセットアップする](set-up-conferencing-policies-for-your-organization.md)

  
 

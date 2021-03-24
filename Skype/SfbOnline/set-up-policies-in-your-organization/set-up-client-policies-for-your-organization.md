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
ms.openlocfilehash: 3706e6b4fafe15aa8b799170001af61b837968da
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100533"
---
# <a name="set-up-client-policies-for-your-organization"></a>組織のクライアント ポリシーをセットアップする

[] クライアント ポリシーはユーザーが利用できる Skype for Business Online の機能を決めるのに役立ちます。たとえば、一部のユーザーにファイルを転送する権限を与えて、他のユーザーに対してはその権限を与えないようにする場合が考えられます。
  
クライアント ポリシー設定は、ポリシーの作成時に構成するか **、Set-CsClientPolicy** コマンドレットを使用して既存のポリシーの設定を変更できます。
  
## <a name="set-your-client-policies"></a>クライアント ポリシーを設定する

> [!NOTE]
> Skype for Business Online のすべてのクライアント ポリシー設定では、Windows PowerShell を使用する必要があります。 **Skype for Business 管理センター** を **使用することはできません**。 
  
### <a name="start-windows-powershell"></a>スタートWindows PowerShell

> [!NOTE]
> Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。 最新の Teams PowerShell パブリック リリースをご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。
1. Teams [PowerShell モジュールをインストールします](/microsoftteams/teams-powershell-install)。
    
2. コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   Windows PowerShell の起動の詳細については、「1 つの Windows PowerShell ウィンドウで[すべての Microsoft 365 または Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)サービスに接続する」[](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)または「Windows PowerShell 用にコンピューターをセットアップする」を参照してください。
 
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>絵文字、プレゼンスの通知を無効にして、インスタントメッセージ (IM) の保存を防止する

- これらの設定のために新しいポリシーを作成するには、次を実行します。
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  [New-CsClientPolicy コマンドレットの詳細については、以下を参照](/powershell/module/skype/New-CsClientPolicy)してください。
    
- 作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  [Grant-CsClientPolicy コマンドレットの詳細については、以下を参照](/powershell/module/skype/Grant-CsClientPolicy)してください。
    
既にポリシーを作成している場合は [、Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) コマンドレットを使用して既存のポリシーを変更し [、Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) コマンドレットを使用して設定をユーザーに適用できます。
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>URL またはハイパーリンクを有効にしてインスタントメッセージ (IM) でクリックできる状態にする

- これらの設定のために新しいポリシーを作成するには、次を実行します。
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  [New-CsClientPolicy コマンドレットの詳細については、以下を参照](/powershell/module/skype/New-CsClientPolicy)してください。
    
- 作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  [Grant-CsClientPolicy コマンドレットの詳細については、以下を参照](/powershell/module/skype/Grant-CsClientPolicy)してください。
    
既にポリシーを作成している場合は [、Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) コマンドレットを使用して既存のポリシーを変更し [、Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) コマンドレットを使用して設定をユーザーに適用できます。
  
### <a name="prevent-showing-recent-contacts"></a>最近の連絡先を表示しないようにする

- これらの設定のために新しいポリシーを作成するには、次を実行します。
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  [New-CsClientPolicy コマンドレットの詳細については、以下を参照](/powershell/module/skype/New-CsClientPolicy)してください。
    
- Amos Marble に作成した新しいポリシーを付与するには、次を実行します。
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  [Grant-CsClientPolicy コマンドレットの詳細については、以下を参照](/powershell/module/skype/Grant-CsClientPolicy)してください。
    
  既にポリシーを作成している場合は [、Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) コマンドレットを使用して既存のポリシーを変更し [、Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) コマンドレットを使用して設定をユーザーに適用できます。
  
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

- Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。 Windows PowerShell を使用すると、単一の管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理できます。複数のタスクを実行する必要がある場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Microsoft 365 または Windows PowerShell 365 の管理に使用する 6 Office理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShellは、多くのユーザーに対して同時に設定変更を行う場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性の点で多くの利点があります。 次のトピックでこれらの利点について説明します。
    
  - [Microsoft 365 または Office 365 を他のユーザーとWindows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Windows PowerShell による Skype for Business Online の管理](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>関連項目
[カスタム外部アクセス ポリシーを作成する](create-custom-external-access-policies.md)

[ポイント間ファイル転送をブロックする](block-point-to-point-file-transfers.md)

[組織で会議ポリシーを設定する](set-up-conferencing-policies-for-your-organization.md)

  

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
ms.openlocfilehash: 59bc9ab406d530bc09803b61cfc4341617dc911d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240089"
---
# <a name="set-up-client-policies-for-your-organization"></a>組織のクライアント ポリシーをセットアップする

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

[] クライアント ポリシーはユーザーが利用できる Skype for Business Online の機能を決めるのに役立ちます。たとえば、一部のユーザーにファイルを転送する権限を与えて、他のユーザーに対してはその権限を与えないようにする場合が考えられます。
  
クライアント ポリシーの設定は、ポリシーの作成時に構成するか **、Set-CsClientPolicy** コマンドレットを使用して既存のポリシーの設定を変更できます。
  
## <a name="set-your-client-policies"></a>クライアント ポリシーを設定する

> [!NOTE]
> Skype for Business Online のすべてのクライアント ポリシー設定では、Windows PowerShell を使用する必要があります。 **Skype for Business 管理センター** を **使用することはできません**。 
  
### <a name="start-windows-powershell"></a>スタートWindows PowerShell

> [!NOTE]
> Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。 最新の Teams PowerShell パブリック リリースをご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。
1. [PowerShell モジュール Teamsインストールします](/microsoftteams/teams-powershell-install)。
    
2. コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   Windows PowerShell の起動の詳細については、「Connect を 1 つの Windows PowerShell ウィンドウですべての Microsoft 365 または[Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)サービスに接続する」または「Windows PowerShell 用にコンピューターをセットアップする」[を参照](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)してください。
 
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>絵文字、プレゼンスの通知を無効にして、インスタントメッセージ (IM) の保存を防止する

- これらの設定のために新しいポリシーを作成するには、次を実行します。
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  [詳細については、New-CsClientPolicy コマンドレットを参照](/powershell/module/skype/New-CsClientPolicy)してください。
    
- 作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  [詳細については、Grant-CsClientPolicy コマンドレットを参照](/powershell/module/skype/Grant-CsClientPolicy)してください。
    
既にポリシーを作成している場合は [、Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) コマンドレットを使用して既存のポリシーを変更し [、Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) コマンドレットを使用して設定をユーザーに適用できます。
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>URL またはハイパーリンクを有効にしてインスタントメッセージ (IM) でクリックできる状態にする

- これらの設定のために新しいポリシーを作成するには、次を実行します。
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  [詳細については、New-CsClientPolicy コマンドレットを参照](/powershell/module/skype/New-CsClientPolicy)してください。
    
- 作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  [詳細については、Grant-CsClientPolicy コマンドレットを参照](/powershell/module/skype/Grant-CsClientPolicy)してください。
    
既にポリシーを作成している場合は [、Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) コマンドレットを使用して既存のポリシーを変更し [、Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) コマンドレットを使用して設定をユーザーに適用できます。
  
### <a name="prevent-showing-recent-contacts"></a>最近の連絡先を表示しないようにする

- これらの設定のために新しいポリシーを作成するには、次を実行します。
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  [詳細については、New-CsClientPolicy コマンドレットを参照](/powershell/module/skype/New-CsClientPolicy)してください。
    
- Amos Marble に作成した新しいポリシーを付与するには、次を実行します。
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  [詳細については、Grant-CsClientPolicy コマンドレットを参照](/powershell/module/skype/Grant-CsClientPolicy)してください。
    
  既にポリシーを作成している場合は [、Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) コマンドレットを使用して既存のポリシーを変更し [、Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) コマンドレットを使用して設定をユーザーに適用できます。
  
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

- Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。 Windows PowerShellでは、1 つの管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理できます。複数のタスクを実行する場合は、毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [アプリを使用して管理や管理をWindows PowerShellする 6 Microsoft 365理由Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell多くのユーザーに対して一度に設定を変更する場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性に多くの利点があります。 次のトピックでこれらの利点について説明します。
    
  - [アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Windows PowerShell による Skype for Business Online の管理](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>関連項目
[カスタム外部アクセス ポリシーを作成する](create-custom-external-access-policies.md)

[ポイント対ポイントファイル転送をブロックする](block-point-to-point-file-transfers.md)

[組織で会議ポリシーを設定する](set-up-conferencing-policies-for-your-organization.md)

  

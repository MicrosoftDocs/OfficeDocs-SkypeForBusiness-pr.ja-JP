---
title: 組織のモバイル ポリシーをセットアップする
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
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
description: モバイル デバイス上の Skype for Business アプリで、携帯電話番号ではなく勤務先の電話番号を使用して携帯電話上で通話を発信および受信できるようにする機能などにより、ユーザーが Skype for Business Online に接続する方法を設定することができます。モバイル機能ポリシーを使用して、通話の発着信時に Wi-Fi 接続を要求するようにすることもできます。
ms.openlocfilehash: b0e2f7524f300733840159eacfcf27bb54f5e815
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100493"
---
# <a name="set-up-mobile-policies-for-your-organization"></a>組織のモバイル ポリシーをセットアップする

[] モバイル デバイス上の Skype for Business アプリで、携帯電話番号ではなく勤務先の電話番号を使用して携帯電話上で通話を発信および受信できるようにする機能などにより、ユーザーが Skype for Business Online に接続する方法を設定することができます。モバイル機能ポリシーを使用して、通話の発着信時に Wi-Fi 接続を要求するようにすることもできます。
  
モバイル機能ポリシー設定はポリシーが作成されるときに構成できます。また、 **Set-CsMobilityPolicy** コマンドレットを使用して既存のポリシーの設定を変更できます。
  
## <a name="set-your-mobile-policies"></a>モバイル機能ポリシーを設定する

> [!NOTE]
> Skype for Business Online のすべてのモバイル機能ポリシー設定では、Windows PowerShell を使用する必要があります。 **Skype for Business 管理センター** を **使用することはできません**。 
  
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
   
### <a name="require-a-wifi-connection-for-video-for-a-user"></a>ユーザーに対してビデオ使用時に WiFi 接続を要求する

- これらの設定のために新しいポリシーを作成するには、次を実行します。
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   [New-CsMobilityPolicy コマンドレットの詳細については、以下を参照](/powershell/module/skype/New-CsMobilityPolicy)してください。
    
- 作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   [Grant-CsMobilityPolicy コマンドレットの詳細については、以下を参照](/powershell/module/skype/Grant-CsMobilityPolicy)してください。
    
  ポリシーを作成済みの場合は、[Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) コマンドレットを使用して、既存のポリシーに対する変更を行います。次に、[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) を使用して設定をユーザーに適用します。
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a>ユーザーが Skype for Business アプリを使用できないようにする

- これらの設定のために新しいポリシーを作成するには、次を実行します。
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  [New-CsMobilityPolicy コマンドレットの詳細については、以下を参照](/powershell/module/skype/New-CsMobilityPolicy)してください。
    
- Amos Marble に作成した新しいポリシーを付与するには、次を実行します。  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   [Grant-CsMobilityPolicy コマンドレットの詳細については、以下を参照](/powershell/module/skype/Grant-CsMobilityPolicy)してください。
    
  既にポリシーを作成している場合は [、Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) コマンドレットを使用して既存のポリシーを変更し [、Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) コマンドレットを使用して設定をユーザーに適用できます。
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a>ユーザーがモバイル デバイスを使用してボイス オーバー IP 通話を行えないようにする

- これらの設定のために新しいポリシーを作成するには、次を実行します。
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   [New-CsMobilityPolicy コマンドレットの詳細については、以下を参照](/powershell/module/skype/New-CsMobilityPolicy)してください。
    
- 作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  [Grant-CsMobilityPolicy コマンドレットの詳細については、以下を参照](/powershell/module/skype/Grant-CsMobilityPolicy)してください。
    
ポリシーを作成済みの場合は、[Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) コマンドレットを使用して、既存のポリシーに対する変更を行います。次に、[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) を使用して設定をユーザーに適用します。
  
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

- Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。 Windows PowerShell を使用すると、単一の管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理できます。複数のタスクを実行する必要がある場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Microsoft 365 または Windows PowerShell 365 の管理に使用する 6 Office理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShellは、多くのユーザーに対して同時に設定変更を行う場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性の点で多くの利点があります。 次のトピックでこれらの利点について説明します。
    
  - [Microsoft 365 または Office 365 を管理するための最適Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Windows PowerShell による Skype for Business Online の管理](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>関連項目
[カスタム外部アクセス ポリシーを作成する](create-custom-external-access-policies.md)

[ポイント間のファイル転送をブロックする](block-point-to-point-file-transfers.md)

[組織のクライアント ポリシーをセットアップする](set-up-client-policies-for-your-organization.md)

[組織で会議ポリシーを設定する](set-up-conferencing-policies-for-your-organization.md)

  

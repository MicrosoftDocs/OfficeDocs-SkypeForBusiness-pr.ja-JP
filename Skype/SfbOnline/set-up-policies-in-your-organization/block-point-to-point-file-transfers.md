---
title: ポイント ツー ポイントのファイル転送を禁止する
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
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
description: Skype for Business Online では、既存の会議ポリシー設定の一部として、ポイント対ポイント (P2P) ファイル転送を制御できます。 ただし、これにより、ユーザーが同じ組織内のユーザーまたは別の組織のフェデレーション ユーザーにファイルを転送するかどうかに関わり、ユーザーのファイル転送が許可またはブロックされます。 以下の手順に従って、フェデレーション組織またはパートナーとの P2P ファイル転送をブロックできます。
ms.openlocfilehash: e2a0bb2f250f89433c09566197df7a56efa7f64f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100623"
---
# <a name="block-point-to-point-file-transfers"></a>ポイント ツー ポイントのファイル転送を禁止する

Skype for Business Online では、既存の会議ポリシー設定の一部として、ポイント対ポイント (P2P) ファイル転送を制御できます。 ただし、これにより、ユーザーが同じ組織内のユーザーまたは別の組織のフェデレーション ユーザーにファイルを転送するかどうかに関わり、ユーザーのファイル転送が許可またはブロックされます。 以下の手順に従って、フェデレーション組織またはパートナーとの P2P ファイル転送をブロックできます。
  
 非常に一般的なシナリオは、内部ユーザーに P2P ファイル転送の使用を許可し、フェデレーション パートナーとのファイル転送をブロックする場合です。 このシナリオでは、次の操作を行う必要があります。
  
- P2P ファイル転送が有効になっている会議ポリシー _(EnableP2PFileTransfer_ を _True_ に設定) を組織内のユーザーに割り当てる。
    
- 外部 P2P ファイル転送 _(EnableP2PFileTransfer_ を _False_ に設定) をブロックするグローバル外部ユーザー通信ポリシー セットを作成し、組織内のユーザーに割り当てる。 
    
これらの設定に関する詳細は、 [ここ](/previous-versions//mt228132(v=technet.10))からご覧いただけます。
  
組織外のフェデレーション ユーザーが、ポリシーが適用されているユーザーにファイルを送信しようとすると、転送失敗エラー **が表示** されます。 ユーザーがファイルを送信しようとすると、ファイル転送が無効になっているエラー **が表示** されます。
  
この作業を行う場合、ユーザーは 2016 年のサポートされるバージョンを使用して、クイック実行 Skype for Business アプリを使用している必要があります。 Skype for Business 2016 クイック実行クライアントの次の最小バージョンが必要です。
  
|**Type**|**リリース日**|**バージョン**|**ビルド**|
|:-----|:-----|:-----|:-----|
|最新機能提供チャネルの最初のリリース  <br/> |2016 年 11 月 17 日  <br/> |16.0.7571.2006  <br/> |バージョン 1611 (ビルド 7571.2006)  <br/> |
|最新機能提供チャネル  <br/> |2016 年 12 月 6 日  <br/> |16.0.7571.2072  <br/> |バージョン 1611 (ビルド 7571.2072)  <br/> |
|段階的提供チャネル  <br/> |2017 年 2 月 22 日  <br/> |16.0.7369.2118  <br/> |バージョン 1609 (ビルド 7369.2118)  <br/> |
   
> [!CAUTION]
> 以前のバージョンの Skype for Business Windows アプリまたは Mac クライアントを使用しているユーザーは、引き続きファイルを転送できます。 
  
## <a name="start-windows-powershell"></a>スタートWindows PowerShell

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
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>組織の P2P ファイル転送を無効にする

既定では _、EnableP2PFileTransfer は_ 組織のグローバル ポリシーで有効になっています。 作成されると、ユーザーに _BposSAllModality ポリシーが割り当_ てされました。
  
組織内での P2P 転送を許可し、別の組織への外部ファイル転送をブロックするには、グローバル レベルで変更する必要があります。 これを行うには、次を実行します。
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>ユーザーの P2P ファイル転送を無効にする

新しいポリシーを作成し、そのユーザーに付与することで、このポリシーをユーザーに適用できます。 これを行うには、次を実行します。 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

- Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。 Windows PowerShell を使用すると、単一の管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理できます。複数のタスクを実行する必要がある場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Microsoft 365 または Office 365 PowerShell を使用する必要がある理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShellは、多くのユーザーに対して同時に設定変更を行う場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性の点で多くの利点があります。 次のトピックでこれらの利点について説明します。
    
  - [Microsoft 365 または Office 365 を管理するための最適Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Windows PowerShell による Skype for Business Online の管理](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>関連項目
[カスタム外部アクセス ポリシーを作成する](create-custom-external-access-policies.md)

[組織のクライアント ポリシーをセットアップする](set-up-client-policies-for-your-organization.md)

[組織で会議ポリシーを設定する](set-up-conferencing-policies-for-your-organization.md)

  

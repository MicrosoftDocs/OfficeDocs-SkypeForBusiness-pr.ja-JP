---
title: Skype for Business クライアントのフィードバック レポートをオンまたはオフにする
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 35562b48-1da1-4081-8a3a-033d0f1986b2
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
description: Skype for Business ユーザーが組み込みの Skype for Business アプリフィードバック ツールを使用して、ユーザーが問題を報告し、エクスペリエンスに関するフィードバックを Microsoft に直接提供することができます。
ms.openlocfilehash: 9b9134f857be540a528ca12b51a4793c01f70fa4
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569003"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a>Skype for Business クライアントのフィードバック レポートをオンまたはオフにする

Skype for Business Online ユーザーが組み込みの Skype for Business アプリフィードバック ツールを使用して、ユーザーが問題を報告し、エクスペリエンスに関するフィードバックを Microsoft に直接提供することができます。 
  
![[フィードバックの提供] アイコン](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
このツールを使用すると、ユーザーはデバイス上のアプリからログをコピーして、Microsoft が発生する可能性のある問題の調査とトラブルシューティングを行う際に役立ちます。 
  
![[設定] アイコンを使用して問題を報告する](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
デバイスのスクリーンショットをユーザーのフィードバックに含めるために  _EnableOnlineFeedbackScreenshot_ の設定を使用することもできます。
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> アプリのフィードバック ツールによって収集されたログは、問題の調査中に最大 90 日間、米国に保存されます。 これが所属する組織のデータ保護ポリシーに抵触する場合は、このフィードバック ツールを有効にしないでください。 
  
## <a name="start-windows-powershell"></a>スタートWindows PowerShell

> [!NOTE]
> Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。 最新の Teams PowerShell パブリック リリースをご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。
1. Teams [PowerShell モジュールをインストールします](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。
    
2. コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
   Windows PowerShell の起動の詳細については、「1 つの Windows PowerShell ウィンドウで[すべての Microsoft 365 または Office 365](https://technet.microsoft.com/library/dn568015.aspx)サービスに接続する」[](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)または「Windows PowerShell 用にコンピューターをセットアップする」を参照してください。
   
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a>組織のすべてのユーザーに対してクライアント アプリのフィードバック レポートをオンにする

組織内のユーザーに対してフィードバックレポートを有効にして、デバイスのスクリーンショットの送信を許可するには、次を実行します。
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報
- Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。 Windows PowerShell を使用すると、単一の管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理できます。複数のタスクを実行する必要がある場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Microsoft 365 または Windows PowerShell 365 の管理に使用する 6 Office理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell多くのユーザーに対して同時に設定変更を行う場合など、Microsoft 365 管理センターのみを使用する場合と同様に、速度、シンプルさ、生産性に多くの利点があります。 次のトピックでこれらの利点について説明します。
    
  - [Microsoft 365 または Office 365 を他のユーザーとWindows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>関連項目
[Skype for Business Online をセットアップする](set-up-skype-for-business-online.md)

[Skype for Business ユーザーが Skype の連絡先を追加できるようにする](let-skype-for-business-users-add-skype-contacts.md)

  
 

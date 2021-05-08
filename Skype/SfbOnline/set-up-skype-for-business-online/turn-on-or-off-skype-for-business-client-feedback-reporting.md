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
description: Skype for Business ユーザーが組み込みの Skype for Business アプリ フィードバック ツールを使用して、ユーザーが問題を報告し、そのエクスペリエンスに関するフィードバックを Microsoft に直接提供することができます。
ms.openlocfilehash: 151ba9ee82c95f088f5c7fc87de3a06ce609ab01
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239100"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a>Skype for Business クライアントのフィードバック レポートをオンまたはオフにする

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype for Business Online ユーザーが組み込みの Skype for Business アプリ フィードバック ツールを使用して、ユーザーが問題を報告し、そのエクスペリエンスに関するフィードバックを Microsoft に直接提供することができます。 
  
![[フィードバックの提供] アイコン](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
このツールを使用すると、ユーザーはデバイス上のアプリからログをコピーして、Microsoft が発生する可能性のある問題の調査とトラブルシューティングを行うのに役立ちます。 
  
![[問題の報告] アイコンを設定する](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
デバイスのスクリーンショットをユーザーのフィードバックに含めるために  _EnableOnlineFeedbackScreenshot_ の設定を使用することもできます。
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> 問題の調査中に、アプリのフィードバック ツールによって収集されたログは、最大 90 日間、米国に保存されます。 これが所属する組織のデータ保護ポリシーに抵触する場合は、このフィードバック ツールを有効にしないでください。 
  
## <a name="start-windows-powershell"></a>スタートWindows PowerShell

> [!NOTE]
> Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。 最新の Teams PowerShell パブリック リリースをご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。
1. [PowerShell モジュール Teamsインストールします](/microsoftteams/teams-powershell-install)。
    
2. コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
   Windows PowerShell の起動の詳細については、「Connect を 1 つの Windows PowerShell ウィンドウですべての Microsoft 365 または[Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)サービスに接続する」または「Windows PowerShell 用にコンピューターをセットアップする」[を参照](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)してください。
   
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a>組織のすべてのユーザーに対してクライアント アプリのフィードバック レポートをオンにする

組織内のユーザーに対するフィードバック レポートを有効にして、デバイスのスクリーンショットを送信するには、次のコマンドを実行します。
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報
- Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。 Windows PowerShellでは、1 つの管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理できます。複数のタスクを実行する場合は、毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [アプリを使用して管理や管理をWindows PowerShellする 6 Microsoft 365理由Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell多くのユーザーに対して一度に設定を変更する場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性に多くの利点があります。 次のトピックでこれらの利点について説明します。
    
  - [アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Windows PowerShell による Skype for Business Online の管理](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>関連トピック
[Skype for Business Online をセットアップする](set-up-skype-for-business-online.md)

[Skype for Business ユーザーが Skype の連絡先を追加できるようにする](let-skype-for-business-users-add-skype-contacts.md)

  

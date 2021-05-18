---
title: Outlook 会議で使用するコンテンツ プリロードの有効化と無効化
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d217d422-f7e9-433d-ad24-bf41751f65ca
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
description: 'See how to turn preloaded content on or off for Skype for Business meetings using files or attachments on an Outlook meeting invitation. '
ms.openlocfilehash: b6ff40e34c6459a75d0b79a8d750902a3457e00d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239110"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a>Outlook 会議で使用するコンテンツ プリロードの有効化と無効化

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

ユーザーは、Outlook 会議出席依頼に添付されているコンテンツ、ファイル、添付ファイルを Skype for Business Online 会議に事前読み込みできますが、オンまたはオフにすることもできます。 この機能は、オンラインで使用しているすべての組織で既定Skype for Businessされます。 会議の添付ファイル[を事前に読み込むSkype for Business参照してください](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)。
  
> [!NOTE]
> 現在 _、MaxContentStorageMB_ と _MaxUploadFileMB_ のオンライン値を設定または表示Skype for Business Online で使用できるコマンドレットはありません。 これは、オンプレミス環境でのみ使用できます。 添付されたコンテンツが  _MaxUploadFileSizeMB_ を超えた場合、または _MaxContentStorageMB_ の制限に達した場合、コンテンツは会議にアップロードされません。
  
## <a name="to-get-you-started"></a>使用するには、次のようにします。

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
  
## <a name="turning-it-on-or-off"></a>機能の有効化と無効化

Skype for Business Online 会議への Outlook 会議出席依頼に添付されたコンテンツを事前に読み込む機能は既定で有効になっていますが、組織内のユーザーが会議のコンテンツを事前に読み込むのを防ぐ必要がある場合があります。
  
> [!IMPORTANT]
> この設定は、組織全体でのみ有効または無効にできます。1 人のユーザーに対して有効またはオフにできない。 
  
 **無効にするには、Windows PowerShell を開いて、次を行います。**
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 **再び有効にするには、Windows PowerShell を開いて、次を行います。**
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

- Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。 Windows PowerShellでは、1 つの管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理できます。複数のタスクを実行する場合は、毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [アプリを使用して管理や管理をWindows PowerShellする 6 Microsoft 365理由Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell多くのユーザーに対して一度に設定を変更する場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性に多くの利点があります。 次のトピックでこれらの利点について説明します。
    
  - [アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Windows PowerShell による Skype for Business Online の管理](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>関連項目
[Skype for Business Online をセットアップする](set-up-skype-for-business-online.md)

[Skype for Business ユーザーが Skype の連絡先を追加できるようにする](let-skype-for-business-users-add-skype-contacts.md)

  

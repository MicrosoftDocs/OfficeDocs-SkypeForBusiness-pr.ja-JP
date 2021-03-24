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
ms.openlocfilehash: ff0603ca68f4e828fc3b6977065ac9ec3ca6a33d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103803"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a>Outlook 会議で使用するコンテンツ プリロードの有効化と無効化

ユーザーは、Skype for Business Online 会議への Outlook 会議出席依頼に添付されているコンテンツ、ファイル、または添付ファイルをプリロードできますが、オンとオフを切り替えることもできます。 Skype for Business Online を使用しているすべての組織で既定で有効になっています。 [Skype for Business 会議の添付ファイルをプリロードする方法をご覧ください](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)。
  
> [!NOTE]
> 現在、Skype for Business Online には  _、MaxContentStorageMB_ と _MaxUploadFileMB_ のオンライン値を設定または表示するコマンドレットはありません。 これは、オンプレミス環境でのみ使用できます。 添付されたコンテンツが  _MaxUploadFileSizeMB_ を超える場合、または _MaxContentStorageMB_ の制限に達した場合、コンテンツは会議にアップロードされません。
  
## <a name="to-get-you-started"></a>使用するには、次のようにします。

## <a name="start-windows-powershell"></a>スタートWindows PowerShell

> [!NOTE]
> Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。 最新の Teams PowerShell パブリック リリースをご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。
1. Teams [PowerShell モジュールをインストールします](/microsoftteams/teams-powershell-install)。
    
2. コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

Windows PowerShell の起動の詳細については、「1 つの Windows PowerShell ウィンドウで[すべての Microsoft 365 または Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)サービスに接続する」[](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)または「Windows PowerShell 用にコンピューターをセットアップする」を参照してください。
  
## <a name="turning-it-on-or-off"></a>機能の有効化と無効化

Outlook 会議出席依頼に添付されたコンテンツを Skype for Business Online 会議にプリロードできる機能は既定で有効になっていますが、組織内のユーザーが会議にコンテンツをプリロードできない場合があります。
  
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

- Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。 Windows PowerShell を使用すると、単一の管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理できます。複数のタスクを実行する必要がある場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Microsoft 365 または Windows PowerShell 365 の管理に使用する 6 Office理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShellは、多くのユーザーに対して同時に設定変更を行う場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性の点で多くの利点があります。 次のトピックでこれらの利点について説明します。
    
  - [Microsoft 365 または Office 365 を他のユーザーとWindows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Windows PowerShell による Skype for Business Online の管理](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>関連項目
[Skype for Business Online をセットアップする](set-up-skype-for-business-online.md)

[Skype for Business ユーザーが Skype の連絡先を追加できるようにする](let-skype-for-business-users-add-skype-contacts.md)

  

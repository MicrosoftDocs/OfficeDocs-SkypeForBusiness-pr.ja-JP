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
f1keywords: None
ms.custom:
- Setup
description: 'See how to turn preloaded content on or off for Skype for Business meetings using files or attachments on an Outlook meeting invitation. '
ms.openlocfilehash: 8b3b912526a44fb10cb685dd6ab9b3dea8f8eac4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284926"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a>Outlook 会議で使用するコンテンツ プリロードの有効化と無効化

ユーザーは、Outlook 会議出席依頼に添付されているコンテンツ、ファイル、または添付ファイルを Skype for Business Online の会議にプリロードできますが、オンとオフを切り替えることができます。 Skype for Business Online を使用しているすべての組織に対して、既定でオンになっています。 [Skype For business 会議の添付ファイルをプリロード](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)する方法について説明します。
  
> [!NOTE]
> 現時点では、 _Maxcontentstoragemb 枠_と_Maxcontentstoragemb_のオンライン値を設定または表示するために、Skype for business Online で利用可能なコマンドレットはありません。 これは、オンプレミス環境でのみ使用できます。 添付されたコンテンツが_Maxuploadfilesizemb 枠_を超えている場合、または_Maxcontentstorag飾り_枠の制限に達している場合は、コンテンツが会議にアップロードされないことを知っておくことが重要です。
  
## <a name="to-get-you-started"></a>使用するには、次のようにします。

### 

 **Windows PowerShell バージョン 3.0 以降を実行していることを確認する**
  
1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
    
2. [ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。
    
3. バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。
    
4. Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。
    
詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」を参照してください。
  
### 

 **Windows PowerShell セッションを開始する**
  
1. From the **Start Menu** > **Windows PowerShell**.
    
2. [ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。
    
    > [!NOTE]
    > Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
$credential = Get-Credential
$session = New-CsOnlineSession -Credential $credential
Import-PSSession $session
```

Windows PowerShell の起動の詳細については、「[単一の Windows powershell ウィンドウですべての Office 365 サービスに接続](https://technet.microsoft.com/EN-US/library/dn568015.aspx)する」または「 [windows powershell 用のコンピューターをセットアップ](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)する」を参照してください。
  
## <a name="turning-it-on-or-off"></a>機能の有効化と無効化

Outlook の会議出席依頼に添付されているコンテンツを Skype for Business Online の会議に自動的に読み込むことができるようになっている場合、既定ではオンになっていますが、組織内のユーザーが会議のコンテンツを事前に設定できないようにする必要があります。
  
> [!IMPORTANT]
> この設定は組織全体で有効または無効にすることができます。1人のユーザに対して有効または無効にすることはできません。 
  
 **無効にするには、Windows PowerShell を開いて、次を行います。**
  
```
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 **再び有効にするには、Windows PowerShell を開いて、次を行います。**
  
```
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

- Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。 Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>関連トピック
[Skype for Business Online のセットアップ](set-up-skype-for-business-online.md)

[Skype for Business ユーザーが Skype の連絡先を追加できるようにする](let-skype-for-business-users-add-skype-contacts.md)

  
 

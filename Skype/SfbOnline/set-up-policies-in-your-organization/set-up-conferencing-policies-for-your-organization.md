---
title: 組織の電話会議ポリシーをセットアップする
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
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
description: 電話会議は Skype for Business Online の重要な部分です。電話会議により、ユーザーのグループがオンラインで一緒にスライドやビデオを表示したり、アプリケーションを共有したり、ファイルをやり取りしたり、連絡を取り合って共同作業することができるようになります。
ms.openlocfilehash: 84037d571bf6f9dc3451793678a6d1b650492bd9
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240079"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a>組織の電話会議ポリシーをセットアップする

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

[] 電話会議は Skype for Business Online の重要な部分です。電話会議により、ユーザーのグループがオンラインで一緒にスライドやビデオを表示したり、アプリケーションを共有したり、ファイルをやり取りしたり、連絡を取り合って共同作業することができるようになります。
  
電話会議および電話会議の設定を制御できる状態を維持することが重要です。場合によって、セキュリティに関する問題があるかもしれません。既定では、未認証のユーザーを含むあらゆるユーザーが会議に参加でき、その会議中に配布されたスライドや資料を保存することができます。さらに、時には法的な問題が発生することもあります。たとえば、既定では会議の参加者は共有コンテンツに注釈を付けることができますが、それらの注釈は会議がアーカイブされるときに保存されません。所属する組織ですべての電子的な通信の記録を保持する必要がある場合は、注釈を無効にする方が良い可能性があります。 
  
Skype for Business Online では、電話会議は電話会議ポリシーを使用して管理されます。電話会議ポリシーにより、電話会議に IP オーディオまたはビデオを含めることができるかということから、会議に出席できるユーザーの最大数についてまで、あらゆる点を含む電話会議で使用できる機能が決まります。電話会議ポリシーは全体的な範囲またはユーザーごとの範囲で構成できます。これにより、管理者は、どの機能をどのユーザーが利用できるようにするかを決めるときに、最大の柔軟性を発揮できます。
  
ポリシー設定はポリシーが作成されるときに構成できます。また、 **Set-CsConferencingPolicy** コマンドレットを使用して既存のポリシーの設定を変更できます。
  
## <a name="set-your-conferencing-policies"></a>電話会議ポリシーを設定する

> [!NOTE]
> Skype for Business Online のすべての電話会議ポリシー設定では、Windows PowerShell を使用する必要があります。 **Skype for Business 管理センター** を **使用することはできません**。 

### <a name="start-windows-powershell"></a>スタートWindows PowerShell

 > [!Note]
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
      
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a>会議中のファイル転送およびデスクトップ共有を禁止する

- これらの設定のために新しいポリシーを作成するには、次を実行します。
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   [New-CsConferencingPolicy コマンドレットの詳細を参照](/powershell/module/skype/New-CsConferencingPolicy)してください。
    
- 作成した新しいポリシーを組織内のすべてのユーザーに付与します。次を実行します。
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   [詳細については、Grant-CsConferencingPolicy コマンドレットを参照](/powershell/module/skype/Grant-CsConferencingPolicy)してください。
    
  ポリシーを作成済みの場合は、[Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) コマンドレットを使用して、既存のポリシーに対する変更を行います。次に、[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) コマンドレットを使用して設定をユーザーに適用します。
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a>電話会議のレコーディングを禁止し、匿名ユーザーの会議参加者を防止する

- これらの設定のために新しいポリシーを作成するには、次を実行します。 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   [New-CsConferencingPolicy コマンドレットの詳細を参照](/powershell/module/skype/New-CsConferencingPolicy)してください。
    
- Amos Marble に作成した新しいポリシーを付与するには、次を実行します。
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   [詳細については、Grant-CsConferencingPolicy コマンドレットを参照](/powershell/module/skype/Grant-CsConferencingPolicy)してください。
    
ポリシーを既に作成している場合は [、Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) コマンドレットを使用して既存のポリシーを変更し [、Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) コマンドレットを使用して設定をユーザーに適用できます。
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a>匿名ユーザーの参加者による会議のレコーディングと、追加ユーザーによる会議の内容の保存を禁止する

- これらの設定のために新しいポリシーを作成するには、次を実行します。  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   [New-CsConferencingPolicy コマンドレットの詳細を参照](/powershell/module/skype/New-CsConferencingPolicy)してください。
    
- 作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

[詳細については、Grant-CsConferencingPolicy コマンドレットを参照](/powershell/module/skype/Grant-CsConferencingPolicy)してください。
    
ポリシーを作成済みの場合は、[Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) コマンドレットを使用して、既存のポリシーに対する変更を行います。次に、[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) コマンドレットを使用して設定をユーザーに適用します。
  
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

[組織のクライアント ポリシーをセットアップする](set-up-client-policies-for-your-organization.md)

  

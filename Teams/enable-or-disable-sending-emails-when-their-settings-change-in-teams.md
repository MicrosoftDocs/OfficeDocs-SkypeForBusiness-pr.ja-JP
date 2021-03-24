---
title: 電話会議の設定が変更された場合のメール オプション
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'ピン留めなどの設定や Microsoft Teams の既定の会議番号の変更時に、Skype がユーザーにメールを送信する機能を有効または無効にする方法について説明します。 '
ms.openlocfilehash: e1bb6df0a443f01ed3c9bc70d03eedc05f217ce4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092705"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Microsoft Teams で電話会議の設定が変更されたときのメールの自動送信を有効または無効にする

電話会議が有効になると、ユーザーにメールで自動的に通知されます。 ただし、Microsoft Teams ユーザーに送信されるメールの数を減らしたい場合があります。 このような場合は、メールの送信を無効にできます。
  
メールの送信を無効にした場合、ユーザーが電話会議で有効または無効になっている場合、PIN がリセットされた場合、会議 ID と既定の会議の電話番号が変更された場合のメールなど、電話会議のメールはユーザーに送信されません。
  
電話会議が有効になっているユーザーに送信されるメールの例を次に示します。
  
![電話会議のメール メッセージの例](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>メールがユーザーに送信されるのは、いつですか?

- 電話会議を有効にすると、組織内のユーザーに送信されるメールが複数あります。
    
  - **電話会議** のライセンスがユーザーに割り当てられた場合。
    
  - ユーザーの電話会議の PIN を手動でリセットする場合。
    
  - ユーザーの会議 ID を手動でリセットした場合。
    
  - 電話会議 **ライセンスが** 削除された場合。
    
  - ユーザーの電話会議プロバイダーが Microsoft から別のプロバイダーまたはなしに変更 **された場合**。
    
  - ユーザーの電話会議プロバイダーが Microsoft に変更された場合。


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>メールがユーザーに送信されるのを有効または無効にする

Microsoft Teams またはメール アカウントをWindows PowerShell、ユーザーに送信されたメールを有効または無効にできます。

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。 

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。 

3. [**ブリッジの設定**] ペインで、[**ダイヤルイン設定が変わると、ユーザーに自動的に電子メールが送信されます**] を有効または無効にします。

4. **[保存]** をクリックします。

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Windows PowerShell を使用する**
  
詳細については、[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)をご覧ください。

    
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。 Windows PowerShell では、単一の管理ポイントを使用して Microsoft 365 または Office 365 を管理できます。複数のタスクを実行する必要がある場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](/previous-versions//dn568025(v=technet.10))
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。
    
  
## <a name="related-topics"></a>関連トピック

[ユーザーの電話会議の設定が変更された場合にユーザーに送信されるメール](emails-sent-to-users-when-their-settings-change-in-teams.md)

[電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
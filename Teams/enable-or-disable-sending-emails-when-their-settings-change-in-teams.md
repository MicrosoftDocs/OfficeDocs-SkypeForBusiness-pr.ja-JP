---
title: Microsoft Teams で電話会議の設定が変更されたときのメールの自動送信を有効または無効にする
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
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Pin が変更された場合や、Microsoft Teams で既定の電話会議番号が変更された場合に、Skype が電子メールをユーザーに送信するのを有効または無効にする方法について説明します。 '
ms.openlocfilehash: e156d9eddead680879f80ef4e50695e9fb41c39d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41696162"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Microsoft Teams で電話会議の設定が変更されたときのメールの自動送信を有効または無効にする

電話会議が有効になっていると、ユーザーにメールで自動的に通知されます。 ただし、Microsoft Teams ユーザーに送信されるメールの数を少なくする必要がある場合もあります。 その場合は、メールの送信を無効にすることができます。
  
メールの送信を無効にした場合、電話会議のメールはユーザーに送信されません。電話会議でユーザーが有効または無効になっているとき、電話会議の PIN がリセットされたとき、会議 ID と既定の会議の電話番号が変更されたときのメールが含まれます。.
  
次に示すのは、電話会議が有効になっているユーザーに送信されるメールの例です。
  
![電話会議のメールメッセージの例](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>ユーザーにメールが送信されるのはいつですか?

- 電話会議を有効にした後、組織内のユーザーに送信されるメールが複数あります。
    
  - **電話会議** のライセンスがユーザーに割り当てられた場合。
    
  - ユーザーの電話会議の PIN を手動でリセットした場合。
    
  - ユーザーの会議 ID を手動でリセットした場合。
    
  - **電話会議**ライセンスが削除されたとき。
    
  - ユーザーの電話会議プロバイダーが Microsoft から別のプロバイダーまたは **[なし**] に変更された場合。
    
  - ユーザーの電話会議プロバイダーが Microsoft に変更された場合。


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>ユーザーへのメール送信を有効または無効にする

Microsoft Teams または Windows PowerShell を使用して、ユーザーに送信されたメールを有効または無効にすることができます。

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。 

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。 

3. [**ブリッジの設定**] ペインで、[**ダイヤルイン設定が変わると、ユーザーに自動的に電子メールが送信されます**] を有効または無効にします。

4. **[保存]** をクリックします。

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Windows PowerShell を使用する**
  
詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。

    
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。
    
  
## <a name="related-topics"></a>関連トピック

[電話会議の設定が変更されたときにユーザーに送信されるメール](emails-sent-to-users-when-their-settings-change-in-teams.md)

[電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)



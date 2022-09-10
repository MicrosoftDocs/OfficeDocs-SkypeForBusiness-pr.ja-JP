---
title: 電話会議の設定が変更されたときにオプションをEmailする
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'ピンの変更や Teams の既定の会議番号の変更などの設定がユーザーに送信されないように Microsoft Teams を有効または無効にする方法について説明します。 '
ms.openlocfilehash: a5119d6f612ed083ac4e72ab52f6bb189af4c9d1
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642108"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Microsoft Teams で電話会議の設定が変更されたときのメールの自動送信を有効または無効にする

ユーザーは、電話会議が有効になると、電子メールで自動的に通知されます。 ただし、Microsoft Teams ユーザーに送信されるメールの数を減らしたい場合があります。 このような場合は、電子メールの送信を無効にすることができます。
  
電子メールの送信を無効にした場合、電話会議の電子メールは、ユーザーが電話会議に対して有効または無効になっている場合、PIN がリセットされたとき、会議 ID と既定の会議電話番号が変更されたときなどの電子メールを含め、ユーザーに送信されません。
  
電話会議が有効になっているユーザーに送信される電子メールの例を次に示します。
  
![電話会議の電子メール メッセージの例。](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>電子メールがユーザーに送信されるのはいつですか?

- 電話会議を有効にした後、組織内のユーザーに送信される電子メールがいくつかあります。

  - **電話会議** のライセンスがユーザーに割り当てられた場合。

  - ユーザーの電話会議 PIN を手動でリセットする場合。

  - ユーザーの会議 ID を手動でリセットした場合。

  - **電話会議** ライセンスが削除されたとき。

  - ユーザーの電話会議プロバイダーが Microsoft から別のプロバイダーまたは **None** に変更されたとき。

  - ユーザーの電話会議プロバイダーが Microsoft に変更されたとき。

## <a name="enable-or-disable-email-from-being-sent-to-users"></a>電子メールがユーザーに送信されないように有効または無効にする

Microsoft Teams またはWindows PowerShellを使用して、ユーザーに送信される電子メールを有効または無効にすることができます。

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。

3. [**ブリッジの設定**] ペインで、[**ダイヤルイン設定が変わると、ユーザーに自動的に電子メールが送信されます**] を有効または無効にします。

4. **[保存]** をクリックします。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

### <a name="using-windows-powershell"></a>Windows PowerShell の使用

Microsoft Teams PowerShell モジュールを使用して、次を実行することもできます。

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

Windows PowerShell を使用して、次を実行することもできます。[](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings)

詳細については、[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)をご覧ください。

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあります。Windows PowerShell があれば、一元管理を使用して Microsoft 365 または Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。

- [Office 365 PowerShell を使用する必要がある理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Windows PowerShell で Office 365 を管理するための最善の方法](/previous-versions//dn568025(v=technet.10))

Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。

## <a name="related-topics"></a>関連トピック

[電話会議の設定が変更されたときにユーザーに送信される電子メール](emails-sent-to-users-when-their-settings-change-in-teams.md)

[電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)

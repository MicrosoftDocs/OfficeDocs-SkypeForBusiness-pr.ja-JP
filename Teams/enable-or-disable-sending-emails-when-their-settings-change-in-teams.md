---
title: 電話会議の設定が変更された場合のメール オプション
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
description: 'ピン留めなどの設定が変更された場合やSkypeの会議番号が変更された場合に、ユーザーにメールを送信するメールを有効または無効にする方法について説明Microsoft Teams。 '
ms.openlocfilehash: 568a42badd375314ee5b29529a53b52b1f6267eb
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055297"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Microsoft Teams で電話会議の設定が変更されたときのメールの自動送信を有効または無効にする

電話会議が有効になると、ユーザーにメールで自動的に通知されます。 ただし、ユーザーに送信されるメールの数を減らしたい場合Microsoft Teamsがあります。 このような場合は、メールの送信を無効にできます。
  
メールの送信を無効にした場合、電話会議メールはユーザーに送信されません。たとえば、ユーザーが電話会議を有効または無効にした場合、PIN がリセットされた場合、電話会議 ID と既定の会議電話番号が変更された場合のメールが含されます。
  
電話会議が有効になっているユーザーに送信されるメールの例を次に示します。
  
![電話会議の電子メール メッセージの例。](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>メールがユーザーに送信されるのは、いつですか?

- 電話会議を有効にした後、組織内のユーザーに送信されるメールは複数あります。

  - **電話会議** のライセンスがユーザーに割り当てられた場合。

  - ユーザーの電話会議 PIN を手動でリセットする場合。

  - ユーザーの会議 ID を手動でリセットした場合。

  - 電話会議 **ライセンスが** 削除された場合。

  - ユーザーの電話会議プロバイダーが Microsoft から別のプロバイダーまたはなし に変更 **された場合**。

  - ユーザーの電話会議プロバイダーが Microsoft に変更された場合。

## <a name="enable-or-disable-email-from-being-sent-to-users"></a>メールがユーザーに送信されるのを有効または無効にする

ユーザーに送信Microsoft TeamsまたはWindows PowerShellを使用して有効または無効にできます。

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。

3. [**ブリッジの設定**] ペインで、[**ダイヤルイン設定が変わると、ユーザーに自動的に電子メールが送信されます**] を有効または無効にします。

4. **[保存]** をクリックします。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

### <a name="using-windows-powershell"></a>Windows PowerShell の使用

PowerShell モジュールの Microsoft Teamsを使用して、次のコマンドを実行できます。

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

Windows PowerShell を使用して、次を実行することもできます。[](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings)

詳細については、[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)をご覧ください。

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作に関するすべてです。 このWindows PowerShell、単一の管理ポイントを使用して Microsoft 365 または Office 365 を管理し、複数のタスクを実行する場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

- [Windows PowerShell で Office 365 を管理するための最善の方法](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Windows PowerShell で Office 365 を管理するための最善の方法](/previous-versions//dn568025(v=technet.10))

Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。

## <a name="related-topics"></a>関連トピック

[電話会議の設定が変更された場合にユーザーに送信されるメール](emails-sent-to-users-when-their-settings-change-in-teams.md)

[電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)

---
title: Teamsで PIN なしで電話で電話会議を開始する
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
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
description: '匿名の発信者がTeams管理センターから会議に参加できないようにする方法について説明します。 '
ms.openlocfilehash: 2937ebc2c8ddec830c6eb130fc5824ed8273a9d3
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055707"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Microsoft Teams で PIN を使用せずに電話で電話会議を開始する

Microsoft Teams会議の開催者が会議を開始していないため、会議にダイヤルインしたユーザーが会議のロビーで音楽を聴いて開催されるのは、イライラする場合があります。
  
会議の開催者が会議に呼び出す場合、既定では、会議を開始するために PIN が必要です。 誰もが会議にダイヤルインでき、会議を開始するための PIN の入力を求めないように設定できます。 管理センターを使用して、1 人のユーザーに対してこの設定を有効または無効にすることができます。
  
他のユーザーがMicrosoft Teams アプリから会議を開始した場合、会議の開催者には PIN は必要ありません。 PIN が必要であるのは、会議の開催者が電話で自分の会議に参加する場合のみです。 会議の PIN は、電話会議ライセンスが割り当てられ、電話会議が有効になっているときに、 **オーディオ** ユーザーに送信されます。 [電話会議の設定が変更されたときに自動的にユーザーに送信される電話会議情報](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)と[電子メールをユーザーに送信する方法に関するページを](emails-sent-to-users-when-their-settings-change-in-teams.md)参照してください。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>匿名の発信者の会議への参加を有効または無効にする

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. 左側のナビゲーションで、[ **ユーザー**] をクリックします。

2. 一覧でユーザーを選択し、ページの上部にある **[編集]** をクリックします。

3. [**電話会議**] の横の [**編集**] をクリックします。

4. **[電話会議**] ウィンドウ **で、ダイヤルインの呼び出し元を有効または無効にして、会議の最初のユーザーにすることができます**。

5. [**適用**] をクリックします。

### <a name="using-windows-powershell"></a>Windows PowerShell の使用

詳細については、[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)をご覧ください。

## <a name="what-else-should-you-know"></a>その他の情報

- PIN をリセットする場合は、「 [電話会議 PIN をリセットする」](reset-the-audio-conferencing-pin-in-teams.md)を参照してください。

- 匿名アクセスが無効になっている場合、または会議を開始するために PIN を必要としない場合:

  - 会議が開始されていない (会議にまだ誰もいない) 場合は、発信者が開催者である場合は、呼び出し元にメッセージが表示されます。"はい" と言うと、PIN の入力を求められます。PIN を入力すると、会議が開始され、ユーザーは会議に参加します。

  - 会議が既に開始されている (他のユーザーが既に会議に参加している場合): 発信者が開催者であり、PIN の入力を求められることはありません。会議は既に開始されており、呼び出し元は会議に参加します。

- 匿名アクセスが有効になっている場合、または会議を開始するために PIN を必要としない場合は、次のようになります。

  - 会議が開始されていない (会議に誰も参加していない) 場合は、発信者が開催者の場合はメッセージが表示されません。PIN の入力を求めるメッセージは表示されません。 開催者の設定がオフになっているため、会議が始まり、匿名の発信者が会議に参加します。

  - 会議が既に開始されている (他のユーザーが既に会議に参加している) 場合、発信者は開催者の場合はメッセージが表示されません。PIN の入力を求めるメッセージは表示されません。会議は既に開始されており、呼び出し元は会議に参加します。

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShellはすべて、ユーザーの管理と、ユーザーの許可または許可されていない操作です。 Windows PowerShellを使用すると、1 つの管理ポイントを使用してMicrosoft 365またはOffice 365を管理できます。複数のタスクがある場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

- [Windows PowerShell で Office 365 を管理するための最善の方法](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Windows PowerShell で Microsoft 365 または Office 365 を管理するための最善の方法](/previous-versions//dn568025(v=technet.10))

Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。
  
## <a name="related-topics"></a>関連トピック

[Microsoft 365またはOffice 365での電話会議の試用または購入](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

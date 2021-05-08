---
title: 電話で電話会議を開始し、PIN を使わずに電話会議を開始Teams
ms.author: tonysmit
author: tonysmit
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: '管理者センターから匿名の発信者が会議に参加Teams方法について学習します。 '
ms.openlocfilehash: 520bf720a01a686a103748cdbbf26cb8426e94f2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116965"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Microsoft Teams で PIN を使用せずに電話で電話会議を開始する

Microsoft Teams 会議の開催者が会議を開始しないので、会議にダイヤルインしたユーザーが音楽を聴いて会議のロビーで開催されるのは、いら立つ場合があります。 
  
会議の開催者が会議にコールインする場合、既定では、会議を開始するために PIN が必要です。 誰でも会議にダイヤルインし、PIN で会議を開始するように求めららなく設定できます。 管理センターを使用して、1 人のユーザーに対してこの設定を有効または無効にできます。
  
他のユーザーが会議アプリから会議を開始した場合、会議の開催者に PIN はMicrosoft Teamsではありません。 PIN が必要であるのは、会議の開催者が電話で自分の会議に参加する場合のみです。 会議の PIN は、電話会議ライセンスが割り当て済みで電話会議が有効になると、音声ユーザーに送信されます。 「 [電話会議の設定が変](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) わると自動的にユーザーに送信される電話会議情報とメールをユーザーに送信する [」を参照してください](emails-sent-to-users-when-their-settings-change-in-teams.md)。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>匿名の発信者の会議への参加を有効または無効にする

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

1. 左側のナビゲーションで、[ユーザー] を **クリックします**。 

2. 一覧でユーザーを選択し、ページの上部にある **[編集** ] をクリックします。 

3. [**電話会議**] の横の [**編集**] をクリックします。

4. [電話 **会議] ウィンドウで**、ダイヤルイン発信者を有効または無効に **できます。**
    
4. [**適用**] をクリックします。 

**Windows PowerShell を使用する**
  
詳細については、[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)をご覧ください。

## <a name="what-else-should-you-know"></a>その他の情報

- PIN をリセットする場合は、「電話会議 PIN をリセット [する」を参照してください](reset-the-audio-conferencing-pin-in-teams.md)。
    
- 匿名アクセス (会議を開始するために PIN を必要としない) が無効になっている場合:
    
  - 会議が開始されていない場合 (会議にまだ誰もいない場合): 開催者の場合、発信者にメッセージが表示されます。「はい」と言った場合は、PIN の入力を求めるメッセージが表示され、PIN を入力すると、会議が開始され、ユーザーが会議に参加します。
    
  - 会議が既に開始されている場合 (他のユーザーが既に会議に参加している場合): 発信者に開催者の場合はメッセージが表示されません。PIN の入力を求めるメッセージは表示されません。会議が既に開始され、呼び出し元が会議に参加します。
    
- 匿名アクセス (会議を開始するために PIN を必要としない) が有効になっている場合:
    
  - 会議が開始されていない場合 (まだ会議に誰もいない場合): 発信者に開催者の場合はメッセージが表示されません。PIN の入力を求めるメッセージは表示されません。 開催者の設定がオフになっているため、会議が始まり、匿名の発信者が会議に参加します。
    
  - 会議が既に開始されている場合 (他のユーザーが既に会議に参加している場合):発信者に開催者の場合はメッセージが表示されません。PIN の入力を求めるメッセージは表示されません。会議は既に開始され、発信者はその会議に参加します。
    
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。 このWindows PowerShell、1 つの管理Microsoft 365または Office 365 を管理し、複数のタスクを実行する場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。
  
## <a name="related-topics"></a>関連トピック

[電話会議を試用または購入するには、Microsoft 365またはOffice 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
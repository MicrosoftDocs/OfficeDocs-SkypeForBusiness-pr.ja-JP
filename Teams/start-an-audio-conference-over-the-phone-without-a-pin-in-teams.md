---
title: チームで PIN を使用せずに電話で音声会議を開始する
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
description: 'チーム管理センターから、匿名の発信者が会議に参加することを有効または無効にする方法について説明します。 '
ms.openlocfilehash: e6e3244a3b2135023d80b9b0df925cc5293244f6
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140830"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Microsoft Teams で PIN を使用せずに電話で電話会議を開始する

Microsoft Teams の会議の開催者が会議を開始していないために、会議にダイヤルインして音楽のロビーを待っているユーザーにとっては、ユーザーにとっては不快な場合があります。 
  
会議の開催者が会議にコールインする場合、既定では、会議を開始するために PIN が必要になります。 すべてのユーザーが会議にダイヤルインできるように設定することができます。また、会議を開始するために PIN の入力を求められることはありません。 管理センターを使用して、1人のユーザーに対してこの設定を有効または無効にすることができます。
  
他のユーザーが Microsoft Teams アプリから会議を開始した場合、会議の開催者は PIN を指定する必要はありません。 PIN が必要であるのは、会議の開催者が電話で自分の会議に参加する場合のみです。 会議の PIN は、電話**会議**ライセンスが割り当てられており、電話会議用に有効になっている場合に、音声ユーザーに送信されます。 「電話会議の[設定が変更されたときにユーザーに自動的に送信される](emails-sent-to-users-when-their-settings-change-in-teams.md)[電話会議情報とメールをユーザーに送信](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)する」を参照してください。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>匿名の発信者の会議への参加を有効または無効にする

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**

1. 左側のナビゲーションで [**ユーザー**] をクリックします。 

2. リストでユーザーを選択し、ページの上部にある [**編集**] をクリックします。 

3. [**電話会議**] の横の [**編集**] をクリックします。

4. [**電話会議**] ウィンドウで、ダイヤルインの発信者を有効または無効にするには、**会議の最初の人になることができ**ます。
    
4. [**適用**] をクリックします。 

**Windows PowerShell を使用する**
  
詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。

## <a name="what-else-should-you-know"></a>その他の情報

- PIN をリセットする場合は、「[電話会議の pin をリセット](reset-the-audio-conferencing-pin-in-teams.md)する」を参照してください。
    
- 匿名アクセスが許可されている場合、または会議の開始に PIN が必要な場合は無効になります。
    
  - 会議が開始されていない (会議にまだ参加していない) 場合: 発信者が開催者であるかどうかを確認するメッセージが表示されます。「はい」というメッセージが表示されると、PIN の入力が求められます。 PIN を入力すると、会議が開始され、ユーザーが会議に参加します。
    
  - 会議が既に始まっている場合 (他のユーザーが既に会議に参加している場合): 発信者は開催者であるかどうかを確認するメッセージは表示されず、PIN の入力を求められることはありません。会議が既に始まっていて、発信者が会議に参加します。
    
- 匿名アクセスが許可されている場合、または会議の開始に PIN が必要ではない場合は、次の操作を行います。
    
  - 会議が開始されていない (会議にまだ参加していない) 場合: 発信者が開催者であるかどうかを確認するメッセージは表示されません。 PIN の入力を求められることはありません。 開催者の設定がオフになっているため、会議が始まり、匿名の発信者が会議に参加します。
    
  - 会議が既に開始されている場合 (他のユーザーが既に会議に参加している場合): 発信者であるかどうかを確認するメッセージは表示されません。会議は既に始まっていて、発信者はその会議に参加します。
    
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。
  
## <a name="related-topics"></a>関連項目

[Office 365 での電話会議を試用または購入する](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

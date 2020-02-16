---
title: Skype for Business Online のユーザーの会議 ID をリセットする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Skype for Business Online でユーザーの会議 ID をリセットし、会議の更新と移行ツールへのリンクを取得する手順について説明します。 '
ms.openlocfilehash: 9a1c2766da021d30feb14954d6e69b6978b64bc9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "41986492"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a>Skype for Business Online のユーザーの会議 ID をリセットする

> [!NOTE]
> Microsoft Teams で会議 ID をリセットする方法の詳細については、「 [Microsoft Teams でユーザーの会議 ID をリセットする](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams)」を参照してください。

動的な会議 ID は、発信者が会議にコールインするのに使用できるダイヤルイン番号と一緒に、会議出席依頼の下に含まれています。 ユーザーが電話番号をダイヤルするときに、発信者が会議に参加できるように、会議の自動応答は発信者にこの会議 ID の入力を求めます。
  
> [!NOTE]
> 会議プロバイダーが Microsoft の場合、ユーザーの会議 Id は [動的限定] に設定されます。 これは変更できません。 会議 ID は、電話会議が有効にされる Skype for Business ユーザーにのみ自動的に設定されます。 

## <a name="resetting-the-conference-id-for-a-user"></a>ユーザーの会議 ID をリセットする
   
1. **Skype for business 管理センター**で、[電話**会議** > **ユーザー**] をクリックし、ユーザーを選択して、操作ウィンドウの [**電話会議 ID** ] で [**リセット**] をクリックします。
    
2. [**会議 ID をリセットしますか?** ] ウィンドウで、[**はい**] をクリックします。 A conference ID will be automatically created and an email sent to the user with the new conference ID. 既定では、メールはユーザーに送信されますが、無効にすることもできます。
    
> [!NOTE]
> 会議 ID をリセットすると、新しい会議 ID を記載したメールがユーザーに送信されます。このメールはプライマリ メール アドレスに送信されます。ほとんどの場合は、Office 365 のメールボックスに送信されます。新しい会議 ID、既定のダイヤルイン電話番号、Skype for Business Meeting Update Tool を使って既存の会議を更新する方法がメールに記載されています。 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>他に必要な情報はありますか?

- 操作ウィンドウで [電話会議**情報をメールで送信**] をクリックすると、会議 ID、ダイヤルイン電話番号などのすべての会議情報をメールでユーザーに送信できます。 PIN は送信されません。
    
- 会議 ID には7桁の値が含まれ、Skype for Business 管理センターまたは Windows PowerShell を使用して、その長さを変更することはできません。
    
- 会議 ID をリセットすると、新しい会議 ID が [ **電話会議 ID**] に一覧表示されます。
    
- 電話会議用のユーザーの会議 ID は、[**ユーザー** ] ページでユーザーを選ぶと、操作ウィンドウの下部にある [電話**会議**] の下に表示されます。
    
- 新しい会議 ID が作成されると、古い会議 ID を使用してダイヤルインすることはできなくなります。 既存の会議の出席依頼のスケジュールを変更して、新しい会議 ID を出席依頼に追加するように、ユーザーに通知してください。 ユーザーは Skype for Business 会議ツールを使って、既存の会議を更新することができます。 Skype for Business 会議更新ツールのダウンロード、インストール、実行の方法については、以下を参照してください。
    
  - [Skype for Business Meeting Update Tool と Lync Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype for Business Online、会議移行ツール (64 ビット)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype for Business Online、会議移行ツール (32 ビット)](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、多くのユーザーについて同時に設定を変更する場合など、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を高めることができます。 次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>関連トピック

[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin.md)

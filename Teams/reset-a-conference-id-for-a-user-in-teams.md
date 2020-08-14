---
title: Microsoft Teams でユーザーの会議 ID をリセットする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: Microsoft Teams でユーザーの会議 ID をリセットし、会議の更新と移行ツールへのリンクを取得する手順について説明します。
ms.openlocfilehash: 52b547fee5bf027bcef21914e3ba3aa79b0e4e08
ms.sourcegitcommit: 7a9c63ee790108eaa61950ce28ae8027311039d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662127"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Microsoft Teams でユーザーの会議 ID をリセットする

動的な会議 ID は、発信者が会議にコールインするのに使用できるダイヤルイン番号と一緒に、会議出席依頼の下に含まれています。 ユーザーが電話番号をダイヤルするときに、発信者が会議に参加できるように、会議の自動応答は発信者にこの会議 ID の入力を求めます。
  
> [!NOTE]
> 会議 Id は自動的に生成され、7-9 桁の数字と、ユーザーの電話会議を有効にしたときに設定されます。 **静的な会議 Id はサポートされません。** 

## <a name="resetting-the-conference-id-for-a-user"></a>ユーザーの会議 ID をリセットする

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. [ **編集**] をクリックします。

3. [電話 **会議** ] の [ **会議 ID のリセット**] をクリックします。

2. [ **電話会議 ID のリセット** ] ウィンドウで、[ **リセット**] をクリックします。 A conference ID will be automatically created and an email sent to the user with the new conference ID. 既定では、メールはユーザーに送信されますが、無効にすることもできます。   

    
> [!NOTE]
> 会議 ID をリセットすると、新しい会議 ID を含むメールがユーザーに送信されます。 このメールは、プライマリメールアドレス (多くの場合、Microsoft 365 または Office 365 メールボックス) に送信されます。 このメールには、新しい会議 ID、既定のダイヤルイン電話番号、および既存の会議を更新するための手順が含まれています。 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>他に必要な情報はありますか?

- 電話会議**のセクションで**、[電話会議情報を**メールで送信**する] をクリックすると、会議 ID、ダイヤルイン電話番号など、会議のすべての情報をメールでユーザーに送信できます。 PIN は送信されません。
    
- 7-9 桁の会議 ID は、Teams サービスによって作成されます。 この長さを変更することはできません。
    
- 会議 ID をリセットすると、新しい会議 ID が [ **電話会議 ID**] に一覧表示されます。
    
- 新しい会議 ID が作成されると、古い会議 ID を使用してダイヤルインすることはできなくなります。 既存の会議の出席依頼のスケジュールを変更して、新しい会議 ID を出席依頼に追加するように、ユーザーに通知してください。 

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。 Windows PowerShell を使用すると、複数のタスクがある場合に、1つの管理ポイントを使用して Microsoft 365 または Office 365 を管理し、日常業務を簡素化することができます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell を使用して Microsoft 365 または Office 365 を管理するのに最適な方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。
    
## <a name="related-topics"></a>関連トピック

[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin-in-teams.md)

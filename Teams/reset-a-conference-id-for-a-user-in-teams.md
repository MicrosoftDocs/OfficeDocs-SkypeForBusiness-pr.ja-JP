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
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Microsoft Teams でユーザーの会議 ID をリセットし、会議の更新と移行ツールへのリンクを取得する手順について説明します。 '
ms.openlocfilehash: 894761811bfc9c353c7a145c83c7a201a587f1e2
ms.sourcegitcommit: 15fe483079847d24869e325eead35f252da8c7dd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "37568369"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Microsoft Teams でユーザーの会議 ID をリセットする

動的な会議 ID は、発信者が会議にコールインするのに使用できるダイヤルイン番号と一緒に、会議出席依頼の下に含まれています。 ユーザーが電話番号をダイヤルするときに、発信者が会議に参加できるように、会議の自動応答は発信者にこの会議 ID の入力を求めます。
  
> [!NOTE]
> 会議プロバイダーが Microsoft の場合、ユーザーの会議 ID がデフォルトで「動的のみ」に設定されます。 残念ながら、これはサポートされていないため、静的になるように変更することはできません。 電話会議 Id は、電話会議用に有効になっている Microsoft Teams ユーザーに対してのみ自動的に設定されます。 


## <a name="resetting-the-conference-id-for-a-user"></a>ユーザーの会議 ID をリセットする

![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. [**編集**] をクリックします。

3. [電話**会議**] の [**会議 ID のリセット**] をクリックします。

2. [**電話会議 ID のリセット**] ウィンドウで、[**リセット**] をクリックします。 A conference ID will be automatically created and an email sent to the user with the new conference ID. 既定では、メールはユーザーに送信されますが、無効にすることもできます。   

    
> [!NOTE]
> 会議 ID をリセットすると、新しい会議 ID を含むメールがユーザーに送信されます。 このメールは、プライマリメールアドレス (多くの場合、Office 365 メールボックス) に送信されます。 このメールには、新しい会議 ID、既定のダイヤルイン電話番号、および既存の会議を更新するための手順が含まれています。 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>他に必要な情報はありますか?

- 電話会議**のセクションで**、[電話会議情報を**メールで送信**する] をクリックすると、会議 ID、ダイヤルイン電話番号など、会議のすべての情報をメールでユーザーに送信できます。 PIN は送信されません。
    
- 会議 ID には7桁の数字が含まれ、その長さを変更することはできません。
    
- 会議 ID をリセットすると、新しい会議 ID が [ **電話会議 ID**] に一覧表示されます。
    
- 新しい会議 ID が作成されると、古い会議 ID を使用してダイヤルインすることはできなくなります。 既存の会議の出席依頼のスケジュールを変更して、新しい会議 ID を出席依頼に追加するように、ユーザーに通知してください。 

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。
    
## <a name="related-topics"></a>関連トピック

[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin-in-teams.md)

---
title: 招待状に含まれている電話番号を設定する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
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
description: Microsoft Teams 会議に参加するための既定の電話番号を作成するには、次の手順に従います。
ms.openlocfilehash: 7dd59950403543074d8428d35270ab963ca824e3
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372186"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Microsfot Teams で招待状に含まれている電話番号を設定する

Microsoft 365 および Office 365 の電話会議では、組織内のユーザーが Microsoft Teams 会議を作成できるようになり、電話を使用してこれらの会議にダイヤルインすることができます。
  
会議ブリッジは、組織用のダイヤルイン電話番号のセットを提供します。これらの番号はすべて会議開催者が作成した会議に参加するために使用できますが、会議出席依頼にどの番号を含めるか選ぶことができます。
  
> [!NOTE]
> 会議主催者の会議出席依頼には、1 つの有料電話番号と 1 つの無料電話番号を含めることができますが、会議出席依頼の下部に、会議に参加するために使用できるダイヤルイン電話番号のすべての一覧を表示するリンクも記載されています。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a>新規ユーザー向けの会議出席依頼に記載されている電話番号の最初の割り当て

電話会議用に有効になっているユーザーの会議の出席依頼に含まれる電話番号は、既定の電話会議の有料電話番号と、既定の電話会議無料電話番号のユーザー設定によって定義されます。 各設定では、特定のユーザーの会議出席依頼に含まれる有料電話と無料電話番号を指定します。 上で説明したように、各会議出席依頼には、1つの有料電話番号、オプションの無料電話番号、および特定の会議に参加するために使用できるすべてのダイヤルイン電話番号の一覧を表示するリンクが含まれています。

新規ユーザーの場合、電話会議サービスが有効になっている場合、ユーザーの Microsoft 365 管理センターで設定された使用場所に基づいて、既定の会議の有料電話番号が割り当てられます。 電話会議でユーザーの国と一致する有料番号がある場合、その番号はユーザーの既定の有料電話番号として自動的に割り当てられます。 存在しない場合、電話会議ブリッジの既定の有料電話番号として定義された番号は、ユーザーの既定の有料電話番号として割り当てられます。  

電話会議サービスのユーザーを有効にすると、ユーザーの既定の有料電話番号と無料電話番号を初期値からいつでも変更できます。

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>会議の開催者またはユーザーの既定の電話会議の電話番号を設定または変更する

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

これらの変更を行うには、Teams サービス管理者である必要があります。 「[チーム管理者ロールを使用してチームを管理する](https://docs.microsoft.com/microsoftteams/using-admin-roles)」を参照して、「管理者ロールと権限の取得」を参照してください。

1. Microsoft Teams 管理センターにログインします。

2. 左側のナビゲーションで [**ユーザー**] をクリックします。

    ![Microsoft Teams 管理センターでのユーザーの選択を示す](media/Admin-users.png)

3. 使用可能なユーザーのリストからユーザー名をクリックします。

4. [**電話会議**] の横の [**編集**] をクリックします。

    ![電話会議の横にある [編集] をクリックする](media/teams-set-phone-numbers-on-invites-image3.png)

5. [**有料**電話番号] または [無料**電話番号**] フィールドを使用して、ユーザーの番号を入力します。

> [!IMPORTANT]
> ユーザーの電話会議の設定を変更すると、定期的な Microsoft Teams の会議を更新して出席者に送信する必要があります。

## <a name="want-to-use-windows-powershell"></a>Windows PowerShell を使用する

Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。 Windows PowerShell を使用すると、複数のタスクがある場合に、1つの管理ポイントを使用して Microsoft 365 または Office 365 を管理し、日常的な作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

- [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)

- [Windows PowerShell を使用して Microsoft 365 または Office 365 を管理するのに最適な方法](https://go.microsoft.com/fwlink/?LinkId=525142)

Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。
  
## <a name="related-topics"></a>関連トピック

[Microsoft 365 または Office 365 で電話会議を試用または購入する](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[電話会議ブリッジの電話番号を変更する](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

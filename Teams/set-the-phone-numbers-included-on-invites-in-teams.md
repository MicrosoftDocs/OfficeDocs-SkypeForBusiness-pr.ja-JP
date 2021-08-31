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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 発信者が会議に参加するための既定の電話番号を作成するには、次のMicrosoft Teamsします。
ms.openlocfilehash: 4c740147e551dade443852a98c5cdafac047815f
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732716"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Microsfot Teams で招待状に含まれている電話番号を設定する

Microsoft 365 と Office 365 の電話会議を使用すると、組織内のユーザーは Microsoft Teams 会議を作成し、ユーザーが電話を使ってそれらの会議にダイヤルインできます。
  
会議ブリッジは、組織用のダイヤルイン電話番号のセットを提供します。これらの番号はすべて会議開催者が作成した会議に参加するために使用できますが、会議出席依頼にどの番号を含めるか選ぶことができます。
  
> [!NOTE]
> 会議主催者の会議出席依頼には、1 つの有料電話番号と 1 つの無料電話番号を含めることができますが、会議出席依頼の下部に、会議に参加するために使用できるダイヤルイン電話番号のすべての一覧を表示するリンクも記載されています。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a>新しいユーザーの会議出席招待に含まれる電話番号の初期割り当て

電話会議が有効になっているユーザーの会議出席招待に含まれる電話番号は、既定の会議の有料電話番号と既定の会議の無料電話番号ユーザーの設定によって定義されます。 各設定では、特定のユーザーの会議出席招待に含める有料電話番号と無料電話番号を指定します。 上で説明したように、各会議出席招待には、1 つの有料電話番号、1 つのオプションの無料電話番号、および特定の会議に参加するために使用できるすべてのダイヤルイン電話番号の完全なリストを開くリンクが含まれている。

新しいユーザーの場合、既定の会議の有料電話番号は、ユーザーが電話会議サービスに対して有効になっているときに、ユーザーの Microsoft 365 管理センターで設定されている [使用場所] に基づいて割り当てられます。 会議ブリッジにユーザーの国と一致する有料電話番号がある場合、その番号はユーザーの既定の有料電話番号として自動的に割り当てられます。 番号が 1 つない場合は、会議ブリッジの既定の有料電話番号として定義されている番号が、ユーザーの既定の有料電話番号として割り当てられます。  

ユーザーが電話会議サービスに対して有効になると、テナント管理者がユーザーの既定の有料電話番号と無料電話番号をいつでも初期値から変更できます。

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>会議の開催者またはユーザーの既定の電話会議電話番号を設定または変更する

![ロゴのアイコンMicrosoft Teams表示されます。](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**

これらの変更を行うには、Teams サービス管理者であることが必要です。 「[Teams 管理者ロールを使用してチームを管理する](./using-admin-roles.md)」をご覧いただき、管理者ロールとアクセス許可を取得する方法について読んでください。

1. 管理センターにMicrosoft Teamsします。

2. 左側のナビゲーションで、[ユーザー] を **クリックします**。

    ![管理センターでユーザーを選択Microsoft Teams表示します。](media/Admin-users.png)

3. 使用可能なユーザーの一覧からユーザー名をクリックします。

4. [**電話会議**] の横の [**編集**] をクリックします。

    ![[電話会議] の横にある [編集] をクリックします。](media/teams-set-phone-numbers-on-invites-image3.png)

5. [有料 **電話番号] フィールドまたは** **[無料電話番号]** フィールドを使用して、ユーザーの番号を入力します。

> [!IMPORTANT]
> ユーザーの電話会議の設定を変更する場合は、定期的な会議とMicrosoft Teams会議を更新して出席者に送信する必要があります。

## <a name="want-to-use-windows-powershell"></a>次のコマンドを使用Windows PowerShell

Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作に関するすべてです。 このWindows PowerShell、1 つの管理ポイントを使用して Microsoft 365 または Office 365 を管理し、複数のタスクを実行する場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

- [Windows PowerShell で Office 365 を管理するための最善の方法](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))

[Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps)を使用して会議開催者またはユーザーの既定の電話会議電話番号を設定または変更するには **`ServiceNumber`** **`TollFreeServiceNumber`** [、Set-CsOnlineDialInConferencingUser](/powershell/module/skype/set-CsOnlineDialInConferencingUser?view=skype-ps)コマンドレットの パラメーターまたは パラメーターを使用可能な番号の 1 つに設定します。

## <a name="related-topics"></a>関連項目

[電話会議を試用または購入するには、Microsoft 365 または Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[電話会議ブリッジの電話番号を変更する](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

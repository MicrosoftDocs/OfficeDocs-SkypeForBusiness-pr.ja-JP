---
title: Microsoft Teams で電話会議の PIN をリセットする
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
- seo-marvel-apr2020
description: Microsoft Teams でユーザーの電話会議 PIN をリセットする方法と、PIN に関する重要な事実について説明します。
ms.openlocfilehash: 51c936580010899355db539a45477afd932fb53d
ms.sourcegitcommit: d3eb876e58c9e4a0a11a21b9292d3a6177508d81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2022
ms.locfileid: "68329031"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Microsoft Teams で電話会議の PIN をリセットする

PIN は、電話会議が有効になっている Microsoft Teams ユーザーごとに作成される番号で構成されたコードです。 電話会議 PIN は、会議の開催者が会議の開催者であることを識別し、電話で会議を開始できるようにするために使用されます。 Microsoft Teams アプリを使用して会議を開始する場合は、PIN は必要ありません。 ユーザーが PIN を忘れ、電話会議を有効にしたときに送信されたメールに見つからない場合、管理者は PIN をリセットするか、自分の PIN をリセットできます。
  
会議は、認証されたユーザーが Microsoft Teams アプリを使用して参加するとき、または開催者が電話で PIN で参加したときに開始できます。 会議を開始するために PIN が必要な場合、電話で参加するユーザーはロビーに配置され、開催者が承認するまで保留の音楽を聞きます。 会議の開催者が、電話で会議を開始するための PIN を要求しない場合、発信者は会議に参加しようとするときに PIN の提示を求められません。

## <a name="reset-a-users-pin"></a>ユーザーの PIN をリセットする

Microsoft Teams 管理センターの使用:

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. [ **編集]** をクリックします。

3. **[電話会議**] の [**PIN のリセット**] をクリックします。

4. [ **リセット**] をクリックします。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="have-a-user-reset-their-own-pin"></a>ユーザーに自分の PIN をリセットさせる

1. ユーザーに移動させます [https://dialin.teams.microsoft.com/usp](https://dialin.teams.microsoft.com/usp)。
2. [ **PIN のリセット] をクリックします**。

> [!NOTE]
> GCCH の場合は、次の手順に進む必要があります [https://dialin.cpc.gov.teams.microsoft.us/usp](https://dialin.cpc.gov.teams.microsoft.us/usp)。
> DoD の場合は次に移動します [https://dialin.cpc.dod.teams.microsoft.us/usp](https://dialin.cpc.dod.teams.microsoft.us/usp)。

> [!NOTE]
> この方法を使用している場合、PIN リセットメールはユーザーに送信されません。

## <a name="what-else-should-you-know-about-pins"></a>PIN について知っておくべきその他のこと

- セキュリティ上の理由から、PIN は、PIN がリセットされたときに管理者に 1 回だけ表示されます。 PIN が管理者によってリセットされると、PIN は *********** として一覧表示されます。

- ユーザーへの電子メールの自動送信は既定で有効になっており、ユーザーは電話会議が有効になっている場合、または PIN がリセットされたときに PIN を含む電子メールを受信します。 ただし、電子メールの自動送信を無効にした場合、PIN リセットメールはユーザーに送信されず、PIN 情報をユーザーに手動で送信する必要があります。

- 会議が開始されると、開催者はロビーのすべての PSTN ユーザーに会議への参加を許可する必要があります。 たとえば、2 人の PSTN 参加者が会議を開始する前に会議に参加しようとすると、ロビーに配置され、保留音が聞こえます。会議の開催者が電話で PIN を使用して参加すると、会議が開始され、開催者は会議内コマンドを使用して (*21 キーを押して) ロビー内のすべての PSTN ユーザーを許可できます。

- 既定の設定では、匿名の呼び出し元による会議の開始を許可しません。

- 電話会議のユーザーを有効にすると、既定では、会議情報とその PIN を含む電子メールが送信されます。 ユーザーは Microsoft 365 または Office 365 メールボックスを持っている必要があります。PIN がリセットされると、ユーザーに設定されているプライマリ SMTP アドレス (エイリアス) に新しい PIN が電子メールでユーザーに送信されるためです。

- 電話会議を設定するときは、組織内の PIN に必要な数字を設定します。 PIN は 4 ~ 12 桁で指定できます。既定値は 5 です。 PIN の長さの設定を変更した場合、この設定は新しく生成された PIN にのみ適用され、電話会議が有効になっている既存のユーザーの PIN 設定には適用されません。 [電話会議会議の PIN の長さを設定する方法に関するページを](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)参照してください。

- 既定では、電子メールは Microsoft 365 またはユーザーのプライマリ SMTP アドレスOffice 365設定されます。 Microsoft 365 以外のアドレス、または Hotmail や MSN メール アドレスなどのOffice 365以外のアドレスに電子メールを送信できます。 Windows PowerShellを使用して、既定の電子メール アドレスをオーバーライドできます。 これは、ユーザーが Microsoft 365 または Office 365に Exchange メールボックスを持っていない場合に便利です。

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShellはすべて、ユーザーの管理と、ユーザーの許可または許可されていない操作です。 Windows PowerShellを使用すると、1 つの管理ポイントを使用して Microsoft 365 またはOffice 365を管理できます。複数のタスクがある場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

- [Windows PowerShell で Office 365 を管理するための最善の方法](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Windows PowerShell で Microsoft 365 または Office 365 を管理するための最善の方法](/previous-versions//dn568025(v=technet.10))

Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。
  
## <a name="related-topics"></a>関連トピック

[ユーザーの会議 ID をリセットする](reset-a-conference-id-for-a-user-in-teams.md)

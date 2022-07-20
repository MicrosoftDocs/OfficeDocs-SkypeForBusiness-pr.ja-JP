---
title: 招待状に含まれている電話番号を設定する
ms.author: heidip
author: MicrosoftHeidi
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
description: 次の手順に従って、発信者が Microsoft Teams 会議に参加するための既定の電話番号を作成します。
ms.openlocfilehash: f0956007d5df72c1fd6c6ae905433e73bd855a56
ms.sourcegitcommit: 312ff79ecab91412918793ec882bfc6e0143d30a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/19/2022
ms.locfileid: "66884846"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Microsfot Teams で招待状に含まれている電話番号を設定する

Microsoft 365 およびOffice 365の電話会議では、組織内のユーザーが Microsoft Teams 会議を作成し、ユーザーが電話番号を使用してそれらの会議にダイヤルインできるようにします。

会議ブリッジは、組織用のダイヤルイン電話番号のセットを提供します。これらの番号はすべて会議開催者が作成した会議に参加するために使用できますが、会議出席依頼にどの番号を含めるか選ぶことができます。

会議開催者の会議出席依頼に含まれる電話番号に加えて、会議への参加に使用できるすべてのダイヤルイン電話番号の完全な一覧を開くリンクも各会議の招待の下部に表示されます。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-users"></a>ユーザーの会議出席依頼に含まれる電話番号の初期割り当て

電話会議が有効になっているユーザーの会議出席依頼に含まれる電話番号は、ユーザーに割り当てられている *TeamsAudioConferencingPolicy* で定義されます。 *TeamsAudioConferencingPolicy* がユーザーに割り当てられている場合、ポリシーに追加されたすべての有料電話番号と無料電話番号は、そのポリシーを持つユーザーの会議出席依頼に含まれます。 ユーザーに *TeamsAudioConferencingPolicy* が割り当てられ、ポリシーに有料電話番号やフリーダイヤル電話番号が追加されていない場合、その場合、これらのユーザーの会議出席依頼に表示される電話番号は、個々のユーザーの設定で既定の会議の有料電話番号と既定の会議無料電話番号によって定義されます。

> [!NOTE]
> ユーザーの *TeamsAudioConferencingPolicy* に追加された有料電話番号またはフリーダイヤル電話番号は、ユーザーの設定で既定の会議の有料電話番号と既定の会議フリーダイヤル電話番号を使用して個別に設定された電話番号よりも優先されます。

前述のように、各会議出席依頼には、電話番号に加えて、特定の会議に参加するために使用できるすべてのダイヤルイン電話番号の完全な一覧を開くリンクが含まれています。

> [!IMPORTANT]
> 割り当てられた電話番号が会議出席依頼に表示されるまでには、最大で 24 時間かかる場合があります。 更新された番号が表示されない場合は、少なくとも 24 時間待ってからサポートにお問い合わせください。

### <a name="new-users"></a>新しいユーザー

新しいユーザーの会議出席依頼に含まれる有料電話番号と無料電話番号も、それらのユーザーに割り当てられている *TeamsAudioconferencingPolicy* によって定義されます。 既定では、すべての新しいユーザーに Global *TeamsAudioconferencingPolicy が* 割り当てられます。 グローバル ポリシーには電話番号は追加されません (テナント管理者が変更しない限り)。 この場合、電話会議が有効になっているユーザーの会議出席依頼に含まれる電話番号は、既定の会議の有料電話番号と、各ユーザーの設定で見つかった既定の会議フリーダイヤル電話番号によって定義されます。

新しいユーザーの場合、電話会議サービスに対してユーザーが有効になっている場合、ユーザーの Microsoft 365 管理センターで設定された使用場所に基づいて、既定の会議の有料電話番号が割り当てられます。 会議ブリッジにユーザーの国と一致する有料電話番号がある場合、その番号はユーザーの既定の有料電話番号として自動的に割り当てられます。 存在しない場合は、会議ブリッジの既定の有料電話番号として定義されている番号が、ユーザーの既定の有料電話番号として割り当てられます。  

ユーザーが電話会議サービスに対して有効になったら、テナント管理者が必要に応じて初期値からユーザーの既定の有料電話番号とフリーダイヤル電話番号を変更できます。

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-users-in-powershell-using-the-teamsaudioconferencingpolicy-cmdlet"></a>*TeamsAudioConferencingPolicy* コマンドレットを使用して、Powershell のユーザーの既定の電話会議電話番号を設定または変更する

[有料電話番号とフリーダイヤル番号の電話会議ポリシー設定](audio-conferencing-toll-free-numbers-policy.md)を参照してください

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user-individually"></a>会議開催者またはユーザーの既定の電話会議電話番号を個別に設定または変更する

これらの変更を行うには、Teams サービス管理者であることが必要です。 「[Teams 管理者ロールを使用してチームを管理する](./using-admin-roles.md)」をご覧いただき、管理者ロールとアクセス許可を取得する方法について読んでください。

1. Microsoft Teams 管理センターにログインします。

2. 左側のナビゲーションで、[ **ユーザー**] をクリックします。

    ![Microsoft Teams 管理センターでユーザーを選択する方法を示します。](media/Admin-users.png)

3. 使用可能なユーザーの一覧からユーザー名をクリックします。

4. [**電話会議**] の横の [**編集**] をクリックします。

    ![電話会議の横にある [編集] をクリックします。](media/teams-set-phone-numbers-on-invites-image3.png)

5. **[有料電話番号**] フィールドまたは **[フリーダイヤル番号**] フィールドを使用して、ユーザーの番号を入力します。

> [!IMPORTANT]
> ユーザーの電話会議設定を変更する場合は、定期的な Microsoft Teams 会議と今後の Microsoft Teams 会議を更新し、出席者に送信する必要があります。

> [!NOTE]
> この設定で入力した電話番号は、ユーザーに割り当てられた *TeamsAudioConferencingPolicy* に電話番号が追加されていない場合にのみ使用されます。

## <a name="want-to-use-windows-powershell"></a>Windows PowerShellを使用する

Windows PowerShellはすべて、ユーザーの管理と、ユーザーの許可または許可されていない操作です。 Windows PowerShellを使用すると、1 つの管理ポイントを使用して Microsoft 365 またはOffice 365を管理できます。複数のタスクがある場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

- [Windows PowerShell で Office 365 を管理するための最善の方法](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Windows PowerShell で Microsoft 365 または Office 365 を管理するための最善の方法](/previous-versions//dn568025(v=technet.10))

[Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) を使用して会議開催者またはユーザーの既定の電話会議電話番号を設定または変更するには、[Set-CsOnlineDialInConferencingUser](/powershell/module/skype/set-CsOnlineDialInConferencingUser?view=skype-ps) コマンドレットのパラメーターを使用可能な番号のいずれかに設定 **`ServiceNumber`** します **`TollFreeServiceNumber`**。

## <a name="related-topics"></a>関連項目

[Microsoft 365 または Office 365で電話会議を試用または購入する](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[電話会議ブリッジの電話番号を変更する](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

---
title: 'Microsoft Teamsでのポリシーの呼び出し: 通話と転送の機能'
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Microsoft Teamsのカスタム通話ポリシーにユーザーを作成、変更、追加する方法と、さまざまな通話ポリシー設定について説明します。
ms.localizationpriority: medium
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callingpolicies.overview
- seo-marvel-apr2020
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e1ed56a843fc0582c903d7b8b549ab1b97eb050a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60783174"
---
# <a name="calling-and-call-forwarding-in-teams"></a>Teamsでの通話と通話転送

Microsoft Teamsでは、通話ポリシーによって、ユーザーが使用できる通話と通話の転送機能が制御されます。 通話ポリシーは、ユーザーがプライベート通話を行うことができるか、通話転送を使用するか、他のユーザーまたは外部電話番号に同時に呼び出すか、通話をボイスメールにルーティングするか、通話グループに通話を送信するか、着信通話と発信通話に委任を使用するかを決定します。

自動的に作成されるグローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てることができます。

## <a name="create-a-custom-calling-policy"></a>カスタム通話ポリシーを作成する

カスタム通話ポリシーを作成するには、次の手順に従います。

1. Microsoft Teams管理センターの左側のナビゲーションで、**VoiceCalling** >  ポリシーに移動します。
2. **[追加]** を選択します。
3. 通話ポリシーで使用する機能をオンまたはオフにします。
4. ユーザーがボイスメールに着信通話をルーティングできるかどうかを制御するには、[ **有効]** または [ **ユーザー制御**] を選択します。 ボイスメールへのルーティングを禁止するには、[ **無効]** を選択します。
5. **[保存]** を選択します。

## <a name="edit-a-calling-policy"></a>通話ポリシーを編集する

既存の通話ポリシーを編集するには、次の手順に従います。

1. Microsoft Teams管理センターの左側のナビゲーションで、**VoiceCalling** >  **ポリシーを選択します**。
2. 変更するポリシーの横にあるをクリックし、[ **編集]** を選択します。
3. 必要な変更を加え、[保存] をクリック **します**。

## <a name="assign-a-custom-calling-policy-to-users"></a>ユーザーにカスタム通話ポリシーを割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>ポリシー設定の呼び出し

ポリシーの呼び出し用に構成できる設定を次に示します。

### <a name="make-private-calls"></a>プライベート通話をする

この設定は、Teamsのすべての呼び出し機能を制御します。 これをオフにすると、Teamsのすべての呼び出し機能がオフになります。

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>組織内のユーザーへの通話転送と同時呼び出し

この設定は、着信呼び出しを他のユーザーに転送するか、同時に別のユーザーを呼び出すことができるかを制御します。

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>通話転送と外部電話番号への同時呼び出し

この設定は、着信呼び出しを外部番号に転送できるか、外部番号を同時に呼び出すことができるかを制御します。

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>ボイスメールは、着信通話のルーティングに使用できます

この設定により、着信通話をボイスメールに送信できます。 有効なオプションは次のとおりです。

- **有効** ボイスメールは、常に着信通話に使用できます。
- **無効**  ボイスメールは、着信通話では使用できません。
- **ユーザー制御** ユーザーは、ボイスメールを使用できるかどうかを判断できます。

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>着信呼び出しを呼び出しグループにルーティングできます

この設定は、着信呼び出しを通話グループに転送できるかどうかを制御します。

### <a name="delegation-for-inbound-and-outbound-calls"></a>着信呼び出しと発信呼び出しの委任

この設定により、受信呼び出しを代理人にルーティングし、委任されたアクセス許可を持つユーザーに代わって発信呼び出しを行うことができます。 詳細については、「 [代理人と電話回線を共有する](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)」を参照してください。

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>通話料金のバイパスを防止し、PSTN 経由で通話を送信する

これを **オン** に設定すると、PSTN 経由で通話が送信され、ネットワーク経由で通話料をバイパスするのではなく、料金が発生します。

### <a name="busy-on-busy-is-available-when-in-a-call"></a>通話中に使用中のビジー状態を利用できます

ビジー状態 (ビジー状態のオプション) を使用すると、ユーザーが既に通話または会議に参加しているか、通話が保留になっている場合に、着信呼び出しを処理する方法を構成できます。 新しい呼び出しまたは着信は、ビジー状態の信号で拒否することも、ユーザーの未応答の設定に応じてルーティングすることもできます。 ビジー状態のオプションは、テナント レベルまたはユーザー レベルで有効にできます。 通話中のオプションの構成方法に関係なく、通話中または会議中のユーザー、または通話を保留しているユーザーは、新しい通話や会議を開始できません。 この設定は既定で無効になっています。

### <a name="web-pstn-calling"></a>Web PSTN 通話

この設定を使用すると、ユーザーはTeams Web クライアントを使用して PSTN 番号を呼び出できます。

### <a name="incoming-meeting-invites-are-automatically-answered"></a>受信会議の招待に自動的に応答する

この設定は、受信会議の招待に自動的に応答するかどうかを制御します。 規定ではオフになっています。 この設定は、受信会議の招待にのみ適用されます。 他の種類の呼び出しには適用されません。

### <a name="allow-music-on-hold"></a>保留音を許可する

この設定を使用すると、PSTN 発信者が保留になったときに保留音をオンまたはオフにすることができます。 既定ではオンになっています。 この設定は、コール パークと上司の委任機能には適用されません。現時点では PowerShell でのみ使用できます。

## <a name="related-articles"></a>関連記事

[Set-CSTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[ Teams でユーザーにポリシーを割り当てる](policy-assignment-overview.md)

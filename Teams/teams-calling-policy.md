---
title: '呼び出しMicrosoft Teams: 通話および通話転送機能'
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: ユーザーを作成、変更、追加する方法と、Microsoft Teams通話ポリシーの設定について説明します。
localization_priority: Normal
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
ms.openlocfilehash: e38a566e025c711a9b17a050137e67af7507e63d5c5e829ba4448ee4a1577790
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309246"
---
#  <a name="calling-and-call-forwarding-in-teams"></a>通話および通話転送 (Teams

Microsoft Teams では、通話ポリシーは、ユーザーが使用できる通話と通話の転送機能を制御します。 通話ポリシーは、ユーザーがプライベート通話を行う、他のユーザーまたは外部電話番号への通話転送または同時呼び出しを使用できるかどうか、ボイスメールへの通話のルーティング、通話グループへの通話の送信、受信および発信通話の委任の使用などについて決定します。

自動的に作成されるグローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てできます。

## <a name="create-a-custom-calling-policy"></a>カスタム通話ポリシーを作成する

カスタム通話ポリシーを作成するには、次の手順に従います。

1. 管理センターの左側のナビゲーションMicrosoft Teams[音声通話ポリシー **]**  >  **に移動します**。
2. **[追加]** を選択します。
3. 通話ポリシーで使用する機能をオンまたはオフにします。
4. ユーザーが着信通話をボイスメールにルーティングできるかどうかを制御するには、**[有効]** または **[ユーザーによる制御]** を選択します。 ボイスメールにルーティングしないようにするには、**[無効]** を選択します。
5. **[保存]** を選択します。

## <a name="edit-a-calling-policy"></a>通話ポリシーを編集する

既存の通話ポリシーを編集するには、次の手順に従います。

1. 管理センターの左側のナビゲーションMicrosoft Teams[音声通話ポリシー **]**  >  **を選択します**。
2. 変更するポリシーの横をクリックし、[編集] を **選択します**。
3. 必要な変更を行い、[保存] を **クリックします**。

## <a name="assign-a-custom-calling-policy-to-users"></a>カスタム通話ポリシーをユーザーに割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>通話ポリシーの設定

通話ポリシー用に構成できる設定を次に示します。

### <a name="make-private-calls"></a>プライベート通話をする

この設定は、すべての通話機能をTeams。 これをオフにすると、Teams のすべての通話機能がオフになります。

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>組織内のユーザーへの通話転送と同時呼び出し

この設定は、着信呼び出しを他のユーザーに転送できるかどうか、または同時に他のユーザーを呼び出すかどうかを制御します。 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>外部の電話番号への通話転送と同時呼び出し

この設定は、着信呼び出しを外部番号に転送できるかどうか、または外部番号を同時に呼び出すかどうかを制御します。

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>着信通話のルーティングのためにボイスメールが利用可能

この設定では、受信通話をボイスメールに送信できます。 有効なオプションは次のとおりです。

- **有効** ボイスメールは、常に受信通話で使用できます。
- **無効**  ボイスメールは、着信呼び出しでは使用できません。
- **ユーザー制御** ユーザーは、ボイスメールを使用できるかどうかを決定できます。

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>着信通話通話グループにルーティングすることができます。

この設定は、着信呼び出しを呼び出しグループに転送できるかどうかを制御します。

### <a name="delegation-for-inbound-and-outbound-calls"></a>着信および送信呼び出しの委任

この設定を使用すると、代理人に受信呼び出しをルーティングし、代理人がアクセス許可を委任したユーザーに代わって発信呼び出しを行うことができます。 詳細については、「代理人と [電話回線を共有する」を参照してください](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)。

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>有料通話のバイパスを防止して PSTN 経由で通話を送信 

これを On **に設定すると** 、PSTN 経由で通話が送信され、ネットワーク経由で通話料を送信して通行料をバイパスするのではなく、料金が発生します。

### <a name="busy-on-busy-is-available-when-in-a-call"></a>通話中にビジー状態が利用可能

Busy on Busy (Busy Options) を使用すると、ユーザーが既に通話または会議に参加している場合、または通話を保留にしている場合の着信呼び出しの処理方法を構成できます。 新しい呼び出しまたは着信呼び出しは、ビジー状態の信号で拒否するか、ユーザーの未応答の設定に応じてルーティングできます。 ビジー オプションは、テナント レベルまたはユーザー レベルで有効にできます。 通話中のオプションの構成方法に関係なく、通話または会議のユーザー、または通話中のユーザーは、新しい通話や会議を開始しません。 この設定は既定では無効になっています。

### <a name="web-pstn-calling"></a>Web PSTN 通話

この設定を使用すると、ユーザーは Web クライアントを使用して PSTN Teams呼び出しできます。

### <a name="incoming-meeting-invites-are-automatically-answered"></a>受信会議の招待に自動的に応答する

この設定は、受信した会議出席招待に自動的に応答するかどうかを制御します。 既定では無効になっています。 この設定は、会議出席招待の受信にのみ適用されます。 他の種類の呼び出しには適用されません。

### <a name="allow-music-on-hold"></a>保留中の音楽を許可

この設定を使用すると、PSTN 発信者が保留に設定されているときに保留音をオンまたはオフにできます。 既定ではオンになっています。 この設定は、コール パーク機能と上司代理人機能には適用されません。現在は PowerShell 経由でのみ使用できます。

## <a name="related-articles"></a>関連記事

[Set-CSTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Teams でユーザーにポリシーを割り当てる](assign-policies.md)

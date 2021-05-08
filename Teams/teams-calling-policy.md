---
title: Microsoft Teams の発信通話制限ポリシー
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Microsoft Teams のカスタム呼び出しポリシーとさまざまな呼び出し元ポリシー設定にユーザーを作成、変更、追加する方法について説明します。
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
ms.openlocfilehash: e469cc183134bab35855e83257126029ce78a8cc
ms.sourcegitcommit: c80af314f1a573f99dd66858301c004ccc5410d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2021
ms.locfileid: "51653949"
---
<a name="calling-policies-in-microsoft-teams"></a>Microsoft Teams の発信通話制限ポリシー
===================================

このMicrosoft Teams呼び出しポリシーは、ユーザーが使用できる通話と呼び出しの転送機能を制御します。 通話ポリシーは、ユーザーがプライベート通話の発信、他のユーザーまたは外部電話番号への着信の転送または同時呼び出しの使用、ボイスメールへの通話のルーティング、通話グループへの呼び出しの送信、着信および発信通話に委任を使用できるかどうかを決定します。

自動的に作成されるグローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てできます。

## <a name="create-a-custom-calling-policy"></a>カスタム呼び出しポリシーを作成する

カスタム呼び出しポリシーを作成するには、次の手順に従います。

1. 管理センターの左側のナビゲーションMicrosoft Teams、[音声通話ポリシー]  >  **に移動します**。
2. **[追加]** を選択します。
3. 呼び出し元ポリシーで使用する機能をオンまたはオフにします。
4. ユーザーが受信通話をボイスメールにルーティングできるかどうかを制御するには、[有効] または [ユーザー **制御]****を選択します**。 ボイスメールへのルーティングを防ぐには、[無効] を **選択します**。
5. **[保存]** を選択します。

## <a name="edit-a-calling-policy"></a>呼び出し元ポリシーを編集する

既存の呼び出し元ポリシーを編集するには、次の手順に従います。

1. 管理センターの左側のナビゲーションで、[音声Microsoft Teams ポリシー]  >  **を選択します**。
2. 変更するポリシーの横にある をクリックし、[編集] を **選択します**。
3. 必要な変更を行い、[保存] を **クリックします**。

## <a name="assign-a-custom-calling-policy-to-users"></a>カスタム呼び出しポリシーをユーザーに割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>呼び出し元ポリシー設定

呼び出しポリシー用に構成できる設定を次に示します。

### <a name="make-private-calls"></a>プライベート通話をする

この設定は、すべての呼び出し機能をTeams。 この設定をオフにし、すべての通話機能を無効Teams。

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>組織内のユーザーへの通話の転送と同時呼び出し

この設定は、着信通話を他のユーザーに転送できるかどうか、または同時に別のユーザーを呼び出すかどうかを制御します。 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>外部の電話番号への通話の転送と同時呼び出し

この設定は、着信通話を外部番号に転送できるかどうか、または外部番号を同時に呼び出すかどうかを制御します。

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>ボイスメールは着信通話のルーティングに使用できます

この設定により、受信呼び出しをボイスメールに送信できます。 有効なオプションは次のとおりです。

- **有効** ボイスメールは、常に着信通話に使用できます。
- **無効**  ボイスメールは、着信通話では使用できません。
- **ユーザー制御** ユーザーは、ボイスメールを使用できるかどうかを決定できます。

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>着信呼び出しを呼び出しグループにルーティングできます。 

この設定は、着信通話を通話グループに転送できるかどうかを制御します。

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>着信呼び出しと送信呼び出しの委任を許可する

この設定により、代理人に受信呼び出しをルーティングし、代理人がアクセス許可を委任したユーザーの代わりに発信呼び出しを行うことができます。 詳細については、「代理人と [電話回線を共有する」を参照してください](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)。

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>有料バイパスを防止し、PSTN 経由で通話を送信する 

これを [ **オン] に** 設定すると、PSTN 経由で通話が送信され、ネットワーク経由で通話を送信して通行料をバイパスするのではなく、料金が発生します。

### <a name="busy-on-busy-is-available-while-in-a-call"></a>通話中に [取り込み中] を使用できます

[取り込み中 (取り込み中] オプション) は、ユーザーが既に通話または電話会議に参加している場合、または通話を保留にした場合の着信呼び出しの処理方法を構成できる新しい設定です。 新しい呼び出しまたは着信呼び出しは、ビジー状態の信号で拒否したり、ユーザーの未応答の設定に応じてルーティングできます。 ビジー状態のオプションは、テナント レベルまたはユーザー レベルで有効にできます。 取り込み中のオプションの構成方法に関係なく、通話または電話会議のユーザー、または保留の通話を持つユーザーが新しい通話や会議を開始できない。 この設定は、既定では無効になっています。

### <a name="allow-web-pstn-calling"></a>Web PSTN 通話を許可する

この設定により、ユーザーは Web クライアントから PSTN 番号Teams呼び出しできます。

### <a name="allow-music-on-hold"></a>保留音を許可する

この設定により、PSTN 発信者が保留にされた場合に、保留音をオンまたはオフにできます。 既定ではオンになっています。 この設定は、コール パークと上司の代理人機能には適用されません。現在は PowerShell 経由でのみ使用できます。

## <a name="related-topics"></a>関連トピック

[Set-CSTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[ Teams でユーザーにポリシーを割り当てる](assign-policies.md)
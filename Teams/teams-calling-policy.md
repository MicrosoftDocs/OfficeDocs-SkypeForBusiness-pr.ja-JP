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
description: Microsoft Teams のカスタム通話ポリシーとさまざまな通話ポリシー設定を作成、変更、追加する方法について説明します。
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

Microsoft Teams では、ユーザーが使用できる通話と通話の転送機能を通話ポリシーで制御します。 通話ポリシーは、ユーザーがプライベート通話を行う、他のユーザーまたは外部の電話番号への着信の転送または同時呼び出しを使用できるかどうか、通話をボイスメールにルーティングする、通話グループに通話を送信する、着信通話と発信通話の委任を使用できるかどうかを決定します。

自動的に作成されるグローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てできます。

## <a name="create-a-custom-calling-policy"></a>カスタム通話ポリシーを作成する

カスタム通話ポリシーを作成するには、次の手順に従います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[音声通話ポリシー **]**  >  **に移動します**。
2. **[追加]** を選択します。
3. 通話ポリシーで使用する機能をオンまたはオフにします。
4. ユーザーが着信通話をボイスメールにルーティングできるかどうかを制御するには、[有効] または [ユーザー制御]**を選択します**。 ボイスメールへのルーティングを防止するには、[無効] を **選択します**。
5. **[保存]** を選択します。

## <a name="edit-a-calling-policy"></a>通話ポリシーを編集する

既存の通話ポリシーを編集するには、次の手順に従います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[音声通話ポリシー **]**  >  **を選択します**。
2. 変更するポリシーの横をクリックし、[編集] を選択 **します**。
3. 必要な変更を行い、[保存] をクリック **します**。

## <a name="assign-a-custom-calling-policy-to-users"></a>カスタム通話ポリシーをユーザーに割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>通話ポリシーの設定

通話ポリシー用に構成できる設定を次に示します。

### <a name="make-private-calls"></a>プライベート通話をする

この設定は、Teams のすべての通話機能を制御します。 これをオフにし、Teams のすべての通話機能をオフにします。

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>組織内のユーザーへの通話の転送と同時呼び出し

この設定では、着信通話を他のユーザーに転送したり、他のユーザーを同時に呼び出したりできるかどうかを制御します。 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>外部の電話番号への通話の転送と同時呼び出し

この設定では、着信通話を外部番号に転送できるかどうか、または外部番号を同時に呼び出すかどうかを制御します。

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>ボイスメールは着信通話をルーティングできます

この設定では、受信通話をボイスメールに送信できます。 有効なオプションは次のとおりです。

- **有効** ボイスメールは、常に着信通話に使用できます。
- **無効**  ボイスメールは着信通話に使用できません。
- **ユーザー制御** ユーザーは、ボイスメールを使用できるかどうかを決定できます。

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>着信通話を通話グループにルーティングできる 

この設定は、着信通話を通話グループに転送できるかどうかを制御します。

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>着信通話と発信通話の委任を許可する

この設定では、着信通話を代理人にルーティングし、代理人がアクセス許可を委任したユーザーの代わりに発信通話を行うことができます。 詳細については、「代理人と [電話回線を共有する」を参照してください](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)。

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>有料バイパスを防止し、PSTN 経由で通話を送信する 

これをオンに **設定** すると、PSTN 経由で通話が送信され、ネットワーク経由で通話を送信して有料通話をバイパスするのではなく、料金が発生します。

### <a name="busy-on-busy-is-available-while-in-a-call"></a>取り込み中は通話中に利用できます

取り込み中 (取り込み中オプション) は、ユーザーが既に通話または会議に参加している場合、または通話を保留にした場合の着信通話の処理方法を構成できる新しい設定です。 新しい通話または着信通話は、取り込み中の信号で拒否したり、ユーザーの未応答の設定に従ってルーティングすることができます。 取り込み中オプションは、テナント レベルまたはユーザー レベルで有効にできます。 取り込み中のオプションの構成方法に関係なく、通話または会議のユーザー、または保留の通話を行っているユーザーは、新しい通話や会議を開始できない状態ではありません。 この設定は、既定では無効になっています。

### <a name="allow-web-pstn-calling"></a>Web PSTN 通話を許可する

この設定により、ユーザーは Teams Web クライアントを使用して PSTN 番号に通話できます。

### <a name="allow-music-on-hold"></a>保留音を許可する

この設定では、PSTN 発信者が保留にされた場合に、保留音のオンとオフを切り替えます。 既定ではオンになっています。 この設定はコール パークや上司の代理人機能には適用されません。現在は PowerShell 経由でのみ使用できます。

## <a name="related-topics"></a>関連項目

[Set-CSTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[ Teams でユーザーにポリシーを割り当てる](assign-policies.md)
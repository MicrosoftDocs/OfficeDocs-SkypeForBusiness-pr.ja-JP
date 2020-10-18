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
description: Microsoft Teams のカスタムの通話ポリシーや、さまざまな通話ポリシーの設定に対してユーザーを作成、変更、および追加する方法について説明します。
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
ms.openlocfilehash: 03ec48de66bc5b179b3a1d8cfe006b1789d09a33
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48581067"
---
<a name="calling-policies-in-microsoft-teams"></a>Microsoft Teams の発信通話制限ポリシー
===================================

Microsoft Teams では、通話ポリシーによって、ユーザーが使用できる通話と通話転送機能が制御されます。 通話ポリシーは、ユーザーがプライベートな通話を行うことができるかどうかを決定します。着信の転送や、他のユーザーや外部の電話番号への同時呼び出し、ボイスメールへの通話のルーティング、通話グループへの通話の送信、受信と発信などの呼び出しに委任を使用するなどを行います。

自動的に作成されるグローバル (組織全体の既定) ポリシーを使用するか、カスタムポリシーを作成して割り当てることができます。

## <a name="create-a-custom-calling-policy"></a>カスタム通話ポリシーを作成する

カスタムの通話ポリシーを作成するには、次の手順を実行します。

1. Microsoft Teams 管理センターの左のナビゲーションで、[**音声**通話のポリシー] に移動し  >  **Calling policies**ます。
2. [ **追加**] を選びます。
3. 通話ポリシーで使用する機能を有効または無効にします。
4. 着信通話をボイスメールにルーティングできるかどうかを制御するには、[ **有効** ] または [ **ユーザー管理**] を選択します。 ボイスメールへのルーティングを禁止するには、[ **無効**] を選択します。
5. **[保存]** を選択します。

## <a name="edit-a-calling-policy"></a>通話ポリシーを編集する

既存の通話ポリシーを編集するには、次の手順を実行します。

1. Microsoft Teams 管理センターの左のナビゲーションで、[**音声**  >  **通話のポリシー**] を選びます。
2. 変更するポリシーの横にあるをクリックし、[ **編集**] を選択します。
3. 必要な変更を加えて、[ **保存**] をクリックします。

## <a name="assign-a-custom-calling-policy-to-users"></a>ユーザーにカスタムの通話ポリシーを割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>通話ポリシーの設定

次に、ポリシーを呼び出すために構成できる設定を示します。

### <a name="make-private-calls"></a>プライベート通話をする

この設定により、Teams のすべての通話機能が制御されます。 Teams のすべての通話機能を無効にするには、このオプションをオフにします。

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>組織内のユーザーとの着信の転送と同時呼び出し

この設定では、着信通話を他のユーザーに転送できるか、または他の人を同時に呼び出すことができるかを制御します。 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>着信の転送と同時呼び出しを外部電話番号に転送する

この設定は、着信通話を外部番号に転送できるか、外部番号を同時に呼び出すことができるかを制御します。

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>着信通話の転送にはボイスメールが利用可能

この設定では、着信通話をボイスメールに送信できます。 有効なオプションは次のとおりです。

- **有効** ボイスメールは、着信通話にいつでも利用できます。
- **無効**  着信通話でボイスメールを使用することはできません。
- **ユーザー** による制御ユーザーはボイスメールを利用できるようにするかどうかを決定できます。

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>着信通話を通話グループにルーティングできる 

> [!Include [feature preview](includes/preview-feature.md)]

この設定は、着信通話を通話グループに転送できるかどうかを制御します。

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>着信と発信の通話の委任を許可する

> [!Include [feature preview](includes/preview-feature.md)]

この設定を有効にすると、着信の代理人へのルーティングが許可され、代理人がアクセス権を委任したユーザーの代わりに発信通話を行うことができます。 詳細については、「 [代理人と電話回線を共有](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)する」を参照してください。

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>通話を発信したり、PSTN 経由で通話を送信したりする 

この設定 **で** は、ネットワーク経由での送信と、tolls のバイパスではなく、PSTN 経由で通話が送信され、料金が発生します。

### <a name="busy-on-busy-is-available-while-in-a-call"></a>通話中に取り込み中

[取り込み中] (取り込み中) は、ユーザーが既に通話または会議に参加している場合や、通話が保留になっている場合に、着信通話の処理方法を構成できる新しい設定です。 新規または着信通話は、取り込み中の信号で拒否することができます。 [取り込み] オプションは、テナントレベルまたはユーザーレベルで有効にすることができます。 通話や電話会議のユーザー、または通話を保留しているユーザーは、会議中の通話や会議の開始を防ぐことはできません。 この設定は、既定では無効になっています。

### <a name="allow-web-pstn-calling"></a>Web PSTN 通話を許可する

この設定により、ユーザーは Teams web クライアントを使って PSTN 番号に通話を発信できます。

### <a name="allow-music-on-hold"></a>保留中の音楽を許可する

この設定では、PSTN の発信者が保留になっているときに、保留中の音楽をオンまたはオフにすることができます。 これは既定でオンになっています。 この設定は、コールパークと上司のデリゲート機能には適用されず、現在、PowerShell でのみ利用可能です。

## <a name="related-topics"></a>関連項目

[Set-Csteam拡張性のポリシー](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[チームのユーザーにポリシーを割り当てる](assign-policies.md)

---
title: Microsoft Teams の発信通話制限ポリシー
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 05/06/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Microsoft Teams での通話ポリシー設定について説明します。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5c94a8c9ff9c1eef2017cf70d69a2308f5c94db6
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243855"
---
<a name="calling-policies-in-microsoft-teams"></a>Microsoft Teams の発信通話制限ポリシー
===================================

Microsoft Teams では、通話ポリシーによって、ユーザーが使用できる通話と通話転送機能が制御されます。 通話ポリシーは、ユーザーがプライベートな通話を行うことができるかどうかを決定します。着信の転送や、他のユーザーや外部の電話番号への同時呼び出し、ボイスメールへの通話のルーティング、通話グループへの通話の送信、受信と発信などの呼び出しに委任を使用するなどを行います。 既定のグローバルポリシーは自動的に作成されますが、管理者はカスタムの通話ポリシーを作成して割り当てることもできます。

## <a name="create-a-custom-calling-policy"></a>カスタム通話ポリシーを作成する

カスタムの通話ポリシーを作成するには、次の手順を実行します。

1. Microsoft Teams 管理センターで、[**音声** > **通話のポリシー**] を選択します。
2. [**新しいポリシー**] を選びます。
3. 通話ポリシーで使用する機能を有効にします。 すべての選択は既定で**オフ**になっています。
4. 着信通話をボイスメールにルーティングできるかどうかを制御するには、[**常に有効**] または [**ユーザー管理**] を選択します。 ボイスメールへのルーティングを禁止するには、[**常に無効**] を選びます。
5. [**保存**] を選びます。

## <a name="modify-an-existing-calling-policy"></a>既存の通話ポリシーを変更する

既存の通話ポリシーを変更するには、次の手順を実行します。

1. Microsoft Teams 管理センターで、[**音声** > **通話のポリシー**] を選択します。
2. 変更するポリシーの横にあるをクリックし、[**編集**] を選択します。
3. 通話ポリシーで使用する機能を有効にします。 すべての選択は既定で**オフ**になっています。
4. 着信通話をボイスメールにルーティングできるかどうかを制御するには、[**常に有効**] または [**ユーザー管理**] を選択します。 ボイスメールへのルーティングを禁止するには、[**常に無効**] を選びます。
5. [**保存**] を選びます。

## <a name="assign-a-calling-policy-to-a-user"></a>ユーザーに通話ポリシーを割り当てる

ユーザーにカスタムの通話ポリシーを割り当てるには、次の手順を実行します。

1. Microsoft Teams 管理センターで、[**音声** > **通話のポリシー**] を選択します。
2. ポリシー名の横にあるをクリックして選択し、[**ユーザーの管理**] を選択します。
3. [**ユーザーの管理**] ウィンドウで、ユーザーの名前を検索します。 (少なくとも3文字を入力する必要があります)。
4. ユーザー名を選択し、[**追加**] を選択します。
5. [**保存**] を選びます。

## <a name="calling-policy-settings"></a>通話ポリシーの設定

カスタムの通話ポリシーを作成するには、次の設定を使用します。

### <a name="user-can-make-private-calls"></a>ユーザはプライベートな通話を発信できます

この設定により、Teams のすべての通話機能が制御されます。 Teams のすべての通話機能を無効にするには、このオプションをオフにします。

### <a name="call-forwarding-and-simultaneous-ringing-to-other-users"></a>他のユーザーとの着信の転送と同時呼び出し

この設定では、着信通話を他のユーザーに転送できるか、または他の人を同時に呼び出すことができるかを制御します。 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>着信の転送と同時呼び出しを外部電話番号に転送する

この設定は、着信通話を外部番号に転送できるか、外部番号を同時に呼び出すことができるかを制御します。

### <a name="voicemail-is-available-for-routing-inbound-calls-to-users"></a>着信通話をユーザにルーティングするためにボイスメールを利用できます

この設定では、着信通話をボイスメールに送信できます。 有効なオプションは次のとおりです。

   - **常に有効**ボイスメールは、着信通話にいつでも利用できます。 
   - **常に無効** 着信通話でボイスメールを使用することはできません。 
   - **ユーザー制御**。 ユーザーはボイスメールを利用できるようにするかどうかを決定できます。

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>着信通話を通話グループにルーティングできる 

> [!Include [feature preview](includes/preview-feature.md)]

この設定は、着信通話を通話グループに転送できるかどうかを制御します。

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>着信と発信の通話の委任を許可する

> [!Include [feature preview](includes/preview-feature.md)]

この設定を有効にすると、着信の代理人へのルーティングが許可され、代理人がアクセス権を委任したユーザーの代わりに発信通話を行うことができます。 詳細については、「[代理人と電話回線を共有](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)する」を参照してください。


### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>通話を発信したり、PSTN 経由で通話を送信したりする 

この設定**で**は、ネットワーク経由での送信と、tolls のバイパスではなく、PSTN 経由で通話が送信され、料金が発生します。

### <a name="busy-on-busy-is-available-while-in-a-call"></a>通話中に取り込み中

[取り込み中] (取り込み中)) は、ユーザーが既に通話または会議に参加している場合や、通話が保留になっている場合に、着信通話の処理方法を構成できる、チーム呼び出しポリシーの新しい設定です。 新規または着信通話は、取り込み中の信号で拒否することができます。 [取り込み] オプションは、テナントレベルまたはユーザーレベルで有効にすることができます。 通話や電話会議のユーザー、または通話を保留しているユーザーは、会議中の通話や会議の開始を防ぐことはできません。 この設定は、既定では無効になっています。

## <a name="see-also"></a>関連項目

[Set-Csteam拡張性のポリシー](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)
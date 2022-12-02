---
title: 'Microsoft Teams でのポリシーの呼び出し: 通話と転送の機能'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Microsoft Teams のカスタム呼び出し元ポリシーと、さまざまな呼び出し元ポリシー設定にユーザーを作成、変更、および追加する方法について説明します。
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
ms.openlocfilehash: a02df903574c7e7db796294ad90c9e05ab732eb0
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2022
ms.locfileid: "69245679"
---
# <a name="calling-policies-calling-and-call-forwarding-features-in-teams"></a>通話ポリシー: Teams での通話と転送の機能

Microsoft Teams では、通話ポリシーによって、ユーザーが使用できる通話および通話転送機能が制御されます。 通話ポリシーは、ユーザーがプライベート通話を行うか、他のユーザーまたは外部の電話番号への通話転送または同時呼び出しを使用できるか、ボイスメールへの通話をルーティングするか、通話グループへの通話を送信するか、着信と発信の呼び出しに委任を使用するかを決定します。

自動的に作成されるグローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てることができます。

## <a name="create-a-custom-calling-policy"></a>カスタム呼び出し元ポリシーを作成する

カスタム呼び出し元ポリシーを作成するには、次の手順に従います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**音声** > **通話ポリシー**] に移動します。
2. **[追加]** を選択します。
3. 通話ポリシーで使用する機能をオンまたはオフにします。
    - たとえば、ユーザーが着信通話をボイスメールにルーティングできるかどうかを制御するには、[ **有効]** または [ **ユーザー制御**] を選択します。 ボイスメールへのルーティングを禁止するには、[ **無効**] を選択します。
4. **[保存]** を選択します。

## <a name="edit-a-calling-policy"></a>通話ポリシーを編集する

既存の通話ポリシーを編集するには、次の手順に従います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**音声** > **通話ポリシー**] を選択します。
2. 変更するポリシーの横にあるをクリックし、[編集] を選択 **します**。
3. 必要な変更を行い、[ **保存**] をクリックします。

## <a name="assign-a-custom-calling-policy-to-users"></a>カスタム呼び出し元ポリシーをユーザーに割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>ポリシー設定の呼び出し

ポリシーの呼び出しに対して構成できる設定を次に示します。

### <a name="make-private-calls"></a>プライベート通話をする

この設定は、Teams のすべての呼び出し機能を制御します。 Teams のすべての通話機能をオフにするには、これをオフにします。

### <a name="cloud-recording-for-calling"></a>呼び出しのためのクラウド記録

この設定は、ユーザーが通話を記録できるかどうかを制御します。 これは既定ではオフになっています。

### <a name="transcription"></a>転写

この設定は、ユーザーが呼び出しの文字起こしを使用できるかどうかを制御します。 これは既定ではオフになっています。

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>組織内のユーザーに転送と同時呼び出しを呼び出す

この設定は、着信通話を他のユーザーに転送できるか、組織内の別のユーザーを同時に呼び出すことができるかを制御します。 これは既定でオンになっています。

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>外部電話番号への転送と同時呼び出し

この設定は、着信呼び出しを外部番号に転送できるか、外部番号を同時に呼び出すことができるかを制御します。 これは既定でオンになっています。

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>ボイスメールは着信通話のルーティングに使用できます

この設定により、着信呼び出しをボイスメールに送信できます。 既定の設定は **[ユーザー制御]** です。 有効なオプションは次のとおりです。

- **有効** ボイスメールは常に着信通話に使用できます。
- **[無効]**  着信通話ではボイスメールを使用できません。
- **ユーザー制御** ユーザーは、ボイスメールを使用できるかどうかを判断できます。

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>着信呼び出しを呼び出しグループにルーティングできます

この設定は、着信呼び出しを呼び出しグループに転送できるかどうかを制御します。 これは既定でオンになっています。

### <a name="delegation-for-inbound-and-outbound-calls"></a>受信呼び出しと送信呼び出しの委任

この設定を使用すると、受信呼び出しをデリゲートにルーティングできます。これにより、委任されたアクセス許可を持つユーザーに代わって、代理人が送信呼び出しを行うことができます。 この設定は既定でオンになっています。 詳細については、「 [代理人と電話回線を共有する](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)」を参照してください。

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>PSTN 経由での有料バイパスと通話の送信を防止する

これを **[オン] に** 設定すると、PSTN 経由で通話が送信され、ネットワーク経由で通話を送信して通行料をバイパスするのではなく、料金が発生します。 この設定は、既定でオフになっています。

### <a name="music-on-hold-for-pstn-calls"></a>PSTN 通話の保留音

この設定を使用すると、PSTN 発信者が保留状態になったときに、保留音をオンまたはオフにすることができます。 既定ではオンになっています。 この設定は、コール パークとボス デリゲート機能には適用されません。 [カスタム音楽を構成](music-on-hold.md)する方法の詳細については、こちらをご覧ください。

### <a name="busy-on-busy-when-in-a-call"></a>通話中のビジー状態

通話中のビジー時 ("ビジー オプション" とも呼ばれます) を使用すると、ユーザーが既に通話または会議に参加している場合、または通話を保留にしている場合の着信呼び出しの処理方法を構成できます。 新規または着信の呼び出しは、ビジー信号で拒否することも、ユーザーの未応答の設定に従ってルーティングすることもできます。 通話または会議のユーザー、または保留中の通話を持つユーザーは、通話中のオプションの構成に関係なく、新しい通話や会議の開始を妨げません。 この設定は、既定では **[無効]** に設定されています。

- **[無効]** ビジー オプションは有効になっていないので、ユーザーが既に通話中でも、新規または着信の呼び出しをユーザーに送信できます。
- **有効** 新規または着信の呼び出しは、ビジー信号で拒否されます。
- **未解決** ボイスメールへのルーティングや別のユーザーへの転送など、ユーザーの未回答の設定が使用されます。

### <a name="web-pstn-calling"></a>Web PSTN 通話

この設定を使用すると、ユーザーは Teams Web クライアントを使用して PSTN 番号を呼び出します。 これは既定でオンになっています。

### <a name="real-time-captions-in-teams-calls"></a>Teams 通話のリアルタイム キャプション

この設定は、Teams 呼び出しのリアルタイム キャプションをユーザーが使用できるかどうかを制御します。 これは既定でオンになっています。

### <a name="automatically-answer-incoming-meeting-invites"></a>会議出席依頼に自動的に応答する

この設定は、受信した会議出席依頼に自動的に応答するかどうかを制御します。 規定ではオフになっています。 この設定は、受信した会議出席依頼にのみ適用されることに注意してください。 他の種類の呼び出しには適用されません。

### <a name="spam-filtering"></a>スパム フィルター処理

この設定を使用すると、着信呼び出しで使用できるスパム フィルター処理の種類を制御できます。 Basic と Captcha Interactive Voice (IVR) の両方のチェックを実行できます。 これは既定でオンになっています。

### <a name="sip-devices-can-be-used-for-calls"></a>SIP デバイスは通話に使用できます

この設定により、ユーザーは SIP デバイスを使用して通話を発信および受信できます。 これは既定でオフになっています。

### <a name="open-apps-in-browser-for-incoming-pstn-calls"></a>着信 PSTN 通話用にブラウザーでアプリを開く

この設定は、ユーザーへの PSTN 通話を受信するために、ブラウザーでアプリを自動的に開くかどうかを制御します。 これは、着信呼び出し元の電話番号をアプリに渡して、通話中に関連付けられている顧客レコードを検索するために使用できます。 この設定は、既定でオフになっています。

オンにした場合は、[ **PSTN 通話の着信用にブラウザーでアプリを開く URL] ボックスにアプリへの** リンクを指定する必要があります。 {phone} プレースホルダーを使用して、電話番号 (E.164 形式) を指定された URL に渡すことができます。 または、プレースホルダーなしで汎用 URL を指定することもできます。 これにより、リストされた URL が起動します。

![PSTN 着信ポリシー設定のブラウザーでアプリを開くスクリーンショット。](media/teams-open-apps-in-browser-pstn.png)

## <a name="related-articles"></a>関連記事

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[ Teams でユーザーにポリシーを割り当てる](policy-assignment-overview.md)

[PSTN 接続オプション](pstn-connectivity.md)

[ユーザーの通話設定を構成する](user-call-settings.md)

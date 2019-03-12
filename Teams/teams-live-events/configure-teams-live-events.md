---
title: Microsoft Teams でライブ イベント設定を構成する
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 組織内に保持されているチームのライブ イベントの設定を管理する方法について説明します。
f1keywords: ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 56a7834f1547c682c690f8c42082af0a314efec9
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "30542840"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Microsoft Teams でライブ イベント設定を構成する
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

チームのライブ イベントの設定を使用すると、組織内で保持されているライブのイベントの設定を構成します。 サポート URL を設定し、サード ・ パーティ製ビデオ配信プロバイダーを構成することができます。 これらの設定は、組織内に作成されるすべてのライブ イベントに適用されます。 

マイクロソフトのチームの管理センターでこれらの設定を簡単に管理することができます。 左側のナビゲーションで**の会議**に移動する > **のライブ イベントを設定**します。 

![ライブ イベント settings.png](../media/teams-live-events-settings.png "チームのスクリーン ショットは、マイクロソフトのチームの管理センターで構成可能なイベントの設定をライブ") 

## <a name="set-up-event-support-url"></a>イベント サポートの URL を設定します

ライブ イベントの参加者には、この URL が表示されます。 ライブ イベント中に、サポートに連絡する方法を参加者に提供する組織のサポート URL を追加します。

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![チーム ・ ロゴ ・ 30x30.png](../media/teams-logo-30x30.png) マイクロソフトのチーム管理センターを使用してください。

1. 左側のナビゲーションでは、**会議**に移動 > **ライブ イベントを設定**します。
2. [**サポート URL**] には、組織のサポートの URL を入力します。 

    ![ライブ マイクロソフト チームの管理センターでのイベントのサポート URL の設定](../media/teams-live-events-settings-supporturl.png "スクリーン ショットは、チームのライブ イベントを設定する URL をサポート")

### <a name="using-windows-powershell"></a>The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.
次のコマンドレットを実行します。
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
詳細については、[一連の CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)を参照してください。
## <a name="configure-a-third-party-video-distribution-provider"></a>サード ・ パーティ製ビデオ配信プロバイダーを構成します。 

購入し、定義されているソフトウェアのネットワーク (SDN) ソリューションや Microsoft ビデオ配信パートナーを通じて、エンタープライズ コンテンツ配信ネットワーク (eCDN) ソリューションを設定すると場合、は、チームでのライブ イベントのプロバイダーを構成します。 

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![チーム ・ ロゴ ・ 30x30.png](../media/teams-logo-30x30.png) マイクロソフトのチーム管理センターを使用してください。

1. 左側のナビゲーションでは、**会議**に移動 > **ライブ イベントを設定**します。
2. [**サード パーティのビデオ配信プロバイダー**では、次の手順を完了します。 

    ![マイクロソフトのチームの管理センターでのサード ・ パーティ製ビデオ配信プロバイダーの設定](../media/teams-live-events-settings-distribution-provider.png "サード ・ パーティ製ビデオ配信プロバイダーの設定のスクリーン ショットのライブ イベント")

    - **配布のサード ・ パーティ製プロバイダーを使用**サード ・ パーティ製ビデオ配信プロバイダーを有効にするには、これを有効にします。
    - **SDN プロバイダー名**使用しているプロバイダーを選択します。
    - **プロバイダー ライセンス ・ キー**相手のプロバイダーから入手したライセンス ID を入力します。
    - **SDN API テンプレートの URL**相手のプロバイダーから入手した API のテンプレートの URL を入力します。

### <a name="using-windows-powershell"></a>The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.
プロバイダーの連絡先からライセンス ID または API トークンおよび API のテンプレートを取得し、お使いのプロバイダーに応じて、次のいずれかを実行します。

**ハイブ** 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
**Kollective** 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
詳細については、[一連の CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)を参照してください。

> [!NOTE]
> 外部エンコーダーを使用して、ライブのイベントを作成する場合は、[マイクロソフトのストリームで、eCDN のプロバイダーを設定](https://docs.microsoft.com/stream/network-caching)する必要もあります。 

### <a name="related-topics"></a>関連項目
- [ライブ イベントをチームは何ですか。](what-are-teams-live-events.md)
- [チームのライブ イベントの計画](plan-for-teams-live-events.md)
- [チームのライブ イベントを設定します。](set-up-for-teams-live-events.md)
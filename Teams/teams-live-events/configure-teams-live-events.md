---
title: マイクロソフトのチームでライブ イベントの設定を構成します。
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.date: 10/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
description: 組織内に保持されているチームのライブ イベントの設定を管理する方法について説明します。
f1keywords: ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: b8e12b6b85b61bb8c6312054be07dc37365c62c0
ms.sourcegitcommit: 2e9761a3b195d31080bff3c9cc17a18adcd5350e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2018
ms.locfileid: "25748150"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>マイクロソフトのチームでライブ イベントの設定を構成します。
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

チームのライブ イベントの設定を使用すると、組織内で保持されているライブのイベントの設定を構成します。 サポート URL を設定し、サード ・ パーティ製ビデオ配信プロバイダーを構成することができます。 これらの設定は、組織内に作成されるすべてのライブ イベントに適用されます。 

ビジネス管理センターの Microsoft のチームと Skype でこれらの設定を簡単に管理することができます。 左側のナビゲーションで**の会議**に移動する > **のライブ イベントを設定**します。 

![ライブ イベント settings.png](../media/teams-live-events-settings.png "チームのスクリーン ショットは、マイクロソフトのチームと Skype のビジネス管理センターで構成可能なイベントの設定をライブ") 

## <a name="set-up-event-support-url"></a>イベント サポートの URL を設定します

ライブ イベントの参加者には、この URL が表示されます。 ライブ イベント中に、サポートに連絡する方法を参加者に提供する組織のサポート URL を追加します。

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams--skype-for-business-admin-center"></a>![チーム ・ ロゴ ・ 30x30.png](../media/teams-logo-30x30.png) ビジネス管理センターの Microsoft のチームと Skype を使用します。

1. 左側のナビゲーションでは、**会議**に移動 > **ライブ イベントを設定**します。
2. [**サポート URL**] には、組織のサポートの URL を入力します。 

    ![サポート URL の設定、マイクロソフトのチームとビジネス管理センターの Skype でのイベントのライブ](../media/teams-live-events-settings-supporturl.png "スクリーン ショットは、チームのライブ イベントを設定する URL をサポート")

### <a name="using-windows-powershell"></a>The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.
次のコマンドレットを実行します。
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
詳細については、[一連の CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)を参照してください。
## <a name="configure-a-third-party-video-distribution-provider"></a>サード ・ パーティ製ビデオ配信プロバイダーを構成します。 

購入し、定義されているソフトウェアのネットワーク (SDN) ソリューションや Microsoft ビデオ配信パートナーを通じて、エンタープライズ コンテンツ配信ネットワーク (eCDN) ソリューションを設定すると場合、は、チームでのライブ イベントのプロバイダーを構成します。 

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams--skype-for-business-admin-center"></a>![チーム ・ ロゴ ・ 30x30.png](../media/teams-logo-30x30.png) ビジネス管理センターの Microsoft のチームと Skype を使用します。

1. 左側のナビゲーションでは、**会議**に移動 > **ライブ イベントを設定**します。
2. [**サード パーティのビデオ配信プロバイダー**では、次の手順を完了します。 

    ![マイクロソフトのチームとビジネス管理センターの Skype でのサード ・ パーティ製ビデオ配信プロバイダーの設定](../media/teams-live-events-settings-distribution-provider.png "サード ・ パーティ製ビデオ配信プロバイダーの設定のスクリーン ショットのライブ イベント")

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

### <a name="related-topics"></a>関連トピック
- [ライブ イベントをチームは何ですか。](what-are-teams-live-events.md)
- [チームのライブ イベントの計画](plan-for-teams-live-events.md)
- [チームのライブ イベントを設定します。](set-up-for-teams-live-events.md)
---
title: Microsoft Teams でライブ イベント設定を構成する
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
- highpri
description: 組織内に保持されている Teams のライブ イベントの設定を管理する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7ff5dada4c1f37c6afaf2948a5cef2b6169350d0
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767618"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Microsoft Teams でライブ イベント設定を構成する

Teams のライブ イベント設定を使用して、組織で保持されているライブ イベントの設定を構成します。 サポート URL を設定して、サード パーティ製のビデオ配信プロバイダーを設定できます。 この設定は、組織で作成したすべてのライブ イベントに適用します。

Microsoft Teams 管理センターでこの設定を簡単にできます。 左側のナビゲーションで、[**会議**]  >  [**ライブ イベント設定**] に移動します。

![Teams のライブ イベント設定のスクリーン ショット。](../media/teams-live-events-settings-new.png "Microsoft Teams 管理センターで構成できる Teams ライブ イベント設定のスクリーン ショット")

## <a name="set-up-event-support-url"></a>イベントのサポート URL を設定する

この URL は、ライブ イベントの参加者に表示されます。 ライブ イベント中にサポートへの連絡方法を参加者に提供する組織のサポートの URL を追加します。

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. 左側のナビゲーションで、[**会議**]  >  [**ライブ イベント設定**] に移動します。
2. [**サポート URL**] で組織のサポート URL を入力します。

    ![管理センターでのライブ イベントの URL 設定をサポートします。](../media/teams-live-events-settings-supporturl.png "Teams ライブ イベントのサポート URL 設定のスクリーン ショット")

### <a name="using-windows-powershell"></a>Windows PowerShell の使用

次のコマンドを実行します。

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```

詳細については、[CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps&preserve-view=true) を参照してください。

## <a name="configure-a-third-party-video-distribution-provider"></a>サード パーティ製のビデオ配信プロバイダーを設定する

Microsoft ビデオ配信パートナーを通じてソフトウェア定義ネットワーク (SDN) ソリューションまたはエンタープライズ コンテンツ配信ネットワーク (eCDN) ソリューションを購入してセット アップした場合は、Teams でライブ イベント プロバイダーを構成します。

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. 左側のナビゲーションで、[**会議**]  >  [**ライブ イベント設定**] に移動します。
2. [**サード パーティ製ビデオ配信プロバイダー**] で次を実行します。

    ![管理センターのサード パーティ製のビデオ配信プロバイダーの設定。](../media/teams-live-events-settings-distribution-provider-new.png "ライブ イベントのサード パーティ製ビデオ配信プロバイダー設定のスクリーン ショット")

    - **サード パーティの配布プロバイダー** これをオンにして、サードパーティのビデオ配信プロバイダーを有効にします。
    - **SDN プロバイダー名** お使いのプロバイダーを選択します。
    - **SDN 構成** 「SDN 構成の詳細」と入力します。

### <a name="using-windows-powershell"></a>Windows PowerShell の使用

プロバイダーの連絡先からのライセンス ID または API トークンと API テンプレートを取得し、お使いのプロバイダーに合わせて次のいずれかを実行します。

**Microsoft eCDN**
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName microsoft
```
**Hive** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
**Kollective** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
**Riverbed** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName riverbed -SdnApiTemplateUrl "{API template URL provided by Riverbed}" -SdnApiToken {API token GUID provided by Riverbed}
```
**Ramp** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName ramp -SdnRuntimeConfiguration "{Configuration provided by RAMP}"
```

詳細については、[CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps&preserve-view=true) を参照してください。

> [!NOTE]
> 外部アプリまたはデバイスを使用してライブ イベントを作成する場合は、 [eCDN プロバイダーを構成](../teams-stream-ecdn.md)する必要もあります。

>[!Note]
> 選択した eCDN ソリューションは、選択したサード パーティ プロバイダーのサービス利用規約とプライバシー ポリシーの対象となります。これにより、eCDN プロバイダーのソリューションの使用が管理されます。 eCDN プロバイダーのソリューションの使用は、Microsoft ボリューム ライセンス条項またはオンライン サービス条項の対象になりません。 サード パーティプロバイダーの条項に同意しない場合は、Microsoft Teams で eCDN ソリューションを有効にしないでください。

### <a name="related-topics"></a>関連項目

- [Teams のライブ イベントについて](what-are-teams-live-events.md)
- [Teams のライブ イベントの計画](plan-for-teams-live-events.md)
- [Teams のライブ イベントをセットアップする](set-up-for-teams-live-events.md)

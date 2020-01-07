---
title: Microsoft Teams でライブ イベント設定を構成する
author: chuckedmonson
ms.author: chucked
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 組織内に保持されている Teams のライブ イベントの設定を管理する方法について説明します。
f1keywords: ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6ad9d97c6d4dd6b7eb370bda026dbee3e33f2a32
ms.sourcegitcommit: 1de5e4d829405b75c0a87918cc7c8fa7227e0ad6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "40952840"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Microsoft Teams でライブ イベント設定を構成する

Teams のライブ イベント設定を使用して、組織で保持されているライブ イベントの設定を構成します。 サポート URL を設定して、サード パーティ製のビデオ配信プロバイダーを設定できます。 この設定は、組織で作成したすべてのライブ イベントに適用します。 

Microsoft Teams 管理センターでこの設定を簡単にできます。 左側のナビゲーションで、[**会議**]  >  [**ライブ イベント設定**] に移動します。 

![Teams ライブイベント設定のスクリーンショット](../media/teams-live-events-settings.png "Microsoft Teams 管理センターで構成できる Teams ライブイベント設定のスクリーンショット") 

## <a name="set-up-event-support-url"></a>イベントのサポート URL を設定する

この URL は、ライブ イベントの参加者に表示されます。 ライブ イベント中にサポートへの連絡方法を参加者に提供する組織のサポートの URL を追加します。

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Microsoft Teams ロゴを示すアイコン](../media/teams-logo-30x30.png) Microsoft Teams 管理センターの使用

1. 左側のナビゲーションで、[**会議**]  >  [**ライブ イベント設定**] に移動します。
2. [**サポート URL**] で組織のサポート URL を入力します。 

    ![管理センターでのライブイベントのサポート URL 設定](../media/teams-live-events-settings-supporturl.png "Teams ライブイベントのサポート URL 設定のスクリーンショット")

### <a name="using-windows-powershell"></a>Windows PowerShell の使用
次のコマンドを実行します。
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
詳細については、[CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) を参照してください。
## <a name="configure-a-third-party-video-distribution-provider"></a>サード パーティ製のビデオ配信プロバイダーを設定する 

Microsoft ビデオ配信パートナーを通じてソフトウェア定義ネットワーク (SDN) ソリューションまたはエンタープライズ コンテンツ配信ネットワーク (eCDN) ソリューションを購入してセット アップした場合は、Teams でライブ イベント プロバイダーを構成します。 

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Microsoft Teams ロゴを示すアイコン](../media/teams-logo-30x30.png) Microsoft Teams 管理センターの使用

1. 左側のナビゲーションで、[**会議**]  >  [**ライブ イベント設定**] に移動します。
2. [**サード パーティ製ビデオ配信プロバイダー**] で次を実行します。 

    ![管理センターでのサードパーティのビデオ配布プロバイダの設定](../media/teams-live-events-settings-distribution-provider.png "ライブイベントのサードパーティのビデオ配布プロバイダー設定のスクリーンショット")

    - **サード パーティ製配信プロバイダーを使用する** これを選択してサード パーティ製ビデオ配信プロバイダーを有効にします。
    - **SDN プロバイダー名** お使いのプロバイダーを選択します。
    - **プロバイダー ライセンス キー** プロバイダーの連絡先から取得したライセンス ID を入力します。
    - **SDN API テンプレート URL** プロバイダーの連絡先から取得した API のテンプレート URL を入力します。

### <a name="using-windows-powershell"></a>Windows PowerShell の使用
プロバイダーの連絡先からのライセンス ID または API トークンと API テンプレートを取得し、お使いのプロバイダーに合わせて次のいずれかを実行します。

**Hive** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
**Kollective** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
詳細については、[CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) を参照してください。

> [!NOTE]
> 外部アプリまたはデバイスを使ってライブイベントを作成する予定の場合は、 [Microsoft Stream を使用して eCDN プロバイダーを構成](https://docs.microsoft.com/stream/network-caching)する必要もあります。 

### <a name="related-topics"></a>関連トピック
- [Teams のライブ イベントについて](what-are-teams-live-events.md)
- [Teams のライブ イベントの計画](plan-for-teams-live-events.md)
- [Teams のライブ イベントをセットアップする](set-up-for-teams-live-events.md)
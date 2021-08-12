---
title: Microsoft Teams でライブ イベント設定を構成する
author: cichur
ms.author: v-cichur
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
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
description: 組織内に保持されている Teams のライブ イベントの設定を管理する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 604f33720b62d6ea675b7dc4604c3c493f88341be5a24e76c1474f6e06025b66
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54332379"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Microsoft Teams でライブ イベント設定を構成する

Teams のライブ イベント設定を使用して、組織で保持されているライブ イベントの設定を構成します。 サポート URL を設定して、サード パーティ製のビデオ配信プロバイダーを設定できます。 この設定は、組織で作成したすべてのライブ イベントに適用します。

Microsoft Teams 管理センターでこの設定を簡単にできます。 左側のナビゲーションで、[**会議**]  >  [**ライブ イベント設定**] に移動します。

![ライブ イベント設定Teamsスクリーン ショット](../media/teams-live-events-settings.png "管理センター Teamsで構成できるライブ イベント設定のスクリーン Microsoft Teamsショット")

## <a name="set-up-event-support-url"></a>イベントのサポート URL を設定する

この URL は、ライブ イベントの参加者に表示されます。 ライブ イベント中にサポートへの連絡方法を参加者に提供する組織のサポートの URL を追加します。

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Microsoft Teams のロゴが表示されたアイコン](../media/teams-logo-30x30.png) Microsoft Teams 管理センターの使用

1. 左側のナビゲーションで、[**会議**]  >  [**ライブ イベント設定**] に移動します。
2. [**サポート URL**] で組織のサポート URL を入力します。

    ![管理センターでのライブ イベントのサポート URL 設定](../media/teams-live-events-settings-supporturl.png "ライブ イベントのサポート URL 設定Teamsスクリーン ショット")

### <a name="using-windows-powershell"></a>Windows PowerShell の使用

次のコマンドを実行します。

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
詳細については、[CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) を参照してください。
## <a name="configure-a-third-party-video-distribution-provider"></a>サード パーティ製のビデオ配信プロバイダーを設定する 

Microsoft ビデオ配信パートナーを通じてソフトウェア定義ネットワーク (SDN) ソリューションまたはエンタープライズ コンテンツ配信ネットワーク (eCDN) ソリューションを購入してセット アップした場合は、Teams でライブ イベント プロバイダーを構成します。 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Microsoft Teams のロゴが表示されたアイコン](../media/teams-logo-30x30.png) Microsoft Teams 管理センターの使用

1. 左側のナビゲーションで、[**会議**]  >  [**ライブ イベント設定**] に移動します。
2. [**サード パーティ製ビデオ配信プロバイダー**] で次を実行します。 

    ![管理センターのサード パーティのビデオ配信プロバイダーの設定](../media/teams-live-events-settings-distribution-provider.png "ライブ イベントのサード パーティのビデオ配信プロバイダー設定のスクリーン ショット")

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
**Riverbed** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName riverbed -SdnApiTemplateUrl "{API template URL provided by Riverbed}" -SdnApiToken {API token GUID provided by Riverbed}
```
**Ramp** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName ramp -SdnRuntimeConfiguration "{Configuration provided by RAMP}"
```

詳細については、[CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) を参照してください。

> [!NOTE]
> 外部アプリまたはデバイスを使用してライブ イベントを作成する場合は、Microsoft Stream を使用して [eCDN](/stream/network-caching)プロバイダーを構成する必要があります。 

>[!Note]
> Microsoft Stream の使用から[会議の記録用の OneDrive for Business および SharePoint ](../tmr-meeting-recording-change.md)への変更は段階的なアプローチになります。リリース時には、この機能にオプトインできるようになります。Stream を使い続けるには、11 月にオプトアウトする必要があります。また、2021 年初頭には、すべてのお客様に、新しい会議の記録に OneDrive と SharePoint を使用するように要請する予定です。

>[!Note]
> 選択した eCDN ソリューションには、選択したサードパーティ プロバイダーのサービス利用規約とプライバシー ポリシーが適用されます。このポリシーによって、eCDN プロバイダーのソリューションの使用が管理されます。 eCDN プロバイダーのソリューションの使用には、Microsoft ボリューム ライセンス条項またはオンライン サービス条件の適用対象となんら適用されないものとします。 サードパーティ プロバイダーの条項に同意しない場合は、Microsoft Teams で eCDN ソリューションを有効にMicrosoft Teams。

### <a name="related-topics"></a>関連項目
- [Teams のライブ イベントについて](what-are-teams-live-events.md)
- [Teams のライブ イベントの計画](plan-for-teams-live-events.md)
- [Teams のライブ イベントをセットアップする](set-up-for-teams-live-events.md)

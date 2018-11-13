---
title: マイクロソフトのチームでのライブ イベントを設定します。
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
search.appverid: MET150
description: マイクロソフトのチーム、ネットワークの準備を含むライブ イベントをユーザーのスケジュールを設定し、eCDN プロバイダーの設定を有効にすると、ライセンスを割り当てることでイベントをライブを設定する手順について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6fa8e2bc277bbece7dcbd94fca397e219cdf278
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296381"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>マイクロソフトのチームでのライブ イベントを設定します。
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

ライブ イベントを設定するときにいくつかの手順を行う必要があります。

## <a name="step-1-set-up-your-network-for-live-events-in-microsoft-teams"></a>手順 1: マイクロソフトのチームでのライブ イベントのネットワークのセットアップします。
クイック スタートのライブ イベントでは、[マイクロソフトのチームの組織のネットワークを準備](https://docs.microsoft.com/microsoftteams/prepare-network)するのには必要です。  

## <a name="step-2-get-and-assign-licenses"></a>手順 2: ライセンスを取得して割り当てる
正しいライセンスの割り当てがあることを確認して[を作成し、ライブ イベントのスケジュールを設定することができますでしょうか。](#who-can-create-and-schedule-live-events)と[のライブ イベントを監視するですか?](#who-can-watch-live-events)。

## <a name="step-3-enable-live-event-scheduling-for-users"></a>手順 3: ユーザーのライブ イベントのスケジュール設定を有効にします。
チームのユーザーが行う必要があります追加の手順がある外部のエンコーダーのイベントをスケジュールするのにはユーザーのお問い合わせは、かどうかの既定では、ライブ イベントのスケジュールを有効になっています。

### <a name="for-quick-start-events"></a>クイック スタートのイベント
チーム PowerShell では、 **TeamsMeetingBroadcastPolicy**の*AllowBroadcastScheduling*コントロールの設定を使用して、ユーザーは、かに、チームでのライブ イベントを作成できるかどうか。 TeamsMeetingBroadcastPolicy の管理に関する詳細については、[ここで](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

 ユーザーに割り当てられているカスタム ポリシーが割り当てられていない場合、*グローバル*ポリシーは、既定で有効になっている記録を持っているが、ユーザーに表示されます。

*AllowBroadcastScheduling*パラメーターが*True*に設定されていることを確認します。
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
*グローバル*ポリシーの実行にユーザーを割り当てます。
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

#### <a name="user-scenarios"></a>ユーザー シナリオ
**ライブ イベントを作成できるよう、社内のすべてのユーザーをします。**

実行し、確認の場合はユーザーには、 *「ローカル*ポリシーが割り当てられているが、その*AllowBroadcastScheduling* * *True*に設定します。
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
ユーザーには、*グローバル*ポリシー以外のポリシーが割り当てられている場合、次を実行し、 *-AllowBroadcastScheduling*が*True*に設定されていることを確認します。
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```

**ライブ イベントを組織全体で 100% 無効にするスケジュールを設定します。**

ブロードキャストのスケジュールを無効にするには、実行します。
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
*グローバル*ポリシーは、実行するには、組織内のすべてのユーザーを割り当てます。
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**ライブ イベントを作成できるユーザーの数が多いが、一連のユーザーがそれらを作成することを防止します。**

一部のユーザーを有効にする) の**補助金 CsTeamsMeetingBroadcastPolicy**を使用して、*グローバル*ポリシーを割り当てるが最初次を実行して、 *AllowBroadcastScheduling*が*True*に設定されていることを確認します。
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
*グローバル*ポリシーの実行にユーザーまたはユーザーを割り当てます。
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
作成し、(無効にする)、他のユーザーに**与える CsTeamsMeetingBroadcastPolicy**コマンドレットを使用してスケジュール設定を無効にするポリシーを設定します。 

新しいポリシーを作成すると無効になっていることを実行します。
```
New-CSTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy
```
スケジュールを無効にするを実行します。
```
Set-CsTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy -AllowBroadcastScheduling $false
```
このポリシーの実行にユーザーを割り当てます。
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingpolicy -Verbose
```
**ライブのイベントを無効にするか、ユーザーの数が多いですが、それを作成するユーザーのセットを許可します。**

ブロードキャストのスケジュールを無効にするには、実行します。
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
*グローバル*ポリシーの実行にこれらのユーザーを割り当てます。
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
作成、スケジュール設定を有効にするポリシーを割り当てると、実行します。
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
スケジューリングを有効にするを実行します。
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
このポリシーの実行にユーザーを割り当てます。
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```

### <a name="for-external-encoder-events"></a>外部エンコーダーのイベント
ライブ イベントをそれらのユーザーのスケジュール設定を有効にするのには、次を行う必要があります。

#### <a name="step-1-enable-microsoft-stream-for-users-in-your-organization"></a>手順 1: のユーザー、組織 * * マイクロソフトのストリームを有効にします。
Microsoft ストリームは、対象の Office 365 サブスクリプションの一部として、またはスタンドアロン サービスとして利用できます。 詳細については、[ストリームのライセンスの概要](https://docs.microsoft.com/stream/license-overview)を参照してください。

> ![メモ]ビジネスに関する重要事項またはビジネス プレミアム プランでは、マイクロソフトのストリームが含まれていません。  

方法[Office 365 のユーザーにライセンスを割り当てる](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC)ユーザーが Microsoft のストリームにアクセスできるようにする方法の詳細について説明します。 [この資料](https://docs.microsoft.com/stream/disable-user-organization)で定義されているユーザーの Microsoft のストリームがブロックされていないことを確認します。

#### <a name="step-2-ensure-users-have-live-event-creation-permission-in-microsoft-stream"></a>手順 2: は、ユーザーは、ライブ イベントの作成のアクセス許可を持つで Microsoft * ストリーム * ことを確認します。
既定では、管理者がエンコーダーを作成する外部のライブ イベントです。 Microsoft ストリームの管理者は、ストリームでの[ライブ イベントを作成するための他のユーザーを有効にする](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating)ことができます。  

#### <a name="step-3-ensure-live-event-organizers-have-consented-to-the-company-policy-set-by-stream-admin"></a>手順 3: がライブ イベントを開催者が会社のポリシーでストリームの管理 * * に設定するに同意したことを確認します。
Microsoft ストリームには、管理者[、会社のガイドラインのポリシーを設定する](https://docs.microsoft.com/stream/company-policy-and-consent)には、従業員がコンテンツを保存する前にこのポリシーをそのまま使用する必要がありますし、ユーザーする必要がありますようにチームで (外部のエンコーダーの生産) でのライブ イベントを作成する前にします。 組織でのライブ イベントの機能をロールアウトする前にこれらのライブ イベントを作成するユーザーは、ポリシーに同意したがいることを確認します。 

## <a name="step-4-set-up-ecdn-provider-for-live-events-in-microsoft-teams"></a>手順 4: マイクロソフトのチームでのライブ イベントの eCDN のプロバイダーのセットアップします。 
適応のビットレート (ABR) のストリーミングを使用して、ライブ イベントのビデオの再生は、ユニキャスト ストリーム、つまり、万人がインターネットから自分のビデオ ストリームを取得します。 ライブ イベントや、組織の大部分に送信されるビデオは、膨大なインターネットの帯域幅のあるユーザーによって消費されている可能性があります。 ライブ イベントの場合は、このインターネット トラフィックを削減する組織では、マイクロソフトのソリューションは、統合のライブ イベントでは、ソフトウェアを提供するビデオの配信パートナーには、ネットワーク (SDNs) またはエンタープライズ ・ コンテンツ配信ネットワーク (eCDNs) が定義されている信頼されています。 これらの SDN/eCDN ・ プラットフォームを犠牲にエンド ユーザー エクスペリエンスを表示することがなくネットワークの帯域幅を最適化するために組織を有効化します。 パートナーは、エンタープライズ ネットワーク上よりスケーラブルで効率的なビデオ配信を有効にするに役立ちます。

**購入とセットアップのソリューションをマイクロソフトのチーム以外で**マイクロソフトのビデオ配信を信頼できるパートナーを活用することでビデオの配信を拡大・縮小で専門的なヘルプを取得します。 チームで使用するビデオ配信プロバイダーを有効にすることができます前に購入して外部とのチームとは別に SDN と eCDN ソリューションをセットアップします。

次の SDN と eCDN ソリューションは、事前統合されてし、Microsoft のストリームで使用する設定をすることができます。

- **ハイブのストリーミング**ビデオ配信のライブとオンデマンドのエンタープライズのシンプルかつ強力なソリューションを提供します。 ハイブは、追加のハードウェアや帯域幅は必要ありませんし、何千ものネットワークに影響を与えず、同時のビデオ ビューアーを有効にするセキュリティで保護された方法を提供するソフトウェア ・ ベースのソリューションです。 お客様への影響のビデオが、SDN と eCDN ソリューションを購入する前に、ネットワーク上にあるを理解して、ハイブのストリーミングが用意されていますブラウザ ・ ベースの分析ソリューション マイクロソフト ユーザーの場合。 [の詳細を表示](https://www.hivestreaming.com/partners/integration-partners/microsoft/)します。
 
- **Kollective**クラウド ・ ベースのスマート ピアリング配布プラットフォーム (ライブのストリーミング ・ ビデオ、オンデマンド ビデオ、ソフトウェアの更新プログラム、セキュリティ修正プログラムなど) には、さまざまな形式でコンテンツを配信する既存のネットワーク インフラストラクチャを活用するがより迅速に、確実にしより少ない帯域幅にします。 ハードウェアの追加と、世界最大の金融機関によって信頼されている、セキュリティで保護されたプラットフォームでは、セットアップと保守が容易です。 [の詳細を表示](http://www.kollective.com)します。
 
- イベントの製作者を支援するネットワーク帯域幅を最適化し、成功したライブ イベントのブロードキャストとオン ・ デマンドをサポートして、**ランプの OmniCache**は、次世代ネットワークの配分を提供し、グローバル Wan 経由でビデオ コンテンツのシームレスな配信を保証ストリーミングします。 ランプの OmniCache のライブ イベントのクイック スタートのサポートを準備中です。  [の詳細を表示](http://www.ramp.com)します。 
 
> [!NOTE] 
> 選択した eCDN ソリューションでは、選択した**サード パーティ プロバイダーのサービスとプライバシーのポリシー条件**、eCDN プロバイダーのソリューションの使用を制御するは。 マイクロソフト ボリューム ライセンス契約の条項またはオンライン サービスの条件は、eCDN プロバイダーのソリューションを使用することはできません。 **サード パーティ プロバイダーの条件**に同意しない場合はチームの eCDN ソリューション有効にしないし。 

**設定可能な「クイック スタート」eCDN のライブ イベント**PowerShell を使用するチームでは、ライブ イベントの eCDN のプロバイダーを構成できます。 

> [!NOTE] 
> 組織の 1 つの eCDN プロバイダーを構成できます。 

***ハイブ***[セット CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell コマンドレットを使用するには eCDN のプロバイダーを構成します。 まず以下を実行して、ハイブのメンバーからライセンス ID と API のテンプレートの URL を入手します。
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
***Kollective***[セット CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell コマンドレットを使用するには eCDN のプロバイダーを構成します。 最初から Kollective 相手では、API トークンおよび API のテンプレートの URL を取得し、次を実行します。
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
**「外部エンコーダー」のライブ イベントを、eCDN を設定します** 

外部エンコーダーを使用して、ライブのイベントを作成する場合は、[マイクロソフトのストリームで、eCDN のプロバイダーを構成する](https://docs.microsoft.com/stream/network-caching)にもする必要があります。 

## <a name="next-steps"></a>次のステップ
[Confgure チーム ライブ イベント](configure-teams-live-events.md)に移動します。

---
title: ネットワーク ローミング ポリシー
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
search.appverid: MET150
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
description: Teams ネットワーク ローミング ポリシーの設定を管理する方法について説明します。
ms.openlocfilehash: f8b1d78754c5f608aa76d9261b2164abc4de9194
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2022
ms.locfileid: "68585065"
---
# <a name="manage-video-and-media-settings-with-the-network-roaming-policy"></a>ネットワーク ローミング ポリシーを使用してビデオとメディアの設定を管理する

会議ポリシーを使用してビデオとメディアの設定を管理するだけでなく、TeamsNetworkRoamingPolicy を使用して、Microsoft Teams クライアントで使用される次の属性の使用を動的に制御できるようになりました。 

- IP ビデオ
- メディア ビット レート

このポリシーを使用すると、ネットワーク サイトに設定を割り当てることができます。 Teams クライアントは、接続先のネットワーク サイトに基づいて設定を動的に取得します。 Teams クライアントがローミング ポリシーが割り当てられているネットワーク サイトからサインインすると、そのポリシーが使用されます。 ポリシーが割り当てられていない場合は、会議ポリシーで設定された値が使用されます。 会議ポリシーのオーディオとビデオの設定の詳細については、「[オーディオとビデオの会議ポリシー設定](meeting-policies-audio-and-video.md)」を参照してください。

## <a name="configure-the-teamsnetworkroamingpolicy"></a>TeamsNetworkRoamingPolicy を構成する

TeamsNetworkRoamingPolicy を構成するには、次の PowerShell コマンドレットを使用します。

- [Get-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/get-csteamsnetworkroamingpolicy)
- [New-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/new-csteamsnetworkroamingpolicy)
- [Set-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/set-csteamsnetworkroamingpolicy)
- [Remove-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/remove-csteamsnetworkroamingpolicy)

TeamsNetworkRoamingPolicy には、次のパラメーターが含まれています。

- AllowIPVideo - この設定は、ユーザーがホストする会議、およびユーザーが開始する 1 対 1 の通話やグループ通話でビデオを有効にできるかどうかを制御します。

- MediaBitRateKb - この設定により、ユーザーの通話および会議でのオーディオ、ビデオ、およびビデオベースのアプリ共有送信のメディア ビット レートの合計平均が決まります。

ポリシーを構成したら、次のように [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) コマンドレットを使用して、ポリシーを 1 つ以上のネットワーク サイトに割り当てます。

```PowerShell
 Set-CsTenantNetworkSite -Identity Burlington -NetworkRoamingPolicy LowBandwidthSite
 ``` 
 
 ネットワーク サイトからポリシーを削除するには、次のコマンドレットを使用します。
 
 ```PowerShell
 Set-CsTenantNetworkSite -Identity Burlington -NetworkRoamingPolicy $null
 ```

To enable the network roaming policy for users who are not enterprise voice enabled, you must also enable the AllowNetworkConfigurationSettingsLookup setting in TeamsMeetingPolicy. This setting is off by default.

ネットワーク サイトの作成の詳細については、「[クラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)」を参照してください。 

## <a name="examples"></a>例

```PowerShell
New-CsTeamsNetworkRoamingPolicy -Identity LowBandwidthSite -AllowIPVideo $false -MediaBitRateKb 1000
```

```PowerShell
Set-CsTenantNetworkSite -Identity Burlington -NetworkRoamingPolicy LowBandwidthSite
```

## <a name="supported-clients"></a>サポートされるクライアント

- Windows 
- MacOS デスクトップ

## <a name="known-issues"></a>既知の問題

Teams Online PowerShell v 2.0.0 で New と Get-CsTeamsNetworkRoamingPolicy を指定すると、追加のデータが表示されます。


## <a name="related-topics"></a>関連項目

- [Get-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/get-csteamsnetworkroamingpolicy)
- [New-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/new-csteamsnetworkroamingpolicy)
- [Set-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/set-csteamsnetworkroamingpolicy)
- [Remove-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/remove-csteamsnetworkroamingpolicy)
- [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite)

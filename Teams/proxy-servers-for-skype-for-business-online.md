---
title: Teams または Skype for Business Online 向けのプロキシ サーバー
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark
ms.topic: reference
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: この記事では、Microsoft Teams またはSkype for Businessでプロキシ サーバーを使用する方法について説明します。
ms.openlocfilehash: b2d46cbaa46670daf0235bfd020cae90c5bf624b
ms.sourcegitcommit: 00a526c5b9829302f7c4e0631d0c2dac50b7d004
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2022
ms.locfileid: "69436683"
---
# <a name="proxy-servers-for-teams-and-skype-for-business-online"></a>Teams および Skype for Business Online 用のプロキシ サーバー

この記事では、Teams または Skype for Business でのプロキシ サーバーの使用に関するガイダンスを提供します。
  
## <a name="not-using-a-proxy-server-is-recommended"></a>プロキシ サーバーの使用はお勧めしません。

Teams またはプロキシ経由のトラフィックをSkype for Businessする場合は、プロキシのバイパスをMicrosoftすることをお勧めします。 プロキシでは、トラフィックが既に暗号化されているため、Teams や Skype for Businessのセキュリティが強化されません。
  
プロキシを使用すると、問題が発生する可能性があります。 パフォーマンス関連の問題は、Teams トラフィックをプロキシ サーバー経由でルーティングすることで、待機時間とパケット損失によって環境に発生する可能性があります。 このような問題は、このような Teams や、リアルタイム ストリームが不可欠なオーディオやビデオなどのSkype for Businessシナリオで否定的なエクスペリエンスを引き起します。

Teams トラフィックはプロキシ サーバー インフラストラクチャをバイパスすることをお勧めします。 これを実現するには、Teams 電話と会議室デバイスを独自の VLAN に配置し、インターネット アクセスを提供します。

## <a name="windows-based-teams-devices"></a>Teams デバイスのWindows-Based

Windows ベースの Teams ミーティング ルームと Surface Hubs では、一部のプロキシ サーバーがサポートされていますが、認証を必要とするプロキシ サーバーはサポートされていません。

これらのデバイスはプロキシ インフラストラクチャをバイパスし、ファイアウォール経由Microsoft 365 サービスにアクセスすることをお勧めします。

## <a name="android-based-teams-devices"></a>Teams デバイスのAndroid-Based

Teams 電話、パネル、ディスプレイ、ボードなど、Android ベースの Teams デバイスはプロキシ サーバーをサポートしていません。

これらのデバイスで実行されている特定のコンポーネントがインターネットにアクセスする方法により、すべてのトラフィックをプロキシ経由でルーティングすることはできません。 これらのデバイスとMicrosoft 365 サービス間のトラフィックがファイアウォール経由で許可されていることを確認する必要があります。

## <a name="if-you-need-to-use-a-proxy-server"></a>プロキシ サーバーを使用する必要がある場合

一部の組織では、Teams のプロキシをバイパスしたり、トラフィックをSkype for Businessしたりできません。 そのような場合は、上記の問題について注意しておく必要があります。

> [!Note]
> プロキシ インフラストラクチャでプライベート署名された証明書を使用する場合は、プライベート署名された証明書と証明書チェーンを Teams ミーティング ルーム デバイスにインストールして、デバイスが証明書を信頼できるようにする必要があります。 Teams 電話やその他の Android ベースの Teams デバイスにプライベート署名された証明書をインストールすることはサポートされていません。
  
Microsoft は次を実行することもお勧めします。
  
- ローカルの外部 DNS 解決を使用する (一部のクラウドベースのプロキシ ソリューションでは、DNS 解決が別の場所で発生する可能性があります)。

- Teams デバイスとサービスの間のパスができるだけ短く直接的であることを確認する
    
- メディアの TCP ベースのルーティングに依存するのではなく、直接 UDP ベースのルーティングを使用する
    
- ファイアウォールを介して Teams Media (3478-3481) の UDP トラフィックを許可する

- ファイアウォールを介して Azure、Office 365、Intune、Teams Room Pro (使用されている場合) 用の URL と IP をすべて許可する
    
- ネットワーク ガイドラインの他の推奨事項に従う: [Teams 用に組織のネットワークを準備する](prepare-network.md)
  
    
このガイダンスに従うことで、問題が生じる可能性が最小になります。
  
## <a name="related-topics"></a>関連項目

[Microsoft 365 および Office 365 ネットワーク接続の原則](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Teams 用に組織のネットワークを準備する](prepare-network.md)

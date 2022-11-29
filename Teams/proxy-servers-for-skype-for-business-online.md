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
ms.openlocfilehash: cdb4e6ccf05f597c87d066c18b1722eb08f89374
ms.sourcegitcommit: e9718ad7e23317d490b238b3801267cb2e6b26e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2022
ms.locfileid: "69176674"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Teams または Skype for Business Online 向けのプロキシ サーバー

この記事では、Teams または Skype for Business でのプロキシ サーバーの使用に関するガイダンスを提供します。
  
## <a name="not-using-a-proxy-server-is-recommended"></a>プロキシ サーバーの使用はお勧めしません。

Teams またはプロキシ経由のトラフィックをSkype for Businessする場合は、プロキシのバイパスをMicrosoftすることをお勧めします。 プロキシでは、トラフィックが既に暗号化されているため、Teams や Skype for Businessのセキュリティが強化されません。
  
プロキシを使用すると、問題が発生する可能性があります。 パフォーマンス関連の問題は、Teams トラフィックをプロキシ サーバー経由でルーティングすることで、待機時間とパケット損失によって環境に発生する可能性があります。 このような問題は、このような Teams や、リアルタイム ストリームが不可欠なオーディオやビデオなどのSkype for Businessシナリオで否定的なエクスペリエンスを引き起します。

Teams トラフィックはプロキシ サーバー インフラストラクチャをバイパスすることをお勧めします。

## <a name="teams-phones"></a>Teams 電話

Teams 電話はプロキシ サーバーをサポートしていません。

推奨される方法は、シグナリング (TCP 443) とメディア (UDP 3478-3481) の両方のトラフィックがプロキシ サーバー インフラストラクチャをバイパスすることです。

## <a name="teams-meeting-rooms-and-panels"></a>Teams ミーティング ルームとパネル

Teams ミーティング ルームがプロキシ インフラストラクチャをバイパスするようにすることをお勧めします。

Windows ベースの Teams ミーティング ルームではプロキシ サーバーがサポートされていますが、認証を必要とするプロキシ サーバーはサポートされていません。 Android ベースの Teams ミーティング ルームでは、プロキシ サーバーはサポートされていません。
  
## <a name="if-you-need-to-use-a-proxy-server"></a>プロキシ サーバーを使用する必要がある場合

一部の組織では、Teams のプロキシをバイパスしたり、トラフィックをSkype for Businessしたりできません。 そのような場合は、上記の問題について注意しておく必要があります。
  
Microsoft は次を実行することもお勧めします。
  
- ローカルの外部 DNS 解決を使用する (一部のクラウドベースのプロキシ ソリューションでは、DNS 解決が別の場所で発生する可能性があります)。
    
- メディアの TCP ベースのルーティングに依存するのではなく、直接 UDP ベースのルーティングを使用する
    
- UDP トラフィックの許可 (3478-3481)

- Azure、Office 365、Intune、Teams Room Pro (使用されている場合) を含むすべての必要な URL と IP を許可する
    
- ネットワーク ガイドラインの他の推奨事項に従う: [Teams 用に組織のネットワークを準備する](prepare-network.md)
  
    
このガイダンスに従うことで、問題が生じる可能性が最小になります。
  
## <a name="related-topics"></a>関連項目

[Microsoft 365 および Office 365 ネットワーク接続の原則](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Teams 用に組織のネットワークを準備する](prepare-network.md)

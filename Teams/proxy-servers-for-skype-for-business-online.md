---
title: Teams または Skype for Business Online 向けのプロキシ サーバー
ms.author: tonysmit
author: tonysmit
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
description: この記事では、Microsoft TeamsまたはSkype for Businessでプロキシ サーバーを使用する方法について説明します。
ms.openlocfilehash: 559a42c19aa47a9e72a5c0549e80f45de8d50fdf
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582161"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Teams または Skype for Business Online 向けのプロキシ サーバー

この記事では、TeamsまたはSkype for Businessでプロキシ サーバーを使用する方法に関するガイダンスを提供します。
  
## <a name="not-using-a-proxy-server-is-recommended"></a>プロキシ サーバーの使用はお勧めしません。

プロキシ経由のトラフィックのTeamsまたはSkype for Businessに関しては、プロキシをバイパスすることをお勧めします。 トラフィックは既に暗号化されているため、プロキシはTeamsやSkype for Businessの安全性を高めるわけではありません。
  
プロキシを使用すると、問題が発生する可能性があります。 パフォーマンス関連の問題は、待ち時間とパケット損失によって環境に発生する可能性があります。 このような問題により、オーディオやビデオなどのTeamsシナリオやSkype for Businessシナリオでは、リアルタイム ストリームが不可欠になります。
  
## <a name="if-you-need-to-use-a-proxy-server"></a>プロキシ サーバーを使用する必要がある場合

一部の組織では、トラフィックをTeamsまたはSkype for Businessするためのプロキシをバイパスするオプションはありません。 そのような場合は、上記の問題について注意しておく必要があります。
  
Microsoft は次を実行することもお勧めします。
  
- 外部の DNS 解決を使用する
    
- ダイレクト UDP ベースのルーティングを使用する
    
- UDP トラフィックを許可する
    
- ネットワーク ガイドラインの他の推奨事項に従う:[組織のネットワークをTeamsに準備する](prepare-network.md)
  
    
このガイダンスに従うことで、問題が生じる可能性が最小になります。
  
## <a name="related-topics"></a>関連項目

[Microsoft 365 および Office 365 ネットワーク接続の原則](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Teams 用に組織のネットワークを準備する](prepare-network.md)
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: この記事では、Microsoft Teams または Skype for Business でプロキシ サーバーを使用する方法について説明します。
ms.openlocfilehash: 0e2089cfa327a610c3ee98f1f20862a28939fd0c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117725"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Teams または Skype for Business Online 向けのプロキシ サーバー

この記事では、Teams または Skype for Business でプロキシ サーバーを使用する方法について、ガイダンスを提供します。
  
## <a name="not-using-a-proxy-server-is-recommended"></a>プロキシ サーバーの使用はお勧めしません。

プロキシ経由の Teams または Skype for Business トラフィックの場合、Microsoft はプロキシをバイパスする方法をお勧めします。 トラフィックは既に暗号化されているので、プロキシによって Teams または Skype for Business のセキュリティが高くなされません。
  
プロキシを使用すると、問題が発生する可能性があります。 パフォーマンス関連の問題は、待機時間とパケット損失によって環境に発生する可能性があります。 このような問題は、リアルタイム ストリームが不可欠な音声やビデオなどの Teams や Skype for Business のシナリオで負のエクスペリエンスを生み出します。
  
## <a name="if-you-need-to-use-a-proxy-server"></a>プロキシ サーバーを使用する必要がある場合

組織によっては、Teams または Skype for Business トラフィックのプロキシをバイパスするオプションはありません。 そのような場合は、上記の問題について注意しておく必要があります。
  
Microsoft は次を実行することもお勧めします。
  
- 外部の DNS 解決を使用する
    
- ダイレクト UDP ベースのルーティングを使用する
    
- UDP トラフィックを許可する
    
- ネットワーク ガイドラインのその他の推奨事項に従う: 組織のネットワーク [を Teams 用に準備する](prepare-network.md)
  
    
このガイダンスに従うことで、問題が生じる可能性が最小になります。
  
## <a name="related-topics"></a>関連項目

[Microsoft 365 および Office 365 ネットワーク接続の原則](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Teams 用に組織のネットワークを準備する](prepare-network.md)
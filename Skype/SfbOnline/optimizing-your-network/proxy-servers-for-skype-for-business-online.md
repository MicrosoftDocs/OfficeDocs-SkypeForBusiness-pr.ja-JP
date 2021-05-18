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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: この記事では、Skype for Business でのプロキシ サーバーの使用に関する情報を提供します。
ms.openlocfilehash: 09ed98c5f69d6e244a5f87125e4ad607e4d16226
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240416"
---
# <a name="proxy-servers-for-skype-for-business-online"></a>Skype for Business Online のプロキシ サーバー

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

この記事では、Skype for Business でのプロキシ サーバーの使用に関するガイダンスを提供します。
  
## <a name="not-using-a-proxy-server-is-recommended"></a>プロキシ サーバーの使用はお勧めしません。

プロキシ経由の Skype for Business トラフィックについては、Microsoft はプロキシをバイパスすることをお勧めします。 プロキシは、トラフィックが既に暗号化されているので、Skype for Business の安全性を高めしません。
  
プロキシを使用すると、問題が発生する可能性があります。 パフォーマンス関連の問題は、待機時間とパケット損失によって環境に発生する可能性があります。 このような問題は、リアルタイム ストリームが不可欠なオーディオやビデオなどの Teams や Skype for Business のシナリオで悪影響を及ぶ結果になります。
  
## <a name="if-you-need-to-use-a-proxy-server"></a>プロキシ サーバーを使用する必要がある場合

組織によっては、Skype for Business トラフィックのプロキシをバイパスするオプションがありません。そのような場合は、上記の問題について注意しておく必要があります。
  
Microsoft は次を実行することもお勧めします。
  
- 外部の DNS 解決を使用する
    
- ダイレクト UDP ベースのルーティングを使用する
    
- UDP トラフィックを許可する
    
- ネットワーク ガイドラインの他の推奨事項に従います。
    
  - [Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス](media-quality-and-network-connectivity-performance.md)
    
  - [Skype for Business Online 向けのネットワークの最適化](optimizing-your-network.md)
    
このガイダンスに従うことで、問題が生じる可能性が最小になります。
  
## <a name="related-topics"></a>関連項目

[Skype for Business Online 向けのネットワークの最適化](optimizing-your-network.md)
 

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
description: この記事では、Skype for Business でのプロキシサーバーの使用について説明します。
ms.openlocfilehash: a154b36fc03dc84916d5cb4bd383ff80bef901cd
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863754"
---
# <a name="proxy-servers-for-skype-for-business-online"></a>Skype for Business Online のプロキシサーバー

この記事では、Skype for Business でのプロキシサーバーの使用に関するガイダンスを提供します。
  
## <a name="not-using-a-proxy-server-is-recommended"></a>プロキシ サーバーの使用はお勧めしません。

プロキシ経由の Skype for Business トラフィックについては、Microsoft はプロキシをバイパスすることをお勧めします。 プロキシでは、トラフィックが既に暗号化されているため、Skype for Business のセキュリティを強化することはできません。
  
また、プロキシを使用すると問題が発生する可能性があります。 パフォーマンスに関連する問題は、待ち時間とパケット損失によって環境に導入される可能性があります。 このような問題が発生した場合、そのようなチームまたは Skype for Business のシナリオでは、リアルタイムのストリームが不可欠であるため、オーディオとビデオとして、否定的な経験が発生する可能性があります。
  
## <a name="if-you-need-to-use-a-proxy-server"></a>プロキシ サーバーを使用する必要がある場合

組織によっては、Skype for Business トラフィックのプロキシをバイパスするオプションがありません。そのような場合は、上記の問題について注意しておく必要があります。
  
Microsoft は次を実行することもお勧めします。
  
- 外部の DNS 解決を使用する
    
- ダイレクト UDP ベースのルーティングを使用する
    
- UDP トラフィックを許可する
    
- ネットワークガイドラインのその他の推奨事項に従ってください。
    
  - [Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス](media-quality-and-network-connectivity-performance.md)
    
  - [Skype for Business Online 向けのネットワークの最適化](optimizing-your-network.md)
    
このガイダンスに従うことで、問題が生じる可能性が最小になります。
  
## <a name="related-topics"></a>関連トピック

[Skype for Business Online 向けのネットワークの最適化](optimizing-your-network.md)
 
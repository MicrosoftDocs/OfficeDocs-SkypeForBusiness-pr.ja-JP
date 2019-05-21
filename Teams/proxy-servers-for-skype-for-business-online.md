---
title: Teams または Skype for Business Online のプロキシサーバー
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: reference
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection: M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: この記事では、Teams または Skype for Business でのプロキシサーバーの使用について説明します。
ms.openlocfilehash: e0733393a40c2d2c2fd62d986a4b4d66d0c2c35f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304371"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Teams または Skype for Business Online のプロキシサーバー

この記事では、Teams または Skype for Business でのプロキシサーバーの使用に関するガイダンスを提供します。
  
## <a name="not-using-a-proxy-server-is-recommended"></a>プロキシ サーバーの使用はお勧めしません。

プロキシ経由の Teams または Skype for Business トラフィックについては、プロキシをバイパスすることをお勧めします。 プロキシは、トラフィックが既に暗号化されているため、チームまたは Skype for Business の安全性を高めません。
  
また、プロキシを使用すると問題が発生する可能性があります。 パフォーマンスに関連する問題は、待ち時間とパケット損失によって環境に導入される可能性があります。 このような問題が発生した場合、そのようなチームまたは Skype for Business のシナリオでは、リアルタイムのストリームが不可欠であるため、オーディオとビデオとして、否定的な経験が発生する可能性があります。
  
## <a name="if-you-need-to-use-a-proxy-server"></a>プロキシ サーバーを使用する必要がある場合

組織によっては、Teams または Skype for Business のトラフィックに対してプロキシをバイパスするオプションがありません。 そのような場合は、上記の問題について注意しておく必要があります。
  
Microsoft は次を実行することもお勧めします。
  
- 外部の DNS 解決を使用する
    
- ダイレクト UDP ベースのルーティングを使用する
    
- UDP トラフィックを許可する
    
- ネットワークガイドラインのその他の推奨事項に従ってください。
    
  - [Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [Skype for Business Online 向けのネットワークの最適化](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
このガイダンスに従うことで、問題が生じる可能性が最小になります。
  
## <a name="related-topics"></a>関連トピック

[Skype for Business Online 向けのネットワークの最適化](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 
---
title: "Skype for Business Online 向けのプロキシ サーバー"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "この記事は、Skype for Business でのプロキシ サーバーの使用に関するガイダンスを提供します。"
ms.openlocfilehash: 325e48c7bfaeffca7c34915e176772f0824903f6
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="proxy-servers-for-skype-for-business-online"></a>Skype for Business Online 向けのプロキシ サーバー

[] この記事は、Skype for Business でのプロキシ サーバーの使用に関するガイダンスを提供します。
  
## <a name="not-using-a-proxy-server-is-recommended"></a>プロキシ サーバーの使用はお勧めしません。

プロキシ経由の Skype for Business トラフィックについては、Microsoft はプロキシをバイパスすることをお勧めします。トラフィックは既に暗号化されているため、プロキシによって Skype for Business のセキュリティがさらに強くなることはありません。
  
パフォーマンスに関連する問題が、遅延時間とパケット損失によって環境に生じる可能性があります。このような問題は、Skype for Business 使用時の音声やビデオにおけるエクスペリエンスの低下につながります。
  
## <a name="if-you-need-to-use-a-proxy-server"></a>プロキシ サーバーを使用する必要がある場合

組織によっては、Skype for Business トラフィックのプロキシをバイパスするオプションがありません。そのような場合は、上記の問題について注意しておく必要があります。
  
Microsoft は次を実行することもお勧めします。
  
- 外部の DNS 解決を使用する
    
- ダイレクト UDP ベースのルーティングを使用する
    
- UDP トラフィックを許可する
    
- 次のネットワーキング ガイドラインのその他の推奨事項に従う
    
  - [Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [Skype for Business Online 向けのネットワークの最適化](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
このガイダンスに従うことで、問題が生じる可能性が最小になります。
  
## <a name="proxy-vendors-with-built-in-skype-for-business-support-or-configuration-options"></a>組み込みの Skype for Business サポートまたは構成オプションを備えたプロキシ ベンダー

このセクションは、Skype for Business トラフィックに対して正常に機能することが証明されている製品またはサービスを提供するプロキシ ベンダーについての情報を示します。
  
**Blue Coat プロキシ ソリューション** を使用する組織に対しては、次の複数の問題に対処する新しいファームウェアがリリースされています。
    
  - SSL 傍受
    
  - OCSP/SRL チェック
    
  - TLS 経由の SIP
    
  - TURN に対するサポート
    
Skype for Business に対する Blue Coat のネイティブ サポートは簡単に有効にすることができ、関連トラフィックの識別と、適切な管理が実現します。これにより最適な認証、シグナリング、メディア トラフィック フローを確実に行えるようになり、セキュリティ上の心配がない優れたユーザー エクスペリエンスが提供されます。
    
Bluecoat のプロキシが、ネットワーク トポロジの一部である場合、次のリンクを参照してください: https://support.symantec.com/en_US/article.DOC9757.html

## <a name="related-topics"></a>関連トピック

[Skype for Business Online 向けのネットワークの最適化](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
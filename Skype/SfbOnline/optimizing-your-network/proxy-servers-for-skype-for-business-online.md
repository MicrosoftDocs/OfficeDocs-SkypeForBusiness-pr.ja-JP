---
title: "Skype for Business Online のプロキシ サーバー"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: "この記事にプロキシ サーバーを skype for Business を使ってに関するガイダンスを支援します。"
ms.openlocfilehash: 19c12ed4265c6549f00b54b3463215702d3ced2b
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="proxy-servers-for-skype-for-business-online"></a>Skype for Business Online のプロキシ サーバー

この記事にプロキシ サーバーを skype for Business を使ってに関するガイダンスを支援します。
  
## <a name="not-using-a-proxy-server-is-recommended"></a>推奨プロキシ サーバーを使用しません。

際に Skype ビジネス トラフィック用プロキシ経由で、プロキシのバイパスをお勧めします。プロキシしない Skype for Business をより安全にトラフィックが既に暗号化されているためです。
  
プロキシのある問題が発生することができます。パフォーマンスに関連する問題を導入して、遅延とパケット損失をすることができます。これらなどの問題がリアルタイム ストリームが必須として、音声、ビデオ、ビジネス シナリオには、このような Skype で負のエクスペリエンスで発生します。
  
## <a name="if-you-need-to-use-a-proxy-server"></a>プロキシ サーバーを使用する必要がある場合

一部の組織には、Skype for Business のトラフィック用のプロキシを使用しないオプションもありますありません。大文字と小文字の場合は、前述の問題を考慮する必要があります。
  
強くお勧めします。
  
- 外部の DNS 解決を使用します。
    
- ベースのルーティングを直接 UDP を使用します。
    
- UDP トラフィックを許可します。
    
- ネットワーク ガイドラインで他の推奨事項します。
    
  - [メディアの品質と skype for Business Online のネットワーク接続パフォーマンス](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [Skype for Business Online のネットワークを最適化します。](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
このガイドをフォローすると、潜在的な問題を最小化する必要があります。
  
## <a name="proxy-vendors-with-built-in-skype-for-business-support-or-configuration-options"></a>組み込みの Skype for Business のサポートや設定のオプションのプロキシ仕入先

このセクションには、製品やがビジネス トラフィック用 Skype で正常に動作する実証されているサービスを提供するプロキシ ベンダーに関する情報が含まれます。
  
**Bluecoat プロキシ ソリューション**を使用して組織の場合、新しいファームウェアがリリースされましたいくつかの問題に対処します。
    
  - SSL 傍受
    
  - OCSP/SRL チェック
    
  - TLS 経由で SIP します。
    
  - サポートを有効にします。
    
Skype for Business の bluecoat のネイティブでサポート簡単にできる、関連するトラフィックを識別するためにできるようにし、適切に管理できます。最適な認証では、通知、これによりし、メディア トラフィック フローは、セキュリティ上の問題なく優れたユーザー エクスペリエンスを提供します。
    
Bluecoat プロキシが、ネットワーク トポロジの一部である場合は、次のリンクを参照してください: https://support.symantec.com/en_US/article.DOC9757.html

## <a name="related-topics"></a>関連トピック

[Skype for Business Online のネットワークを最適化します。](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
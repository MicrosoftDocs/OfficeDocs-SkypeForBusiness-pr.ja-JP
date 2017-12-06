---
title: "Skype for Business Online 向けのプロキシ サーバー"
ms.author: tonysmit
author: tonysmit
ms.date: 11/6/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
description: "この記事は、Skype for Business でのプロキシ サーバーの使用に関するガイダンスを提供します。"
---

# Skype for Business Online 向けのプロキシ サーバー

> [!IMPORTANT]
> この記事は機械翻訳されています。機械翻訳についての「[免責事項](7acaf2c2-35fa-490f-84cd-822e446e0fc7.md#MT_Footer)」をお読みください。この記事の英語版を参照するには、[ここ](https://support.office.com/en-us/article/7acaf2c2-35fa-490f-84cd-822e446e0fc7)をクリックしてください。 
  
この記事は、Skype for Business でのプロキシ サーバーの使用に関するガイダンスを提供します。
  
## プロキシ サーバーの使用はお勧めしません。

プロキシ経由の Skype for Business トラフィックについては、Microsoft はプロキシをバイパスすることをお勧めします。トラフィックは既に暗号化されているため、プロキシによって Skype for Business のセキュリティがさらに強くなることはありません。
  
パフォーマンスに関連する問題が、遅延時間とパケット損失によって環境に生じる可能性があります。このような問題は、Skype for Business 使用時の音声やビデオにおけるエクスペリエンスの低下につながります。
  
## プロキシ サーバーを使用する必要がある場合

一部の組織には、Skype for Business のトラフィック用のプロキシを使用しないオプションもありますありません。大文字と小文字の場合は、前述の問題を考慮する必要があります。
  
Microsoft は次を実行することもお勧めします。
  
- 外部の DNS 解決を使用する
    
- ダイレクト UDP ベースのルーティングを使用する
    
- UDP トラフィックを許可する 
    
- 次のネットワーキング ガイドラインのその他の推奨事項に従う
    
  - [Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [Skype for Business Online 向けのネットワークの最適化](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
このガイダンスに従うことで、問題が生じる可能性が最小になります。
  
## 組み込みの Skype for Business サポートまたは構成オプションを備えたプロキシ ベンダー

このセクションは、Skype for Business トラフィックに対して正常に機能することが証明されている製品またはサービスを提供するプロキシ ベンダーについての情報を示します。
  
- **Blue Coat プロキシ ソリューション** を使用する組織に対しては、次の複数の問題に対処する新しいファームウェアがリリースされています。
    
  - SSL 傍受
    
  - OCSP/SRL チェック
    
  - TLS 経由の SIP
    
  - TURN に対するサポート
    
    Skype for Business に対する Blue Coat のネイティブ サポートは簡単に有効にすることができ、関連トラフィックの識別と、適切な管理が実現します。これにより最適な認証、シグナリング、メディア トラフィック フローを確実に行えるようになり、セキュリティ上の心配がない優れたユーザー エクスペリエンスが提供されます。
    
    Bluecoat プロキシが、ネットワーク トポロジの一部である場合は、次のリンクを参照してください。
    
- https://support.symantec.com/en_US/article.DOC9757.html
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **機械翻訳についての免責事項**: この記事の翻訳はコンピューター システムによって行われており、人間の手は加えられていません。マイクロソフトでは、英語を話さないユーザーがマイクロソフトの製品、サービス、テクノロジに関するコンテンツを理解するのに役立てるため、こうした機械翻訳を提供しています。記事は機械翻訳されているため、用語、構文、文法などに誤りがある場合があります。 
  


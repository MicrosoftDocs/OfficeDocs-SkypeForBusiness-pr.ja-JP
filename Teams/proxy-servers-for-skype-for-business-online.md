---
title: チームやビジネス オンラインの Skype のプロキシ サーバー
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: この資料では、ビジネスのためのチームまたは Skype でプロキシ サーバーを使用する方法の情報を提供します。
ms.openlocfilehash: 1b25d0554ec8c5dca113be0842149dae11850b7e
ms.sourcegitcommit: 327fe807b461aff18b06449f06b9e51ce393c4bc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2019
ms.locfileid: "29972212"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>チームやビジネス オンラインの Skype のプロキシ サーバー

この資料では、ビジネスのためのチームまたは Skype でプロキシ サーバーを使用する方法のガイダンスを提供します。
  
## <a name="not-using-a-proxy-server-is-recommended"></a>プロキシ サーバーの使用はお勧めしません。

に関してはチームまたは Skype ビジネス トラフィックのプロキシを介して場合、は、プロキシをバイパスすることをお勧めします。 プロキシを作成しないチームやビジネス用の Skype よりセキュリティで保護されたトラフィックが既に暗号化されているためです。
  
プロキシを持つと、問題が発生することができます。 パフォーマンス関連の問題は、遅延とパケット損失を環境に導入できます。 リアルタイム ストリームが必要なオーディオとビデオ、ビジネス シナリオのようなチームや Skype での負の経験ではこれらの問題が発生します。
  
## <a name="if-you-need-to-use-a-proxy-server"></a>プロキシ サーバーを使用する必要がある場合

一部の組織があるチームまたは Skype のビジネスのトラフィックのプロキシをバイパスするオプションなし。 そのような場合は、上記の問題について注意しておく必要があります。
  
Microsoft は次を実行することもお勧めします。
  
- 外部の DNS 解決を使用する
    
- ダイレクト UDP ベースのルーティングを使用する
    
- UDP トラフィックを許可する
    
- ネットワーク ガイドラインの他の推奨事項に従います。
    
  - [Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [Skype for Business Online 向けのネットワークの最適化](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
このガイダンスに従うことで、問題が生じる可能性が最小になります。
  
## <a name="related-topics"></a>関連トピック

[Skype for Business Online 向けのネットワークの最適化](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 
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
description: この記事では、Microsoft Teams または Skype for Business でのプロキシサーバーの使用に関する情報を提供します。
ms.openlocfilehash: 5a0d35ee2b8c95c4dea30886497e184f57077264
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905679"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Teams または Skype for Business Online 向けのプロキシ サーバー

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
    
- ネットワークガイドラインのその他の推奨事項に従う: [Teams 用に組織のネットワークを準備](prepare-network.md)する
  
    
このガイダンスに従うことで、問題が生じる可能性が最小になります。
  
## <a name="related-topics"></a>関連項目

[Office 365 のネットワーク接続の原則](https://aka.ms/pnc)

[Teams 用に組織のネットワークを準備する](prepare-network.md)

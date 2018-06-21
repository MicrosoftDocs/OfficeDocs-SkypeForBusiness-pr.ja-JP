---
title: ディレクター (計画ツール)
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: ディレクターは、ユーザーの要求を認証することができますが、すべてのユーザー アカウントのホームがないビジネス サーバー通信ソフトウェアの Skype を実行しているサーバーです。
ms.openlocfilehash: a1920d11ed354cab3409a9f2a1fd39280ce2d29d
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2018
ms.locfileid: "19975989"
---
# <a name="director-planning-tool"></a>ディレクター (計画ツール)
 
ディレクターは、ユーザーの要求を認証することができますが、すべてのユーザー アカウントのホームがないビジネス サーバー通信ソフトウェアの Skype を実行しているサーバーです。 
  
この役割は、オプションですが、次の 2 つのシナリオでディレクターを展開するように選択します。
  
- エッジ サーバーを展開することで外部のユーザーによるアクセスを有効にした場合もディレクターを展開する必要があります。 このシナリオでは、ディレクターは、外部ユーザーの認証し、内部サーバーへのトラフィックを通過し。 ディレクターが使用すると、外部ユーザーを認証するためにフロント エンド プールのサーバーこれらのユーザーの認証を実行するためのオーバーヘッドからを緩和します。 サービス拒否の攻撃などの悪意のあるトラフィックから内部のフロント エンド プールを分離することもできます。 ネットワークは、このような攻撃での無効な外部トラフィックであふれ、このトラフィックはディレクターで終了します。
    
- セントラル サイトに複数のフロント エンド プールを展開する場合は、ディレクターをそのサイトに追加することによって認証要求を効率化してパフォーマンスを向上できます。 このシナリオでは、すべての要求では、ディレクターでは、適切なフロント エンド プールにルーティングすることに最初に移動します。
    


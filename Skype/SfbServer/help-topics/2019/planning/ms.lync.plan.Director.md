---
title: Director (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
ROBOTS: NOINDEX, NOFOLLOW
description: ディレクターは、ユーザーの要求を認証することができますが、すべてのユーザー アカウントのホームがないビジネス サーバー通信ソフトウェアの Skype を実行しているサーバーです。
ms.openlocfilehash: 9ba73f88ba58abd25cdbd11b2efa5129b0322cfd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33889501"
---
# <a name="director-planning-tool"></a>Director (Planning Tool)
 
ディレクターは、ユーザーの要求を認証することができますが、すべてのユーザー アカウントのホームがないビジネス サーバー通信ソフトウェアの Skype を実行しているサーバーです。 
  
この役割は、オプションですが、次の 2 つのシナリオでディレクターを展開するように選択します。
  
- エッジ サーバーを展開することで外部のユーザーによるアクセスを有効にした場合もディレクターを展開する必要があります。 このシナリオでは、ディレクターは、外部ユーザーの認証し、内部サーバーへのトラフィックを通過し。 ディレクターが使用すると、外部ユーザーを認証するためにフロント エンド プールのサーバーこれらのユーザーの認証を実行するためのオーバーヘッドからを緩和します。 サービス拒否の攻撃などの悪意のあるトラフィックから内部のフロント エンド プールを分離することもできます。 ネットワークは、このような攻撃での無効な外部トラフィックであふれ、このトラフィックはディレクターで終了します。
    
- セントラル サイトに複数のフロント エンド プールを展開する場合は、ディレクターをそのサイトに追加することによって認証要求を効率化してパフォーマンスを向上できます。 このシナリオでは、すべての要求では、ディレクターでは、適切なフロント エンド プールにルーティングすることに最初に移動します。
    


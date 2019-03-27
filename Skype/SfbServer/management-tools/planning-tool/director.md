---
title: Director (Planning Tool)
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/8/2016
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: ディレクターは、ユーザーの要求を認証することができますが、すべてのユーザー アカウントのホームがないビジネス サーバー 2015 通信ソフトウェアの Skype を実行しているサーバーです。
ms.openlocfilehash: b6cdecd01183f8e249aaf97e6b4e7bbbbfcbe7cd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885306"
---
# <a name="director-planning-tool"></a>Director (Planning Tool)
 
ディレクターは、ユーザーの要求を認証することができますが、すべてのユーザー アカウントのホームがないビジネス サーバー 2015 通信ソフトウェアの Skype を実行しているサーバーです。 
  
この役割は、オプションですが、次の 2 つのシナリオでディレクターを展開するように選択します。
  
- エッジ サーバーを展開することで外部のユーザーによるアクセスを有効にした場合もディレクターを展開する必要があります。 このシナリオでは、ディレクターは、外部ユーザーの認証し、内部サーバーへのトラフィックを通過し。 ディレクターが使用すると、外部ユーザーを認証するためにフロント エンド プールのサーバーこれらのユーザーの認証を実行するためのオーバーヘッドからを緩和します。 サービス拒否の攻撃などの悪意のあるトラフィックから内部のフロント エンド プールを分離することもできます。 ネットワークは、このような攻撃での無効な外部トラフィックであふれ、このトラフィックはディレクターで終了します。
    
- セントラル サイトに複数のフロント エンド プールを展開する場合は、ディレクターをそのサイトに追加することによって認証要求を効率化してパフォーマンスを向上できます。 このシナリオでは、すべての要求では、ディレクターでは、適切なフロント エンド プールにルーティングすることに最初に移動します。
    


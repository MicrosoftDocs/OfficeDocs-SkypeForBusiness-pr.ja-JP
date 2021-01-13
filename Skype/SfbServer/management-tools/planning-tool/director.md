---
title: ディレクター (計画ツール)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: ディレクターは、Skype for Business Server 2015 通信ソフトウェアを実行しているサーバーで、ユーザー要求を認証できますが、ユーザー アカウントは存在しません。
ms.openlocfilehash: 76315e9f63e1121119f3823187c379985c4914f0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834937"
---
# <a name="director-planning-tool"></a>ディレクター (計画ツール)
 
ディレクターは、Skype for Business Server 2015 通信ソフトウェアを実行しているサーバーで、ユーザー要求を認証できますが、ユーザー アカウントは含めことはできません。 
  
この役割は省略可能です。次の 2 つのシナリオでディレクターを展開します。
  
- エッジ サーバーを展開して外部ユーザーによるアクセスを有効にする場合は、ディレクターも展開する必要があります。 このシナリオでは、ディレクターは外部ユーザーを認証し、そのトラフィックを内部サーバーに渡します。 ディレクターを使用して外部ユーザーを認証すると、フロントエンド プール サーバーがこれらのユーザーの認証を実行するオーバーヘッドを軽減します。 また、サービス拒否攻撃などの悪意のあるトラフィックから内部フロント エンド プールを保護するのにも役立ちます。 このような攻撃でネットワークに無効な外部トラフィックが殺到しても、このトラフィックはディレクターで終了します。
    
- 中央サイトに複数のフロントエンド プールを展開する場合は、ディレクターをそのサイトに追加することで、認証要求を合理化し、パフォーマンスを向上させることができます。 このシナリオでは、すべての要求が最初にディレクターに送信され、次に適切なフロントエンド プールにルーティングされます。
    


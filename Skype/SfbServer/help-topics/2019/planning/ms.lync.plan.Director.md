---
title: ディレクター (計画ツール)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
ROBOTS: NOINDEX, NOFOLLOW
description: ディレクターは、ユーザー要求を認証Skype for Business Server、ユーザー アカウントは含めない通信ソフトウェアを実行しているサーバーです。
ms.openlocfilehash: 26a6e7e0807f29622214d733b1d848180a3e437c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58597141"
---
# <a name="director-planning-tool"></a>ディレクター (計画ツール)
 
ディレクターは、ユーザー要求を認証Skype for Business Server、ユーザー アカウントは含めない通信ソフトウェアを実行しているサーバーです。 
  
この役割はオプションですが、次の 2 つのシナリオでディレクターの展開を選択します。
  
- エッジ サーバーを展開して外部ユーザーによるアクセスを有効にする場合は、ディレクターも展開する必要があります。 このシナリオでは、ディレクターは外部ユーザーを認証し、そのトラフィックを内部サーバーに渡します。 ディレクターを使用して外部ユーザーを認証すると、フロントエンド プール サーバーは、これらのユーザーの認証を実行するオーバーヘッドから解放されます。 また、内部フロントエンド プールをサービス拒否攻撃などの悪意のあるトラフィックから保護するのにも役立ちます。 このような攻撃でネットワークに無効な外部トラフィックが殺到しても、このトラフィックはディレクターで終了します。
    
- 中央サイトに複数のフロントエンド プールを展開する場合は、ディレクターをそのサイトに追加することで、認証要求を合理化し、パフォーマンスを向上させることができます。 このシナリオでは、すべての要求が最初にディレクターに移動し、その要求を正しいフロントエンド プールにルーティングします。
    


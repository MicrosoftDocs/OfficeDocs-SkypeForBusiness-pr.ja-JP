---
title: Skype for Business Serverディレクター計画ツール
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 4/8/2016
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
description: ディレクターは、2015 年Skype for Business Serverを実行しているサーバーで、ユーザー要求を認証できますが、ユーザー アカウントは使用しません。
---

# <a name="skype-for-business-server-director-planning-tool"></a>Skype for Business Serverディレクター計画ツール
 
ディレクターは、2015 年Skype for Business Serverを実行しているサーバーで、ユーザー要求を認証できますが、ユーザー アカウントは使用しません。 
  
この役割はオプションですが、次の 2 つのシナリオでディレクターの展開を選択します。
  
- エッジ サーバーを展開してゲスト ユーザーによるアクセスを有効にする場合は、ディレクターも展開する必要があります。 このシナリオでは、ディレクターはゲストを認証し、そのトラフィックを内部サーバーに渡します。 ディレクターを使用してゲストを認証すると、フロントエンド プール サーバーは、これらのユーザーの認証を行うオーバーヘッドから解放されます。 また、内部フロントエンド プールをサービス拒否攻撃などの悪意のあるトラフィックから保護するのにも役立ちます。 このような攻撃でネットワークに無効な外部トラフィックが殺到しても、このトラフィックはディレクターで終了します。
    
- 中央サイトに複数のフロントエンド プールを展開する場合は、ディレクターをそのサイトに追加することで、認証要求を合理化し、パフォーマンスを向上させることができます。 このシナリオでは、すべての要求が最初にディレクターに移動し、その要求を正しいフロントエンド プールにルーティングします。
    


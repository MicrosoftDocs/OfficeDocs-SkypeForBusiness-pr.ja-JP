---
title: 通話受付管理のリセット
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 従来のフロントエンド プールが通話受付管理 (CAC) をホストしている場合は、従来のフロント エンド プールを削除する前に、CAC ホスティングを Skype for Business Server 2019 プールに移動する必要があります。
ms.openlocfilehash: f660f14adfcdee64d9fa4c79e08393d4f0a0af2d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583451"
---
# <a name="reset-call-admission-control"></a>通話受付管理のリセット

従来のフロントエンド プールが通話受付管理 (CAC) をホストしている場合は、従来のフロント エンド プールを削除する前に、CAC ホスティングを Skype for Business Server 2019 プールに移動する必要があります。
  
### <a name="to-reset-cac"></a>CAC をリセットするには

1. トポロジ ビルダーを開きます。
    
2. サイト ノードを右クリックし、[**プロパティの編集**] をクリックします。
    
3. [**通話受付管理の設定**] で、[**通話受付管理の有効化**] が選択されていることを確認します。 
    
4. [**通話受付制御 (CAC)** を実行するフロントエンド プール] で、CAC をホストする Skype for Business Server 2019 プールを選択し **、[OK] をクリックします**。
    
5. トポロジを公開します。
    


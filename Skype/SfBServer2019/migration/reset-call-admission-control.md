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
localization_priority: Normal
description: 従来のフロントエンド プールが通話受付管理 (CAC) をホストしている場合は、従来のフロント エンド プールを削除する前に、CAC ホスティングを Skype for Business Server 2019 プールに移動する必要があります。
ms.openlocfilehash: c3ebb748d877e88060b699b1599c39038124565df361c5032533260e4c5643e2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54334569"
---
# <a name="reset-call-admission-control"></a>通話受付管理のリセット

従来のフロントエンド プールが通話受付管理 (CAC) をホストしている場合は、従来のフロント エンド プールを削除する前に、CAC ホスティングを Skype for Business Server 2019 プールに移動する必要があります。
  
### <a name="to-reset-cac"></a>CAC をリセットするには

1. トポロジ ビルダーを開きます。
    
2. サイト ノードを右クリックし、[**プロパティの編集**] をクリックします。
    
3. [**通話受付管理の設定**] で、[**通話受付管理の有効化**] が選択されていることを確認します。 
    
4. [**通話受付制御 (CAC)** を実行するフロントエンド プール] で、CAC をホストする Skype for Business Server 2019 プールを選択し **、[OK] をクリックします**。
    
5. トポロジを公開します。
    


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
description: 従来のフロントエンドプールが通話受付管理 (CAC) をホストしている場合は、従来のフロントエンドプールを削除する前に、CAC ホスティングを Skype for Business Server 2019 プールに移動する必要があります。
ms.openlocfilehash: 850ab5c13483d024d52c483c63ef09468f8374b3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753299"
---
# <a name="reset-call-admission-control"></a>通話受付管理のリセット

従来のフロントエンドプールが通話受付管理 (CAC) をホストしている場合は、従来のフロントエンドプールを削除する前に、CAC ホスティングを Skype for Business Server 2019 プールに移動する必要があります。
  
### <a name="to-reset-cac"></a>CAC をリセットするには

1. トポロジ ビルダーを開きます。
    
2. サイト ノードを右クリックし、[**プロパティの編集**] をクリックします。
    
3. [**通話受付管理の設定**] で、[**通話受付管理の有効化**] が選択されていることを確認します。 
    
4. [**フロントエンドプール] で通話受付管理 (cac) を実行する**には、cac をホストする Skype For business Server 2019 プールを選択し、[ **OK**] をクリックします。
    
5. トポロジを公開します。
    


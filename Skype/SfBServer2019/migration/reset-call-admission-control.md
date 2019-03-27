---
title: 通話受付管理のリセット
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 従来のフロント エンド プールは、呼受付制御 (CAC) でホストされている場合、CAC は、従来のフロント エンド プールを削除する前に、Skype のビジネス サーバー 2019 プールにホストを移動する必要があります。
ms.openlocfilehash: 3b94322b86feb2c647f88102617ab1dcc9d5f8bc
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895776"
---
# <a name="reset-call-admission-control"></a>通話受付管理のリセット

従来のフロント エンド プールは、呼受付制御 (CAC) でホストされている場合、CAC は、従来のフロント エンド プールを削除する前に、Skype のビジネス サーバー 2019 プールにホストを移動する必要があります。
  
### <a name="to-reset-cac"></a>CAC をリセットするのには

1. トポロジ ビルダーを開きます。
    
2. [サイト] ノードを右クリックし、**プロパティの編集**] をクリックします。
    
3. **呼の受付制御の設定**、[**電話受付制御を有効にする**が選択されていることを確認します。 
    
4. **呼受付制御 (CAC) を実行するフロント エンド プール**] の下には、CAC をホストするビジネス サーバー 2019 プールの Skype を選択し、[ **OK**] をクリックします。
    
5. トポロジを公開します。
    


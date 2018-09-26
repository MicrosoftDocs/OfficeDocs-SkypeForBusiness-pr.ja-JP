---
title: 通話受付管理のリセット
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 従来のフロント エンド プールは、呼受付制御 (CAC) でホストされている場合、CAC は、従来のフロント エンド プールを削除する前に、Skype のビジネス サーバー 2019 プールにホストを移動する必要があります。
ms.openlocfilehash: 65d56d000c5bcec5f7aae73413c287dee8ab29ca
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027320"
---
# <a name="reset-call-admission-control"></a>通話受付管理のリセット

従来のフロント エンド プールは、呼受付制御 (CAC) でホストされている場合、CAC は、従来のフロント エンド プールを削除する前に、Skype のビジネス サーバー 2019 プールにホストを移動する必要があります。
  
### <a name="to-reset-cac"></a>CAC をリセットするのには

1. トポロジ ビルダーを開きます。
    
2. [サイト] ノードを右クリックし、**プロパティの編集**] をクリックします。
    
3. **呼の受付制御の設定**、[**電話受付制御を有効にする**が選択されていることを確認します。 
    
4. **呼受付制御 (CAC) を実行するフロント エンド プール**] の下には、CAC をホストするビジネス サーバー 2019 プールの Skype を選択し、[ **OK**] をクリックします。
    
5. トポロジを公開します。
    


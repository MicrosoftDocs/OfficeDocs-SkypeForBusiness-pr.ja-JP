---
title: 通話受付管理のリセット
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 従来のフロントエンドプールが通話受付制御 (CAC) をホストしている場合は、従来のフロントエンドプールを削除する前に、CAC ホスティングを Skype for Business Server 2019 プールに移動する必要があります。
ms.openlocfilehash: cbc481e55d044ef196bd91dbfa8f7ebc796f28b5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812805"
---
# <a name="reset-call-admission-control"></a>通話受付管理のリセット

従来のフロントエンドプールが通話受付制御 (CAC) をホストしている場合は、従来のフロントエンドプールを削除する前に、CAC ホスティングを Skype for Business Server 2019 プールに移動する必要があります。
  
### <a name="to-reset-cac"></a>CAC をリセットするには

1. トポロジビルダーを開きます。
    
2. サイトノードを右クリックし、[プロパティの**編集**] をクリックします。
    
3. 「**通話受付制御の設定**」で、「**通話受付制御を有効にする**」が選択されていることを確認します。 
    
4. [**フロントエンドプール] で通話受付制御 (cac) を実行する**には、cac をホストする Skype For business Server 2019 プールを選び、[ **OK]** をクリックします。
    
5. トポロジを公開します。
    


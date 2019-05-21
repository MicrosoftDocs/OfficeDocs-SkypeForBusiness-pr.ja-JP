---
title: 通話受付管理のリセット
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 従来のフロントエンドプールが通話受付制御 (CAC) をホストしている場合は、従来のフロントエンドプールを削除する前に、CAC ホスティングを Skype for Business Server 2019 プールに移動する必要があります。
ms.openlocfilehash: 7b4aa42b20bfad5506d47c16038d1765f3ac8571
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307099"
---
# <a name="reset-call-admission-control"></a>通話受付管理のリセット

従来のフロントエンドプールが通話受付制御 (CAC) をホストしている場合は、従来のフロントエンドプールを削除する前に、CAC ホスティングを Skype for Business Server 2019 プールに移動する必要があります。
  
### <a name="to-reset-cac"></a>CAC をリセットするには

1. トポロジビルダーを開きます。
    
2. サイトノードを右クリックし、[プロパティの**編集**] をクリックします。
    
3. 「**通話受付制御の設定**」で、「**通話受付制御を有効にする**」が選択されていることを確認します。 
    
4. [**フロントエンドプール] で通話受付制御 (cac) を実行する**には、cac をホストする Skype For business Server 2019 プールを選び、[ **OK]** をクリックします。
    
5. トポロジを公開します。
    


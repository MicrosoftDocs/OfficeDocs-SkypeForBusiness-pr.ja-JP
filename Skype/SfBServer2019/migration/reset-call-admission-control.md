---
title: 通話受付管理のリセット
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 従来のフロントエンドプールが通話受付制御 (CAC) をホストしている場合は、従来のフロントエンドプールを削除する前に、CAC ホスティングを Skype for Business Server 2019 プールに移動する必要があります。
ms.openlocfilehash: 812391eda436906020c41b14a53c8ea18c4b1aee
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241326"
---
# <a name="reset-call-admission-control"></a>通話受付管理のリセット

従来のフロントエンドプールが通話受付制御 (CAC) をホストしている場合は、従来のフロントエンドプールを削除する前に、CAC ホスティングを Skype for Business Server 2019 プールに移動する必要があります。
  
### <a name="to-reset-cac"></a>CAC をリセットするには

1. トポロジビルダーを開きます。
    
2. サイトノードを右クリックし、[プロパティの**編集**] をクリックします。
    
3. 「**通話受付制御の設定**」で、「**通話受付制御を有効にする**」が選択されていることを確認します。 
    
4. [**フロントエンドプール] で通話受付制御 (cac) を実行する**には、cac をホストする Skype For business Server 2019 プールを選び、[ **OK]** をクリックします。
    
5. トポロジを公開します。
    


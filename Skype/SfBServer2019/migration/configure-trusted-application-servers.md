---
title: 信頼済みアプリケーション サーバーの構成
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
description: 混在環境で、新しい信頼済みアプリケーション サーバーを作成する場合は、次ホップ プールを 2019 年 2019 年Skype for Business Serverする必要があります。 混在環境では、従来のプールと 2019 年Skype for Business Server両方がドロップダウン リストに表示されます。 従来のプールを選択することはできません。
ms.openlocfilehash: 9965af757a570cfd787bb482a932d2817fd07ab0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58584471"
---
# <a name="configure-trusted-application-servers"></a>信頼済みアプリケーション サーバーの構成

混在環境で、新しい信頼済みアプリケーション サーバーを作成する場合は、次ホップ プールを 2019 年 2019 年Skype for Business Serverする必要があります。 混在環境では、従来のプールと 2019 Skype for Business Serverプールの両方がドロップダウン リストに表示されます。 従来のプールを選択することはできません。
  
> [!IMPORTANT]
> 信頼できるアプリケーション サーバーを移行する場合は、使用している UCMA のバージョンも更新する必要があります。 Skype for Business Server 2019 用に新しい信頼済みアプリケーション プールを作成する場合は、UCMA を Skype for Business Server 2019 または利用可能な最新バージョンに更新する必要があります。 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>信頼Skype for Business Serverアプリケーション サーバーを作成するときに、[2019 年 2019 年を次ホップとして選択する] を選択します。

1. トポロジ ビルダーを開きます。
    
2. 左側のウィンドウで、[信頼済みアプリケーション サーバー] を **右クリックし、[** 新しい信頼された **アプリケーション プール] をクリックします**。
    
3. 信頼済 **みアプリケーション プールの Pool FQDN** を入力し、単一サーバーまたは複数サーバーを選択します。 
    
4. [**次へ**] をクリックします。
    
5. [次 **ホップの選択] ページ** の一覧から、[2019 Skype for Business Serverプール] を選択します。 
    
6. **[完了]** をクリックします。
    
7. [操作]**メニューでSkype for Business Server** を選択し、[発行] を **選択します**。
    
    信頼済み **アプリケーション プールが** 正常に作成され、正しいフロントエンド プールに関連付けられているか確認します。 
    


---
title: 信頼済みアプリケーション サーバーの構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 混在環境で、新しい信頼されたアプリケーション サーバーを作成する場合、次ホップ プールのプールのビジネス サーバー 2019、Skype を設定する必要があります。 混在環境で、従来のプールとプールのビジネス サーバー 2019 Skype の両方がドロップ ダウン リストに表示されます。 従来のプールを選択することはサポートされていません。
ms.openlocfilehash: 79f4de527008d2d9bf295fcb82eee433d04a1691
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890889"
---
# <a name="configure-trusted-application-servers"></a>信頼済みアプリケーション サーバーの構成

混在環境で、新しい信頼されたアプリケーション サーバーを作成する場合、次ホップ プールのプールのビジネス サーバー 2019、Skype を設定する必要があります。 混在環境で、従来のプールとプールのビジネス サーバー 2019 Skype の両方がドロップ ダウン リストに表示されます。 従来のプールを選択することはサポートされていません。
  
> [!IMPORTANT]
> 信頼されたアプリケーション サーバーを移行する場合もを使用している UCMA のバージョンを更新する必要があります。 Skype のビジネス サーバー 2019 の新しい信頼されたアプリケーション プールを作成する場合は、Skype のビジネス サーバー 2019 に含まれているバージョンまたは最新バージョンに UCMA を更新してください。 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>信頼済みアプリケーション サーバーを作成するときは、次のホップとしてビジネス サーバー 2019 の Skype を選択します。

1. トポロジ ビルダーを開きます。
    
2. 左側のウィンドウで**信頼済みアプリケーション サーバー** ] を右クリックし、**新しい信頼されたアプリケーション プール**] をクリックします。
    
3. 信頼されたアプリケーション プールの**プールの FQDN**を入力し、1 台のサーバーまたは複数のサーバーかどうかを選択します。 
    
4. [ **次へ**] をクリックします。
    
5. **次ホップの選択**] ページで、ボックスの一覧からビジネス サーバー 2019 のフロント エンド プールの Skype を選択します。 
    
6. [**完了**] をクリックします。
    
7. **Skype**ビジネス サーバーは、最上位のノードを選択し、 **[操作**] メニューから [**発行**] を選択します。
    
    **信頼されたアプリケーション プール**が正常に作成されて、適切なフロント エンド プールに関連付けられていることを確認します。 
    


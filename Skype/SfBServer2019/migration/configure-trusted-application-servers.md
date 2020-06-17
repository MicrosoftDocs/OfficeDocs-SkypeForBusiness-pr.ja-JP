---
title: 信頼されたアプリケーション サーバーを構成する
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
description: 混在環境では、信頼されたアプリケーションサーバーを新たに作成する場合は、次ホッププールを Skype for Business Server 2019 プールとして設定する必要があります。 混在環境では、ドロップダウンリストに従来のプールと Skype for Business Server 2019 プールの両方が表示されます。 従来のプールを選択することはできません。
ms.openlocfilehash: 1c0aac1efa4f83a81ccf2f3bb5ecbc925ee58839
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753947"
---
# <a name="configure-trusted-application-servers"></a>信頼されたアプリケーション サーバーを構成する

混在環境では、信頼されたアプリケーションサーバーを新たに作成する場合は、次ホッププールを Skype for Business Server 2019 プールとして設定する必要があります。 混在環境では、ドロップダウンリストに従来のプールと Skype for Business Server 2019 プールの両方が表示されます。 従来のプールを選択することはできません。
  
> [!IMPORTANT]
> 信頼されたアプリケーションサーバーを移行する場合は、使用している UCMA のバージョンも更新する必要があります。 Skype for business Server 2019 用の新しい信頼されたアプリケーションプールを作成する場合は、UCMA を Skype for Business Server 2019 に含まれているバージョンまたは利用可能な最新バージョンに更新する必要があります。 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>信頼されたアプリケーションサーバーを作成するときは、次ホップとして Skype for Business Server 2019 を選択します。

1. トポロジ ビルダーを開きます。
    
2. 左側のウィンドウで、[**信頼済みアプリケーションサーバー** ] を右クリックし、[**新しい信頼済みアプリケーションプール**] をクリックします。
    
3. 信頼されたアプリケーションプールの [**プールの FQDN** ] を入力し、単一サーバーにするか複数サーバーにするかを選択します。 
    
4. [**次へ**] をクリックします。
    
5. [**次ホップの選択**] ページで、リストから [Skype For business Server 2019 フロントエンドプール] を選択します。 
    
6. [**完了**] をクリックします。
    
7. 最上位の [ **Skype For Business Server**] ノードを選択し、[**アクション**] メニューの [**発行**] を選択します。
    
    **信頼済みアプリケーションプール**が正常に作成され、適切なフロントエンドプールに関連付けられていることを確認します。 
    


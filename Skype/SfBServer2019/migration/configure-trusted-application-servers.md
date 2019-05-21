---
title: 信頼済みアプリケーション サーバーの構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 混在環境では、新しい信頼できるアプリケーションサーバーを作成する場合は、次ホッププールを Skype for Business Server 2019 プールとして設定する必要があります。 混在環境では、ドロップダウンリストに従来のプールと Skype for Business Server 2019 プールの両方が表示されます。 従来のプールの選択はサポートされていません。
ms.openlocfilehash: b0dfb9ba1e4744ba3e0ea0c376f67a224e70376a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289600"
---
# <a name="configure-trusted-application-servers"></a>信頼済みアプリケーション サーバーの構成

混在環境では、新しい信頼できるアプリケーションサーバーを作成する場合は、次ホッププールを Skype for Business Server 2019 プールとして設定する必要があります。 混在環境では、ドロップダウンリストに従来のプールと Skype for Business Server 2019 プールの両方が表示されます。 従来のプールの選択はサポートされていません。
  
> [!IMPORTANT]
> 信頼されているアプリケーションサーバーを移行する場合は、使用している UCMA のバージョンも更新する必要があります。 Skype for Business Server 2019 用の新しい信頼できるアプリケーションプールを作成する場合は、UCMA を Skype for Business Server 2019 に含まれているバージョン、または利用可能な最新バージョンに更新する必要があります。 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>信頼されたアプリケーションサーバーを作成するときに、[Skype for Business Server 2019 (次ホップ)] を選択します。

1. トポロジビルダーを開きます。
    
2. 左側のウィンドウで、[**信頼されたアプリケーションサーバー** ] を右クリックし、[**新しい信頼できるアプリケーションプール**] をクリックします。
    
3. 信頼されているアプリケーションプールの**プール FQDN**を入力し、シングルサーバーとマルチサーバーのどちらにするかを選択します。 
    
4. [ **次へ**] をクリックします。
    
5. **[次ホップの選択**] ページで、一覧から [Skype For business Server 2019 フロントエンドプール] を選びます。 
    
6. [**完了**] をクリックします。
    
7. トップノードの**Skype For Business Server**を選び、[**アクション**] メニューから [**発行**] を選択します。
    
    信頼された**アプリケーションプール**が正常に作成され、正しいフロントエンドプールに関連付けられていることを確認します。 
    


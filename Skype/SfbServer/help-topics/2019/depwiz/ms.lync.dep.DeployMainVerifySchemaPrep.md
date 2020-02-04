---
title: スキーマ パーティションのレプリケーションの確認
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
ROBOTS: NOINDEX, NOFOLLOW
description: Active Directory ドメインサービスフォレストでスキーマ拡張が正常にレプリケートされたことを確認するには、次の手順を実行します。
ms.openlocfilehash: 2d739bece89d43d5d3be289be55c90c2a63b49fe
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705342"
---
# <a name="verify-replication-of-schema-partition"></a>スキーマ パーティションのレプリケーションの確認
 
Active Directory ドメインサービスフォレストでスキーマ拡張が正常にレプリケートされたことを確認するには、次の手順を実行します。
  
1. Active Directory ドメインサービスフォレストのドメインコントローラー (スキーママスターの役割を保持しているドメインコントローラー以外) にログオンします。ここでは、スキーマの拡張機能が Enterprise Admins グループのメンバーとして適用されています。
    
2. ADSI の編集を開く: [**スタート**] をクリックし、[**管理ツール**] をクリックして、[ **adsi の編集**] をクリックします。
    
    > [!TIP]
    > または、[**スタート**] をクリックし、[**実行**] をクリックします。次に、「 **adsiedit** 」と入力して ADSI エディターを起動します。
  
3. Microsoft 管理コンソール (MMC) ツリーでまだ選択されていない場合は、[ADSI Edit] をクリックします。
    
4. [**アクション**] メニューで、[**接続**] をクリックします。
    
5. [**接続の設定**] ダイアログ ボックスの [**既知の名前付けコンテキストを選択する**] で、[**スキーマ**] を選択して [**OK**] をクリックします。
    
6. スキーマ コンテナーで、CN=ms-RTC-SIP-SchemaVersion を検索します。 このオブジェクトが存在し、 **Rangeupper**属性の値が1150であり、 **rangeupper**属性の値が3の場合は、スキーマが正常に更新され、複製されています。 このオブジェクトが存在しない場合、または**Rangeupper**属性と**rangeupper**属性の値が指定されていない場合は、スキーマが変更されていないか、複製されていません。
    
> [!NOTE]
> スキーマの複製を確認しても正常な複製が表示されない場合は、約15分待ってからもう一度確認してください。 Active Directory のレプリケーションは、緩やかな一貫性モデルに基づいており、サーバーとインフラストラクチャのさまざまな要因に基づいて、いくつかのレプリケーション待ち時間が発生する可能性があります。 
  


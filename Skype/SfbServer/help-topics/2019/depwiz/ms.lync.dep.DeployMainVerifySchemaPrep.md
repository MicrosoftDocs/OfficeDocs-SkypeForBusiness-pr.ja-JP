---
title: スキーマ パーティションのレプリケーションの確認
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
ROBOTS: NOINDEX, NOFOLLOW
description: Active Directory ドメイン サービス フォレストでスキーマ拡張機能が正常にレプリケートされたことを確認するには、次の手順を実行します。
ms.openlocfilehash: ad48543f6b14e3e65750582caa42d050b0c2cd58
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848000"
---
# <a name="verify-replication-of-schema-partition"></a>スキーマ パーティションのレプリケーションの確認
 
Active Directory ドメイン サービス フォレストでスキーマ拡張機能が正常にレプリケートされたことを確認するには、次の手順を実行します。
  
1. スキーマ拡張機能が Enterprise Admins グループのメンバーとして適用された Active Directory ドメイン サービス フォレストのドメイン コントローラー (スキーマ マスター の役割を保持するドメイン コントローラー以外) にログオンします。
    
2. [**スタート**] をクリックして [**管理ツール**] をクリックし、[**ADSI エディター**] をクリックして ADSI エディターを開きます。
    
    > [!TIP]
    > または [**スタート**] をクリックして [**ファイル名を指定して実行**] をクリックし、「**adsiedit.msc**」と入力して ADSI エディターを起動します。
  
3. Microsoft 管理コンソール (MMC) ツリーで、まだ選択されていない場合には [ADSI エディタ] をクリックします。
    
4. **[アクション]** メニューで、**[接続]** をクリックします。
    
5. [**接続の設定**] ダイアログ ボックスの [**既知の名前付けコンテキストを選択する**] で、[**スキーマ**] を選択して [**OK**] をクリックします。
    
6. スキーマ コンテナーで、CN=ms-RTC-SIP-SchemaVersion を検索します。このオブジェクトが存在し、**rangeUpper** 属性の値が 1150 で、**rangeLower** 属性の値が 3 の場合、スキーマは正しく更新され、レプリケートされています。このオブジェクトが存在しないか、**rangeUpper** および **rangeLower** 属性の値が指定された値と異なる場合、スキーマは変更されていないか、レプリケートされていません。
    
> [!NOTE]
> スキーマのレプリケーションが成功したことを確認できなかった場合は、およそ 15 分待ってからもう一度確認してください。 Active Directory レプリケーションは緩やかな整合性モデルに基づいており、サーバーとインフラストラクチャの多くの要因に基づいて、一部のレプリケーション待機時間が発生する可能性があります。 
  


---
title: スキーマ パーティションのレプリケーションの確認
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: スキーマ拡張機能が Active Directory ドメイン サービス フォレストに正常にレプリケートされたことを確認するには、次の手順を実行します。
ms.openlocfilehash: db30087e6b996b70fe97e3249c1bf2eaa97a694c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800547"
---
# <a name="verify-replication-of-schema-partition"></a>スキーマ パーティションのレプリケーションの確認
 
スキーマ拡張機能が Active Directory ドメイン サービス フォレストに正常にレプリケートされたことを確認するには、次の手順を実行します。
  
1. スキーマ拡張機能が Enterprise Admins グループのメンバーとして適用された Active Directory ドメイン サービス フォレスト内のドメイン コントローラー (スキーマ マスターの役割を持つドメイン コントローラー以外) にログオンします。
    
2. [**スタート**] をクリックして [**管理ツール**] をクリックし、[**ADSI エディター**] をクリックして ADSI エディターを開きます。
    
    > [!TIP]
    > または [**スタート**] をクリックして [**ファイル名を指定して実行**] をクリックし、「**adsiedit.msc**」と入力して ADSI エディターを起動します。
  
3. Microsoft 管理コンソール (MMC) ツリーで、まだ選択されていない場合には [ADSI エディタ] をクリックします。
    
4. **[アクション]** メニューで、**[接続]** をクリックします。
    
5. [**接続の設定**] ダイアログ ボックスの [**既知の名前付けコンテキストを選択する**] で、[**スキーマ**] を選択して [**OK**] をクリックします。
    
6. スキーマ コンテナーで、CN=ms-RTC-SIP-SchemaVersion を検索します。このオブジェクトが存在し、**rangeUpper** 属性の値が 1150 で、**rangeLower** 属性の値が 3 の場合、スキーマは正しく更新され、レプリケートされています。このオブジェクトが存在しないか、**rangeUpper** および **rangeLower** 属性の値が指定された値と異なる場合、スキーマは変更されていないか、レプリケートされていません。
    
> [!NOTE]
> スキーマのレプリケーションが成功したことを確認できなかった場合は、およそ 15 分待ってからもう一度確認してください。 Active Directory レプリケーションは、緩やかな一貫性モデルに基づいており、サーバーとインフラストラクチャの多くの要因に基づいて、一部のレプリケーション遅延が発生する可能性があります。 
  


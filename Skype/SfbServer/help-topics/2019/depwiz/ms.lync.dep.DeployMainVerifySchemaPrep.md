---
title: スキーマ パーティションのレプリケーションを確認します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: Active Directory ドメイン サービス フォレストでスキーマ拡張機能が正常にレプリケートされていることを確認するには、次の操作を行います。
ms.openlocfilehash: a5628e369ffc796affe9984cef8ecb1ba044ec8a
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2018
---
# <a name="verify-replication-of-schema-partition"></a>スキーマ パーティションのレプリケーションを確認します。
 
Active Directory ドメイン サービス フォレストでスキーマ拡張機能が正常にレプリケートされていることを確認するには、次の操作を行います。
  
1. Enterprise Admins グループのメンバーとして、スキーマの拡張機能が適用された場所、Active Directory ドメイン サービス フォレスト内ドメイン コント ローラー (ただし、スキーマ マスターの役割を保持しているドメイン コント ローラー) にログオンします。
    
2. ADSI 編集を開く: [**スタート**] ボタン、 **[管理ツール**] をクリックし、[ **ADSI Edit**] をクリックします。
    
    > [!TIP]
    > または、**開始**] をクリックし、**実行**、ADSI Edit を起動するのには入力**ファイル名を指定**] をクリックします。
  
3. Microsoft 管理コンソール (MMC) ツリーで、選択されていない場合は、ADSI Edit] をクリックします。
    
4. [**アクション**] メニューで、[**接続**] をクリックします。
    
5. [**接続の設定**] ダイアログ ボックスの [**既知の名前付けコンテキストを選択する**] で、[**スキーマ**] を選択して [**OK**] をクリックします。
    
6. [スキーマ] コンテナーを探します CN = ms の RTC の SIP を含んでいます。 、このオブジェクトが存在し、 **rangeUpper**属性の値は、1150、 **rangeLower**属性の値は 3、スキーマが正常に更新し、レプリケートします。 **RangeLower**し、 **rangeUpper**属性の値として使用されてない場合またはこのオブジェクトが存在しない場合を指定し、スキーマが変更されていないまたはレプリケートされていません。
    
> [!NOTE]
> スキーマのレプリケーションのチェックが正常に複製をまだ表示されていない場合は、約 15 分間待機し、再び確認します。 Active Directory のレプリケーションはゆるやかな一貫性モデルに基づくし、いくつかのサーバーとインフラストラクチャの要因に基づくいくつかのレプリケーションの遅延が発生することが。 
  


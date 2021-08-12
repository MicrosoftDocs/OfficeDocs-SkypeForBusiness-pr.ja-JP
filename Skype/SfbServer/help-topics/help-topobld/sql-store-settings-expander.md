---
title: SQL ストア設定エキスパンダー
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
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: データベースのプロパティを編集するにはSQL Serverデータベース インスタンスをSQL Serverする必要があります。 [プロパティの編集] ダイアログ ボックスで、アーカイブ サーバー データベースをコンピューター間で移動するなどのタスクを実行することはできません。 また、[プロパティの編集] ダイアログ ボックスを使用して、サーバーの全体管理ストアをSQL Serverのインスタンスを変更することはできません。
ms.openlocfilehash: bb89251ac2f29ee15aa10caadf942a9d0896156aedf39394a763b44d6ce9e8d2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341922"
---
# <a name="sql-store-settings-expander"></a>SQL ストア設定エキスパンダー
 
データベースのプロパティを編集するにはSQL Serverデータベース インスタンスをSQL Serverする必要があります。 [**プロパティの編集**] ダイアログ ボックスで、アーカイブ サーバー データベースをコンピューター間で移動するなどのタスクを実行することはできません。 さらに、[プロパティの編集]ダイアログ ボックスを使用して、サーバーの全体管理ストアをホストSQL Serverインスタンスを変更することはできません。
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>データベースのプロパティSQL Serverする

サーバーの全体管理ストア以外SQL Serverで使用されるデータベースのインスタンスを変更するには、トポロジ ビルダーで次の手順を実行します。
  
### <a name="to-modify-an-instance-of-sql-server"></a>オブジェクトのインスタンスを変更SQL Server

1. [**SQL ストア**] ノードの下で該当するデータベースを選択し、[**プロパティの編集**] をクリックします。
    
2. [**プロパティの編集**] ダイアログ ボックスで、次のどちらかの操作を行います。
    
   - 既定のインスタンスを使用するにはSQL Server **インスタンスを選択** し **、[OK] をクリックします**。
    
   - 名前付きデータベース インスタンスを使用するには、[**名前付きインスタンス**] を選択し、テキスト ボックスにインスタンス名を入力してから [**OK**] をクリックします。 インスタンス名 (たとえば、ArchivingInstance) のみを入力し、パス全体をSQL Serverしてください。
    
[プロパティの編集] **ダイアログ** ボックスで作業している場合、トポロジ ビルダーは、入力したデータベース インスタンスが有効なインスタンスであるのを確認できません。 たとえば、インスタンス名として誤ってArchivingInstanecと入力し **、[OK]** をクリックすると、トポロジ ビルダーはその無効なインスタンスを受け入れる。 このトポロジを公開する前に、この間違いを修正する必要があります。SQL Server インスタンスが見つからない場合、トポロジ ビルダーは、そのインスタンスを作成できません。
  


---
title: SQL ストアの設定の拡張
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: SQL Server データベースのプロパティを編集するには、SQL Server データベース インスタンスを変更してください。 1 台のコンピューターから、アーカイブ サーバー データベースを移動するなどのタスクを実行するのには、[プロパティの編集] ダイアログ ボックスを使うことはできません。 さらに、使うことはできません、プロパティの編集] ダイアログ ボックスをホストする SQL Server のインスタンスを変更するのには、中央管理ストアです。
ms.openlocfilehash: 2a1fc051e3dc848272a7cad539eaa749ff95d9b9
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2018
---
# <a name="sql-store-settings-expander"></a>SQL ストアの設定の拡張
 
SQL Server データベースのプロパティを編集するには、SQL Server データベース インスタンスを変更してください。 1 台のコンピューターから、アーカイブ サーバー データベースを移動するなどのタスクを実行するのには、[**プロパティの編集**] ダイアログ ボックスを使うことはできません。 さらに、使うことはできません、**プロパティの編集**] ダイアログ ボックスをホストする SQL Server のインスタンスを変更するのには、中央管理ストアです。
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>SQL Server データベースのプロパティの編集

中央管理ストア以外のデータベースで使用される SQL Server のインスタンスを変更するには、トポロジ ビルダーで次の手順を行います。
  
### <a name="to-modify-an-instance-of-sql-server"></a>SQL Server のインスタンスを変更するのには

1. **SQL ストア**ノードの下の適切なデータベースを選択し、 **[プロパティの編集**] をクリックします。
    
2. **プロパティの編集**] ダイアログ ボックスで、次のいずれかの操作を行います。
    
  - 既定の SQL Server のインスタンスを使用して、**既定のインスタンス**を選択し、[ **OK**] をクリックします。
    
  - 名前付きデータベース インスタンスを使用するには、**という名前のインスタンス**を選択して、テキスト ボックスで、インスタンス名を入力し、[ **OK**] をクリックします。 のみ、インスタンス名 (ArchivingInstance など)、および全体の SQL Server のパスではなくを入力する必要があります。
    
**プロパティの編集**] ダイアログ ボックスでの作業は、トポロジ ビルダーには入力したデータベース ・ インスタンスが有効なインスタンスは確認できません。 などの場合、インスタンス名として typeArchivingInstanec を誤ってとは、 **[ok]** をクリックし、トポロジ ビルダーは、無効なインスタンスを受け取ります。。 このトポロジを公開する前に、この間違いを修正する必要があります: SQL Server のインスタンスが見つかりません、トポロジ ビルダーが作成されませんインスタンスをするのです。
  


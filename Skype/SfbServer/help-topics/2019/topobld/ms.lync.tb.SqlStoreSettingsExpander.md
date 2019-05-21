---
title: SQL ストア設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
ROBOTS: NOINDEX, NOFOLLOW
description: SQL Server データベースのプロパティを編集するには、SQL Server データベースインスタンスを変更する必要があります。 [プロパティの編集] ダイアログボックスを使用して、アーカイブサーバーデータベースを別のコンピューターに移動するなどのタスクを実行することはできません。 さらに、[プロパティの編集] ダイアログボックスを使って、中央管理ストアをホストする SQL Server のインスタンスを変更することはできません。
ms.openlocfilehash: 816733627bcaf1156e5ad34955bb8aa9cf580642
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303019"
---
# <a name="sql-store-settings-expander"></a>SQL ストア設定エキスパンダー
 
SQL Server データベースのプロパティを編集するには、SQL Server データベースインスタンスを変更する必要があります。 [**プロパティの編集**] ダイアログボックスを使用して、アーカイブサーバーデータベースを別のコンピューターに移動するなどのタスクを実行することはできません。 さらに、[**プロパティの編集**] ダイアログボックスを使って、中央管理ストアをホストする SQL Server のインスタンスを変更することはできません。
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>SQL Server データベースのプロパティを編集する

サーバーの全体管理ストア以外のデータベースによって使用される SQL Server のインスタンスを変更するには、次の手順を実行します。
  
### <a name="to-modify-an-instance-of-sql-server"></a>SQL Server のインスタンスを変更するには

1. [ **SQL ストア**] ノードで適切なデータベースを選択し、[**プロパティの編集**] をクリックします。
    
2. [**プロパティの編集**] ダイアログボックスで、次のいずれかの操作を行います。
    
   - 既定の SQL Server インスタンスを使用するには、[**既定のインスタンス**] を選び、[ **OK]** をクリックします。
    
   - 名前付きのデータベースインスタンスを使用するには、[**名前付きインスタンス**] を選択し、テキストボックスにインスタンス名を入力して、[ **OK]** をクリックします。 SQL Server のパス全体ではなく、インスタンス名だけを入力する必要があります (たとえば、ArchivingInstance)。
    
[**プロパティの編集**] ダイアログボックスで作業している場合、トポロジビルダーは、入力したデータベースインスタンスが有効なインスタンスであることを確認しません。 たとえば、誤ってインスタンス名として typeArchivingInstanec して [ **OK]** をクリックした場合、トポロジビルダーは無効なインスタンスを受け入れます。 このトポロジを公開する前に、この間違いを修正する必要があります。 SQL Server インスタンスが見つからない場合は、トポロジビルダーでそのインスタンスが作成されることはありません。
  


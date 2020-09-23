---
title: SQL ストア設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: SQL Server データベースのプロパティを編集するには、SQL Server データベースのインスタンスを変更する必要があります。 [プロパティの編集] ダイアログ ボックスで、アーカイブ サーバー データベースをコンピューター間で移動するなどのタスクを実行することはできません。 さらに、[プロパティの編集] ダイアログボックスを使用して、中央管理ストアをホストする SQL Server のインスタンスを変更することはできません。
ms.openlocfilehash: e3b16d8c6eab4f4918ef39b3c4f1ab4d0c6fc057
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219612"
---
# <a name="sql-store-settings-expander"></a>SQL ストア設定エキスパンダー
 
SQL Server データベースのプロパティを編集するには、SQL Server データベースのインスタンスを変更する必要があります。 [**プロパティの編集**] ダイアログ ボックスで、アーカイブ サーバー データベースをコンピューター間で移動するなどのタスクを実行することはできません。 さらに、[ **プロパティの編集** ] ダイアログボックスを使用して、中央管理ストアをホストする SQL Server のインスタンスを変更することはできません。
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>SQL Server データベースのプロパティを編集する

中央管理ストア以外のデータベースで使用されている SQL Server のインスタンスを変更するには、トポロジビルダーで以下の手順を実行します。
  
### <a name="to-modify-an-instance-of-sql-server"></a>SQL Server のインスタンスを変更するには

1. [**SQL ストア**] ノードの下で該当するデータベースを選択し、[**プロパティの編集**] をクリックします。
    
2. [**プロパティの編集**] ダイアログ ボックスで、次のどちらかの操作を行います。
    
   - 既定の SQL Server インスタンスを使用するには、[ **既定のインスタンス** ] を選択し、[ **OK]** をクリックします。
    
   - 名前付きデータベース インスタンスを使用するには、[**名前付きインスタンス**] を選択し、テキスト ボックスにインスタンス名を入力してから [**OK**] をクリックします。 SQL Server パス全体ではなく、インスタンス名のみ (ArchivingInstance など) を入力する必要があります。
    
[ **プロパティの編集** ] ダイアログボックスで作業している場合、入力したデータベースインスタンスが有効なインスタンスであることは、トポロジビルダーによって確認されません。 たとえば、誤ってインスタンス名を typeArchivingInstanec し、[ **OK**] をクリックすると、その無効なインスタンスがトポロジビルダーによって受け入れられます。 このトポロジを公開するには、その前に、この間違いを修正する必要があります。 SQL Server インスタンスが見つからない場合、トポロジビルダーはそのインスタンスを作成しません。
  


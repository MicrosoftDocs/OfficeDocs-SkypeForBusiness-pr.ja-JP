---
title: データベースの作成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: トポロジビルダーには、SQL Server ストアにデータベースをインストールする方法が用意されています。 トポロジビルダーを使用してデータベースをインストールすると、アプリケーションはトポロジから情報を読み取ってから、指定された SQL Server コンピューターまたは SQL Server クラスターに必要なデータベースをインストールします。 これは、トポロジビルダーを使用して使用できる唯一の種類のデータベースインストールです。 特定のコンピューターに特定のデータベースをインストールする必要がある場合、または併置されたデータベースをインストールする必要がある場合は、代わりに Windows PowerShell コマンドラインインターフェイスと Install-CsDatabase コマンドレットを使用する必要があります。
ms.openlocfilehash: ea7daab44c6075e40e3f8a1b900fe43b84048ed5
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219508"
---
# <a name="create-database"></a>データベースの作成
 
トポロジビルダーには、SQL Server ストアにデータベースをインストールする方法が用意されています。 トポロジビルダーを使用してデータベースをインストールすると、アプリケーションはトポロジから情報を読み取ってから、指定された SQL Server コンピューターまたは SQL Server クラスターに必要なデータベースをインストールします。 これは、トポロジビルダーを使用して使用できる唯一の種類のデータベースインストールです。 特定のコンピューターに特定のデータベースをインストールする必要がある場合、または併置されたデータベースをインストールする必要がある場合は、代わりに Windows PowerShell コマンドラインインターフェイスと [install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) コマンドレットを使用する必要があります。
  
### <a name="creating-a-database"></a>データベースの作成

1. [Skype for Business Server 2015] ノードをクリックし、[ **データベースのインストール**] をクリックします。
    
2. [データベースの **インストール** ] ダイアログボックスの [ **データベースの作成** ] ページで、新しいデータベースを作成する SQL Server ストアの完全修飾ドメイン名 (FQDN) を選択します。
    
3. [**詳細設定**] をクリックします。 **[データベースファイルの場所の選択**] ダイアログボックスで、次のいずれかのオプションを選択します。
    
   - **データベースファイルの場所を自動的に決定**します。 このオプションを選択すると、トポロジビルダーは組み込みのアルゴリズムを使用して、データベースログとデータファイルの格納場所を選択します。
    
   - **[既定の SQL Server インスタンスを使用する]**。 このオプションを選択すると、データベースログおよびデータファイルの格納場所の選択に組み込みのアルゴリズムは使用されません。 代わりに、ログ ファイルとデータ ファイルは SQL Server の既定のパスによって指定された場所に保存されます (SQL Server 管理者がこれらのパスを事前に構成しておく必要があります)。 データ ファイルは既定の SQL Server データ ファイルの場所に格納され、ログ ファイルは既定の SQL Server ログ ファイルの場所に格納されます。
    
4. [**OK**] をクリックします。
    
5. [ **データベースの作成** ] ページで、[ **次へ**] をクリックします。
    
6. [ **データベースの作成の完了** ] ページで、[ **完了**] をクリックします。
    


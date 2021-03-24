---
title: データベースの作成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: トポロジ ビルダーは、データベースをデータベース ストアにインストールSQL Serverします。 トポロジ ビルダーを使用してデータベースをインストールすると、アプリケーションはトポロジから情報を読み取り、指定された SQL Server コンピューターまたは SQL Server クラスターにインストールします。 これは、トポロジ ビルダーを使用して使用できるデータベース インストールの唯一の種類です。 特定のコンピューターに特定のデータベースをインストールする必要がある場合、または同一データベースをインストールする必要がある場合は、代わりに Windows PowerShell コマンド ライン インターフェイスと Install-CsDatabase コマンドレットを使用する必要があります。
ms.openlocfilehash: 70c3da98f3839d59567cdfb2db3a93de99b22824
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106903"
---
# <a name="create-database"></a>データベースの作成
 
トポロジ ビルダーは、データベースをデータベース ストアにインストールSQL Serverします。 トポロジ ビルダーを使用してデータベースをインストールすると、アプリケーションはトポロジから情報を読み取り、指定された SQL Server コンピューターまたは SQL Server クラスターにインストールします。 これは、トポロジ ビルダーを使用して使用できるデータベース インストールの唯一の種類です。 特定のコンピューターに特定のデータベースをインストールする必要がある場合、または同一データベースをインストールする必要がある場合は、代わりに Windows PowerShell コマンド ライン インターフェイスと [Install-CsDatabase](/powershell/module/skype/install-csdatabase?view=skype-ps) コマンドレットを使用する必要があります。
  
### <a name="creating-a-database"></a>データベースの作成

1. [Skype for Business Server 2015] ノードをクリックし、[データベースのインストール] **をクリックします**。
    
2. [データベースの **インストール**] ダイアログ ボックスの [データベースの作成] ページで、新しいデータベースを作成する SQL Server ストアの完全修飾ドメイン名 (FQDN) を選択します。
    
3. [**詳細設定**] をクリックします。 [データベース ファイル **の場所の選択] ダイアログ** ボックスで、次のいずれかのオプションを選択します。
    
   - **データベース ファイルの場所を自動的に決定します**。 このオプションを選択すると、トポロジ ビルダーは組み込みのアルゴリズムを使用して、データベース ログとデータ ファイルの保存場所を選択します。
    
   - **[既定の SQL Server インスタンスを使用する]**。 このオプションを選択した場合、組み込みのアルゴリズムを使用して、データベース ログとデータ ファイルの保存場所を選択できません。 代わりに、ログ ファイルとデータ ファイルは SQL Server の既定のパスによって指定された場所に保存されます (SQL Server 管理者がこれらのパスを事前に構成しておく必要があります)。 データ ファイルは既定の SQL Server データ ファイルの場所に格納され、ログ ファイルは既定の SQL Server ログ ファイルの場所に格納されます。
    
4. **[OK]** をクリックします。
    
5. [データベースの作成 **] ページで** 、[次へ] を **クリックします**。
    
6. [データベース作成 **の完了] ページで、[** 完了] を **クリックします**。

---
title: データベースの作成
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
ROBOTS: NOINDEX, NOFOLLOW
description: トポロジ ビルダーは、データベースをデータベース ストアにインストールSQL Serverします。 トポロジ ビルダーを使用してデータベースをインストールすると、アプリケーションはトポロジから情報を読み取り、必要なデータベースを指定した SQL Server コンピューターまたは SQL Server クラスターにインストールします。 これは、トポロジ ビルダーを使用して使用できるデータベース インストールの唯一の種類です。 特定のコンピューターに特定のデータベースをインストールする必要がある場合、または同一データベースをインストールする必要がある場合は、代わりに Windows PowerShell コマンド ライン インターフェイスと Install-CsDatabase コマンドレットを使用する必要があります。
ms.openlocfilehash: d864f469d9200040c61611a70f81c442cfdb7269
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759909"
---
# <a name="create-database"></a>データベースの作成
 
トポロジ ビルダーは、データベースをデータベース ストアにインストールSQL Serverします。 トポロジ ビルダーを使用してデータベースをインストールすると、アプリケーションはトポロジから情報を読み取り、必要なデータベースを指定した SQL Server コンピューターまたは SQL Server クラスターにインストールします。 これは、トポロジ ビルダーを使用して使用できるデータベース インストールの唯一の種類です。 特定のコンピューターに特定のデータベースをインストールする必要がある場合、または同一データベースをインストールする必要がある場合は、代わりに Windows PowerShell コマンド ライン インターフェイスと[Install-CsDatabase](/powershell/module/skype/install-csdatabase?view=skype-ps)コマンドレットを使用する必要があります。
  
### <a name="creating-a-database"></a>データベースの作成

1. [データベース] ノードSkype for Business Serverクリックし、[データベースのインストール]**をクリックします**。
    
2. [データベースの **インストール**] ダイアログ ボックスの [データベースの作成] ページで、新しいデータベースを作成する SQL Server ストアの完全修飾ドメイン名 (FQDN) を選択します。
    
3. [**詳細設定**] をクリックします。 [データベース ファイル **の場所の選択] ダイアログ** ボックスで、次のいずれかのオプションを選択します。
    
   - **データベース ファイルの場所を自動的に決定します**。 このオプションを選択すると、トポロジ ビルダーは組み込みのアルゴリズムを使用して、データベース ログとデータ ファイルの保存場所を選択します。
    
   - **[既定の SQL Server インスタンスを使用する]**。 このオプションを選択した場合、組み込みのアルゴリズムを使用して、データベース ログとデータ ファイルの保存場所を選択できません。 代わりに、ログ ファイルとデータ ファイルは SQL Server の既定のパスによって指定された場所に保存されます (SQL Server 管理者がこれらのパスを事前に構成しておく必要があります)。 データ ファイルは既定の SQL Server データ ファイルの場所に格納され、ログ ファイルは既定の SQL Server ログ ファイルの場所に格納されます。
    
4. [**OK**] をクリックします。
    
5. [データベースの作成 **] ページで** 、[次へ] を **クリックします**。
    
6. [データベース作成 **の完了] ページで、[** 完了] を **クリックします**。

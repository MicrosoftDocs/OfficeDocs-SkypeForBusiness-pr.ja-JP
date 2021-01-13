---
title: データベースの作成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
ROBOTS: NOINDEX, NOFOLLOW
description: トポロジ ビルダーを使用すると、データベースをデータベース ストアにSQL Serverできます。 トポロジ ビルダーを使用してデータベースをインストールすると、アプリケーションはトポロジから情報を読み取り、必要なデータベースを指定した SQL Server コンピューターまたは SQL Server クラスターにインストールします。 これは、トポロジ ビルダーを使用して使用できる唯一の種類のデータベース インストールです。 特定のコンピューターに特定のデータベースをインストールする必要がある場合、または、一方のデータベースをインストールする必要がある場合は、代わりに Windows PowerShell コマンドライン インターフェイスと Install-CsDatabase コマンドレットを使用する必要があります。
ms.openlocfilehash: 1092840305d1a455aa094776ae757cf074f7e89a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822287"
---
# <a name="create-database"></a>データベースの作成
 
トポロジ ビルダーを使用すると、データベースをデータベース ストアにSQL Serverできます。 トポロジ ビルダーを使用してデータベースをインストールすると、アプリケーションはトポロジから情報を読み取り、必要なデータベースを指定した SQL Server コンピューターまたは SQL Server クラスターにインストールします。 これは、トポロジ ビルダーを使用して使用できる唯一の種類のデータベース インストールです。 特定のコンピューターに特定のデータベースをインストールする必要がある場合や、データベースを一覧に表示する必要がある場合は、代わりに Windows PowerShell コマンドライン インターフェイスと [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) コマンドレットを使用する必要があります。
  
### <a name="creating-a-database"></a>データベースの作成

1. [Skype for Business Server] ノードをクリックし、[データベースのインストール] **をクリックします**。
    
2. [データベースのインストール] ダイアログ ボックスの [データベースの作成] ページで、新しいデータベースを作成する SQL Server ストアの完全修飾ドメイン名 (FQDN) を選択します。
    
3. [**詳細設定**] をクリックします。 [データベース **ファイルの場所の選択** ] ダイアログ ボックスで、次のいずれかのオプションを選択します。
    
   - **データベース ファイルの場所を自動的に決定します**。 このオプションを選択すると、トポロジ ビルダーは組み込みのアルゴリズムを使用して、データベース ログおよびデータ ファイルの保存場所を選択します。
    
   - **[既定の SQL Server インスタンスを使用する]**。 このオプションを選択した場合、組み込みのアルゴリズムを使用して、データベース ログおよびデータ ファイルの保存場所を選択できません。 代わりに、ログ ファイルとデータ ファイルは SQL Server の既定のパスによって指定された場所に保存されます (SQL Server 管理者がこれらのパスを事前に構成しておく必要があります)。 データ ファイルは既定の SQL Server データ ファイルの場所に格納され、ログ ファイルは既定の SQL Server ログ ファイルの場所に格納されます。
    
4. [**OK**] をクリックします。
    
5. [データベースの **作成] ページで** 、[次へ] を **クリックします**。
    
6. [データベースの **作成完了] ページで** 、[完了] を **クリックします**。
    


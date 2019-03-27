---
title: データベースの作成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
ROBOTS: NOINDEX, NOFOLLOW
description: トポロジ ビルダーは、SQL Server にデータベースをインストールする方法を提供します。 トポロジ ビルダーを使用してデータベースをインストールしてアプリケーション トポロジから情報を読み取り、指定された SQL Server コンピューターまたは SQL Server クラスターに必要なデータベースがインストールされます。 トポロジ ビルダーを使用したデータベースのインストールは、この方法のみです。 特定のコンピューター上の特定のデータベースをインストールする必要がありますか、Windows PowerShell のコマンド ライン インターフェイスおよびインストール CsDatabase コマンドレットが代わりに使用する必要がある場合は配置されているデータベースをインストールする必要があります。
ms.openlocfilehash: 0929c87381fb6535d076161a301a662a15452024
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878677"
---
# <a name="create-database"></a><span data-ttu-id="d3ec6-106">データベースの作成</span><span class="sxs-lookup"><span data-stu-id="d3ec6-106">Create Database</span></span>
 
<span data-ttu-id="d3ec6-107">トポロジ ビルダーは、SQL Server にデータベースをインストールする方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="d3ec6-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="d3ec6-108">トポロジ ビルダーを使用してデータベースをインストールしてアプリケーション トポロジから情報を読み取り、指定された SQL Server コンピューターまたは SQL Server クラスターに必要なデータベースがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d3ec6-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="d3ec6-109">トポロジ ビルダーを使用したデータベースのインストールは、この方法のみです。</span><span class="sxs-lookup"><span data-stu-id="d3ec6-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="d3ec6-110">特定のコンピューター上の特定のデータベースをインストールする必要がありますか、Windows PowerShell のコマンド ライン インターフェイスおよび[インストール CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps)コマンドレットが代わりに使用する必要がある場合は配置されているデータベースをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3ec6-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="d3ec6-111">データベースの作成</span><span class="sxs-lookup"><span data-stu-id="d3ec6-111">Creating a Database</span></span>

1. <span data-ttu-id="d3ec6-112">ビジネス サーバー ノードの Skype をクリックし、**データベースのインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3ec6-112">Click the Skype for Business Server node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="d3ec6-113">[**データベースの作成**] ページで、**データベースのインストール**] ダイアログ ボックスで新しいデータベースが作成される SQL Server ストアの完全修飾ドメイン名 (FQDN) を選択します。</span><span class="sxs-lookup"><span data-stu-id="d3ec6-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="d3ec6-p103">[**詳細設定**] をクリックします。[**データベース ファイルの場所の選択**] ダイアログ ボックスで、次のどちらかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d3ec6-p103">Click **Advanced**. In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
   - <span data-ttu-id="d3ec6-p104">[**データベース ファイルの場所を自動的に判断する**]。このオプションを選択すると、トポロジ ビルダーは、組み込みのアルゴリズムを使用して、データベースのログ ファイルとデータ ファイルの格納場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="d3ec6-p104">**Automatically determine database file location**. If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
   - <span data-ttu-id="d3ec6-118">[**既定の SQL Server インスタンスを使用する**]。</span><span class="sxs-lookup"><span data-stu-id="d3ec6-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="d3ec6-119">このオプションを選択すると、データベースのログ ファイルとデータ ファイルの格納場所を選択するために、組み込みのアルゴリズムは使用されません。</span><span class="sxs-lookup"><span data-stu-id="d3ec6-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="d3ec6-120">代わりに、ログ ファイルとデータ ファイルは、(これらのパスする必要があります構成で SQL Server の管理者が高度な) SQL Server の既定のパスで指定された場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="d3ec6-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="d3ec6-121">データ ファイルは SQL Server の既定のデータ ファイルの場所に格納され、ログ ファイルは SQL Server の既定のログ ファイルの場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="d3ec6-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="d3ec6-122">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3ec6-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="d3ec6-123">[**データベースの作成**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3ec6-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="d3ec6-124">[**データベースの作成の完了**] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3ec6-124">On the **Database Creation Complete** page, click **Finish**.</span></span>
    


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
# <a name="create-database"></a><span data-ttu-id="58d46-106">データベースの作成</span><span class="sxs-lookup"><span data-stu-id="58d46-106">Create Database</span></span>
 
<span data-ttu-id="58d46-107">トポロジビルダーには、SQL Server ストアにデータベースをインストールする方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="58d46-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="58d46-108">トポロジビルダーを使用してデータベースをインストールすると、アプリケーションはトポロジから情報を読み取ってから、指定された SQL Server コンピューターまたは SQL Server クラスターに必要なデータベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="58d46-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="58d46-109">これは、トポロジビルダーを使用して使用できる唯一の種類のデータベースインストールです。</span><span class="sxs-lookup"><span data-stu-id="58d46-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="58d46-110">特定のコンピューターに特定のデータベースをインストールする必要がある場合、または併置されたデータベースをインストールする必要がある場合は、代わりに Windows PowerShell コマンドラインインターフェイスと [install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58d46-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="58d46-111">データベースの作成</span><span class="sxs-lookup"><span data-stu-id="58d46-111">Creating a Database</span></span>

1. <span data-ttu-id="58d46-112">[Skype for Business Server 2015] ノードをクリックし、[ **データベースのインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58d46-112">Click the Skype for Business Server 2015 node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="58d46-113">[データベースの **インストール** ] ダイアログボックスの [ **データベースの作成** ] ページで、新しいデータベースを作成する SQL Server ストアの完全修飾ドメイン名 (FQDN) を選択します。</span><span class="sxs-lookup"><span data-stu-id="58d46-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="58d46-114">[**詳細設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58d46-114">Click **Advanced**.</span></span> <span data-ttu-id="58d46-115">**[データベースファイルの場所の選択**] ダイアログボックスで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="58d46-115">In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
   - <span data-ttu-id="58d46-116">**データベースファイルの場所を自動的に決定**します。</span><span class="sxs-lookup"><span data-stu-id="58d46-116">**Automatically determine database file location**.</span></span> <span data-ttu-id="58d46-117">このオプションを選択すると、トポロジビルダーは組み込みのアルゴリズムを使用して、データベースログとデータファイルの格納場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="58d46-117">If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
   - <span data-ttu-id="58d46-118">**[既定の SQL Server インスタンスを使用する]**。</span><span class="sxs-lookup"><span data-stu-id="58d46-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="58d46-119">このオプションを選択すると、データベースログおよびデータファイルの格納場所の選択に組み込みのアルゴリズムは使用されません。</span><span class="sxs-lookup"><span data-stu-id="58d46-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="58d46-120">代わりに、ログ ファイルとデータ ファイルは SQL Server の既定のパスによって指定された場所に保存されます (SQL Server 管理者がこれらのパスを事前に構成しておく必要があります)。</span><span class="sxs-lookup"><span data-stu-id="58d46-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="58d46-121">データ ファイルは既定の SQL Server データ ファイルの場所に格納され、ログ ファイルは既定の SQL Server ログ ファイルの場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="58d46-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="58d46-122">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58d46-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="58d46-123">[ **データベースの作成** ] ページで、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58d46-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="58d46-124">[ **データベースの作成の完了** ] ページで、[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58d46-124">On the **Database Creation Complete** page, click **Finish**.</span></span>
    


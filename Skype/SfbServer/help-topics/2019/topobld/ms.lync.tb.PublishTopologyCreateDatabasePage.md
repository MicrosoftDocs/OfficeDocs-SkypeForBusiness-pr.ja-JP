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
description: トポロジ ビルダーは、データベースをデータベース ストアにインストールSQL Serverします。 トポロジ ビルダーを使用してデータベースをインストールすると、アプリケーションはトポロジから情報を読み取り、指定された SQL Server コンピューターまたは SQL Server クラスターにインストールします。 これは、トポロジ ビルダーを使用して使用できるデータベース インストールの唯一の種類です。 特定のコンピューターに特定のデータベースをインストールする必要がある場合、または同一データベースをインストールする必要がある場合は、代わりに Windows PowerShell コマンド ライン インターフェイスと Install-CsDatabase コマンドレットを使用する必要があります。
ms.openlocfilehash: 92e0c8c0221fbd697ce59587ff4543d6cf7e119d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101833"
---
# <a name="create-database"></a><span data-ttu-id="40127-106">データベースの作成</span><span class="sxs-lookup"><span data-stu-id="40127-106">Create Database</span></span>
 
<span data-ttu-id="40127-107">トポロジ ビルダーは、データベースをデータベース ストアにインストールSQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="40127-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="40127-108">トポロジ ビルダーを使用してデータベースをインストールすると、アプリケーションはトポロジから情報を読み取り、指定された SQL Server コンピューターまたは SQL Server クラスターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="40127-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="40127-109">これは、トポロジ ビルダーを使用して使用できるデータベース インストールの唯一の種類です。</span><span class="sxs-lookup"><span data-stu-id="40127-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="40127-110">特定のコンピューターに特定のデータベースをインストールする必要がある場合、または同一データベースをインストールする必要がある場合は、代わりに Windows PowerShell コマンド ライン インターフェイスと [Install-CsDatabase](/powershell/module/skype/install-csdatabase?view=skype-ps) コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40127-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="40127-111">データベースの作成</span><span class="sxs-lookup"><span data-stu-id="40127-111">Creating a Database</span></span>

1. <span data-ttu-id="40127-112">[Skype for Business Server] ノードをクリックし、[データベースのインストール] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="40127-112">Click the Skype for Business Server node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="40127-113">[データベースの **インストール**] ダイアログ ボックスの [データベースの作成] ページで、新しいデータベースを作成する SQL Server ストアの完全修飾ドメイン名 (FQDN) を選択します。</span><span class="sxs-lookup"><span data-stu-id="40127-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="40127-114">[**詳細設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40127-114">Click **Advanced**.</span></span> <span data-ttu-id="40127-115">[データベース ファイル **の場所の選択] ダイアログ** ボックスで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="40127-115">In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
   - <span data-ttu-id="40127-116">**データベース ファイルの場所を自動的に決定します**。</span><span class="sxs-lookup"><span data-stu-id="40127-116">**Automatically determine database file location**.</span></span> <span data-ttu-id="40127-117">このオプションを選択すると、トポロジ ビルダーは組み込みのアルゴリズムを使用して、データベース ログとデータ ファイルの保存場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="40127-117">If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
   - <span data-ttu-id="40127-118">**[既定の SQL Server インスタンスを使用する]**。</span><span class="sxs-lookup"><span data-stu-id="40127-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="40127-119">このオプションを選択した場合、組み込みのアルゴリズムを使用して、データベース ログとデータ ファイルの保存場所を選択できません。</span><span class="sxs-lookup"><span data-stu-id="40127-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="40127-120">代わりに、ログ ファイルとデータ ファイルは SQL Server の既定のパスによって指定された場所に保存されます (SQL Server 管理者がこれらのパスを事前に構成しておく必要があります)。</span><span class="sxs-lookup"><span data-stu-id="40127-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="40127-121">データ ファイルは既定の SQL Server データ ファイルの場所に格納され、ログ ファイルは既定の SQL Server ログ ファイルの場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="40127-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="40127-122">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40127-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="40127-123">[データベースの作成 **] ページで** 、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="40127-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="40127-124">[データベース作成 **の完了] ページで、[** 完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="40127-124">On the **Database Creation Complete** page, click **Finish**.</span></span>

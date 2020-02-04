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
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: トポロジビルダーを使用すると、SQL Server ストアにデータベースをインストールすることができます。 トポロジビルダーを使用してデータベースをインストールする場合、アプリケーションはトポロジから情報を読み取り、指定された SQL Server コンピューターまたは SQL Server クラスターに必要なデータベースをインストールします。 トポロジ ビルダーを使用したデータベースのインストールは、この方法のみです。 特定のコンピューターに特定のデータベースをインストールする必要がある場合、または併置されたデータベースをインストールする必要がある場合は、代わりに Windows PowerShell コマンドラインインターフェイスと、CsDatabase コマンドレットを使用する必要があります。
ms.openlocfilehash: 02d754870cb2d2db16424474a68b8ea0245191f7
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684850"
---
# <a name="create-database"></a><span data-ttu-id="85e59-106">データベースの作成</span><span class="sxs-lookup"><span data-stu-id="85e59-106">Create Database</span></span>
 
<span data-ttu-id="85e59-107">トポロジビルダーを使用すると、SQL Server ストアにデータベースをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="85e59-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="85e59-108">トポロジビルダーを使用してデータベースをインストールする場合、アプリケーションはトポロジから情報を読み取り、指定された SQL Server コンピューターまたは SQL Server クラスターに必要なデータベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="85e59-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="85e59-109">トポロジ ビルダーを使用したデータベースのインストールは、この方法のみです。</span><span class="sxs-lookup"><span data-stu-id="85e59-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="85e59-110">特定のコンピューターに特定のデータベースをインストールする必要がある場合、または併置されたデータベースをインストールする必要がある場合は、代わりに Windows PowerShell コマンドラインインターフェイスと、 [CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps)コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85e59-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="85e59-111">データベースの作成</span><span class="sxs-lookup"><span data-stu-id="85e59-111">Creating a Database</span></span>

1. <span data-ttu-id="85e59-112">[Skype for Business Server 2015] ノードをクリックし、[**データベースのインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85e59-112">Click the Skype for Business Server 2015 node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="85e59-113">[データベースの**インストール**] ダイアログボックスの [**データベースの作成**] ページで、新しいデータベースを作成する SQL Server ストアの完全修飾ドメイン名 (FQDN) を選びます。</span><span class="sxs-lookup"><span data-stu-id="85e59-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="85e59-p103">[**詳細設定**] をクリックします。[**データベース ファイルの場所の選択**] ダイアログ ボックスで、次のどちらかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="85e59-p103">Click **Advanced**. In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
   - <span data-ttu-id="85e59-p104">[**データベース ファイルの場所を自動的に判断する**]。このオプションを選択すると、トポロジ ビルダーは、組み込みのアルゴリズムを使用して、データベースのログ ファイルとデータ ファイルの格納場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="85e59-p104">**Automatically determine database file location**. If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
   - <span data-ttu-id="85e59-118">[**既定の SQL Server インスタンスを使用する**]。</span><span class="sxs-lookup"><span data-stu-id="85e59-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="85e59-119">このオプションを選択すると、データベースのログ ファイルとデータ ファイルの格納場所を選択するために、組み込みのアルゴリズムは使用されません。</span><span class="sxs-lookup"><span data-stu-id="85e59-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="85e59-120">代わりに、ログとデータファイルは、SQL Server の既定のパスで指定した場所に保存されます (これらのパスは、SQL Server 管理者が advanced で構成する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="85e59-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="85e59-121">データ ファイルは SQL Server の既定のデータ ファイルの場所に格納され、ログ ファイルは SQL Server の既定のログ ファイルの場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="85e59-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="85e59-122">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85e59-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="85e59-123">[**データベースの作成**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85e59-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="85e59-124">[**データベースの作成の完了**] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85e59-124">On the **Database Creation Complete** page, click **Finish**.</span></span>
    


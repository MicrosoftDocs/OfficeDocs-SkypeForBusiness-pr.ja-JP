---
title: データベースのインストールと作成
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
ROBOTS: NOINDEX, NOFOLLOW
description: 展開を作成するデータベースを選択します。 既定では、データベース定義済みのサイトでは、定義済みの SQL Server 上に作成されますと、自動的に展開および構成データベースを配置するのには、SQL Server のデータベース ファイルです。
ms.openlocfilehash: f9b345a741182968e32bc0907d70c0924a61ea3f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32201794"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="af495-104">データベースのインストールと作成</span><span class="sxs-lookup"><span data-stu-id="af495-104">Install and Create Databases</span></span>

<span data-ttu-id="af495-105">展開を作成するデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="af495-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="af495-106">既定では、データベース定義済みのサイトでは、定義済みの SQL Server 上に作成されますと、自動的に展開および構成データベースを配置するのには、SQL Server のデータベース ファイルです。</span><span class="sxs-lookup"><span data-stu-id="af495-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="af495-107">**作成するデータベースを選択**します。 展開および構成するすべてのデータベースのチェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="af495-107">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure.</span></span> <span data-ttu-id="af495-108">展開する任意またはすべてのデータベースのチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="af495-108">Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="af495-109">SQL Server する必要があります既に設定されているインスタンス (ある場合) と、データベースを配置するインスタンスに対応するため、ファイアウォールのポートを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="af495-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="af495-110">詳細については、 [SQL Server の構成](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af495-110">For details, see [Configure SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>

 <span data-ttu-id="af495-111">**詳細設定**: [SQL Server] をクリックし、SQL Server 上のファイルの場所、データベースのオプションを選択する [**詳細設定**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="af495-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="af495-112">高度なデータベース ファイルの配置の詳細については、[データベースのインストールを使用して Lync Server 管理シェル](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af495-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>

 <span data-ttu-id="af495-113">**戻る**: このボタンをクリックすると (常に使用できない、このダイアログ ボックスに到着する方法に基づく)、前の画面に戻ります。</span><span class="sxs-lookup"><span data-stu-id="af495-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="af495-114">**次へ**: このボタンをクリックすると現在のダイアログ ボックスで選択内容をコミットし、追加情報を構成するための次のダイアログ ボックスに進み、</span><span class="sxs-lookup"><span data-stu-id="af495-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="af495-115">**キャンセル**: 変更を破棄して構成を終了して、このボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="af495-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="af495-116">終了し、変更を破棄する場合は、いくつかの構成画面では表示されます。</span><span class="sxs-lookup"><span data-stu-id="af495-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="af495-117">**[はい]** を選択するとは現在の構成を終了し現在の構成を終了し、トポロジ ビルダーに戻ります。</span><span class="sxs-lookup"><span data-stu-id="af495-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="af495-118">**いいえ**を選択すると、現在の構成] ダイアログ ボックスに戻ります、構成を続行することです。</span><span class="sxs-lookup"><span data-stu-id="af495-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="af495-119">**ヘルプ**: [**ヘルプ**] ボタンをクリックすると現在の構成] ダイアログ ボックスに関連付けられているヘルプ情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="af495-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>



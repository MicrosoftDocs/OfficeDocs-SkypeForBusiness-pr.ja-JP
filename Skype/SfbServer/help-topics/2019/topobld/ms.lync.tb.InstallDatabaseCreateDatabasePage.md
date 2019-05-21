---
title: データベースのインストールと作成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
ROBOTS: NOINDEX, NOFOLLOW
description: 展開用に作成するデータベースを選択します。 既定では、データベースは定義されたサイト内の定義された SQL Server 上に作成され、データベースの配置元の SQL Server に基づいて自動的にデータベースファイルを展開し、構成します。
ms.openlocfilehash: f4ee4bb5c5b6dcfe66680fdc163930470f1b50a5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291680"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="02ede-104">データベースのインストールと作成</span><span class="sxs-lookup"><span data-stu-id="02ede-104">Install and Create Databases</span></span>

<span data-ttu-id="02ede-105">展開用に作成するデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="02ede-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="02ede-106">既定では、データベースは定義されたサイト内の定義された SQL Server 上に作成され、データベースの配置元の SQL Server に基づいて自動的にデータベースファイルを展開し、構成します。</span><span class="sxs-lookup"><span data-stu-id="02ede-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="02ede-107">**作成するデータベースを選択**します。展開して構成するデータベースのチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="02ede-107">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure.</span></span> <span data-ttu-id="02ede-108">展開する任意またはすべてのデータベースのチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="02ede-108">Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="02ede-109">SQL Server はインスタンス (存在する場合) に対して既に設定されている必要があります。また、データベースの展開先のインスタンスに対応するためにファイアウォールポートを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="02ede-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="02ede-110">詳細については、「 [SQL Server の構成](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02ede-110">For details, see [Configure SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>

 <span data-ttu-id="02ede-111">**詳細設定**: sql server をクリックし、[**詳細設定**] ボタンをクリックして、sql server 上のデータベースファイルの場所のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="02ede-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="02ede-112">データベースファイルの高度な配置について詳しくは、「 [Lync Server 管理シェルを使用したデータベースのインストール](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="02ede-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>

 <span data-ttu-id="02ede-113">**戻る**: このボタンをクリックすると、前の画面に戻ります (このダイアログでの表示に応じて、常に使用できるとは限りません)。</span><span class="sxs-lookup"><span data-stu-id="02ede-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="02ede-114">**次へ**: このボタンをクリックすると、現在のダイアログで選択した内容がコミットされ、追加情報を構成するための次のダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="02ede-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="02ede-115">**[キャンセル**]: このボタンをクリックすると、構成が終了し、変更内容は破棄されます。</span><span class="sxs-lookup"><span data-stu-id="02ede-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="02ede-116">一部の構成画面では、変更を終了して破棄するかどうかを確認するメッセージが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="02ede-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="02ede-117">**[はい]** を選択すると、現在の構成が閉じられ、現在の構成が閉じて、トポロジビルダーに戻ります。</span><span class="sxs-lookup"><span data-stu-id="02ede-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="02ede-118">[**いいえ**] を選択すると、現在の構成ダイアログに戻り、構成を続行することができます。</span><span class="sxs-lookup"><span data-stu-id="02ede-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="02ede-119">**ヘルプ**: [**ヘルプ**] ボタンをクリックすると、現在の構成ダイアログに関連付けられたこのヘルプ情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="02ede-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>



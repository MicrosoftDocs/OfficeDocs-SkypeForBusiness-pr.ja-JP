---
title: データベースのインストールと作成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
ROBOTS: NOINDEX, NOFOLLOW
description: 展開用に作成するデータベースを選択します。 既定では、データベースは定義済みのサイトの定義済みの SQL Server に作成され、データベースを配置する SQL Server に基づいてデータベース ファイルを自動的に展開および構成します。
ms.openlocfilehash: 4d7a6e4f67dd6b97c8f5f837589af7b096da50b5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835717"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="e6876-104">データベースのインストールと作成</span><span class="sxs-lookup"><span data-stu-id="e6876-104">Install and Create Databases</span></span>

<span data-ttu-id="e6876-105">展開用に作成するデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="e6876-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="e6876-106">既定では、データベースは定義済みのサイトの定義済みの SQL Server に作成され、データベースを配置する SQL Server に基づいてデータベース ファイルを自動的に展開および構成します。</span><span class="sxs-lookup"><span data-stu-id="e6876-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="e6876-p103">[**作成するデータベースを選択**]: 展開および構成を行う任意のデータベースのチェックボックスをオンにします。展開を行う一部または全部のデータベースのチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e6876-p103">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure. Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="e6876-109">データベースSQL Serverインスタンス用に構成されている必要があります (存在する場合)、データベースを展開するインスタンスに合わせてファイアウォール ポートを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6876-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="e6876-110">詳細については、「Configure [SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span><span class="sxs-lookup"><span data-stu-id="e6876-110">For details, see [Configure SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>

 <span data-ttu-id="e6876-111">**[詳細設定**] : [SQL Server] をクリックし、[詳細設定] ボタンをクリックして、データベース上のデータベース ファイルの場所のオプションをSQL Server。</span><span class="sxs-lookup"><span data-stu-id="e6876-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="e6876-112">高度なデータベース ファイル配置の詳細については、「[Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6876-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>

 <span data-ttu-id="e6876-113">[**戻る**]: このボタンをクリックすると、前画面に戻ります (このダイアログへの到達方法によっては、必ずしも利用できない場合があります)。</span><span class="sxs-lookup"><span data-stu-id="e6876-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="e6876-114">[**次へ**]: このボタンをクリックすると、現在のダイアログでの選択を確定し、追加情報を構成する次のダイアログに移動します。</span><span class="sxs-lookup"><span data-stu-id="e6876-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="e6876-115">[**キャンセル**]: このボタンをクリックすると、構成を終了し、変更を破棄します。</span><span class="sxs-lookup"><span data-stu-id="e6876-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="e6876-116">終了し、変更を破棄する場合、確認メッセージが表示されることがあります (すべての構成画面で表示されるわけではありません)。</span><span class="sxs-lookup"><span data-stu-id="e6876-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="e6876-117">[はい **] を** 選択すると、現在の構成が閉じ、現在の構成が閉じ、トポロジ ビルダーに戻されます。</span><span class="sxs-lookup"><span data-stu-id="e6876-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="e6876-118">[**いいえ**] を選択すると、現在の構成ダイアログに戻り、構成を続行できます。</span><span class="sxs-lookup"><span data-stu-id="e6876-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="e6876-119">[**ヘルプ**]: [**ヘルプ**] をクリックすると、現在の構成ダイアログに関連付けられた、このヘルプ情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="e6876-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>



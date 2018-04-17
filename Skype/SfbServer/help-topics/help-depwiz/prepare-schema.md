---
title: スキーマの準備
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
description: To prepare the schema for Active Directory Domain Services, you run the Prepare Schema step in the Skype for Business Server Deployment Wizard. Click Run to begin the preparation of the schema. The Prepare Schema step reads the supplied schema definition files in the /Program Files/Microsoft Lync Server 2013/Deployment/Setup directory on the system that the Deployment Wizard is running on. These files are also available on the installation media in the Support/Schema directory. [スキーマの準備] 手順では、スキーマを拡張し、プロセスの状態を報告します。 また、プロセスが完了したことも通知します。 概要画面では、プロセスのログを表示できます。 ログを調べ、正常に準備が完了したことを確認してください。
ms.openlocfilehash: 190ee654984916e1f3417769ea65863f82566853
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="prepare-schema"></a><span data-ttu-id="7af92-110">スキーマの準備</span><span class="sxs-lookup"><span data-stu-id="7af92-110">Prepare Schema</span></span>
 
<span data-ttu-id="7af92-111">To prepare the schema for Active Directory Domain Services, you run the Prepare Schema step in the Skype for Business Server Deployment Wizard.</span><span class="sxs-lookup"><span data-stu-id="7af92-111">To prepare the schema for Active Directory Domain Services, you run the Prepare Schema step in the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="7af92-112">[**実行**] をクリックしてスキーマの準備を開始します。</span><span class="sxs-lookup"><span data-stu-id="7af92-112">Click **Run** to begin the preparation of the schema.</span></span> <span data-ttu-id="7af92-113">[スキーマの準備] 手順では、展開ウィザードが実行されているシステムの \Program Files\Microsoft Lync Server 2013\Deployment\Setup ディレクトリにある指定されたスキーマ定義ファイルを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="7af92-113">The Prepare Schema step reads the supplied schema definition files in the \Program Files\Microsoft Lync Server 2013\Deployment\Setup directory on the system that the Deployment Wizard is running on.</span></span> <span data-ttu-id="7af92-114">これらのファイルは、インストール メディアの \Support\Schema ディレクトリにもあります。</span><span class="sxs-lookup"><span data-stu-id="7af92-114">These files are also available on the installation media in the \Support\Schema directory.</span></span> <span data-ttu-id="7af92-115">[スキーマの準備] 手順では、スキーマを拡張し、プロセスの状態を報告します。</span><span class="sxs-lookup"><span data-stu-id="7af92-115">The Prepare Schema step will extend the schema and report the status of the process.</span></span> <span data-ttu-id="7af92-116">また、プロセスが完了したことも通知します。</span><span class="sxs-lookup"><span data-stu-id="7af92-116">It will also notify you when the process is complete.</span></span> <span data-ttu-id="7af92-117">概要画面では、プロセスのログを表示できます。</span><span class="sxs-lookup"><span data-stu-id="7af92-117">The summary screen will enable you to view the logs of the process.</span></span> <span data-ttu-id="7af92-118">ログを調べ、正常に準備が完了したことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7af92-118">Review the logs to be sure that the preparation was complete and successful.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7af92-119">スキーマを拡張するには、Schema Admins グループおよび Enterprise Admins グループのメンバーとしてドメインにログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7af92-119">To extend the schema, you must be logged into the domain as a member of the Schema Admins group and the Enterprise Admins group.</span></span> 
  
<span data-ttu-id="7af92-120">Classes and attributes are added to extend the Active Directory Domain Services schema to support Skype for Business Server 2015 server, service, and user objects.</span><span class="sxs-lookup"><span data-stu-id="7af92-120">Classes and attributes are added to extend the Active Directory Domain Services schema to support Skype for Business Server 2015 server, service, and user objects.</span></span> <span data-ttu-id="7af92-121">Before extending the schema, you should take a System State backup of the domain controller that holds the schema master role.</span><span class="sxs-lookup"><span data-stu-id="7af92-121">Before extending the schema, you should take a System State backup of the domain controller that holds the schema master role.</span></span> <span data-ttu-id="7af92-122">For details about the backup process for Windows Server 2008 R2 with SP1, see [https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198).</span><span class="sxs-lookup"><span data-stu-id="7af92-122">For details about the backup process for Windows Server 2008 R2 with SP1, see [https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198).</span></span> <span data-ttu-id="7af92-123">For Windows Server 2003 and Windows Server 2003 R2, see [https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199).</span><span class="sxs-lookup"><span data-stu-id="7af92-123">For Windows Server 2003 and Windows Server 2003 R2, see [https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="7af92-124">スキーマの拡張は元に戻すことはできません。</span><span class="sxs-lookup"><span data-stu-id="7af92-124">Extending the schema is not reversible.</span></span> <span data-ttu-id="7af92-125">スキーマ拡張が失敗した場合の潜在的な影響を抑制するためにあらゆる手段を講じて、スキーマの拡張が成功するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="7af92-125">You should make all possible efforts to limit the potential impact of a failed schema extension, and to ensure that the extension of the schema will be successful.</span></span> <span data-ttu-id="7af92-126">これは、通信が途絶えた場合や、サーバーでその他の障害が発生した場合には特に重要です。</span><span class="sxs-lookup"><span data-stu-id="7af92-126">This is particularly critical in the event of loss of communication or any other failure at the server.</span></span> <span data-ttu-id="7af92-127">You should perform a backup of the schema master domain controller and a complete backup of Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7af92-127">You should perform a backup of the schema master domain controller and a complete backup of Active Directory.</span></span> 
  
<span data-ttu-id="7af92-128">To perform a backup of the schema master domain controller and a complete backup of Active Directory:</span><span class="sxs-lookup"><span data-stu-id="7af92-128">To perform a backup of the schema master domain controller and a complete backup of Active Directory:</span></span>
  
1. <span data-ttu-id="7af92-129">スキーマ マスターの役割を持つドメイン コントローラーをネットワークから切断します。</span><span class="sxs-lookup"><span data-stu-id="7af92-129">Disconnect the domain controller that holds the schema master role from the network.</span></span>
    
2. <span data-ttu-id="7af92-130">スキーマ マスターを保持するドメイン コントローラーのシステム状態のバックアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="7af92-130">Perform a System State backup of the domain controller that holds the schema master.</span></span>
    
3. <span data-ttu-id="7af92-131">スキーマを拡張します。</span><span class="sxs-lookup"><span data-stu-id="7af92-131">Extend the schema.</span></span>
    
4. <span data-ttu-id="7af92-132">スキーマを正常に拡張できたら、ドメイン コントローラーをネットワークに再接続し、レプリケーションがアクティブで機能していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7af92-132">When the schema extension is successful, reconnect the domain controller to the network, and be sure that replication is active and working.</span></span>
    
5. <span data-ttu-id="7af92-133">In the unlikely event of a schema extension failure, restore the systems state of the domain controller and Active Directory by using the System State backup that you took earlier.</span><span class="sxs-lookup"><span data-stu-id="7af92-133">In the unlikely event of a schema extension failure, restore the systems state of the domain controller and Active Directory by using the System State backup that you took earlier.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7af92-134">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find the files on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span><span class="sxs-lookup"><span data-stu-id="7af92-134">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find the files on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="7af92-135">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="7af92-135">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  


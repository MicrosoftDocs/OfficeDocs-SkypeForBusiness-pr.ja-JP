---
title: スキーマの準備
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
description: Active Directory ドメイン サービスのスキーマを準備するには、Skype for Business Server 展開ウィザードでスキーマの準備手順を実行します。 [実行] をクリックしてスキーマの準備を開始します。 [スキーマの準備] 手順では、展開ウィザードが実行されているシステムの /Program Files/Microsoft Lync Server 2013/Deployment/Setup ディレクトリ内の指定されたスキーマ定義ファイルを読み取ります。 これらのファイルは、サポート/スキーマ ディレクトリのインストール メディアでも使用できます。 [スキーマの準備] 手順では、スキーマを拡張し、プロセスの状態を報告します。 また、プロセスが完了したことも通知します。 概要画面では、プロセスのログを表示できます。 ログを調べ、正常に準備が完了したことを確認してください。
ms.openlocfilehash: c3279be54ad5f68d5c2ee61d8d3c12c0fc9d9203
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51108623"
---
# <a name="prepare-schema"></a><span data-ttu-id="5dfdb-110">スキーマの準備</span><span class="sxs-lookup"><span data-stu-id="5dfdb-110">Prepare Schema</span></span>
 
<span data-ttu-id="5dfdb-111">Active Directory ドメイン サービスのスキーマを準備するには、Skype for Business Server 展開ウィザードでスキーマの準備手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5dfdb-111">To prepare the schema for Active Directory Domain Services, you run the Prepare Schema step in the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="5dfdb-112">**[実行]** をクリックしてスキーマの準備を開始します。</span><span class="sxs-lookup"><span data-stu-id="5dfdb-112">Click **Run** to begin the preparation of the schema.</span></span> <span data-ttu-id="5dfdb-113">[スキーマの準備] 手順では、展開ウィザードが実行されているシステムの \Program Files\Microsoft Lync Server 2013\Deployment\Setup ディレクトリにある指定されたスキーマ定義ファイルを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="5dfdb-113">The Prepare Schema step reads the supplied schema definition files in the \Program Files\Microsoft Lync Server 2013\Deployment\Setup directory on the system that the Deployment Wizard is running on.</span></span> <span data-ttu-id="5dfdb-114">これらのファイルは、インストール メディアの \Support\Schema ディレクトリにもあります。</span><span class="sxs-lookup"><span data-stu-id="5dfdb-114">These files are also available on the installation media in the \Support\Schema directory.</span></span> <span data-ttu-id="5dfdb-115">[スキーマの準備] 手順では、スキーマを拡張し、プロセスの状態を報告します。</span><span class="sxs-lookup"><span data-stu-id="5dfdb-115">The Prepare Schema step will extend the schema and report the status of the process.</span></span> <span data-ttu-id="5dfdb-116">また、プロセスが完了したことも通知します。</span><span class="sxs-lookup"><span data-stu-id="5dfdb-116">It will also notify you when the process is complete.</span></span> <span data-ttu-id="5dfdb-117">概要画面では、プロセスのログを表示できます。</span><span class="sxs-lookup"><span data-stu-id="5dfdb-117">The summary screen will enable you to view the logs of the process.</span></span> <span data-ttu-id="5dfdb-118">ログを調べ、正常に準備が完了したことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5dfdb-118">Review the logs to be sure that the preparation was complete and successful.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5dfdb-119">スキーマを拡張するには、Schema Admins グループおよび Enterprise Admins グループのメンバーとしてドメインにログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5dfdb-119">To extend the schema, you must be logged into the domain as a member of the Schema Admins group and the Enterprise Admins group.</span></span> 
  
<span data-ttu-id="5dfdb-120">クラスと属性が追加され、Active Directory ドメイン サービス スキーマが拡張され、Skype for Business Server 2015 サーバー、サービス、およびユーザー オブジェクトがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="5dfdb-120">Classes and attributes are added to extend the Active Directory Domain Services schema to support Skype for Business Server 2015 server, service, and user objects.</span></span> <span data-ttu-id="5dfdb-121">スキーマを拡張する前に、スキーマ マスター役割を持つドメイン コントローラーのシステム状態バックアップを行ってください。</span><span class="sxs-lookup"><span data-stu-id="5dfdb-121">Before extending the schema, you should take a System State backup of the domain controller that holds the schema master role.</span></span> <span data-ttu-id="5dfdb-122">SP1 を使用する場合のバックアップ プロセスWindows Server 2008 R2を参照してください [https://go.microsoft.com/fwlink/p/?linkId=207198](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee849849(v=ws.10)) 。</span><span class="sxs-lookup"><span data-stu-id="5dfdb-122">For details about the backup process for Windows Server 2008 R2 with SP1, see [https://go.microsoft.com/fwlink/p/?linkId=207198](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee849849(v=ws.10)).</span></span> <span data-ttu-id="5dfdb-123">Windows Server 2003 および windows Server 2003 Windows Server 2003 R2を参照してください [https://go.microsoft.com/fwlink/p/?linkId=207199](/previous-versions/windows/it-pro/windows-server-2003/cc787254(v=ws.10)) 。</span><span class="sxs-lookup"><span data-stu-id="5dfdb-123">For Windows Server 2003 and Windows Server 2003 R2, see [https://go.microsoft.com/fwlink/p/?linkId=207199](/previous-versions/windows/it-pro/windows-server-2003/cc787254(v=ws.10)).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="5dfdb-124">スキーマの拡張は元に戻すことはできません。</span><span class="sxs-lookup"><span data-stu-id="5dfdb-124">Extending the schema is not reversible.</span></span> <span data-ttu-id="5dfdb-125">スキーマ拡張が失敗した場合の潜在的な影響を抑制するためにあらゆる手段を講じ、スキーマの拡張が成功するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="5dfdb-125">You should make all possible efforts to limit the potential impact of a failed schema extension, and to ensure that the extension of the schema will be successful.</span></span> <span data-ttu-id="5dfdb-126">これは、通信が途絶えた場合や、サーバーでその他の障害が発生した場合には特に重要です。</span><span class="sxs-lookup"><span data-stu-id="5dfdb-126">This is particularly critical in the event of loss of communication or any other failure at the server.</span></span> <span data-ttu-id="5dfdb-127">スキーマ マスター ドメイン コントローラーのバックアップと Active Directory の完全なバックアップを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5dfdb-127">You should perform a backup of the schema master domain controller and a complete backup of Active Directory.</span></span> 
  
<span data-ttu-id="5dfdb-128">スキーマ マスター ドメイン コントローラーのバックアップと Active Directory の完全なバックアップを実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5dfdb-128">To perform a backup of the schema master domain controller and a complete backup of Active Directory:</span></span>
  
1. <span data-ttu-id="5dfdb-129">スキーマ マスター役割を持つドメイン コントローラーをネットワークから切断します。</span><span class="sxs-lookup"><span data-stu-id="5dfdb-129">Disconnect the domain controller that holds the schema master role from the network.</span></span>
    
2. <span data-ttu-id="5dfdb-130">スキーマ マスターを保持するドメイン コントローラーのシステム状態バックアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="5dfdb-130">Perform a System State backup of the domain controller that holds the schema master.</span></span>
    
3. <span data-ttu-id="5dfdb-131">スキーマを拡張します。</span><span class="sxs-lookup"><span data-stu-id="5dfdb-131">Extend the schema.</span></span>
    
4. <span data-ttu-id="5dfdb-132">スキーマを正常に拡張できたら、ドメイン コントローラーをネットワークに再接続し、レプリケーションがアクティブで機能していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5dfdb-132">When the schema extension is successful, reconnect the domain controller to the network, and be sure that replication is active and working.</span></span>
    
5. <span data-ttu-id="5dfdb-133">スキーマ拡張機能に障害が発生した場合は、前に行った System State バックアップを使用して、ドメイン コントローラーと Active Directory のシステム状態を復元します。</span><span class="sxs-lookup"><span data-stu-id="5dfdb-133">In the unlikely event of a schema extension failure, restore the systems state of the domain controller and Active Directory by using the System State backup that you took earlier.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5dfdb-134">Skype for Business Server 展開ウィザードによって作成されたログ ファイルを確認する必要がある場合は、展開ウィザードが実行されたコンピューター上のファイルを、手順を実行した Active Directory ユーザーの Users ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="5dfdb-134">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find the files on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="5dfdb-135">たとえば、ユーザーがドメイン Contoso.net でドメイン管理者としてログインした場合、ログ ファイルは C:\Users\Administrator.Contoso\AppData\Local\Temp にあります。</span><span class="sxs-lookup"><span data-stu-id="5dfdb-135">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 

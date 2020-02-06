---
title: スキーマの準備
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
ROBOTS: NOINDEX, NOFOLLOW
description: Active Directory ドメインサービスのスキーマを準備するには、Skype for Business Server 展開ウィザードでスキーマの準備手順を実行します。 [実行] をクリックしてスキーマの準備を開始します。
ms.openlocfilehash: c7a9529112aace5199a45c9556d3756a940fba95
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794806"
---
# <a name="prepare-schema"></a><span data-ttu-id="2b96c-104">スキーマの準備</span><span class="sxs-lookup"><span data-stu-id="2b96c-104">Prepare Schema</span></span>
 
<span data-ttu-id="2b96c-105">Active Directory ドメインサービスのスキーマを準備するには、Skype for Business Server 展開ウィザードでスキーマの準備手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2b96c-105">To prepare the schema for Active Directory Domain Services, you run the Prepare Schema step in the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="2b96c-106">[**実行**] をクリックしてスキーマの準備を開始します。</span><span class="sxs-lookup"><span data-stu-id="2b96c-106">Click **Run** to begin the preparation of the schema.</span></span> <span data-ttu-id="2b96c-107">[スキーマの準備] 手順では、展開ウィザードが実行されているシステム上の Files\Skype ディレクトリで、提供されているスキーマ定義のファイルを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="2b96c-107">The Prepare Schema step reads the supplied schema definition files in the \Program Files\Skype for Business Server 2019\Deployment\Setup directory on the system that the Deployment Wizard is running on.</span></span> <span data-ttu-id="2b96c-108">これらのファイルは、インストール メディアの \Support\Schema ディレクトリにもあります。</span><span class="sxs-lookup"><span data-stu-id="2b96c-108">These files are also available on the installation media in the \Support\Schema directory.</span></span> <span data-ttu-id="2b96c-109">[スキーマの準備] 手順では、スキーマを拡張し、プロセスの状態を報告します。</span><span class="sxs-lookup"><span data-stu-id="2b96c-109">The Prepare Schema step will extend the schema and report the status of the process.</span></span> <span data-ttu-id="2b96c-110">また、プロセスが完了したことも通知します。</span><span class="sxs-lookup"><span data-stu-id="2b96c-110">It will also notify you when the process is complete.</span></span> <span data-ttu-id="2b96c-111">概要画面では、プロセスのログを表示できます。</span><span class="sxs-lookup"><span data-stu-id="2b96c-111">The summary screen will enable you to view the logs of the process.</span></span> <span data-ttu-id="2b96c-112">ログを調べ、正常に準備が完了したことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2b96c-112">Review the logs to be sure that the preparation was complete and successful.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2b96c-113">スキーマを拡張するには、Schema Admins グループおよび Enterprise Admins グループのメンバーとしてドメインにログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b96c-113">To extend the schema, you must be logged into the domain as a member of the Schema Admins group and the Enterprise Admins group.</span></span> 
  
<span data-ttu-id="2b96c-114">クラスと属性を追加して、Skype for Business Server server、サービス、ユーザーオブジェクトをサポートするように Active Directory ドメインサービススキーマを拡張します。</span><span class="sxs-lookup"><span data-stu-id="2b96c-114">Classes and attributes are added to extend the Active Directory Domain Services schema to support Skype for Business Server server, service, and user objects.</span></span> <span data-ttu-id="2b96c-115">スキーマを拡張する前に、スキーママスターの役割を保持しているドメインコントローラーのシステム状態のバックアップを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b96c-115">Before extending the schema, you should take a System State backup of the domain controller that holds the schema master role.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="2b96c-116">スキーマの拡張は元に戻すことはできません。</span><span class="sxs-lookup"><span data-stu-id="2b96c-116">Extending the schema is not reversible.</span></span> <span data-ttu-id="2b96c-117">スキーマ拡張が失敗した場合の潜在的な影響を抑制するためにあらゆる手段を講じて、スキーマの拡張が成功するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="2b96c-117">You should make all possible efforts to limit the potential impact of a failed schema extension, and to ensure that the extension of the schema will be successful.</span></span> <span data-ttu-id="2b96c-118">これは、通信が途絶えた場合や、サーバーでその他の障害が発生した場合には特に重要です。</span><span class="sxs-lookup"><span data-stu-id="2b96c-118">This is particularly critical in the event of loss of communication or any other failure at the server.</span></span> <span data-ttu-id="2b96c-119">スキーママスタードメインコントローラーのバックアップを実行し、Active Directory の完全なバックアップを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b96c-119">You should perform a backup of the schema master domain controller and a complete backup of Active Directory.</span></span> 
  
<span data-ttu-id="2b96c-120">スキーママスタードメインコントローラーのバックアップ、および Active Directory の完全なバックアップを実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2b96c-120">To perform a backup of the schema master domain controller and a complete backup of Active Directory:</span></span>
  
1. <span data-ttu-id="2b96c-121">スキーマ マスターの役割を持つドメイン コントローラーをネットワークから切断します。</span><span class="sxs-lookup"><span data-stu-id="2b96c-121">Disconnect the domain controller that holds the schema master role from the network.</span></span>
    
2. <span data-ttu-id="2b96c-122">スキーマ マスターを保持するドメイン コントローラーのシステム状態のバックアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="2b96c-122">Perform a System State backup of the domain controller that holds the schema master.</span></span>
    
3. <span data-ttu-id="2b96c-123">スキーマを拡張します。</span><span class="sxs-lookup"><span data-stu-id="2b96c-123">Extend the schema.</span></span>
    
4. <span data-ttu-id="2b96c-124">スキーマを正常に拡張できたら、ドメイン コントローラーをネットワークに再接続し、レプリケーションがアクティブで機能していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2b96c-124">When the schema extension is successful, reconnect the domain controller to the network, and be sure that replication is active and working.</span></span>
    
5. <span data-ttu-id="2b96c-125">スキーマの拡張エラーが発生した場合は、前に行ったシステム状態のバックアップを使用して、ドメインコントローラーと Active Directory のシステム状態を復元します。</span><span class="sxs-lookup"><span data-stu-id="2b96c-125">In the unlikely event of a schema extension failure, restore the systems state of the domain controller and Active Directory by using the System State backup that you took earlier.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2b96c-126">Skype for Business Server Deployment ウィザードによって作成されたログファイルを確認する必要がある場合は、展開ウィザードが実行されたコンピューター上のファイルを、手順を実行した Active Directory ユーザーの Users ディレクトリで見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="2b96c-126">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find the files on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="2b96c-127">たとえば、ユーザーがドメイン Contoso.net のドメイン管理者としてログインしている場合、ログファイルは C:\Users\Administrator.Contoso\AppData\Local\Temp にあります。</span><span class="sxs-lookup"><span data-stu-id="2b96c-127">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  


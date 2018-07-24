---
title: スキーマの準備
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
ROBOTS: NOINDEX, NOFOLLOW
description: Active Directory ドメイン サービスのスキーマを準備するのにはビジネス サーバーの展開ウィザードは、Skype で、スキーマの準備の手順を実行します。 [実行] をクリックしてスキーマの準備を開始します。
ms.openlocfilehash: adc0ad796b608671816d50a93f75dc89f2a4a13b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21020134"
---
# <a name="prepare-schema"></a><span data-ttu-id="97958-104">スキーマの準備</span><span class="sxs-lookup"><span data-stu-id="97958-104">Prepare Schema</span></span>
 
<span data-ttu-id="97958-105">Active Directory ドメイン サービスのスキーマを準備するのにはビジネス サーバーの展開ウィザードは、Skype で、スキーマの準備の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="97958-105">To prepare the schema for Active Directory Domain Services, you run the Prepare Schema step in the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="97958-106">[**実行**] をクリックしてスキーマの準備を開始します。</span><span class="sxs-lookup"><span data-stu-id="97958-106">Click **Run** to begin the preparation of the schema.</span></span> <span data-ttu-id="97958-107">[スキーマの準備] 手順では、展開ウィザードが実行されているシステムの \Program Files\Microsoft Lync Server 2013\Deployment\Setup ディレクトリにある指定されたスキーマ定義ファイルを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="97958-107">The Prepare Schema step reads the supplied schema definition files in the \Program Files\Microsoft Lync Server 2013\Deployment\Setup directory on the system that the Deployment Wizard is running on.</span></span> <span data-ttu-id="97958-108">これらのファイルは、インストール メディアの \Support\Schema ディレクトリにもあります。</span><span class="sxs-lookup"><span data-stu-id="97958-108">These files are also available on the installation media in the \Support\Schema directory.</span></span> <span data-ttu-id="97958-109">[スキーマの準備] 手順では、スキーマを拡張し、プロセスの状態を報告します。</span><span class="sxs-lookup"><span data-stu-id="97958-109">The Prepare Schema step will extend the schema and report the status of the process.</span></span> <span data-ttu-id="97958-110">また、プロセスが完了したことも通知します。</span><span class="sxs-lookup"><span data-stu-id="97958-110">It will also notify you when the process is complete.</span></span> <span data-ttu-id="97958-111">概要画面では、プロセスのログを表示できます。</span><span class="sxs-lookup"><span data-stu-id="97958-111">The summary screen will enable you to view the logs of the process.</span></span> <span data-ttu-id="97958-112">ログを調べ、正常に準備が完了したことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="97958-112">Review the logs to be sure that the preparation was complete and successful.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="97958-113">スキーマを拡張するには、Schema Admins グループおよび Enterprise Admins グループのメンバーとしてドメインにログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="97958-113">To extend the schema, you must be logged into the domain as a member of the Schema Admins group and the Enterprise Admins group.</span></span> 
  
<span data-ttu-id="97958-114">ビジネス サーバーのサーバー、サービス、およびユーザー オブジェクトの Skype をサポートするために Active Directory ドメイン サービス スキーマを拡張するクラスおよび属性が追加されます。</span><span class="sxs-lookup"><span data-stu-id="97958-114">Classes and attributes are added to extend the Active Directory Domain Services schema to support Skype for Business Server server, service, and user objects.</span></span> <span data-ttu-id="97958-115">スキーマを拡張する前に行う必要があるシステムの状態、スキーマ マスターの役割を保持しているドメイン コント ローラーのバックアップを作成します。</span><span class="sxs-lookup"><span data-stu-id="97958-115">Before extending the schema, you should take a System State backup of the domain controller that holds the schema master role.</span></span> <span data-ttu-id="97958-116">Windows Server 2008 R2 の sp1 のバックアップ ・ プロセスに関する詳細についてを参照してください[https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198)。</span><span class="sxs-lookup"><span data-stu-id="97958-116">For details about the backup process for Windows Server 2008 R2 with SP1, see [https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198).</span></span> <span data-ttu-id="97958-117">Windows Server 2003 と Windows Server 2003 R2 を参照してください[https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199)。</span><span class="sxs-lookup"><span data-stu-id="97958-117">For Windows Server 2003 and Windows Server 2003 R2, see [https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="97958-118">スキーマの拡張は元に戻すことはできません。</span><span class="sxs-lookup"><span data-stu-id="97958-118">Extending the schema is not reversible.</span></span> <span data-ttu-id="97958-119">スキーマ拡張が失敗した場合の潜在的な影響を抑制するためにあらゆる手段を講じて、スキーマの拡張が成功するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="97958-119">You should make all possible efforts to limit the potential impact of a failed schema extension, and to ensure that the extension of the schema will be successful.</span></span> <span data-ttu-id="97958-120">これは、通信が途絶えた場合や、サーバーでその他の障害が発生した場合には特に重要です。</span><span class="sxs-lookup"><span data-stu-id="97958-120">This is particularly critical in the event of loss of communication or any other failure at the server.</span></span> <span data-ttu-id="97958-121">スキーマ マスター ドメイン コント ローラーのバックアップとアクティブなディレクトリの完全なバックアップを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97958-121">You should perform a backup of the schema master domain controller and a complete backup of Active Directory.</span></span> 
  
<span data-ttu-id="97958-122">スキーマ マスター ドメイン コント ローラーのバックアップおよび Active Directory の完全なバックアップを実行するには。</span><span class="sxs-lookup"><span data-stu-id="97958-122">To perform a backup of the schema master domain controller and a complete backup of Active Directory:</span></span>
  
1. <span data-ttu-id="97958-123">スキーマ マスターの役割を持つドメイン コントローラーをネットワークから切断します。</span><span class="sxs-lookup"><span data-stu-id="97958-123">Disconnect the domain controller that holds the schema master role from the network.</span></span>
    
2. <span data-ttu-id="97958-124">スキーマ マスターを保持するドメイン コントローラーのシステム状態のバックアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="97958-124">Perform a System State backup of the domain controller that holds the schema master.</span></span>
    
3. <span data-ttu-id="97958-125">スキーマを拡張します。</span><span class="sxs-lookup"><span data-stu-id="97958-125">Extend the schema.</span></span>
    
4. <span data-ttu-id="97958-126">スキーマを正常に拡張できたら、ドメイン コントローラーをネットワークに再接続し、レプリケーションがアクティブで機能していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="97958-126">When the schema extension is successful, reconnect the domain controller to the network, and be sure that replication is active and working.</span></span>
    
5. <span data-ttu-id="97958-127">スキーマ拡張機能障害が万一、前述したシステム状態バックアップを使用してドメイン コント ローラーと Active Directory のシステム状態を復元します。</span><span class="sxs-lookup"><span data-stu-id="97958-127">In the unlikely event of a schema extension failure, restore the systems state of the domain controller and Active Directory by using the System State backup that you took earlier.</span></span>
    
> [!NOTE]
> <span data-ttu-id="97958-128">ビジネス サーバーの展開ウィザードは、Skype によって作成されるログ ファイルを確認する場合は、コンピューター上で、展開ウィザードが実行されたの手順を実行した Active Directory ユーザーのユーザー ディレクトリにファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="97958-128">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find the files on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="97958-129">たとえば、ユーザー Contoso.net のドメインのドメイン管理者としてログインしている場合、ログ ・ ファイル内にある: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="97958-129">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  


---
title: ユーザー レプリケーションの完了の確認
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 移動-CsUser コマンドレットを実行しているときに、最初のレプリケーションが完了していないため、Active Directory ドメインサービス (AD DS) と Skype for Business Server 2019 データベース間のユーザー情報が同期されていないため、エラーが発生する可能性があります。 Skype for Business Server 2019 ユーザーレプリケーターサービスの初期同期が正常に完了するまでにかかる時間は、Skype for Business をホストしている Active Directory フォレストでホストされているドメインコントローラーの数によって異なります。サーバー2019プール。 Skype for Business Server 2019 ユーザーレプリケーターサービスの初期同期処理は、Skype for Business Server 2019 フロントエンドサーバーが初めて起動したときに発生します。 その後、同期はユーザーレプリケーターの間隔に基づいています。 次の手順を実行して、ユーザーの複製が完了したことを確認してから、移動-CsUser コマンドレットを実行します。
ms.openlocfilehash: 31f4f9f1045367e376d4536df54c32be14580312
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812655"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="a4117-107">ユーザー レプリケーションの完了の確認</span><span class="sxs-lookup"><span data-stu-id="a4117-107">Verify user replication has completed</span></span>

<span data-ttu-id="a4117-108">**移動-csuser**コマンドレットを実行しているときに、最初のレプリケーションが完了していないため、Active Directory ドメインサービス (AD DS) と Skype For business Server 2019 データベースの間でユーザー情報が同期されていない場合、エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a4117-108">When running the **Move-CsUser** cmdlet, you may experience a failure if user information between Active Directory Domain Services (AD DS) and the Skype for Business Server 2019 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="a4117-109">Skype for Business Server 2019 ユーザーレプリケーターサービスの初期同期が正常に完了するまでにかかる時間は、Skype for Business をホストしている Active Directory フォレストでホストされているドメインコントローラーの数によって異なります。サーバー2019プール。</span><span class="sxs-lookup"><span data-stu-id="a4117-109">The time it takes for the successful completion of the Skype for Business Server 2019 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="a4117-110">Skype for Business Server 2019 ユーザーレプリケーターサービスの初期同期処理は、Skype for Business Server 2019 フロントエンドサーバーが初めて起動したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="a4117-110">The Skype for Business Server 2019 User Replicator service initial synchronization process occurs when the Skype for Business Server 2019 Front End Server is started for the first time.</span></span> <span data-ttu-id="a4117-111">その後、同期はユーザーレプリケーターの間隔に基づいています。</span><span class="sxs-lookup"><span data-stu-id="a4117-111">After that, the synchronization is based on the User Replicator interval.</span></span> <span data-ttu-id="a4117-112">次の手順を実行して、ユーザーの複製が完了していることを確認してから、 **csuser**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="a4117-112">Complete the following steps to verify that user replication has completed before running the **Move-CsUser** cmdlet.</span></span> 
  
### <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="a4117-113">ユーザーの複製が完了したことを確認するには</span><span class="sxs-lookup"><span data-stu-id="a4117-113">To verify that user replication has completed</span></span>

1. <span data-ttu-id="a4117-114">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="a4117-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="a4117-115">[**スタート**] メニューをクリックし、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4117-115">Click the **Start** menu, and then click **Run**.</span></span> 
    
3. <span data-ttu-id="a4117-116">**Eventvwr.exe**と入力して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4117-116">Enter **eventvwr.exe**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="a4117-117">イベントビューアーで [**アプリケーションとサービスログ**] をクリックして展開し、[Skype For business Server] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4117-117">In Event Viewer, click **Applications and Services logs** to expand it, and then select Skype for Business Server.</span></span> 
    
5. <span data-ttu-id="a4117-118">[**操作**] ウィンドウで、[**現在のログをフィルター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4117-118">In the **Actions** pane, click **Filter Current Log**.</span></span>
    
6. <span data-ttu-id="a4117-119">[**イベントソース**] ボックスの一覧の [ **LS ユーザーレプリケーター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4117-119">From the **Event sources** list, click **LS User Replicator**.</span></span>
    
7. <span data-ttu-id="a4117-120">\*\* \<すべてのイベント id\>\*\* で「 **30024**」と入力して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4117-120">In **\<All Event IDs\>**, enter **30024**, and then click **OK**.</span></span> 
    
8. <span data-ttu-id="a4117-121">[フィルター処理されたイベント] ボックスの一覧の **[全般**] タブで、ユーザーの複製が正常に完了したことを示すエントリを探します。</span><span class="sxs-lookup"><span data-stu-id="a4117-121">In the filtered events list, on the **General** tab, look for an entry that states that user replication has completed successfully.</span></span> 
    


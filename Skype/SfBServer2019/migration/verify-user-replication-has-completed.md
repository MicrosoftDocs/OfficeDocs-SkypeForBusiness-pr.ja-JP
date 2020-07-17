---
title: ユーザー レプリケーションの完了の確認
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 最初のレプリケーションが完了していないため、Active Directory ドメインサービス (AD DS) と Skype for Business Server 2019 データベース間のユーザー情報が同期されていないため、CsUser コマンドレットを実行しているときにエラーが発生することがあります。 Skype for Business Server 2019 のユーザーレプリケーターサービスの初期同期が正常に完了するまでにかかる時間は、Skype for Business Server 2019 プールをホストしている Active Directory フォレスト内でホストされているドメインコントローラーの数によって異なります。 Skype for Business Server 2019 のユーザーレプリケーターサービスの初期同期処理は、Skype for business Server 2019 フロントエンドサーバーが初めて起動されたときに発生します。 それ以降は、ユーザー レプリケーターの間隔に基づいて同期が行われます。 Move-CsUser コマンドレットを実行する前に、次の手順を実行して、ユーザーのレプリケーションが完了していることを確認してください。
ms.openlocfilehash: 5aa832216cc5eddce1d80cc9401ec9992c9edbf1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751649"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="9ed98-107">ユーザー レプリケーションの完了の確認</span><span class="sxs-lookup"><span data-stu-id="9ed98-107">Verify user replication has completed</span></span>

<span data-ttu-id="9ed98-108">最初のレプリケーションが完了していないために、Active Directory ドメインサービス (AD DS) と Skype for Business Server 2019 データベースの間のユーザー情報が同期されていない場合、 **csuser**コマンドレットを実行すると障害が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9ed98-108">When running the **Move-CsUser** cmdlet, you may experience a failure if user information between Active Directory Domain Services (AD DS) and the Skype for Business Server 2019 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="9ed98-109">Skype for Business Server 2019 のユーザーレプリケーターサービスの初期同期が正常に完了するまでにかかる時間は、Skype for Business Server 2019 プールをホストしている Active Directory フォレスト内でホストされているドメインコントローラーの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="9ed98-109">The time it takes for the successful completion of the Skype for Business Server 2019 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="9ed98-110">Skype for Business Server 2019 のユーザーレプリケーターサービスの初期同期処理は、Skype for business Server 2019 フロントエンドサーバーが初めて起動されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="9ed98-110">The Skype for Business Server 2019 User Replicator service initial synchronization process occurs when the Skype for Business Server 2019 Front End Server is started for the first time.</span></span> <span data-ttu-id="9ed98-111">その後は、ユーザーレプリケーターの間隔に基づいて同期が実行されます。</span><span class="sxs-lookup"><span data-stu-id="9ed98-111">After that, the synchronization is based on the User Replicator interval.</span></span> <span data-ttu-id="9ed98-112">次の手順を実行して、ユーザーのレプリケーションが完了したことを確認してから、 **csuser**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="9ed98-112">Complete the following steps to verify that user replication has completed before running the **Move-CsUser** cmdlet.</span></span> 
  
### <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="9ed98-113">ユーザーのレプリケーションが完了していることを確認するには</span><span class="sxs-lookup"><span data-stu-id="9ed98-113">To verify that user replication has completed</span></span>

1. <span data-ttu-id="9ed98-114">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="9ed98-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="9ed98-115">[**スタート**] メニューをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ed98-115">Click the **Start** menu, and then click **Run**.</span></span> 
    
3. <span data-ttu-id="9ed98-116">「**eventvwr.exe**」と入力し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ed98-116">Enter **eventvwr.exe**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="9ed98-117">イベントビューアーで、[**アプリケーションとサービスログ**] をクリックして展開し、[Skype For business Server] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ed98-117">In Event Viewer, click **Applications and Services logs** to expand it, and then select Skype for Business Server.</span></span> 
    
5. <span data-ttu-id="9ed98-118">[**操作**] ウィンドウで [**現在のログをフィルター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ed98-118">In the **Actions** pane, click **Filter Current Log**.</span></span>
    
6. <span data-ttu-id="9ed98-119">[**イベント ソース**] ボックスの一覧の [**LS User Replicator**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ed98-119">From the **Event sources** list, click **LS User Replicator**.</span></span>
    
7. <span data-ttu-id="9ed98-120">で **\<All Event IDs\>** 、 **30024**と入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ed98-120">In **\<All Event IDs\>**, enter **30024**, and then click **OK**.</span></span> 
    
8. <span data-ttu-id="9ed98-121">フィルター処理されたイベントの一覧の **[全般**] タブで、ユーザーのレプリケーションが正常に完了したことを示すエントリを探します。</span><span class="sxs-lookup"><span data-stu-id="9ed98-121">In the filtered events list, on the **General** tab, look for an entry that states that user replication has completed successfully.</span></span> 
    


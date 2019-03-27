---
title: ユーザー レプリケーションの完了の確認
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 移動 CsUser コマンドレットを実行するときの最初のレプリケーションは完全ではありませんので、ユーザー情報を Active Directory ドメイン サービス (AD DS) とデータベースのビジネス サーバー 2019 Skype との間はとれていないため障害が発生した可能性があります。 サーバー 2019 ユーザー レプリケーターのビジネス サービスの初期同期のための Skype が正常に完了にかかる時間は、ビジネスの Skype をホストしている Active Directory フォレスト内でホストされているドメイン コント ローラーの数によって異なります。サーバー 2019年プールです。 サーバー 2019 ユーザー レプリケーターのビジネス サービスの初期同期プロセスの Skype は、ビジネス 2019 フロント エンド サーバーの Skype が最初に起動したときに発生します。 その後は、同期は、ユーザー レプリケーター間隔をに基づいてください。 移動 CsUser コマンドレットを実行する前にユーザーの複製が完了していることを確認するのには次の手順を完了します。
ms.openlocfilehash: bab54e91ebda7a10804980e368e05bb58ff911ff
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889509"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="4fb14-107">ユーザー レプリケーションの完了の確認</span><span class="sxs-lookup"><span data-stu-id="4fb14-107">Verify user replication has completed</span></span>

<span data-ttu-id="4fb14-108">**移動 CsUser**コマンドレットを実行するときの最初のレプリケーションは完全ではありませんので、ユーザー情報を Active Directory ドメイン サービス (AD DS) とデータベースのビジネス サーバー 2019 Skype との間はとれていない場合は、障害が発生した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4fb14-108">When running the **Move-CsUser** cmdlet, you may experience a failure if user information between Active Directory Domain Services (AD DS) and the Skype for Business Server 2019 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="4fb14-109">サーバー 2019 ユーザー レプリケーターのビジネス サービスの初期同期のための Skype が正常に完了にかかる時間は、ビジネスの Skype をホストしている Active Directory フォレスト内でホストされているドメイン コント ローラーの数によって異なります。サーバー 2019年プールです。</span><span class="sxs-lookup"><span data-stu-id="4fb14-109">The time it takes for the successful completion of the Skype for Business Server 2019 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="4fb14-110">サーバー 2019 ユーザー レプリケーターのビジネス サービスの初期同期プロセスの Skype は、ビジネス 2019 フロント エンド サーバーの Skype が最初に起動したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="4fb14-110">The Skype for Business Server 2019 User Replicator service initial synchronization process occurs when the Skype for Business Server 2019 Front End Server is started for the first time.</span></span> <span data-ttu-id="4fb14-111">その後は、同期は、ユーザー レプリケーターの間隔に基づいています。</span><span class="sxs-lookup"><span data-stu-id="4fb14-111">After that, the synchronization is based on the User Replicator interval.</span></span> <span data-ttu-id="4fb14-112">**移動 CsUser**コマンドレットを実行する前に、ユーザー レプリケーションが完了することを確認するのには次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="4fb14-112">Complete the following steps to verify that user replication has completed before running the **Move-CsUser** cmdlet.</span></span> 
  
### <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="4fb14-113">そのユーザーの複製が完了したことを確認するのには</span><span class="sxs-lookup"><span data-stu-id="4fb14-113">To verify that user replication has completed</span></span>

1. <span data-ttu-id="4fb14-114">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="4fb14-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="4fb14-115">[**スタート**] メニューのをクリックし、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4fb14-115">Click the **Start** menu, and then click **Run**.</span></span> 
    
3. <span data-ttu-id="4fb14-116">**Eventvwr.exe**を入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4fb14-116">Enter **eventvwr.exe**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="4fb14-117">イベント ビューアーでは、展開する**アプリケーションとサービス ログ**] をクリックし、Skype をビジネス サーバーの選択。</span><span class="sxs-lookup"><span data-stu-id="4fb14-117">In Event Viewer, click **Applications and Services logs** to expand it, and then select Skype for Business Server.</span></span> 
    
5. <span data-ttu-id="4fb14-118">[**操作**] ウィンドウには、**現在のログをフィルター**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4fb14-118">In the **Actions** pane, click **Filter Current Log**.</span></span>
    
6. <span data-ttu-id="4fb14-119">**イベント ソース**の一覧から、**ユーザー レプリケーターの LS**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4fb14-119">From the **Event sources** list, click **LS User Replicator**.</span></span>
    
7. <span data-ttu-id="4fb14-120">**\<すべてのイベント Id\>**、 **30024**を入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4fb14-120">In **\<All Event IDs\>**, enter **30024**, and then click **OK**.</span></span> 
    
8. <span data-ttu-id="4fb14-121">[**全般**] タブで、フィルター処理されたイベントの一覧では、そのユーザーの複製が正常に完了したことを示すエントリを探します。</span><span class="sxs-lookup"><span data-stu-id="4fb14-121">In the filtered events list, on the **General** tab, look for an entry that states that user replication has completed successfully.</span></span> 
    


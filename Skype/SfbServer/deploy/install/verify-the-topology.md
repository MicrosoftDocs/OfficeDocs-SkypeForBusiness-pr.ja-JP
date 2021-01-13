---
title: Skype for Business Server でのトポロジの確認
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: '概要: Skype for Business Server トポロジと Active Directory サーバーが期待通り動作を確認する方法について学習します。 Microsoft Evaluation Center から Skype for Business Server の無料試用版を次の場所からダウンロードします https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。'
ms.openlocfilehash: 0c2307f3ad0416a7175d92a1440744dbda9b31d3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833837"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a><span data-ttu-id="14ba8-104">Skype for Business Server でのトポロジの確認</span><span class="sxs-lookup"><span data-stu-id="14ba8-104">Verify the topology in Skype for Business Server</span></span>
 
<span data-ttu-id="14ba8-105">**概要:** Skype for Business Server トポロジと Active Directory サーバーが期待通り動作しているのを確認する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="14ba8-105">**Summary:** Learn how to verify the Skype for Business Server topology and Active Directory servers are working as expected.</span></span> <span data-ttu-id="14ba8-106">Microsoft Evaluation Center から Skype for Business Server の無料試用版 [をダウンロードします](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="14ba8-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="14ba8-107">トポロジを公開し、トポロジ内の各サーバーに Skype for Business Server システム コンポーネントをインストールしたら、トポロジが期待通り動作している状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="14ba8-107">After you have the topology published and the Skype for Business Server system components installed on each of the servers in the topology, you are ready to verify that the topology is working as expected.</span></span> <span data-ttu-id="14ba8-108">これには、構成がすべての Active Directory サーバーに伝達され、ドメイン全体が Skype for Business がドメイン内で利用可能なことを知っていることを確認する機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="14ba8-108">This includes verifying that the configuration has propagated out to all of the Active Directory servers so that the entire domain knows Skype for Business is available in the domain.</span></span> <span data-ttu-id="14ba8-109">手順 1. ~ 5. は任意の順序で実行できます。</span><span class="sxs-lookup"><span data-stu-id="14ba8-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="14ba8-110">ただし、手順 6、7、および 8 を順番に実行し、図に示されている手順 1 ~ 5 の後に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14ba8-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="14ba8-111">トポロジの確認は手順 8/8 です。</span><span class="sxs-lookup"><span data-stu-id="14ba8-111">Verifying the topology is step 8 of 8.</span></span>
  
![概要図](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a><span data-ttu-id="14ba8-113">フロントエンド プールの展開をテストする</span><span class="sxs-lookup"><span data-stu-id="14ba8-113">Test the Front End pool deployment</span></span>

<span data-ttu-id="14ba8-114">最後の手順では、フロントエンド プールをテストし、Skype for Business クライアントが相互に通信可能な環境を確認します。</span><span class="sxs-lookup"><span data-stu-id="14ba8-114">The final step is to test the Front End pool and confirm that Skype for Business clients can communicate with each other.</span></span> 
  
### <a name="add-users-and-verify-client-connectivity"></a><span data-ttu-id="14ba8-115">ユーザーの追加とクライアント接続の確認</span><span class="sxs-lookup"><span data-stu-id="14ba8-115">Add users and verify client connectivity</span></span>

1. <span data-ttu-id="14ba8-116">Active Directory コンピューターとユーザーを使用して、(Skype for Business Server コントロール パネルがインストールされている) Skype for Business Server 展開の管理者の役割の Active Directory ユーザー オブジェクトを **CSAdministrator** グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="14ba8-116">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Skype for Business Server deployment (on which Skype for Business Server Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="14ba8-117">CsAdministors グループに適切なユーザーとグループを追加しない場合、Skype for Business Server コントロール パネルを開く際に、「Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.」というエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="14ba8-117">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when you open Skype for Business Server Control Panel which reads, "Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure."</span></span> 
  
2. <span data-ttu-id="14ba8-118">ユーザー オブジェクトが現在ログオンしている場合は、ログオフしてから再度ログオンし、新しいグループ割り当てを登録します。</span><span class="sxs-lookup"><span data-stu-id="14ba8-118">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="14ba8-119">ユーザー アカウントは、Skype for Business Server を実行しているサーバーのローカル管理者にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="14ba8-119">The user account cannot be the local administrator of any server running Skype for Business Server.</span></span> 
  
3. <span data-ttu-id="14ba8-120">管理アカウントを使用して、Skype for Business Server コントロール パネルがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="14ba8-120">Use the administrative account to log on to the computer where Skype for Business Server Control Panel is installed.</span></span>
    
4. <span data-ttu-id="14ba8-121">Skype for Business Server コントロール パネルを起動し、メッセージが表示されたら資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="14ba8-121">Start Skype for Business Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="14ba8-122">Skype for Business Server コントロール パネルには展開情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="14ba8-122">Skype for Business Server Control Panel displays deployment information.</span></span>
    
5. <span data-ttu-id="14ba8-123">左側のナビゲーション バーで[トポロジ] をクリックし、サービスの状態に緑色の矢印が表示されたコンピューターと、展開されオンラインにされた各 Skype for Business Server の役割の横に、レプリケーション状態の緑色のチェック マークが表示されます。</span><span class="sxs-lookup"><span data-stu-id="14ba8-123">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Skype for Business Server role that has been deployed and brought online.</span></span> 
    
6. <span data-ttu-id="14ba8-124">左側のナビゲーション バーで、[**ユーザー**] をクリックし、[**ユーザーを有効にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14ba8-124">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span> 
    
7. <span data-ttu-id="14ba8-125">[新しい **Skype for Business Server ユーザー] ページで、[** 追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="14ba8-125">On the **New Skype for Business Server User** page, click **Add**.</span></span>
    
8. <span data-ttu-id="14ba8-126">検索するオブジェクトの検索パラメーターを定義するには、[**Active Directory から選択**] ページで [**検索**] を選択し、オプションで [**フィルターの追加**] をクリックできます。</span><span class="sxs-lookup"><span data-stu-id="14ba8-126">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**.</span></span> <span data-ttu-id="14ba8-127">また [**LDAP 検索**] を選択し、LDAP 表現を入力して、戻されるオブジェクトをフィルター処理または制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="14ba8-127">You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned.</span></span> <span data-ttu-id="14ba8-128">検索オプションを決定した後、[検索] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="14ba8-128">After you have decided on your Search options, click **Find**.</span></span>
    
9. <span data-ttu-id="14ba8-129">[検索結果] ウィンドウで、追加するユーザーを選択し **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14ba8-129">In the Search results pane, select the users you want to add, and then click **OK**.</span></span>
    
10. <span data-ttu-id="14ba8-130">[ **新しい Skype for Business Server ユーザー] ページ** で、選択したユーザーが [ユーザー] 表示 **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="14ba8-130">On the **New Skype for Business Server User** page, the users you selected are in the **Users** display.</span></span> <span data-ttu-id="14ba8-131">[ユーザー **をプールに割り当てる** ] ボックスの一覧で、ユーザーが存在するサーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="14ba8-131">In the **Assign users to a pool** list, select the server where the users should reside.</span></span>
    
    <span data-ttu-id="14ba8-132">オブジェクトの構成に使用できるオプションの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="14ba8-132">The following is a list of options you can use to configure the objects.</span></span>
    
    - <span data-ttu-id="14ba8-133">**ユーザーの SIP URI を生成する**</span><span class="sxs-lookup"><span data-stu-id="14ba8-133">**Generate user's SIP URI**</span></span>
    
    - <span data-ttu-id="14ba8-134">**テレフォニー**</span><span class="sxs-lookup"><span data-stu-id="14ba8-134">**Telephony**</span></span>
    
    - <span data-ttu-id="14ba8-135">[**回線 URI**]</span><span class="sxs-lookup"><span data-stu-id="14ba8-135">**Line URI**</span></span>
    
    - <span data-ttu-id="14ba8-136">**会議ポリシー**</span><span class="sxs-lookup"><span data-stu-id="14ba8-136">**Conferencing policy**</span></span>
    
    - <span data-ttu-id="14ba8-137">**クライアント バージョン ポリシー**</span><span class="sxs-lookup"><span data-stu-id="14ba8-137">**Client version policy**</span></span>
    
    - <span data-ttu-id="14ba8-138">**PIN ポリシー**</span><span class="sxs-lookup"><span data-stu-id="14ba8-138">**PIN policy**</span></span>
    
    - <span data-ttu-id="14ba8-139">**外部アクセス ポリシー**</span><span class="sxs-lookup"><span data-stu-id="14ba8-139">**External access policy**</span></span>
    
    - <span data-ttu-id="14ba8-140">**アーカイブ ポリシー**</span><span class="sxs-lookup"><span data-stu-id="14ba8-140">**Archiving policy**</span></span>
    
    - <span data-ttu-id="14ba8-141">**場所のポリシー**</span><span class="sxs-lookup"><span data-stu-id="14ba8-141">**Location policy**</span></span>
    
    - <span data-ttu-id="14ba8-142">**クライアント ポリシー**</span><span class="sxs-lookup"><span data-stu-id="14ba8-142">**Client policy**</span></span>
    
    <span data-ttu-id="14ba8-143">基本的な機能をテストするには、[ユーザー **の SIP URI** を生成する] 設定に使用するオプションを選択し (構成内の他のオプションでは既定の設定を使用)、[有効] をクリックします (図を参照)。</span><span class="sxs-lookup"><span data-stu-id="14ba8-143">To test the basic functionality, select the option you prefer for the **Generate user's SIP URI** setting (the other options in the configuration use default settings), and then click **Enable**, as shown in the figure.</span></span>
    
     ![コントロール パネルでユーザーを有効にします。](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. <span data-ttu-id="14ba8-145">ユーザーがセットアップ中かどうかを示すチェック マークが **[有効** ] 列に表示される概要ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="14ba8-145">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the users are setup.</span></span> <span data-ttu-id="14ba8-146">**SIP アドレス列には**、ユーザーサインイン構成に必要なアドレスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="14ba8-146">The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>
    
     ![Skype for Business Server コントロール パネルに追加されたユーザー。](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. <span data-ttu-id="14ba8-148">ドメインに参加しているコンピューターに 1 人のユーザーをログオンし、別のユーザーをドメイン内の別のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="14ba8-148">Log one user on to a computer that is joined to the domain and another user on to another computer in the domain.</span></span>
    
13. <span data-ttu-id="14ba8-149">2 台のクライアント コンピューターのそれぞれに Skype for Business クライアントをインストールし、両方のユーザーが Skype for Business Server にサインインして、インスタント メッセージを互いに送信できる点を確認します。</span><span class="sxs-lookup"><span data-stu-id="14ba8-149">Install Skype for Business client on each of the two client computers, and then verify that both users can sign in to Skype for Business Server and can send instant messages to each other.</span></span>
    


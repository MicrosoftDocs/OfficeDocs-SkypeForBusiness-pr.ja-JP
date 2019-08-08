---
title: Skype for Business Server でトポロジを確認する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: '概要: Skype for Business Server トポロジと Active Directory サーバーが予期したとおりに動作していることを確認する方法について説明します。 Skype for Business Server の無料トライアルは、次https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverの Microsoft 評価センターからダウンロードしてください。'
ms.openlocfilehash: 6c7d7a67cab2cbd383ee26eb64f478985bcc4b27
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245237"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a><span data-ttu-id="8eb38-104">Skype for Business Server でトポロジを確認する</span><span class="sxs-lookup"><span data-stu-id="8eb38-104">Verify the topology in Skype for Business Server</span></span>
 
<span data-ttu-id="8eb38-105">**概要:** Skype for Business Server トポロジと Active Directory サーバーが予期したとおりに動作していることを確認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8eb38-105">**Summary:** Learn how to verify the Skype for Business Server topology and Active Directory servers are working as expected.</span></span> <span data-ttu-id="8eb38-106">[Microsoft の評価センター](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)から Skype For business Server の無料トライアルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="8eb38-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="8eb38-107">トポロジを公開し、各サーバーに Skype for Business Server システムコンポーネントをインストールしたら、トポロジが予期したとおりに機能しているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="8eb38-107">After you have the topology published and the Skype for Business Server system components installed on each of the servers in the topology, you are ready to verify that the topology is working as expected.</span></span> <span data-ttu-id="8eb38-108">これには、構成がすべての Active Directory サーバーに伝達されていることを確認することによって、ドメイン全体で Skype for Business がドメインで利用可能であることがわかっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8eb38-108">This includes verifying that the configuration has propagated out to all of the Active Directory servers so that the entire domain knows Skype for Business is available in the domain.</span></span> <span data-ttu-id="8eb38-109">手順 1 ～ 5 は任意の順序で実行できます。</span><span class="sxs-lookup"><span data-stu-id="8eb38-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="8eb38-110">ただし、手順 6、7、および 8 は、手順 1 ～ 5 の後に、図の順序で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8eb38-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="8eb38-111">トポロジの確認は、手順 8/8 です。</span><span class="sxs-lookup"><span data-stu-id="8eb38-111">Verifying the topology is step 8 of 8.</span></span>
  
![概要図](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a><span data-ttu-id="8eb38-113">フロントエンドプールの展開をテストする</span><span class="sxs-lookup"><span data-stu-id="8eb38-113">Test the Front End pool deployment</span></span>

<span data-ttu-id="8eb38-114">最後の手順では、フロントエンドプールをテストし、Skype for Business クライアントが相互に通信できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8eb38-114">The final step is to test the Front End pool and confirm that Skype for Business clients can communicate with each other.</span></span> 
  
### <a name="add-users-and-verify-client-connectivity"></a><span data-ttu-id="8eb38-115">ユーザーを追加してクライアント接続を確認する</span><span class="sxs-lookup"><span data-stu-id="8eb38-115">Add users and verify client connectivity</span></span>

1. <span data-ttu-id="8eb38-116">Active Directory コンピューターとユーザーを使って、Skype for Business Server の展開 (Skype for Business Server コントロールパネルがインストールされている) の管理者ロールの Active Directory ユーザーオブジェクトを**csadministrator**グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="8eb38-116">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Skype for Business Server deployment (on which Skype for Business Server Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8eb38-117">適切なユーザーとグループを CsAdministors グループに追加していない場合、Skype for Business Server コントロールパネルを開くとエラーが表示されます。 "権限がありません。役割ベースのアクセス制御 (RBAC) 認証エラーによりアクセスが拒否されました。"."</span><span class="sxs-lookup"><span data-stu-id="8eb38-117">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when you open Skype for Business Server Control Panel which reads, "Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure."</span></span> 
  
2. <span data-ttu-id="8eb38-118">ユーザーオブジェクトが現在ログオンしている場合は、ログオフしてから再びログオンして、新しいグループの割り当てを登録します。</span><span class="sxs-lookup"><span data-stu-id="8eb38-118">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8eb38-119">ユーザーアカウントは、Skype for Business Server を実行しているサーバーのローカル管理者になることはできません。</span><span class="sxs-lookup"><span data-stu-id="8eb38-119">The user account cannot be the local administrator of any server running Skype for Business Server.</span></span> 
  
3. <span data-ttu-id="8eb38-120">管理者アカウントを使用して、Skype for Business Server コントロールパネルがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8eb38-120">Use the administrative account to log on to the computer where Skype for Business Server Control Panel is installed.</span></span>
    
4. <span data-ttu-id="8eb38-121">Skype for Business Server コントロールパネルを起動し、メッセージが表示されたら、資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="8eb38-121">Start Skype for Business Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="8eb38-122">Skype for Business Server コントロールパネルに展開情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8eb38-122">Skype for Business Server Control Panel displays deployment information.</span></span>
    
5. <span data-ttu-id="8eb38-123">左側のナビゲーションバーで、[**トポロジ**] をクリックし、[サービスの状態] に緑色の矢印が表示されていることを確認し、[レプリケーションの状態] に緑色のチェックマークが表示されることを確認します。これは、展開されてオンラインになっている各 Skype For business Server の役割の隣にあります。</span><span class="sxs-lookup"><span data-stu-id="8eb38-123">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Skype for Business Server role that has been deployed and brought online.</span></span> 
    
6. <span data-ttu-id="8eb38-124">左側のナビゲーションバーで [**ユーザー**] をクリックし、[**ユーザーの有効化**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8eb38-124">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span> 
    
7. <span data-ttu-id="8eb38-125">[**新しい Skype For Business Server ユーザー** ] ページで、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8eb38-125">On the **New Skype for Business Server User** page, click **Add**.</span></span>
    
8. <span data-ttu-id="8eb38-126">検索するオブジェクトの検索パラメーターを定義するには、[ **Active Directory から選択**] ページで [**検索**] を選択し、必要に応じて [**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8eb38-126">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**.</span></span> <span data-ttu-id="8eb38-127">**Ldap 検索**を選択し、返されるオブジェクトをフィルター処理または制限するための ldap 式を入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="8eb38-127">You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned.</span></span> <span data-ttu-id="8eb38-128">検索オプションを決定したら、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8eb38-128">After you have decided on your Search options, click **Find**.</span></span>
    
9. <span data-ttu-id="8eb38-129">[検索結果] ウィンドウで、追加するユーザーを選び、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8eb38-129">In the Search results pane, select the users you want to add, and then click **OK**.</span></span>
    
10. <span data-ttu-id="8eb38-130">**新しい Skype For Business Server**の [ユーザー] ページで、選択したユーザーが [**ユーザー** ] 画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8eb38-130">On the **New Skype for Business Server User** page, the users you selected are in the **Users** display.</span></span> <span data-ttu-id="8eb38-131">[**プールへのユーザーの割り当て**] ボックスの一覧で、ユーザーが存在する必要があるサーバーを選びます。</span><span class="sxs-lookup"><span data-stu-id="8eb38-131">In the **Assign users to a pool** list, select the server where the users should reside.</span></span>
    
    <span data-ttu-id="8eb38-132">次に、オブジェクトを構成するために使用できるオプションの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="8eb38-132">The following is a list of options you can use to configure the objects.</span></span>
    
    - <span data-ttu-id="8eb38-133">**ユーザーの SIP URI を生成する**</span><span class="sxs-lookup"><span data-stu-id="8eb38-133">**Generate user's SIP URI**</span></span>
    
    - <span data-ttu-id="8eb38-134">**テレフォニー**</span><span class="sxs-lookup"><span data-stu-id="8eb38-134">**Telephony**</span></span>
    
    - <span data-ttu-id="8eb38-135">**行の URI**</span><span class="sxs-lookup"><span data-stu-id="8eb38-135">**Line URI**</span></span>
    
    - <span data-ttu-id="8eb38-136">**会議ポリシー**</span><span class="sxs-lookup"><span data-stu-id="8eb38-136">**Conferencing policy**</span></span>
    
    - <span data-ttu-id="8eb38-137">**クライアントのバージョンポリシー**</span><span class="sxs-lookup"><span data-stu-id="8eb38-137">**Client version policy**</span></span>
    
    - <span data-ttu-id="8eb38-138">**PIN ポリシー**</span><span class="sxs-lookup"><span data-stu-id="8eb38-138">**PIN policy**</span></span>
    
    - <span data-ttu-id="8eb38-139">**外部アクセスポリシー**</span><span class="sxs-lookup"><span data-stu-id="8eb38-139">**External access policy**</span></span>
    
    - <span data-ttu-id="8eb38-140">**アーカイブポリシー**</span><span class="sxs-lookup"><span data-stu-id="8eb38-140">**Archiving policy**</span></span>
    
    - <span data-ttu-id="8eb38-141">**場所のポリシー**</span><span class="sxs-lookup"><span data-stu-id="8eb38-141">**Location policy**</span></span>
    
    - <span data-ttu-id="8eb38-142">**クライアントポリシー**</span><span class="sxs-lookup"><span data-stu-id="8eb38-142">**Client policy**</span></span>
    
    <span data-ttu-id="8eb38-143">基本機能をテストするには、[**ユーザーの SIP URI の生成**] 設定で希望のオプションを選択し ([構成] のその他のオプションで既定の設定を使用します)、[**有効**にする] をクリックします (図を参照)。</span><span class="sxs-lookup"><span data-stu-id="8eb38-143">To test the basic functionality, select the option you prefer for the **Generate user's SIP URI** setting (the other options in the configuration use default settings), and then click **Enable**, as shown in the figure.</span></span>
    
     ![コントロール パネルでユーザーを有効にします。](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. <span data-ttu-id="8eb38-145">概要ページが表示され、[**有効**] 列にチェックマークが表示され、ユーザーが設定されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="8eb38-145">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the users are setup.</span></span> <span data-ttu-id="8eb38-146">**SIP アドレス**列には、ユーザーのサインイン構成に必要なアドレスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8eb38-146">The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>
    
     ![Skype for Business Server コントロール パネルにユーザーが追加されました。](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. <span data-ttu-id="8eb38-148">1人のユーザーを、ドメインに参加しているコンピューターまたは別のユーザーのドメイン内の別のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8eb38-148">Log one user on to a computer that is joined to the domain and another user on to another computer in the domain.</span></span>
    
13. <span data-ttu-id="8eb38-149">2台の各クライアントコンピューターに Skype for Business クライアントをインストールし、両方のユーザーが Skype for Business Server にサインインして、互いにインスタントメッセージを送信できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8eb38-149">Install Skype for Business client on each of the two client computers, and then verify that both users can sign in to Skype for Business Server and can send instant messages to each other.</span></span>
    


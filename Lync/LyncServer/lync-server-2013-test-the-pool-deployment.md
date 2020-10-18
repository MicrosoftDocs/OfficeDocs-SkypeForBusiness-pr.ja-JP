---
title: 'Lync Server 2013: プール展開のテスト'
description: 'Lync Server 2013: プール展開をテストします。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the pool deployment
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413092(v=OCS.15)
ms:contentKeyID: 48185976
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28101a252eda5048ded9f1eaf76c092c5cb7f986
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576043"
---
# <a name="test-the-pool-deployment-in-lync-server-2013"></a><span data-ttu-id="f9471-103">Lync Server 2013 でプール展開をテストする</span><span class="sxs-lookup"><span data-stu-id="f9471-103">Test the pool deployment in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9471-104">_**トピックの最終更新日:** 2013-09-25_</span><span class="sxs-lookup"><span data-stu-id="f9471-104">_**Topic Last Modified:** 2013-09-25_</span></span>

<span data-ttu-id="f9471-105">次の手順では、フロントエンドプールの展開をテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f9471-105">The following procedure describes how to test the deployment of the Front End pool.</span></span>

<div>

## <a name="to-test-the-pool-deployment"></a><span data-ttu-id="f9471-106">プール展開をテストするには</span><span class="sxs-lookup"><span data-stu-id="f9471-106">To test the pool deployment</span></span>

1.  <span data-ttu-id="f9471-107">Active Directory のコンピューターとユーザーを使用して、Lync Server 2013 の展開 (Lync Server 2013 コントロールパネルがインストールされている) の管理者ロールの Active Directory ユーザーオブジェクトを **Csadministrator** グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="f9471-107">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Lync Server 2013 deployment (on which Lync Server 2013 Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f9471-108">CsAdministors グループに適切なユーザーとグループを追加しないと、Lync Server コントロールパネルを開くときにエラーが表示されます。これは、"権限のない: 役割ベースのアクセス制御 (RBAC) の承認エラーによってアクセスが拒否されました" というメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="f9471-108">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when opening Lync Server Control Panel, which states that “Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.”</span></span>

    
    </div>

2.  <span data-ttu-id="f9471-109">ユーザー オブジェクトが現在ログオンしている場合は、ログオフしてから再度ログオンし、新しいグループ割り当てを登録します。</span><span class="sxs-lookup"><span data-stu-id="f9471-109">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f9471-110">ユーザーアカウントは、Lync Server 2013 を実行しているサーバーのローカル管理者になることはできません。</span><span class="sxs-lookup"><span data-stu-id="f9471-110">The user account cannot be the local administrator of any server running Lync Server 2013.</span></span>

    
    </div>

3.  <span data-ttu-id="f9471-111">管理者アカウントを使用して、Lync Server コントロールパネルがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f9471-111">Use the administrative account to log on to the computer where Lync Server Control Panel is installed.</span></span>

4.  <span data-ttu-id="f9471-112">[Lync Server コントロールパネル] を起動し、メッセージが表示された場合は、資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="f9471-112">Start Lync Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="f9471-113">Lync Server コントロールパネルに展開情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9471-113">Lync Server Control Panel displays deployment information.</span></span>

5.  <span data-ttu-id="f9471-114">左側のナビゲーションバーで [ **トポロジ**] をクリックし、サービスの状態に緑色の矢印が表示されていること、および展開されてオンラインになっている各 Lync server のサーバーの役割の横に、レプリケーションの状態を示す緑のチェックマークが付いていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f9471-114">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Lync Server server role that has been deployed and brought online.</span></span>

6.  <span data-ttu-id="f9471-115">左側のナビゲーション バーで、[**ユーザー**] をクリックし、[**ユーザーを有効にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9471-115">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span>

7.  <span data-ttu-id="f9471-116">[**新規 Lync Server ユーザー**] ページで [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9471-116">On the **New Lync Server User** page, click **Add**.</span></span>

8.  <span data-ttu-id="f9471-p102">検索するオブジェクトの検索パラメーターを定義するには、[**Active Directory から選択**] ページで [**検索**] を選択し、オプションで [**フィルターの追加**] をクリックできます。 また [**LDAP 検索**] を選択し、LDAP 表現を入力して、戻されるオブジェクトをフィルター処理または制限することもできます。 [検索] オプションの内容を決定した後、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9471-p102">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**. You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned. After you have decided on your Search options, clink **Find**.</span></span>

9.  <span data-ttu-id="f9471-120">[検索結果] ウィンドウでこの検索セッションのオブジェクトをすべて選択し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9471-120">In the Search results pane, select all the objects for this search session, and then click **OK**.</span></span>

10. <span data-ttu-id="f9471-p103">[**新しい Lync Server ユーザー**] ページで、選択した 1 つまたは複数のオブジェクトが [**ユーザー**] に表示されます。 [**ユーザーのプールへの割り当て**] リストで、オブジェクトの所属先となるサーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="f9471-p103">On the **New Lync Server User** page, the object or objects you selected are in the **Users** display. In the **Assign users to a pool** list, select the server where the objects should be homed.</span></span>
    
    <span data-ttu-id="f9471-123">オブジェクトを構成するためのいくつかのオプションを次に示します。</span><span class="sxs-lookup"><span data-stu-id="f9471-123">Following are a number of options for configuring the objects.</span></span>
    
      - <span data-ttu-id="f9471-124">**ユーザーの SIP URI の生成**</span><span class="sxs-lookup"><span data-stu-id="f9471-124">**Generate user’s SIP URI**</span></span>
    
      - <span data-ttu-id="f9471-125">**網**</span><span class="sxs-lookup"><span data-stu-id="f9471-125">**Telephony**</span></span>
    
      - <span data-ttu-id="f9471-126">[**回線 URI**]</span><span class="sxs-lookup"><span data-stu-id="f9471-126">**Line URI**</span></span>
    
      - <span data-ttu-id="f9471-127">**会議ポリシー**</span><span class="sxs-lookup"><span data-stu-id="f9471-127">**Conferencing policy**</span></span>
    
      - <span data-ttu-id="f9471-128">**クライアント バージョン ポリシー**</span><span class="sxs-lookup"><span data-stu-id="f9471-128">**Client version policy**</span></span>
    
      - <span data-ttu-id="f9471-129">**PIN ポリシー**</span><span class="sxs-lookup"><span data-stu-id="f9471-129">**PIN policy**</span></span>
    
      - <span data-ttu-id="f9471-130">**外部アクセス ポリシー**</span><span class="sxs-lookup"><span data-stu-id="f9471-130">**External access policy**</span></span>
    
      - <span data-ttu-id="f9471-131">**アーカイブ ポリシー**</span><span class="sxs-lookup"><span data-stu-id="f9471-131">**Archiving policy**</span></span>
    
      - <span data-ttu-id="f9471-132">**場所のポリシー**</span><span class="sxs-lookup"><span data-stu-id="f9471-132">**Location policy**</span></span>
    
      - <span data-ttu-id="f9471-133">**クライアント ポリシー**</span><span class="sxs-lookup"><span data-stu-id="f9471-133">**Client policy**</span></span>
    
    <span data-ttu-id="f9471-134">基本機能をテストするには、[**ユーザーの SIP URI の生成**] 設定の任意のオプションを選択し (構成内のその他のオプションでは既定の設定を使用)、[**有効にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9471-134">For the purposes of testing the basic functionality, select the option you prefer for the **Generate user’s SIP URI** setting (the other options in the configuration will use default settings), and then click **Enable**.</span></span>

11. <span data-ttu-id="f9471-p104">概要ページが表示されます。このページの [**有効にする**] の列に、オブジェクトが使用できることを示すチェック マークが表示されます。 [**SIP アドレス**] の列に、ユーザーのサインインの構成に必要なアドレスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9471-p104">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the objects are now ready for use. The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>

12. <span data-ttu-id="f9471-137">あるユーザーはドメインに参加しているコンピューターにログオンし、他のユーザーはドメイン内の他のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f9471-137">Log one user on to a computer that is joined to the domain, and another user on to another computer in the domain.</span></span>

13. <span data-ttu-id="f9471-138">2台の各クライアントコンピューターに Lync 2013 をインストールしてから、両方のユーザーが Lync Server 2013 にサインインして、互いにインスタントメッセージを送信できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f9471-138">Install Lync 2013 on each of the two client computers, and then verify that both users can sign in to Lync Server 2013 and can send instant messages to each other.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f9471-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9471-139">See Also</span></span>


[<span data-ttu-id="f9471-140">Lync Server 2013 でのクライアントとデバイスの展開</span><span class="sxs-lookup"><span data-stu-id="f9471-140">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


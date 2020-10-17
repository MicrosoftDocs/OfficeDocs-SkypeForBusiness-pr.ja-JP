---
title: 'Lync Server 2013: 常設チャットのグローバルポリシーの構成'
description: 'Lync Server 2013: 常設チャットのグローバルポリシーを構成します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the global policy for Persistent Chat
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204951(v=OCS.15)
ms:contentKeyID: 48184323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 830074c31791ee8ff489d9a67af189be609c7f4c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544943"
---
# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="7aa30-103">Lync Server 2013 で常設チャットのグローバルポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="7aa30-103">Configure the global policy for Persistent Chat in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7aa30-104">_**トピックの最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="7aa30-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="7aa30-105">既定のグローバルポリシーを単独で使用して、展開内のすべてのユーザーの常設チャット設定を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7aa30-105">You can use the default global policy by itself to enable Persistent Chat settings for all users in your deployment.</span></span> <span data-ttu-id="7aa30-106">また、特定のユーザーやサイトに対して常設チャットを有効または無効にするかどうかを制御するために、サイトおよびユーザーの追加のポリシーを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="7aa30-106">You can also specify additional policies for sites and users to control whether Persistent Chat is enabled or disabled for specific users and sites.</span></span>

<span data-ttu-id="7aa30-107">グローバル ポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="7aa30-107">You cannot delete the global policy.</span></span> <span data-ttu-id="7aa30-108">削除しようとすると、構成が既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="7aa30-108">If you attempt to delete it, the configuration resets to the default values.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7aa30-109">常設チャットサーバーを構成して使用するには、まず、トポロジビルダーを使用して、常設チャットサーバーのサポートをトポロジに追加してから、トポロジを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7aa30-109">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="7aa30-110">詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 での展開への常設チャットサーバーの追加</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7aa30-110">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="7aa30-111">常設チャットサーバーの構成設定を構成するには、「展開」のドキュメントの「 <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure 常設 Chat server options For Lync server 2013</A> の常設チャットサーバーのオプション」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7aa30-111">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="7aa30-112">常設チャットのグローバルポリシーを構成するには</span><span class="sxs-lookup"><span data-stu-id="7aa30-112">To configure the Global Policy for Persistent Chat</span></span>

1.  <span data-ttu-id="7aa30-113">CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="7aa30-113">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7aa30-114">[ **スタート** ] メニューから [Lync Server コントロールパネル] を選択するか、ブラウザーウィンドウを開いて管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="7aa30-114">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="7aa30-115">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「操作」のドキュメントの「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7aa30-115">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md) in the Operations documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7aa30-116">Windows PowerShell コマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="7aa30-116">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="7aa30-117">詳細については、「展開」のドキュメントの「 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell コマンドレットを使用して常設チャットサーバーを構成する</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7aa30-117">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="7aa30-118">Lync Server コントロールパネルで、[ **常設チャット**] をクリックし、[ **常設チャットのポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7aa30-118">In Lync Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>

4.  <span data-ttu-id="7aa30-119">ポリシーの一覧の [**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7aa30-119">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="7aa30-120">[**編集 常設チャットのポリシー - Global**] で、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7aa30-120">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
      - <span data-ttu-id="7aa30-121">グローバルという既定の名前を使用しない場合は、[**名前**] でグローバル ポリシーの新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="7aa30-121">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
      - <span data-ttu-id="7aa30-122">[ **説明**] に、ユーザーポリシーの内容に関する詳細を入力します (たとえば、CentralSiteName のグローバルポリシー)。</span><span class="sxs-lookup"><span data-stu-id="7aa30-122">In **Description**, provide details about what the user policy is (for example, Global policy for centralSiteName).</span></span>
    
      - <span data-ttu-id="7aa30-123">サイトポリシーまたはユーザーポリシーによって特に制御されていないすべてのサイトとユーザーの常設チャットを制御するには、[ **常設チャットを有効に** する] チェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="7aa30-123">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>

6.  <span data-ttu-id="7aa30-124">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7aa30-124">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


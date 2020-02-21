---
title: 'Lync Server 2013: 常設チャットのグローバルポリシーの構成'
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
ms.openlocfilehash: b9c4596749e1c4bf4c9f4002b33234c83afa1fd5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="92d96-102">Lync Server 2013 で常設チャットのグローバルポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="92d96-102">Configure the global policy for Persistent Chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92d96-103">_**トピックの最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="92d96-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="92d96-104">既定のグローバルポリシーを単独で使用して、展開内のすべてのユーザーの常設チャット設定を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="92d96-104">You can use the default global policy by itself to enable Persistent Chat settings for all users in your deployment.</span></span> <span data-ttu-id="92d96-105">また、特定のユーザーやサイトに対して常設チャットを有効または無効にするかどうかを制御するために、サイトおよびユーザーの追加のポリシーを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="92d96-105">You can also specify additional policies for sites and users to control whether Persistent Chat is enabled or disabled for specific users and sites.</span></span>

<span data-ttu-id="92d96-106">グローバル ポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="92d96-106">You cannot delete the global policy.</span></span> <span data-ttu-id="92d96-107">削除しようとすると、構成が既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="92d96-107">If you attempt to delete it, the configuration resets to the default values.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="92d96-108">常設チャットサーバーを構成して使用するには、まず、トポロジビルダーを使用して、常設チャットサーバーのサポートをトポロジに追加してから、トポロジを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92d96-108">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="92d96-109">詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 での展開への常設チャットサーバーの追加</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92d96-109">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="92d96-110">常設チャットサーバーの構成設定を構成するには、「展開」のドキュメントの「 <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure 常設 Chat server options For Lync server 2013</A>の常設チャットサーバーのオプション」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92d96-110">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="92d96-111">常設チャットのグローバルポリシーを構成するには</span><span class="sxs-lookup"><span data-stu-id="92d96-111">To configure the Global Policy for Persistent Chat</span></span>

1.  <span data-ttu-id="92d96-112">CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="92d96-112">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="92d96-113">[**スタート**] メニューから [Lync Server コントロールパネル] を選択するか、ブラウザーウィンドウを開いて管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="92d96-113">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="92d96-114">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「操作」のドキュメントの「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92d96-114">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md) in the Operations documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="92d96-115">Windows PowerShell コマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="92d96-115">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="92d96-116">詳細については、「展開」のドキュメントの「 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell コマンドレットを使用して常設チャットサーバーを構成する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92d96-116">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="92d96-117">Lync Server コントロールパネルで、[**常設チャット**] をクリックし、[**常設チャットのポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92d96-117">In Lync Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>

4.  <span data-ttu-id="92d96-118">ポリシーの一覧の [**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92d96-118">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="92d96-119">[**編集 常設チャットのポリシー - Global**] で、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="92d96-119">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
      - <span data-ttu-id="92d96-120">グローバルという既定の名前を使用しない場合は、[**名前**] でグローバル ポリシーの新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="92d96-120">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
      - <span data-ttu-id="92d96-121">[**説明**] に、ユーザーポリシーの内容に関する詳細を入力します (たとえば、CentralSiteName のグローバルポリシー)。</span><span class="sxs-lookup"><span data-stu-id="92d96-121">In **Description**, provide details about what the user policy is (for example, Global policy for centralSiteName).</span></span>
    
      - <span data-ttu-id="92d96-122">サイトポリシーまたはユーザーポリシーによって特に制御されていないすべてのサイトとユーザーの常設チャットを制御するには、[**常設チャットを有効に**する] チェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="92d96-122">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>

6.  <span data-ttu-id="92d96-123">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92d96-123">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


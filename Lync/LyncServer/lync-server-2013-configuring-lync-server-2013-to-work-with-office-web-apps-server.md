---
title: Office Web Apps サーバーで動作するように Lync Server 2013 を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to work with Office Web Apps Server
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204944(v=OCS.15)
ms:contentKeyID: 48184288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92409327c28716f804ecc915e0ff4e298e1e42b4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134213"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-office-web-apps-server"></a><span data-ttu-id="5b1c1-102">Office Web Apps サーバーで動作するように Lync Server 2013 を構成する</span><span class="sxs-lookup"><span data-stu-id="5b1c1-102">Configuring Lync Server 2013 to work with Office Web Apps Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b1c1-103">_**トピックの最終更新日:** 2013-04-22_</span><span class="sxs-lookup"><span data-stu-id="5b1c1-103">_**Topic Last Modified:** 2013-04-22_</span></span>

<span data-ttu-id="5b1c1-104">Office Web Apps サーバーを使用するように Lync Server 2013 を構成する前に、Office Web Apps サーバーを展開して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b1c1-104">Before you can configure Lync Server 2013 to use Office Web Apps Server, Office Web Apps Server must be deployed and configured.</span></span> <span data-ttu-id="5b1c1-105">単一の Office Web Apps サーバーのインストールおよび構成方法、または高可用性を得るための Office Web Apps サーバー ファームのインストールおよび構成方法の詳細については、「**Office Web Apps サーバーおよび Office Web アプリを展開するためのガイド**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b1c1-105">See the document **Guide to Deploying Office Web Apps Server and Office Web Apps** for detail information on how to install and configure a single Office Web Apps Server, or for information on how to install and configure an Office Web Apps Server Farm for high availability.</span></span>

<span data-ttu-id="5b1c1-106">Office Web Apps サーバーが正常にインストールされ、Web ファームが正しく構成された後、新しいサーバーと通信するように Lync Server を構成する必要があります。これを行うには、Office Web Apps サーバーの検出 URL を Lync Server トポロジに追加します。</span><span class="sxs-lookup"><span data-stu-id="5b1c1-106">After Office Web Apps Server has been successfully installed and your Web farm correctly configured, you must then configure Lync Server to communicate with the new server; this is done by adding the Office Web Apps Server discovery URL to your Lync Server topology.</span></span> <span data-ttu-id="5b1c1-107">Office Web Apps サーバーをトポロジに追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5b1c1-107">To add Office Web Apps Server to your topology, complete the following steps:</span></span>

1.  <span data-ttu-id="5b1c1-108">[**スタート**]、[**すべてのプログラム**]、[ **Microsoft lync Server 2013**]、[ **lync server トポロジビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="5b1c1-108">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="5b1c1-109">[**トポロジ ビルダー**] ダイアログ ボックスで、[**既存の展開環境からトポロジをダウンロードする**] をクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5b1c1-109">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>

3.  <span data-ttu-id="5b1c1-p103">[**トポロジに名前を付けて保存**] ダイアログ ボックスで、トポロジ ドキュメントの名前 (例: **PreWebAppsServerTopology**) を [**ファイル名**] ボックスに入力し、[**保存**] をクリックします。新しいトポロジで問題が発生した場合、後でこのトポロジを取得して再発行できます。</span><span class="sxs-lookup"><span data-stu-id="5b1c1-p103">In the **Save Topology As** dialog box, type a name for your topology document (for example, **PreWebAppsServerTopology**) in the **File name** box and then click **Save**. This topology can later be retrieved and republished if you encounter problems with your new topology.</span></span>

4.  <span data-ttu-id="5b1c1-112">トポロジビルダーで、[ **Lync Server 2013**] を展開し、サイトの名前を展開します。次に、[ **Enterprise Edition フロントエンドプール**] を展開して、プールの名前を右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5b1c1-112">In Topology Builder, expand **Lync Server 2013**, expand the name of your site, expand **Enterprise Edition Front End pools**, right-click the name of one of your pools, and then click **Edit Properties**.</span></span>

5.  <span data-ttu-id="5b1c1-113">[**プロパティの編集**] ダイアログ ボックスの [**全般**] タブで、[**Office Web Apps サーバーの関連付け**] という見出しを探し、[**新規作成**] をクリックします (または、ドロップダウン リストから既存の Office Web Apps サーバーを選択します)。</span><span class="sxs-lookup"><span data-stu-id="5b1c1-113">In the **Edit Properties** dialog box, on the **General** tab, find the heading **Associate Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

6.  <span data-ttu-id="5b1c1-114">[**新しい Office Web Apps サーバーの定義**] ダイアログ ボックスで、Office Web Apps サーバー コンピューターの完全修飾ドメイン名 (FQDN) を [**Office Web Apps サーバーの FQDN**] ボックスに入力します。これを行うと、Office Web Apps サーバー検出の URL が [**Office Web Apps サーバー検出の URL**] ボックスに自動的に入力されます。</span><span class="sxs-lookup"><span data-stu-id="5b1c1-114">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="5b1c1-115">Office Web Apps サーバーがオンプレミスでインストールされており、Lync Server 2013 と同じネットワークゾーンにある場合、オプションの**Office Web Apps サーバーは外部ネットワーク (境界/インターネット) に展開**されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b1c1-115">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="5b1c1-116">Office Web Apps サーバーを内部ファイアウォールの外側に展開する場合は、[**Office Web Apps サーバーは外部ネットワークで展開 (境界ネットワークまたはインターネット)**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="5b1c1-116">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>

7.  <span data-ttu-id="5b1c1-p104">[**新しい Office Web Apps サーバーの定義**] ダイアログ ボックスで、[**OK**] をクリックし、[**プロパティの編集**] ダイアログ ボックスで [**OK**] をクリックします。Office Web Apps 検出 URL がプールの関連付けの 1 つとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="5b1c1-p104">In the **Define New Office Web Apps Server** dialog box, click **OK**, and then click **OK** in the **Edit Properties** dialog box. The Office Web Apps discovery URL will then be listed as one of the pool's Associations.</span></span>

<span data-ttu-id="5b1c1-119">Office Web Apps サーバーに関連付ける必要がある各プールに対してこのプロセスを繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b1c1-119">You will have to repeat this process for each pool that needs to be associated with your Office Web Apps Server.</span></span>

<span data-ttu-id="5b1c1-p105">検出 URL をトポロジに追加した後、この更新されたトポロジを公開する必要があります。これを行うには、トポロジ ビルダーで次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5b1c1-p105">After you have added the discovery URL to the topology you must then publish this updated topology. To do that in Topology Builder:</span></span>

1.  <span data-ttu-id="5b1c1-122">[**操作**] をクリックし、[**トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5b1c1-122">Click **Action** and then click **Publish Topology**.</span></span>

2.  <span data-ttu-id="5b1c1-123">トポロジの公開ウィザードの [**トポロジの公開**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5b1c1-123">In the Publish Topology wizard, on the **Publish the Topology** page, click **Next**.</span></span>

3.  <span data-ttu-id="5b1c1-124">[**公開ウィザードの完了**] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5b1c1-124">On the **Publishing wizard complete** page, click **Finish**.</span></span>

4.  <span data-ttu-id="5b1c1-125">トポロジ ビルダーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5b1c1-125">Close Topology Builder.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


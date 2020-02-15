---
title: 'Lync Server 2013: Lync server 2013 Standard Edition を既存の Lync Server 2013 エンタープライズに展開する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398112(v=OCS.15)
ms:contentKeyID: 48183297
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b344b3e4ffbeb5d429db2d7220be5bbca9fbed6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a><span data-ttu-id="f9ea2-102">既存の Lync Server 2013 Enterprise への Lync Server 2013 Standard Edition の展開</span><span class="sxs-lookup"><span data-stu-id="f9ea2-102">Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9ea2-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f9ea2-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f9ea2-104">Standard Edition サーバーを既存の Enterprise Edition の展開に展開することは、追加のサーバーの役割の展開に似ています。</span><span class="sxs-lookup"><span data-stu-id="f9ea2-104">Deploying a Standard Edition server into an existing Enterprise Edition deployment is similar to deploying additional server roles.</span></span> <span data-ttu-id="f9ea2-105">Standard Edition サーバーは別のサイトに展開される可能性があります。これにより、そのサイトのユーザーは、ワイドエリアネットワーク (WAN) を介してフロントエンドプールではなく、Standard Edition サーバーに所属することができます。</span><span class="sxs-lookup"><span data-stu-id="f9ea2-105">A Standard Edition server might be deployed to another site, allowing for users in that site to be homed on the Standard Edition server rather than the Front End pool across a wide area network (WAN).</span></span> <span data-ttu-id="f9ea2-106">サイトに新しいサイトとサーバーをインストールする手順は、「 [Lync Server 2013](lync-server-2013-deploying-lync-server.md)ドキュメントの展開」の他のセクションで既に定義されています。</span><span class="sxs-lookup"><span data-stu-id="f9ea2-106">The procedures for installing the new site and servers in that site are already defined in other sections of the [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) documentation.</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="f9ea2-107">**新しいサイトを定義するには**</span><span class="sxs-lookup"><span data-stu-id="f9ea2-107">**To define a new site**</span></span>

1.  <span data-ttu-id="f9ea2-108">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9ea2-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="f9ea2-109">コンソールツリーで、[ **Lync Server 2013**] を右クリックし、[**新しいセントラルサイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9ea2-109">In the console tree, right-click **Lync Server 2013**, and then click **New Central Site**.</span></span>

3.  <span data-ttu-id="f9ea2-110">[**サイトの識別**] ページでサイトに名前を付け、オプションで説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="f9ea2-110">On the **Identify the site** page, give a name to the site and optionally enter a description.</span></span>

4.  <span data-ttu-id="f9ea2-111">サイト トポロジの残りを定義する手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f9ea2-111">Follow the procedures for defining the rest of the site topology.</span></span> <span data-ttu-id="f9ea2-112">詳細については、「 [Lync Server 2013 でのトポロジの定義と構成](lync-server-2013-defining-and-configuring-the-topology.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9ea2-112">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

5.  <span data-ttu-id="f9ea2-113">更新したトポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="f9ea2-113">Publish the updated topology.</span></span> <span data-ttu-id="f9ea2-114">詳細については、「 [Lync Server 2013 でトポロジを公開する](lync-server-2013-publish-the-topology.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9ea2-114">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

6.  <span data-ttu-id="f9ea2-115">Standard Edition サーバーをセットアップしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="f9ea2-115">Set up and install a Standard Edition server.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="f9ea2-116">Standard Edition サーバーのみを使用して環境を展開した場合は、[<STRONG>最初の Standard edition サーバーの準備</STRONG>] リンクを使用して、新しい standard edition サーバーに初期データベースファイルをインストールすることによって、Lync Server 展開ウィザードからセットアッププロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="f9ea2-116">If you have deployed an environment with only a Standard Edition server, you would have begun the setup process from the Lync Server Deployment Wizard by using the <STRONG>Prepare first Standard Edition server</STRONG> link to install the initial database files to the new Standard Edition server.</span></span> <span data-ttu-id="f9ea2-117">Standard Edition サーバーを既存の Lync Server 2013 展開にインストールする場合は、このプロセスを実行<STRONG>しないでください</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="f9ea2-117"><STRONG>Do not</STRONG> follow that process when installing a Standard Edition server into an existing Lync Server 2013 deployment.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


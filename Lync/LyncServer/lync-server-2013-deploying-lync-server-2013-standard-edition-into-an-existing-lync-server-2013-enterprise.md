---
title: 'Lync Server 2013: 既存の Lync Server 2013 Enterprise への Lync Server 2013 Standard Edition の展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398112(v=OCS.15)
ms:contentKeyID: 48183297
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c505a692590662adf03e48d695b3c1ff089d8d7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a><span data-ttu-id="d6517-102">既存の Lync Server 2013 Enterprise への Lync Server 2013 Standard Edition の展開</span><span class="sxs-lookup"><span data-stu-id="d6517-102">Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6517-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="d6517-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="d6517-104">Standard Edition server を既存の Enterprise Edition の展開に展開することは、追加のサーバーロールの展開に似ています。</span><span class="sxs-lookup"><span data-stu-id="d6517-104">Deploying a Standard Edition server into an existing Enterprise Edition deployment is similar to deploying additional server roles.</span></span> <span data-ttu-id="d6517-105">Standard Edition サーバーは、別のサイトに展開されることがあります。これにより、そのサイトのユーザーは、ワイドエリアネットワーク (WAN) 上のフロントエンドプールではなく、Standard Edition server をホームとして使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d6517-105">A Standard Edition server might be deployed to another site, allowing for users in that site to be homed on the Standard Edition server rather than the Front End pool across a wide area network (WAN).</span></span> <span data-ttu-id="d6517-106">このサイトに新しいサイトとサーバーをインストールする手順は、「[展開する Lync Server 2013](lync-server-2013-deploying-lync-server.md)ドキュメント」の他のセクションで既に定義されています。</span><span class="sxs-lookup"><span data-stu-id="d6517-106">The procedures for installing the new site and servers in that site are already defined in other sections of the [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) documentation.</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="d6517-107">**新しいサイトを定義するには**</span><span class="sxs-lookup"><span data-stu-id="d6517-107">**To define a new site**</span></span>

1.  <span data-ttu-id="d6517-108">トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6517-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="d6517-109">コンソールツリーで、[ **Lync Server 2013**] を右クリックし、[**新しいセントラルサイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6517-109">In the console tree, right-click **Lync Server 2013**, and then click **New Central Site**.</span></span>

3.  <span data-ttu-id="d6517-110">[**サイトの識別**] ページで、サイトに名前を付け、必要に応じて説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="d6517-110">On the **Identify the site** page, give a name to the site and optionally enter a description.</span></span>

4.  <span data-ttu-id="d6517-111">残りのサイトトポロジを定義する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d6517-111">Follow the procedures for defining the rest of the site topology.</span></span> <span data-ttu-id="d6517-112">詳細については、「 [Lync Server 2013 でトポロジを定義して構成する](lync-server-2013-defining-and-configuring-the-topology.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6517-112">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

5.  <span data-ttu-id="d6517-113">更新されたトポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="d6517-113">Publish the updated topology.</span></span> <span data-ttu-id="d6517-114">詳細については、「 [Lync Server 2013 でトポロジを発行する](lync-server-2013-publish-the-topology.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6517-114">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

6.  <span data-ttu-id="d6517-115">Standard Edition サーバーのセットアップとインストールを行います。</span><span class="sxs-lookup"><span data-stu-id="d6517-115">Set up and install a Standard Edition server.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="d6517-116">Standard Edition サーバーのみを使用して環境を展開した場合、初期のデータベースファイルを新規にインストールするには、Lync Server <STRONG></STRONG>展開ウィザードのセットアッププロセスを開始します。Standard Edition サーバー。</span><span class="sxs-lookup"><span data-stu-id="d6517-116">If you have deployed an environment with only a Standard Edition server, you would have begun the setup process from the Lync Server Deployment Wizard by using the <STRONG>Prepare first Standard Edition server</STRONG> link to install the initial database files to the new Standard Edition server.</span></span> <span data-ttu-id="d6517-117">既存の Lync Server 2013 展開に Standard Edition サーバーをインストールする場合は、そのプロセスに従わ<STRONG>ないでください</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="d6517-117"><STRONG>Do not</STRONG> follow that process when installing a Standard Edition server into an existing Lync Server 2013 deployment.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: トポロジビルダーでのトポロジの定義と構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a topology in Topology Builder
ms:assetid: 99231ff5-1c21-432b-ad65-8675fcd484f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398788(v=OCS.15)
ms:contentKeyID: 48184953
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3877b19bac01991856313302378c92065bacf22
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a><span data-ttu-id="0401d-102">Lync Server 2013 のトポロジビルダーでのトポロジの定義と構成</span><span class="sxs-lookup"><span data-stu-id="0401d-102">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0401d-103">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="0401d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="0401d-104">トポロジビルダーを実行して新しいトポロジを定義したり、既存のトポロジを変更したりするには、ローカル管理者または特権ドメイングループのメンバーである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0401d-104">Running Topology Builder to define a new topology or to modify an existing topology does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="0401d-105">トポロジビルダーは、構成要件に基づいて、Enterprise Edition フロントエンドプールまたは Standard Edition のトポロジを定義するために必要な手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="0401d-105">Topology Builder guides you through the steps necessary to define your topology for an Enterprise Edition Front End pool or a Standard Edition, based on your configuration requirements.</span></span>

<span data-ttu-id="0401d-106">サーバーに Lync Server 2013 をインストールするには、トポロジビルダーを使用してトポロジを完成させ、公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0401d-106">You must use Topology Builder to complete and publish the topology before you can install Lync Server 2013 on servers.</span></span> <span data-ttu-id="0401d-107">次の手順には、新しいトポロジを定義するために必要な手順も含まれています。</span><span class="sxs-lookup"><span data-stu-id="0401d-107">The following procedure includes the steps required to define a new topology.</span></span>

<div>

## <a name="to-define-a-topology"></a><span data-ttu-id="0401d-108">トポロジを定義するには</span><span class="sxs-lookup"><span data-stu-id="0401d-108">To define a topology</span></span>

1.  <span data-ttu-id="0401d-109">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="0401d-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="0401d-110">[トポロジビルダー] で、[**新しいトポロジ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0401d-110">In Topology Builder, select **New Topology**.</span></span> <span data-ttu-id="0401d-111">トポロジを保存する場所とファイル名を指定するように求められます。</span><span class="sxs-lookup"><span data-stu-id="0401d-111">You are prompted for a location and file name for saving the topology.</span></span> <span data-ttu-id="0401d-112">トポロジ ファイルにわかりやすい名前を付け、既定の拡張子 .tbxml をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="0401d-112">Give the topology file a meaningful name and accept the default extension of .tbxml.</span></span> <span data-ttu-id="0401d-113">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0401d-113">Click **OK**.</span></span>

3.  <span data-ttu-id="0401d-114">新しいトポロジ XML ファイルを保存する場所に移動してファイル名を入力し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0401d-114">Navigate to the location where you want to save the new topology XML file, enter a name for the file, and then click **Save**.</span></span>

4.  <span data-ttu-id="0401d-115">[**プライマリ ドメインの定義**] ページで、組織のプライマリ SIP ドメイン名を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0401d-115">On the **Define the primary domain** page, enter the name of the primary SIP domain for your organization, and then click **Next**.</span></span>

5.  <span data-ttu-id="0401d-116">[**追加でサポートされるドメインの指定**] ページで、追加のドメイン名を入力し (存在する場合)、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0401d-116">On the **Specify additional supported domains** page, enter the names of additional domains, if any, and then click **Next**.</span></span>

6.  <span data-ttu-id="0401d-117">[**最初のサイトの定義**] ページで、最初のサイトの名前と説明を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0401d-117">On the **Define the first site** page, enter a name and a description for the first site, and then click **Next**.</span></span>

7.  <span data-ttu-id="0401d-118">[**サイト詳細の指定**] ページで、サイトの場所情報を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0401d-118">On the **Specify site details** page, enter the location information for the site, and then click **Next**.</span></span>

8.  <span data-ttu-id="0401d-119">[**新しいトポロジが正常に定義されました**] ページで、[**このウィザードを閉じるときに新しいフロントエンドウィザードを開く**] チェックボックスがオンになっていることを確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0401d-119">On the **New topology was successfully defined** page, make sure the **Open the New Front End Wizard when this wizard closes** check box is selected, and then click **Finish**.</span></span>

<span data-ttu-id="0401d-120">トポロジを定義して保存した後、新しいフロントエンドウィザードを使用して、サイトのフロントエンドプールまたは Standard Edition サーバーを定義します。</span><span class="sxs-lookup"><span data-stu-id="0401d-120">After you’ve defined and saved the topology, use the New Front End Wizard to define a Front End pool or Standard Edition server for your site.</span></span> <span data-ttu-id="0401d-121">詳細については、「 [Lync server 2013 でのフロントエンドプールまたは Standard Edition サーバーの定義と構成](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0401d-121">For details, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


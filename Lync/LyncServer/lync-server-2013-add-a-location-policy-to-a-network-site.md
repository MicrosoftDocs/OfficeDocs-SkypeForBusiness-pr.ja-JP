---
title: 'Lync Server 2013: 場所のポリシーをネットワークサイトに追加する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add a location policy to a network site
ms:assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425936(v=OCS.15)
ms:contentKeyID: 48183980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95ca625746fc38d8cab9c25701a8bf22718e71e0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529574"
---
# <a name="add-a-location-policy-to-a-network-site-in-lync-server-2013"></a><span data-ttu-id="8de7b-102">Lync Server 2013 でのネットワークサイトへの場所ポリシーの追加</span><span class="sxs-lookup"><span data-stu-id="8de7b-102">Add a location policy to a network site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8de7b-103">_**トピックの最終更新日:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="8de7b-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="8de7b-104">次の例は、 [Lync Server 2013 の [場所ポリシーの作成](lync-server-2013-create-location-policies.md)] で定義された**redmond**の場所のポリシーを既存のネットワークサイトに追加する方法と、 **redmond**の場所のポリシーを使用する新しいネットワークサイトを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8de7b-104">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>

<span data-ttu-id="8de7b-105">ネットワークサイトの使用の詳細については、以下のコマンドレットの Lync Server Management Shell のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8de7b-105">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="8de7b-106">**新しい-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="8de7b-106">**New-CsNetworkSite**</span></span>

  - <span data-ttu-id="8de7b-107">**-CsNetworkSite の取得**</span><span class="sxs-lookup"><span data-stu-id="8de7b-107">**Get-CsNetworkSite**</span></span>

  - <span data-ttu-id="8de7b-108">**設定-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="8de7b-108">**Set-CsNetworkSite**</span></span>

  - <span data-ttu-id="8de7b-109">**-CsNetworkSite の削除**</span><span class="sxs-lookup"><span data-stu-id="8de7b-109">**Remove-CsNetworkSite**</span></span>

<div>

## <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="8de7b-110">場所のポリシーを既存のネットワーク サイトに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="8de7b-110">To assign a location policy to an existing network site</span></span>

1.  <span data-ttu-id="8de7b-111">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8de7b-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8de7b-112">既存のネットワーク サイトを変更するには、以下のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="8de7b-112">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="8de7b-113">**Redmond というタグ付き**の場所のポリシーを、 **redmond**という名前の既存のネットワークサイトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8de7b-113">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

<div>

## <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="8de7b-114">場所のポリシーを新しいネットワーク サイトに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="8de7b-114">To assign a location policy to a new network site</span></span>

1.  <span data-ttu-id="8de7b-115">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8de7b-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8de7b-116">新しいネットワーク サイトを作成するには、以下のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="8de7b-116">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="8de7b-117">ネットワーク地域の新しいネットワーク サイトを作成して、**Redmond** とマークされた場所のポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8de7b-117">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

</div>

<span> </span>

</div>

</div>

</div>


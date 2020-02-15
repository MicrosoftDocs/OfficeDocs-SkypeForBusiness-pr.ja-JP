---
title: 'Lync Server 2013: 場所データベースの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the location database
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398679(v=OCS.15)
ms:contentKeyID: 48184704
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f79587526172c7ccade1b74574b20657d1a82300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-location-database-in-lync-server-2013"></a><span data-ttu-id="2d5a8-102">Lync Server 2013 で場所データベースを構成する</span><span class="sxs-lookup"><span data-stu-id="2d5a8-102">Configure the location database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d5a8-103">_**トピックの最終更新日:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="2d5a8-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="2d5a8-p101">クライアントがネットワーク内の各自の場所を自動検出できるようにするには、まず場所データベースを構成する必要があります。場所データベースを構成しておらず、場所のポリシーで [**場所は必須**] が [**はい**] または [**免責事項**] に設定されている場合、ユーザーは場所を手動で入力するよう求められます。</span><span class="sxs-lookup"><span data-stu-id="2d5a8-p101">To enable clients to automatically detect their location within a network, you first need to configure the location database. If you do not configure a location database, and **Location Required** in the location policy is set to **Yes** or **Disclaimer**, the user will be prompted to manually enter a location.</span></span>

<span data-ttu-id="2d5a8-106">場所データベースを構成するには、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="2d5a8-106">To configure the location database, you will perform the following tasks:</span></span>

1.  <span data-ttu-id="2d5a8-107">ネットワーク要素と場所のマッピングをデータベースに設定します。</span><span class="sxs-lookup"><span data-stu-id="2d5a8-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="2d5a8-108">緊急位置識別番号 (ELIN) ゲートウェイを使用する場合は、[会社\<名\> ] フィールドに ELIN を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d5a8-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>

2.  <span data-ttu-id="2d5a8-109">E9-1-1 サービス プロバイダーで保持されている主要道路住所案内 (MSAG) と照らし合わせて住所を確認します。</span><span class="sxs-lookup"><span data-stu-id="2d5a8-109">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="2d5a8-110">更新したデータベースを公開します。</span><span class="sxs-lookup"><span data-stu-id="2d5a8-110">Publish the updated database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2d5a8-111">または、場所データベースの代わりに使用できるセカンダリ場所データベースを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="2d5a8-111">Alternately, you can define a secondary location source database that can be used in placed of the location database.</span></span> <span data-ttu-id="2d5a8-112">詳細については、「 <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a Secondary Location Information service In Lync Server 2013</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d5a8-112">For details, see <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2d5a8-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2d5a8-113">In This Section</span></span>

  - [<span data-ttu-id="2d5a8-114">Lync Server 2013 で場所データベースを設定する</span><span class="sxs-lookup"><span data-stu-id="2d5a8-114">Populate the location database in Lync Server 2013</span></span>](lync-server-2013-populate-the-location-database.md)

  - [<span data-ttu-id="2d5a8-115">Lync Server 2013 での住所の検証</span><span class="sxs-lookup"><span data-stu-id="2d5a8-115">Validate addresses in Lync Server 2013</span></span>](lync-server-2013-validate-addresses.md)

  - [<span data-ttu-id="2d5a8-116">Lync Server 2013 からの場所データベースの公開</span><span class="sxs-lookup"><span data-stu-id="2d5a8-116">Publish the location database from Lync Server 2013</span></span>](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


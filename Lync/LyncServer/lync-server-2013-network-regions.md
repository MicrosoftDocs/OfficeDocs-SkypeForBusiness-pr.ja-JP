---
title: 'Lync Server 2013: ネットワーク地域'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network regions
ms:assetid: 1818e9d2-bbb7-420a-93ea-4c3da3a55ad3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687979(v=OCS.15)
ms:contentKeyID: 49733567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dd0a41aae0244eb6f0212c6c620d23f1bbf6400
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-regions-in-lync-server-2013"></a><span data-ttu-id="42d84-102">Lync Server 2013 のネットワーク地域</span><span class="sxs-lookup"><span data-stu-id="42d84-102">Network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42d84-103">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="42d84-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="42d84-104">*ネットワーク地域*は、通話受付管理、E9-1-1、およびメディアバイパスの構成で使用されるネットワークハブまたはバックボーンです。</span><span class="sxs-lookup"><span data-stu-id="42d84-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="42d84-105">ネットワーク地域を表示、作成、または変更するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="42d84-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="42d84-106">たとえば、1つの音声機能に対してネットワーク地域が既に作成されている場合、新しいネットワーク地域を作成する必要はありません。その他の高度なエンタープライズ Voip 機能でも同じネットワーク地域が使用されます。</span><span class="sxs-lookup"><span data-stu-id="42d84-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="42d84-107">ただし、機能固有の設定を適用するために、既存のネットワーク地域定義を変更することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="42d84-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="42d84-108">たとえば、E9-1-1 用のネットワーク地域を作成していて、通話受付管理を展開する場合は、ネットワーク地域定義を変更して中央サイトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42d84-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="42d84-109">詳細については、「 [Lync Server 2013 での CAC のネットワーク地域の構成](lync-server-2013-configure-network-regions-for-cac.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42d84-109">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="42d84-110">ネットワーク地域の定義で機能固有の要件については、すべてその機能の「展開」のトピックで説明されています。</span><span class="sxs-lookup"><span data-stu-id="42d84-110">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="42d84-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="42d84-111">In This Section</span></span>

  - [<span data-ttu-id="42d84-112">Lync Server 2013 でのネットワーク地域情報の表示</span><span class="sxs-lookup"><span data-stu-id="42d84-112">Viewing network region information in Lync Server 2013</span></span>](lync-server-2013-viewing-network-region-information.md)

  - [<span data-ttu-id="42d84-113">Lync Server 2013 でのネットワーク地域の作成または変更</span><span class="sxs-lookup"><span data-stu-id="42d84-113">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)

  - [<span data-ttu-id="42d84-114">Lync Server 2013 の既存のネットワーク領域の削除</span><span class="sxs-lookup"><span data-stu-id="42d84-114">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)

</div>

<div>

## <a name="reference"></a><span data-ttu-id="42d84-115">リファレンス</span><span class="sxs-lookup"><span data-stu-id="42d84-115">Reference</span></span>

[<span data-ttu-id="42d84-116">Lync Server 2013 での高度なエンタープライズ Voip 機能の展開</span><span class="sxs-lookup"><span data-stu-id="42d84-116">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


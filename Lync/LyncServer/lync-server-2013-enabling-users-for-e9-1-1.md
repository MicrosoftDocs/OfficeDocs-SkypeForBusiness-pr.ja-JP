---
title: 'Lync Server 2013: E9-1-1 でのユーザーの有効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling users for E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425892(v=OCS.15)
ms:contentKeyID: 48183884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95f03e3f0249897a17af8354cfca9f58a4d6508b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500914"
---
# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="5ef73-102">Lync Server 2013 での E9-1-1 のユーザーの有効化</span><span class="sxs-lookup"><span data-stu-id="5ef73-102">Enabling users for E9-1-1 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ef73-103">_**トピックの最終更新日:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="5ef73-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="5ef73-104">クライアントの登録時に、Lync Server は場所のポリシーを使用して、エンタープライズ Voip が有効なユーザーの E9-1-1 プロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="5ef73-104">During client registration, Lync Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="5ef73-105">このポリシーには、E9-1-1 の実装方法を定義する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5ef73-105">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="5ef73-106">たとえば、場所のポリシーには緊急ダイヤル文字列などの情報が含まれており、場所情報サービスが自動的に所在地情報を提供しない場合は、ユーザーが場所を手動で入力する必要があるかどうか。</span><span class="sxs-lookup"><span data-stu-id="5ef73-106">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="5ef73-107">場所ポリシーの完全な定義については、「 [Lync Server 2013 の場所のポリシーの定義](lync-server-2013-defining-the-location-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ef73-107">For a complete definition of a location policy, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="5ef73-108">Lync Server は、サブネットに基づいて、またはグローバル、サイトごと、またはユーザーごとのポリシーに基づいて、場所ポリシーをクライアントに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="5ef73-108">Lync Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="5ef73-109">ユーザーを有効にする方法を決定するには、まず、次の情報を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ef73-109">To help decide how you will enable users, you should first answer the following questions.</span></span>

  - <span data-ttu-id="5ef73-110">**すべてのユーザーを有効にするか、またはエンタープライズの特定の地理的領域にサポートを限定するか。**</span><span class="sxs-lookup"><span data-stu-id="5ef73-110">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>  
    <span data-ttu-id="5ef73-111">グローバルな場所ポリシーを使用することで、エンタープライズ内のすべてのユーザーに場所を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="5ef73-111">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="5ef73-112">ただし、場所のポリシーを Lync Server ネットワークサイトに割り当ててからサブネットをサイトに追加することによって、E9-1-1 のサポートをエンタープライズ内の選択された場所に制限し、E9-1-1 のルーティング動作をサイトごとに指定することができます。</span><span class="sxs-lookup"><span data-stu-id="5ef73-112">However, by assigning a location policy to a Lync Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span>

<!-- end list -->

  - <span data-ttu-id="5ef73-113">**ユーザー ポリシーを使用して個々のユーザーを有効にするか。**</span><span class="sxs-lookup"><span data-stu-id="5ef73-113">**Do you plan to enable individual users through a user policy?**</span></span>  
    <span data-ttu-id="5ef73-114">E9-1-1 サポートをカスタマイズする必要がある場合は、場所ポリシーを特定のユーザーまたは共通領域電話の連絡先オブジェクトに直接割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="5ef73-114">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>

<!-- end list -->

  - <span data-ttu-id="5ef73-115">**クライアントがネットワーク外を移動している場合、または定義されていないサブネットから接続されている場合、そのクライアントでも E9-1-1 を有効にするか。**</span><span class="sxs-lookup"><span data-stu-id="5ef73-115">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="5ef73-116">ユーザーがグローバル、サイト、またはユーザー単位の場所のポリシーを割り当てられている場合は、クライアントが定義されたサブネット内に存在しないか、場所情報サービスによって場所が見つからない場合は、クライアントに場所を手動で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ef73-116">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="5ef73-117">詳細については、「 [Lync Server 2013 で手動で場所を取得するためのユーザーの作業を定義](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ef73-117">For details, see [Defining the user experience for manually acquiring a location in Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


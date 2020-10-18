---
title: 'Lync Server 2013: 共通領域電話'
description: 'Lync Server 2013: 共通領域電話'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common area phones
ms:assetid: d63bb3de-154e-4347-9251-9fa94e7d593a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994076(v=OCS.15)
ms:contentKeyID: 51803987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af8a68f875bba1d43a91e5a252259841d7a6bbda
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577033"
---
# <a name="common-area-phones-in-lync-server-2013"></a><span data-ttu-id="376aa-103">Lync Server 2013 の共通領域電話</span><span class="sxs-lookup"><span data-stu-id="376aa-103">Common area phones in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="376aa-104">_**トピックの最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="376aa-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="376aa-105">共通領域電話は、個々のユーザーに関連付けられていない IP 電話です。</span><span class="sxs-lookup"><span data-stu-id="376aa-105">Common area phones are IP phones that are not associated with an individual user.</span></span> <span data-ttu-id="376aa-106">一般的なエリア電話は、誰かのオフィスに配置するのではなく、通常、ロビー、cafeterias、従業員 lounges、会議室、および多数の人々が収集する可能性のある場所の作成に配置されます。</span><span class="sxs-lookup"><span data-stu-id="376aa-106">Instead of being located in someone’s office, common area phones are typically located in building lobbies, cafeterias, employee lounges, meeting rooms, and other locations where a large number of people are likely to gather.</span></span> <span data-ttu-id="376aa-107">Lync Server の他の電話とは異なり、個々のユーザーに割り当てられている音声ポリシーとダイヤルプランを使用することで管理されていますが、共通領域の電話には個々のユーザーが割り当てられることはありません。</span><span class="sxs-lookup"><span data-stu-id="376aa-107">Unlike other phones in Lync Server, which are typically maintained by using voice policies and dial plans that are assigned to individual users, common area phones do not have individual users assigned to them.</span></span> <span data-ttu-id="376aa-108">これは、他の電話とは異なる方法で管理する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="376aa-108">This means that they must be managed differently than your other phones.</span></span>

<span data-ttu-id="376aa-109">共通領域電話を管理するには、ユーザーアカウントなどの共通領域電話すべてに対して Active Directory ドメインサービスの連絡先オブジェクトを作成し、ポリシーおよび音声プランを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="376aa-109">To manage common area phones, you create Active Directory Domain Services contact objects for all your common area phones that, like user accounts, can be assigned policies and voice plans.</span></span> <span data-ttu-id="376aa-110">このアプローチを使用すると、これらの電話が個々のユーザーに関連付けられていない場合でも、共通領域電話の制御を維持できます。</span><span class="sxs-lookup"><span data-stu-id="376aa-110">This approach enables you to maintain control over common area phones, even though those phones are not associated with an individual user.</span></span>

<span data-ttu-id="376aa-111">このセクションのトピックを使用して、共通領域電話の連絡先オブジェクトを作成し、それを変更および削除し、展開内の共通領域電話に関する構成情報を構成および表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="376aa-111">Use the topics in this section to learn how to create contact objects for common area phones, modify and delete them, and configure and view configuration information about the common area phones in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="376aa-112">共通領域電話には、Aastra 6721ip 共通領域電話、HP 4110 IP 電話、および Polycom CX500 IP 共通領域電話の3つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="376aa-112">You have three options for common area phones: the Aastra 6721ip common area phone, the HP 4110 IP Phone, and the Polycom CX500 IP common area phone.</span></span> <span data-ttu-id="376aa-113">Polycom CX3000 IP 会議電話は、別のバリエーション共通領域電話です。</span><span class="sxs-lookup"><span data-stu-id="376aa-113">The Polycom CX3000 IP conferencing phone is another variant common area phone.</span></span> <span data-ttu-id="376aa-114">ただし、会議室での使用を目的としています。</span><span class="sxs-lookup"><span data-stu-id="376aa-114">However, it is intended for use in conference rooms.</span></span> <span data-ttu-id="376aa-115">共通領域電話の詳細については、「 <A href="https://technet.microsoft.com/library/gg398958(v=ocs.14).aspx">New Devices</A>」を選択するの「共通領域電話機」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="376aa-115">For details about common area phones, see the Common Area Phones section of <A href="https://technet.microsoft.com/library/gg398958(v=ocs.14).aspx">Choosing New Devices</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="376aa-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="376aa-116">In This Section</span></span>

  - [<span data-ttu-id="376aa-117">Lync Server 2013 で共通領域電話の情報を表示する</span><span class="sxs-lookup"><span data-stu-id="376aa-117">View common area phone information in Lync Server 2013</span></span>](lync-server-2013-view-common-area-phone-information.md)

  - [<span data-ttu-id="376aa-118">Lync Server 2013 で共通領域電話の連絡先オブジェクトを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="376aa-118">Create or modify a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-common-area-phone-contact-object.md)

  - <span data-ttu-id="376aa-119">[Lync Server 2013 の [ホット desking] を有効または無効にする](lync-server-2013-enable-or-disable-hot-desking.md)</span><span class="sxs-lookup"><span data-stu-id="376aa-119">[Enable or disable hot desking in Lync Server 2013](lync-server-2013-enable-or-disable-hot-desking.md)</span></span>

  - [<span data-ttu-id="376aa-120">Lync Server 2013 で共通領域電話の連絡先オブジェクトを削除する</span><span class="sxs-lookup"><span data-stu-id="376aa-120">Delete a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-delete-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="376aa-121">Lync Server 2013 のポリシーを共通領域電話に割り当てる</span><span class="sxs-lookup"><span data-stu-id="376aa-121">Assign policies in Lync Server 2013 to a common area phone</span></span>](lync-server-2013-assign-policies-to-a-common-area-phone.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


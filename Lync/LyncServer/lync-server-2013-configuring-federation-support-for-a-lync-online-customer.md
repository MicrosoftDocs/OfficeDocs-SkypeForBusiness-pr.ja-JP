---
title: 'Lync Server 2013: Lync Online お客様のためのフェデレーションサポートの構成'
description: 'Lync Server 2013: Lync Online お客様のためのフェデレーションサポートの構成。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring federation support for a Lync Online customer
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b5e7995e686a9492b3a4be98a92b848716cacf9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548423"
---
# <a name="configuring-federation-support-for-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="59f54-103">Lync Server 2013 で Lync Online 顧客のフェデレーションサポートを構成する</span><span class="sxs-lookup"><span data-stu-id="59f54-103">Configuring federation support for a Lync Online customer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59f54-104">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="59f54-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="59f54-105">次のいずれかの方法で、組織のユーザーに通信サービスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="59f54-105">You can provide communications services to users in your organization in any of the following ways:</span></span>

  - <span data-ttu-id="59f54-106">組織で Lync Server 2013 を展開する ( *オンプレミスのサービス*とも呼ばれます)。また、組織で lync 2013 ユーザーアカウントをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="59f54-106">Deploying Lync Server 2013 in your organization (known as *on-premises services*) and setting up Lync 2013 user accounts in your organization.</span></span>

  - <span data-ttu-id="59f54-107">ホスティングプロバイダーを使用して Microsoft Lync Online 2010 の顧客アカウントを設定し、ホスティングプロバイダーでユーザーアカウントをセットアップする ( *オンラインサービス*とも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="59f54-107">Setting up a Microsoft Lync Online 2010 customer account with a Hosting Provider and setting up user accounts with the Hosting Provider (known as *online services*).</span></span>

<span data-ttu-id="59f54-108">組織で Lync 2013 を展開する場合、1人以上の Microsoft Lync Online 2010 ユーザーのドメインとフェデレーションを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="59f54-108">If you deploy Lync 2013 in your organization, you can federate with the domains of one or more Microsoft Lync Online 2010 customers.</span></span> <span data-ttu-id="59f54-109">オンプレミスの Lync 2013 展開のユーザーと Lync Online 2010 お客様のユーザーとの間のフェデレーションを有効にするには、Lync Online 顧客のドメインとユーザーのサポートを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59f54-109">To enable federation between users of your on-premises Lync 2013 deployment and users of a Lync Online 2010 customer, you must configure support for the domain and users of the Lync Online customer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="59f54-110">このドキュメントでは、Lync Online 2010 顧客とのフェデレーションをサポートするように組織を構成する手順についてのみ説明します。</span><span class="sxs-lookup"><span data-stu-id="59f54-110">This documentation describes only the procedures for configuring your organization to support federation with an Lync Online 2010 customer.</span></span> <span data-ttu-id="59f54-111">このドキュメントでは、フェデレーションをサポートするように Lync Online 2010 お客様を構成する手順については説明しません。</span><span class="sxs-lookup"><span data-stu-id="59f54-111">This documentation does not describe the procedures for configuring the Lync Online 2010 customer to support federation.</span></span> <span data-ttu-id="59f54-112">Lync Online サービスの詳細については、「Lync Online at」を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=218941">https://go.microsoft.com/fwlink/p/?linkId=218941</A> 。</span><span class="sxs-lookup"><span data-stu-id="59f54-112">For details about Lync Online services, see Lync Online at <A href="https://go.microsoft.com/fwlink/p/?linkid=218941">https://go.microsoft.com/fwlink/p/?linkId=218941</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="59f54-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="59f54-113">In This Section</span></span>

  - [<span data-ttu-id="59f54-114">Lync Server 2013 での Lync Online 顧客とのフェデレーションの前提条件</span><span class="sxs-lookup"><span data-stu-id="59f54-114">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)

  - [<span data-ttu-id="59f54-115">Lync Server 2013 で Lync Online ドメインのフェデレーションサポートを構成する</span><span class="sxs-lookup"><span data-stu-id="59f54-115">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)

  - [<span data-ttu-id="59f54-116">Lync Server 2013 で Lync Online の顧客とのフェデレーションのユーザーアクセスを構成する</span><span class="sxs-lookup"><span data-stu-id="59f54-116">Configure user access for federation with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)

  - [<span data-ttu-id="59f54-117">Lync Server 2013 で Lync Online の顧客との通信を確認する</span><span class="sxs-lookup"><span data-stu-id="59f54-117">Verify communications with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-verify-communications-with-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


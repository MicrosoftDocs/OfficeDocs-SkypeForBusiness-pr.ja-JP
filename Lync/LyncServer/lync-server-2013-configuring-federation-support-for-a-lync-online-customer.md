---
title: 'Lync Server 2013: Lync Online お客様のためのフェデレーションサポートの構成'
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
ms.openlocfilehash: cffed0c856577a60a9782850006b82f2c9d45374
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202923"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-federation-support-for-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="392cf-102">Lync Server 2013 で Lync Online 顧客のフェデレーションサポートを構成する</span><span class="sxs-lookup"><span data-stu-id="392cf-102">Configuring federation support for a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="392cf-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="392cf-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="392cf-104">次のいずれかの方法で、組織のユーザーに通信サービスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="392cf-104">You can provide communications services to users in your organization in any of the following ways:</span></span>

  - <span data-ttu-id="392cf-105">組織で Lync Server 2013 を展開する (*オンプレミスのサービス*とも呼ばれます)。また、組織で lync 2013 ユーザーアカウントをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="392cf-105">Deploying Lync Server 2013 in your organization (known as *on-premises services*) and setting up Lync 2013 user accounts in your organization.</span></span>

  - <span data-ttu-id="392cf-106">ホスティングプロバイダーを使用して Microsoft Lync Online 2010 の顧客アカウントを設定し、ホスティングプロバイダーでユーザーアカウントをセットアップする (*オンラインサービス*とも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="392cf-106">Setting up a Microsoft Lync Online 2010 customer account with a Hosting Provider and setting up user accounts with the Hosting Provider (known as *online services*).</span></span>

<span data-ttu-id="392cf-107">組織で Lync 2013 を展開する場合、1人以上の Microsoft Lync Online 2010 ユーザーのドメインとフェデレーションを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="392cf-107">If you deploy Lync 2013 in your organization, you can federate with the domains of one or more Microsoft Lync Online 2010 customers.</span></span> <span data-ttu-id="392cf-108">オンプレミスの Lync 2013 展開のユーザーと Lync Online 2010 お客様のユーザーとの間のフェデレーションを有効にするには、Lync Online 顧客のドメインとユーザーのサポートを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="392cf-108">To enable federation between users of your on-premises Lync 2013 deployment and users of a Lync Online 2010 customer, you must configure support for the domain and users of the Lync Online customer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="392cf-109">このドキュメントでは、Lync Online 2010 顧客とのフェデレーションをサポートするように組織を構成する手順についてのみ説明します。</span><span class="sxs-lookup"><span data-stu-id="392cf-109">This documentation describes only the procedures for configuring your organization to support federation with an Lync Online 2010 customer.</span></span> <span data-ttu-id="392cf-110">このドキュメントでは、フェデレーションをサポートするように Lync Online 2010 お客様を構成する手順については説明しません。</span><span class="sxs-lookup"><span data-stu-id="392cf-110">This documentation does not describe the procedures for configuring the Lync Online 2010 customer to support federation.</span></span> <span data-ttu-id="392cf-111">Lync Online サービスの詳細については、「 <A href="https://go.microsoft.com/fwlink/p/?linkid=218941">https://go.microsoft.com/fwlink/p/?linkId=218941</A>lync online at」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="392cf-111">For details about Lync Online services, see Lync Online at <A href="https://go.microsoft.com/fwlink/p/?linkid=218941">https://go.microsoft.com/fwlink/p/?linkId=218941</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="392cf-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="392cf-112">In This Section</span></span>

  - [<span data-ttu-id="392cf-113">Lync Server 2013 での Lync Online 顧客とのフェデレーションの前提条件</span><span class="sxs-lookup"><span data-stu-id="392cf-113">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)

  - [<span data-ttu-id="392cf-114">Lync Server 2013 で Lync Online ドメインのフェデレーションサポートを構成する</span><span class="sxs-lookup"><span data-stu-id="392cf-114">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)

  - [<span data-ttu-id="392cf-115">Lync Server 2013 で Lync Online の顧客とのフェデレーションのユーザーアクセスを構成する</span><span class="sxs-lookup"><span data-stu-id="392cf-115">Configure user access for federation with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)

  - [<span data-ttu-id="392cf-116">Lync Server 2013 で Lync Online の顧客との通信を確認する</span><span class="sxs-lookup"><span data-stu-id="392cf-116">Verify communications with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-verify-communications-with-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


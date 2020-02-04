---
title: 'Lync Server 2013: Lync Online の顧客のためのフェデレーションサポートの構成'
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
ms.openlocfilehash: 76582be324977d5466d234a37e4352806dd6d92f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728997"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-federation-support-for-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="2cf6a-102">Lync Server 2013 での Lync Online ユーザーのフェデレーションサポートの構成</span><span class="sxs-lookup"><span data-stu-id="2cf6a-102">Configuring federation support for a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cf6a-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2cf6a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2cf6a-104">次のいずれかの方法で、組織内のユーザーに通信サービスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="2cf6a-104">You can provide communications services to users in your organization in any of the following ways:</span></span>

  - <span data-ttu-id="2cf6a-105">組織内の Lync Server 2013 (*オンプレミスサービス*とも呼ばれます) を展開して、組織内の lync 2013 ユーザーアカウントをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="2cf6a-105">Deploying Lync Server 2013 in your organization (known as *on-premises services*) and setting up Lync 2013 user accounts in your organization.</span></span>

  - <span data-ttu-id="2cf6a-106">ホスティングプロバイダーを使用して Microsoft Lync Online 2010 顧客アカウントを設定し、ホスティングプロバイダー (*オンラインサービス*とも呼ばれます) を使用してユーザーアカウントをセットアップする。</span><span class="sxs-lookup"><span data-stu-id="2cf6a-106">Setting up a Microsoft Lync Online 2010 customer account with a Hosting Provider and setting up user accounts with the Hosting Provider (known as *online services*).</span></span>

<span data-ttu-id="2cf6a-107">組織に Lync 2013 を展開する場合は、1つ以上の Microsoft Lync Online 2010 ユーザーのドメインとフェデレーションを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2cf6a-107">If you deploy Lync 2013 in your organization, you can federate with the domains of one or more Microsoft Lync Online 2010 customers.</span></span> <span data-ttu-id="2cf6a-108">オンプレミスの Lync 2013 の展開と Lync Online 2010 のユーザーとのフェデレーションを有効にするには、ドメインと Lync Online のユーザーのサポートを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cf6a-108">To enable federation between users of your on-premises Lync 2013 deployment and users of a Lync Online 2010 customer, you must configure support for the domain and users of the Lync Online customer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2cf6a-109">このドキュメントでは、Lync Online 2010 顧客とのフェデレーションをサポートするように組織を構成する手順についてのみ説明します。</span><span class="sxs-lookup"><span data-stu-id="2cf6a-109">This documentation describes only the procedures for configuring your organization to support federation with an Lync Online 2010 customer.</span></span> <span data-ttu-id="2cf6a-110">このドキュメントでは、Lync Online 2010 顧客がフェデレーションをサポートするように構成する手順については説明していません。</span><span class="sxs-lookup"><span data-stu-id="2cf6a-110">This documentation does not describe the procedures for configuring the Lync Online 2010 customer to support federation.</span></span> <span data-ttu-id="2cf6a-111">Lync Online サービスの詳細については、「 <A href="http://go.microsoft.com/fwlink/p/?linkid=218941">http://go.microsoft.com/fwlink/p/?linkId=218941</A>lync online at」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2cf6a-111">For details about Lync Online services, see Lync Online at <A href="http://go.microsoft.com/fwlink/p/?linkid=218941">http://go.microsoft.com/fwlink/p/?linkId=218941</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2cf6a-112">このセクション中</span><span class="sxs-lookup"><span data-stu-id="2cf6a-112">In This Section</span></span>

  - [<span data-ttu-id="2cf6a-113">Lync Online のユーザーと Lync Server 2013 でフェデレーションを行うための前提条件</span><span class="sxs-lookup"><span data-stu-id="2cf6a-113">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)

  - [<span data-ttu-id="2cf6a-114">Lync Server 2013 での Lync Online ドメインのフェデレーションサポートの構成</span><span class="sxs-lookup"><span data-stu-id="2cf6a-114">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)

  - [<span data-ttu-id="2cf6a-115">Lync Server 2013 で Lync Online ユーザーとのフェデレーション用にユーザーアクセスを構成する</span><span class="sxs-lookup"><span data-stu-id="2cf6a-115">Configure user access for federation with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)

  - [<span data-ttu-id="2cf6a-116">Lync Online の顧客との通信を Lync Server 2013 で確認する</span><span class="sxs-lookup"><span data-stu-id="2cf6a-116">Verify communications with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-verify-communications-with-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


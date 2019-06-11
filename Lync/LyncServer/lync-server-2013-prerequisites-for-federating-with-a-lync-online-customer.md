---
title: 'Lync Server 2013: Lync Online の顧客とのフェデレーションの前提条件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prerequisites for federating with a Lync Online customer
ms:assetid: f57d8f8a-2b1e-4186-a74f-1d7c6872bfdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202196(v=OCS.15)
ms:contentKeyID: 48185838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af3db1918e2d347084f1bbdcdf5ea4eb92ae8d91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-federating-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="2b0e3-102">Lync Online のユーザーと Lync Server 2013 でフェデレーションを行うための前提条件</span><span class="sxs-lookup"><span data-stu-id="2b0e3-102">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b0e3-103">_**最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="2b0e3-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="2b0e3-104">Lync Online 2010 ユーザーとのフェデレーションを行うには、組織での Lync Server 2013 の最初の展開と構成を既に完了している必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b0e3-104">To federate with a Lync Online 2010 customer, you should have already completed initial deployment and configuration of Lync Server 2013 in your organization.</span></span> <span data-ttu-id="2b0e3-105">これには、次のポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2b0e3-105">This includes the following:</span></span>

  - <span data-ttu-id="2b0e3-106">少なくとも1つの Standard Edition サーバーまたは1つの Enterprise Edition フロントエンドプールを組織に展開します。</span><span class="sxs-lookup"><span data-stu-id="2b0e3-106">Deploying at least one Standard Edition server or one Enterprise Edition Front End pool in your organization.</span></span> <span data-ttu-id="2b0e3-107">内部サーバーの展開の詳細については、「展開ドキュメントに[Lync Server 2013 を展開](lync-server-2013-deploying-lync-server.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b0e3-107">For details about deploying internal servers, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="2b0e3-108">Lync Server 2013 の内部ユーザーアカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2b0e3-108">Enabling internal user accounts for Lync Server 2013.</span></span> <span data-ttu-id="2b0e3-109">詳細については、展開ドキュメントまたは運用マニュアルの「 [Lync Server 2013 のユーザーアカウントを無効にするか、もう一度有効にする](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b0e3-109">For details, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) in the Deployment documentation or the Operations documentation.</span></span>

  - <span data-ttu-id="2b0e3-110">少なくとも1つのエッジサーバーと、外部ユーザーのアクセスをサポートするために必要なその他のコンポーネントを展開します。</span><span class="sxs-lookup"><span data-stu-id="2b0e3-110">Deploying at least one Edge Server and the other components required to support external user access.</span></span> <span data-ttu-id="2b0e3-111">詳細については、展開ドキュメントで「 [Lync Server 2013 へのフェデレーションと外部アクセスを管理する](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b0e3-111">For details, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="2b0e3-112">組織内でフェデレーションサポートを有効にし、フェデレーションドメインによるアクセスを制御するための適切なメソッドを構成します。</span><span class="sxs-lookup"><span data-stu-id="2b0e3-112">Enabling federation support within your organization and configuring the appropriate method for controlling access by federated domains.</span></span> <span data-ttu-id="2b0e3-113">詳細については、「 [Lync server 2013 でリモートユーザーアクセスを有効または無効](lync-server-2013-enable-or-disable-remote-user-access.md)にする」および「運用ドキュメントの[lync server 2013 で組織の SIP フェデレーションプロバイダーを管理](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b0e3-113">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md) and [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="2b0e3-114">組織内のユーザーに対して外部ユーザーアクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2b0e3-114">Enabling external user access for users in your organization.</span></span> <span data-ttu-id="2b0e3-115">詳細については、「Lync Server 2013 で Lync を有効にしているユーザーと展開ドキュメントまたは操作ドキュメントに[外部ユーザーアクセスポリシーを割り当てる](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b0e3-115">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) and in the Deployment documentation or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


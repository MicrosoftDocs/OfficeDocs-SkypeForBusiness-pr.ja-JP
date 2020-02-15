---
title: 'Lync Server 2013: Lync Online の顧客とのフェデレーションの前提条件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for federating with a Lync Online customer
ms:assetid: f57d8f8a-2b1e-4186-a74f-1d7c6872bfdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202196(v=OCS.15)
ms:contentKeyID: 48185838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71ad28107f31bf2593952ae8356ac2c9af2b4bc6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-federating-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="8e7b9-102">Lync Server 2013 での Lync Online 顧客とのフェデレーションの前提条件</span><span class="sxs-lookup"><span data-stu-id="8e7b9-102">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e7b9-103">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="8e7b9-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="8e7b9-104">Lync Online 2010 お客様とフェデレーションするには、組織での Lync Server 2013 の初期展開と構成をすでに完了している必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e7b9-104">To federate with a Lync Online 2010 customer, you should have already completed initial deployment and configuration of Lync Server 2013 in your organization.</span></span> <span data-ttu-id="8e7b9-105">エクスポートできるものには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="8e7b9-105">This includes the following:</span></span>

  - <span data-ttu-id="8e7b9-106">少なくとも1つの Standard Edition サーバーまたは1つの Enterprise Edition フロントエンドプールを組織に展開します。</span><span class="sxs-lookup"><span data-stu-id="8e7b9-106">Deploying at least one Standard Edition server or one Enterprise Edition Front End pool in your organization.</span></span> <span data-ttu-id="8e7b9-107">内部サーバーの展開の詳細については、「展開」のドキュメントの「[展開 Lync Server 2013](lync-server-2013-deploying-lync-server.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e7b9-107">For details about deploying internal servers, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="8e7b9-108">Lync Server 2013 の内部ユーザーアカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8e7b9-108">Enabling internal user accounts for Lync Server 2013.</span></span> <span data-ttu-id="8e7b9-109">詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「 [Lync Server 2013 のユーザーアカウントの無効化または再有効化](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e7b9-109">For details, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) in the Deployment documentation or the Operations documentation.</span></span>

  - <span data-ttu-id="8e7b9-110">少なくとも1つのエッジサーバーと、外部ユーザーアクセスをサポートするために必要なその他のコンポーネントを展開します。</span><span class="sxs-lookup"><span data-stu-id="8e7b9-110">Deploying at least one Edge Server and the other components required to support external user access.</span></span> <span data-ttu-id="8e7b9-111">詳細については、「展開」のドキュメントの「[管理フェデレーション」および「Lync Server 2013 への外部アクセス」を](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e7b9-111">For details, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="8e7b9-112">組織内でフェデレーションのサポートを有効にし、フェデレーションドメインによるアクセスを制御するための適切な方法を構成します。</span><span class="sxs-lookup"><span data-stu-id="8e7b9-112">Enabling federation support within your organization and configuring the appropriate method for controlling access by federated domains.</span></span> <span data-ttu-id="8e7b9-113">詳細については、「操作」のドキュメントの「 [lync server 2013 でのリモートユーザーアクセスの有効化または無効化](lync-server-2013-enable-or-disable-remote-user-access.md)」および「 [lync server 2013 での組織の SIP フェデレーションプロバイダーの管理](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e7b9-113">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md) and [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="8e7b9-114">組織内のユーザーの外部ユーザーアクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8e7b9-114">Enabling external user access for users in your organization.</span></span> <span data-ttu-id="8e7b9-115">詳細については、「 [Lync Server 2013 での lync が有効なユーザーへの外部ユーザーアクセスポリシーの割り当て](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)」および「展開」のドキュメントまたは「操作」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e7b9-115">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) and in the Deployment documentation or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Lync Online の顧客との通信を確認する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify communications with a Lync Online customer
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202189(v=OCS.15)
ms:contentKeyID: 48185378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59fcf8398fa012543303f959f4888074f5192470
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-communications-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="3b676-102">Lync Server 2013 で Lync Online の顧客との通信を確認する</span><span class="sxs-lookup"><span data-stu-id="3b676-102">Verify communications with a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b676-103">_**トピックの最終更新日:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="3b676-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="3b676-104">組織内の Lync ユーザーが Microsoft Lync Online 2010 顧客のユーザーと通信できるようにするには、次の手順を完了している必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b676-104">To enable Lync users in your organization to communicate with users of a Microsoft Lync Online 2010 customer, you must have completed the following steps:</span></span>

  - <span data-ttu-id="3b676-105">すべての前提条件を満たします。</span><span class="sxs-lookup"><span data-stu-id="3b676-105">Met all prerequisites.</span></span> <span data-ttu-id="3b676-106">このための作業には、内部サーバーとエッジ サーバーを展開する、組織に対してフェデレーションのサポートを有効にする、ユーザー アカウントを設定するなどがあります。</span><span class="sxs-lookup"><span data-stu-id="3b676-106">This includes deploying your internal and edge servers, enabling federation support for your organization, and setting up user accounts.</span></span> <span data-ttu-id="3b676-107">詳細については、「lync [Server 2013 での Lync Online の顧客とのフェデレーションの前提条件](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b676-107">For details, see [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).</span></span>

  - <span data-ttu-id="3b676-108">内部展開にドメイン アクセスのサポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="3b676-108">Configured domain access support in your internal deployment.</span></span> <span data-ttu-id="3b676-109">これには、Lync Online の顧客のドメインからのアクセスを許可するように、ホストプロバイダエントリを作成し、展開を構成することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3b676-109">This includes creating a host provider entry and configuring your deployment to allow access from the Lync Online customer’s domain.</span></span> <span data-ttu-id="3b676-110">詳細については、「 [Lync Server 2013 で Lync Online ドメインのフェデレーションサポートを構成する](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b676-110">For details, see [Configure federation support for a Lync Online domain in Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).</span></span>

  - <span data-ttu-id="3b676-111">フェデレーションをサポートするようにユーザー アカウントを構成します。</span><span class="sxs-lookup"><span data-stu-id="3b676-111">Configured your user accounts to support federation.</span></span> <span data-ttu-id="3b676-112">詳細については、「lync [Server 2013 で Lync Online の顧客とのフェデレーションのユーザーアクセスを構成する](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b676-112">For details, see [Configure user access for federation with a Lync Online customer in Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).</span></span>

<span data-ttu-id="3b676-113">これらの手順をすべて完了し、Lync Online 2010 お客様の管理者が組織とのフェデレーションをサポートするようにオンラインサービスのすべての構成を完了したら、内部の通信をテストして通信を確認します。組織内のユーザーと Lync Online 顧客のユーザー。</span><span class="sxs-lookup"><span data-stu-id="3b676-113">After you complete all of these steps and the administrator of the Lync Online 2010 customer completes all configuration of their online services to support federation with your organization, verify communications by testing communications between an internal user in your organization and a user of the Lync Online customer.</span></span> <span data-ttu-id="3b676-114">通信が成功しなかった場合は、エッジサーバーのログツールを使用して、問題のトラブルシューティングのためにログとトレースファイルをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="3b676-114">If communication is not successful, use the Logging Tool from your Edge Server to capture log and trace files in order to troubleshoot the problem.</span></span> <span data-ttu-id="3b676-115">ログツールの使用の詳細については、「操作」のドキュメントの「 [Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b676-115">For details about using the Logging Tool, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md) in the Operations documentation.</span></span> <span data-ttu-id="3b676-116">ログツールの詳細については、TechNet ライブラリの Lync Server 2010 ログツールに関するドキュメント[https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b676-116">For details about the Logging Tool, see the Lync Server 2010 Logging Tool documentation on the TechNet Library at [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


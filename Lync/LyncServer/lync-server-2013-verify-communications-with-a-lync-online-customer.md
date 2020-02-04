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
ms.openlocfilehash: f9b20be32ecbc7c3c684009c9c2f928c9dc897cd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-communications-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="b5cd0-102">Lync Online の顧客との通信を Lync Server 2013 で確認する</span><span class="sxs-lookup"><span data-stu-id="b5cd0-102">Verify communications with a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5cd0-103">_**最終更新日:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="b5cd0-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="b5cd0-104">組織内の Lync ユーザーが Microsoft Lync Online 2010 顧客のユーザーと通信できるようにするには、次の手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5cd0-104">To enable Lync users in your organization to communicate with users of a Microsoft Lync Online 2010 customer, you must have completed the following steps:</span></span>

  - <span data-ttu-id="b5cd0-105">すべての前提条件を満たしていること。</span><span class="sxs-lookup"><span data-stu-id="b5cd0-105">Met all prerequisites.</span></span> <span data-ttu-id="b5cd0-106">これには、内部サーバーとエッジサーバーの展開、組織に対するフェデレーションサポートの有効化、ユーザーアカウントのセットアップなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b5cd0-106">This includes deploying your internal and edge servers, enabling federation support for your organization, and setting up user accounts.</span></span> <span data-ttu-id="b5cd0-107">詳細については、「 [Lync Online のお客様とのフェデレーションの前提条件 Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5cd0-107">For details, see [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).</span></span>

  - <span data-ttu-id="b5cd0-108">内部展開でドメインアクセスのサポートが構成されている。</span><span class="sxs-lookup"><span data-stu-id="b5cd0-108">Configured domain access support in your internal deployment.</span></span> <span data-ttu-id="b5cd0-109">これには、ホストプロバイダーエントリの作成、および Lync Online の顧客のドメインからのアクセスを許可するように展開を構成することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b5cd0-109">This includes creating a host provider entry and configuring your deployment to allow access from the Lync Online customer’s domain.</span></span> <span data-ttu-id="b5cd0-110">詳細については、「 [Lync Server 2013 で Lync Online ドメインのフェデレーションサポートを構成する](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5cd0-110">For details, see [Configure federation support for a Lync Online domain in Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).</span></span>

  - <span data-ttu-id="b5cd0-111">フェデレーションをサポートするようにユーザーアカウントを構成しました。</span><span class="sxs-lookup"><span data-stu-id="b5cd0-111">Configured your user accounts to support federation.</span></span> <span data-ttu-id="b5cd0-112">詳細については、「 [Lync Online のユーザーとのフェデレーションのためのユーザーアクセスを Lync Server 2013 で構成する](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5cd0-112">For details, see [Configure user access for federation with a Lync Online customer in Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).</span></span>

<span data-ttu-id="b5cd0-113">すべての手順を完了して、Lync Online 2010 顧客の管理者が、組織とのフェデレーションをサポートするためにオンラインサービスのすべての構成を完了したら、社内の間の通信をテストして通信を確認します。組織内のユーザー、および Lync Online 顧客のユーザー。</span><span class="sxs-lookup"><span data-stu-id="b5cd0-113">After you complete all of these steps and the administrator of the Lync Online 2010 customer completes all configuration of their online services to support federation with your organization, verify communications by testing communications between an internal user in your organization and a user of the Lync Online customer.</span></span> <span data-ttu-id="b5cd0-114">通信が失敗した場合は、エッジサーバーのログツールを使用して、ログファイルとトレースファイルをキャプチャし、問題のトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="b5cd0-114">If communication is not successful, use the Logging Tool from your Edge Server to capture log and trace files in order to troubleshoot the problem.</span></span> <span data-ttu-id="b5cd0-115">ログツールの使用について詳しくは、「 [Lync Server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)を使用する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b5cd0-115">For details about using the Logging Tool, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md) in the Operations documentation.</span></span> <span data-ttu-id="b5cd0-116">ログツールの詳細については、TechNet ライブラリの Lync Server 2010 Logging Tool のマニュアルを[http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265)参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5cd0-116">For details about the Logging Tool, see the Lync Server 2010 Logging Tool documentation on the TechNet Library at [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


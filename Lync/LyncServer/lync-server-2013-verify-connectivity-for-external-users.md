---
title: 'Lync Server 2013: 外部ユーザーの接続の確認'
description: 'Lync Server 2013: 外部ユーザーの接続を確認します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity for external users
ms:assetid: 5c02bd6e-1c96-448a-a21d-58c9961c6640
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398402(v=OCS.15)
ms:contentKeyID: 48184249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50ef728157d01b93e7d0b8420442ce083a42b5b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547093"
---
# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a><span data-ttu-id="472e0-103">Lync Server 2013 での外部ユーザーの接続の確認</span><span class="sxs-lookup"><span data-stu-id="472e0-103">Verify connectivity for external users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="472e0-104">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="472e0-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="472e0-105">外部ユーザーの接続を検証するには、ユーザーからアクセス エッジ サービスのサーバーおよびポートへの接続を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="472e0-105">Validating connectivity for external users requires ensuring connectivity from users to the server and port for the Access Edge service.</span></span>

<span data-ttu-id="472e0-106">構成を確認し、外部ユーザーアクセスが必要とするシナリオに対して適切なメッセージを送受信する機能がリモート接続アナライザーサイト () であることを確認するための貴重なリソースです <http://www.testocsconnectivity.com> 。</span><span class="sxs-lookup"><span data-stu-id="472e0-106">A valuable resource for confirming your configuration and the ability to connect, send and receive the correct messages for the scenarios that external user access requires is the Remote Connectivity Analyzer site (<http://www.testocsconnectivity.com>).</span></span> <span data-ttu-id="472e0-107">サイトは、Microsoft サポートによって管理および管理されます。</span><span class="sxs-lookup"><span data-stu-id="472e0-107">The site is managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="472e0-108">リモート接続アナライザーにアクセスするには、ブラウザーでこの Web サイトを開き、指示に従ってシナリオを選択します。</span><span class="sxs-lookup"><span data-stu-id="472e0-108">To reach the Remote Connectivity Analyzer, open the Web site in a browser and follow the instructions to select the scenario.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="472e0-109">外部ユーザーの接続と外部アクセスをテストするには</span><span class="sxs-lookup"><span data-stu-id="472e0-109">Test Connectivity of External Users and External access</span></span>

<span data-ttu-id="472e0-110">外部ユーザー アクセスのテストには、次のいずれかまたはすべてなど、組織がサポートしている各外部ユーザー タイプを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="472e0-110">Tests for external user access should include each type of external user that your organization supports, including any or all of the following:</span></span>

  - <span data-ttu-id="472e0-111">少なくとも 1 つのフェデレーション ドメインのユーザーと、IM、プレゼンス、音声ビデオ、およびデスクトップ共有のテスト。</span><span class="sxs-lookup"><span data-stu-id="472e0-111">Users from at least one federated domain, and test IM, presence, A/V and desktop sharing.</span></span>

  - <span data-ttu-id="472e0-112">組織がサポート (およびプロビジョニングが完了) している各パブリック IM サービス プロバイダーのユーザー。</span><span class="sxs-lookup"><span data-stu-id="472e0-112">Users of each public IM service provider that your organization supports (and for which provisioning has been completed).</span></span>

  - <span data-ttu-id="472e0-113">匿名ユーザー。</span><span class="sxs-lookup"><span data-stu-id="472e0-113">Anonymous users.</span></span>

  - <span data-ttu-id="472e0-114">VPN を使用せずに Lync にリモートでログインする組織内のユーザー。</span><span class="sxs-lookup"><span data-stu-id="472e0-114">Users within your organization who are logged into Lync remotely, but not using VPN.</span></span>

<span data-ttu-id="472e0-115">これらのテストで、エッジ サーバーが次のことを実行しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="472e0-115">These tests determine whether your Edge Server is:</span></span>

  - <span data-ttu-id="472e0-116">ネットワーク外から telnet クライアントを使用して必要なポートをリッスンする。</span><span class="sxs-lookup"><span data-stu-id="472e0-116">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
      - <span data-ttu-id="472e0-117">例:  telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="472e0-117">Example: telnet sip.contoso.com 443</span></span>
    
      - <span data-ttu-id="472e0-118">展開に応じて、エッジ サーバーまたはエッジ サーバー プールで使用しているポートで上記のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="472e0-118">Perform the preceding test on ports you are using on the Edge Server or Edge Server pool depending on your deployment.</span></span>

  - <span data-ttu-id="472e0-119">正確な外部 DNS 解決を実行する。</span><span class="sxs-lookup"><span data-stu-id="472e0-119">Performing accurate external DNS resolution.</span></span>
    
      - <span data-ttu-id="472e0-p102">ネットワーク外から、エッジまたはエッジ プールの各外部 FQDN で Ping を実行します。 Ping が失敗した場合でも、IP アドレスを確認できるため、割り当てた IP アドレスと比較できます。</span><span class="sxs-lookup"><span data-stu-id="472e0-p102">From outside your network ping each of the external FQDN’s of your Edge or Edge pool. Even if the ping fails you will see the IP addresses, which you can compare to the ones you have assigned.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


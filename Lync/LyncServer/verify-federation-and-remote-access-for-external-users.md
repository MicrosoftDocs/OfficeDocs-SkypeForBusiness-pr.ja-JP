---
title: 外部ユーザーのフェデレーションとリモート アクセスの確認
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify federation and remote access for external users
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49733768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33eb8fddaef96da047a6e87f1961b2fbea73c29d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="0adca-102">外部ユーザーのフェデレーションとリモート アクセスの確認</span><span class="sxs-lookup"><span data-stu-id="0adca-102">Verify federation and remote access for external users</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0adca-103">_**最終更新日:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="0adca-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="0adca-104">Lync Server 2013 エッジサーバーへのフェデレーションルートの移行が完了したら、いくつかの機能テストを実行して、フェデレーションが期待どおりに実行されることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0adca-104">After transitioning the federation route to the Lync Server 2013 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="0adca-105">外部ユーザーアクセスのテストには、次のいずれか、またはすべてを含む、組織がサポートしている各種類の外部ユーザーを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="0adca-105">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="0adca-106">外部ユーザーと外部アクセスの接続性をテストする</span><span class="sxs-lookup"><span data-stu-id="0adca-106">Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="0adca-107">少なくとも1つのフェデレーションドメイン、Lync Server 2013 上の内部ユーザー、および Lync Server 2010 上のユーザー。</span><span class="sxs-lookup"><span data-stu-id="0adca-107">Users from at least one federated domain, an internal user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="0adca-108">インスタントメッセージング (IM)、プレゼンス、音声/ビデオ (A/V)、デスクトップ共有をテストします。</span><span class="sxs-lookup"><span data-stu-id="0adca-108">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="0adca-109">組織がサポートしている各パブリック IM サービスプロバイダー (およびプロビジョニングが完了した) のユーザーが、Lync Server 2013 および Lync Server 2010 上のユーザーと通信します。</span><span class="sxs-lookup"><span data-stu-id="0adca-109">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Lync Server 2010.</span></span>

  - <span data-ttu-id="0adca-110">匿名ユーザーが会議に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0adca-110">Verify that anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="0adca-111">Lync server 2010 でホストされているユーザー (lync server 2013、および lync server 2010 上のユーザーとの間で Lync Server 2010 にログインします)。</span><span class="sxs-lookup"><span data-stu-id="0adca-111">A user hosted on Lync Server 2010 using remote user access (logging into Lync Server 2010 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="0adca-112">IM、プレゼンス、A/V、およびデスクトップ共有をテストします。</span><span class="sxs-lookup"><span data-stu-id="0adca-112">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="0adca-113">Lync server 2013 でホストされているユーザー (lync server 2013、および lync server 2010 上のユーザーとの間で Lync Server 2013 にログインします)。</span><span class="sxs-lookup"><span data-stu-id="0adca-113">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="0adca-114">IM、プレゼンス、A/V、およびデスクトップ共有をテストします。</span><span class="sxs-lookup"><span data-stu-id="0adca-114">Test IM, presence, A/V, and desktop sharing.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


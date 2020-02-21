---
title: 'Lync Server 2013: サポートされている Active Directory トポロジ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported Active Directory topologies
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398173(v=OCS.15)
ms:contentKeyID: 48183391
ms.date: 10/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9437df126889aefb8400b50d118d44dac12f285d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-active-directory-topologies-in-lync-server-2013"></a><span data-ttu-id="37750-102">Lync Server 2013 でサポートされている Active Directory トポロジ</span><span class="sxs-lookup"><span data-stu-id="37750-102">Supported Active Directory topologies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37750-103">_**トピックの最終更新日:** 2014-10-02_</span><span class="sxs-lookup"><span data-stu-id="37750-103">_**Topic Last Modified:** 2014-10-02_</span></span>

<span data-ttu-id="37750-104">Lync Server 2013 は、Microsoft Lync Server 2010 および Microsoft Office Communications Server 2007 R2 と同じ Active Directory ドメインサービストポロジをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="37750-104">Lync Server 2013 supports the same Active Directory Domain Services topologies as Microsoft Lync Server 2010 and Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="37750-105">次のトポロジがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="37750-105">The following topologies are supported:</span></span>

  - <span data-ttu-id="37750-106">単一のドメインを含む単一のフォレスト</span><span class="sxs-lookup"><span data-stu-id="37750-106">Single forest with single domain</span></span>

  - <span data-ttu-id="37750-107">単一のツリーと複数のドメインを含む単一のフォレスト</span><span class="sxs-lookup"><span data-stu-id="37750-107">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="37750-108">複数のツリーと不整合の名前空間を含む単一のフォレスト</span><span class="sxs-lookup"><span data-stu-id="37750-108">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="37750-109">中央フォレスト トポロジの複数のフォレスト</span><span class="sxs-lookup"><span data-stu-id="37750-109">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="37750-110">リソース フォレスト トポロジの複数のフォレスト</span><span class="sxs-lookup"><span data-stu-id="37750-110">Multiple forests in a resource forest topology</span></span>

  - <span data-ttu-id="37750-111">Exchange Online を使用する Lync リソースフォレストトポロジ内の複数のフォレスト</span><span class="sxs-lookup"><span data-stu-id="37750-111">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="37750-112">次の図に、このセクションで使用されるアイコンを示します。</span><span class="sxs-lookup"><span data-stu-id="37750-112">The following figure identifies the icons used in the illustrations in this section.</span></span>

<span data-ttu-id="37750-113">**トポロジに関する重要点**</span><span class="sxs-lookup"><span data-stu-id="37750-113">**Key to topology illustrations**</span></span>

<span data-ttu-id="37750-114">![トポロジに関する重要点](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "トポロジに関する重要点")</span><span class="sxs-lookup"><span data-stu-id="37750-114">![Key to topology illustrations](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Key to topology illustrations")</span></span>

<div>

## <a name="single-forest-single-domain"></a><span data-ttu-id="37750-115">単一フォレスト、単一ドメイン</span><span class="sxs-lookup"><span data-stu-id="37750-115">Single Forest, Single Domain</span></span>

<span data-ttu-id="37750-116">単一のドメインフォレストである Lync Server でサポートされている最も簡単な Active Directory トポロジは、一般的なトポロジです。</span><span class="sxs-lookup"><span data-stu-id="37750-116">The simplest Active Directory topology supported by Lync Server, a single domain forest, is a common topology.</span></span>

<span data-ttu-id="37750-117">次の図は、1つのドメインの Active Directory トポロジにおける Lync Server の展開を示しています。</span><span class="sxs-lookup"><span data-stu-id="37750-117">The following figure illustrates a Lync Server deployment in a single domain Active Directory topology.</span></span>

<span data-ttu-id="37750-118">**単一ドメイントポロジ**</span><span class="sxs-lookup"><span data-stu-id="37750-118">**Single domain topology**</span></span>

<span data-ttu-id="37750-119">![単一ドメイントポロジ](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "単一ドメイン トポロジ")</span><span class="sxs-lookup"><span data-stu-id="37750-119">![Single domain topology](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Single domain topology")</span></span>

</div>

<div>

## <a name="single-forest-multiple-domains"></a><span data-ttu-id="37750-120">単一フォレスト、複数ドメイン</span><span class="sxs-lookup"><span data-stu-id="37750-120">Single Forest, Multiple Domains</span></span>

<span data-ttu-id="37750-121">Lync Server でサポートされている他の Active Directory トポロジは、1つのフォレストで、1つのルートドメインと1つ以上の子ドメインから構成されます。</span><span class="sxs-lookup"><span data-stu-id="37750-121">Another Active Directory topology supported by Lync Server is a single forest that consists of a root domain and one or more child domains.</span></span> <span data-ttu-id="37750-122">この種類の Active Directory トポロジでは、ユーザーを作成するドメインは、Lync Server を展開するドメインとは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="37750-122">In this type of Active Directory topology, the domain where you create users can be different from the domain where you deploy Lync Server.</span></span> <span data-ttu-id="37750-123">ただし、フロントエンド プールを展開する場合、プール内のすべてのフロントエンド サーバーを 1 つのドメインに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37750-123">However, if you deploy a Front End pool, you must deploy all the Front End Servers in the pool within a single domain.</span></span> <span data-ttu-id="37750-124">Windows ユニバーサル管理者グループの Lync Server のサポートにより、ドメインを越えた管理が可能になります。</span><span class="sxs-lookup"><span data-stu-id="37750-124">Lync Server support for Windows universal administrator groups enables cross-domain administration.</span></span>

<span data-ttu-id="37750-125">次の図に、複数のドメインを持つ単一フォレストの展開を示します。</span><span class="sxs-lookup"><span data-stu-id="37750-125">The following figure illustrates a deployment in a single forest with multiple domains.</span></span> <span data-ttu-id="37750-126">この図では、ユーザーアカウントが所属しているドメインがユーザーアイコンに表示され、矢印は Lync Server プールが存在するドメインを指しています。</span><span class="sxs-lookup"><span data-stu-id="37750-126">In this figure, a user icon shows the domain where the user account is homed, and the arrow points to the domain where the Lync Server pool resides.</span></span> <span data-ttu-id="37750-127">ユーザー アカウントには次の種類があります。</span><span class="sxs-lookup"><span data-stu-id="37750-127">User accounts include the following:</span></span>

  - <span data-ttu-id="37750-128">Lync Server プールと同じドメイン内のユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="37750-128">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="37750-129">Lync Server プールとは別のドメインにあるユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="37750-129">User accounts in a different domain from the Lync Server pool</span></span>

  - <span data-ttu-id="37750-130">Lync Server プールを使用するドメインの子ドメイン内のユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="37750-130">User accounts in a child domain of the domain with the Lync Server pool</span></span>

<span data-ttu-id="37750-131">**複数のドメインを含む単一のフォレスト**</span><span class="sxs-lookup"><span data-stu-id="37750-131">**Single forest with multiple domains**</span></span>

<span data-ttu-id="37750-132">![複数のドメインを含む単一のフォレスト](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "複数のドメインを含む単一のフォレスト")</span><span class="sxs-lookup"><span data-stu-id="37750-132">![Single forest with multiple domains](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Single forest with multiple domains")</span></span>

</div>

<div>

## <a name="single-forest-multiple-trees"></a><span data-ttu-id="37750-133">単一フォレスト、複数ツリー</span><span class="sxs-lookup"><span data-stu-id="37750-133">Single Forest, Multiple Trees</span></span>

<span data-ttu-id="37750-134">複数ツリーのフォレスト トポロジは、独立したツリー構造を定義し、Active Directory 名前空間を分ける 2 つ以上のドメインで構成されます。</span><span class="sxs-lookup"><span data-stu-id="37750-134">A multiple-tree forest topology consists of two or more domains that define independent tree structures and separate Active Directory namespaces.</span></span>

<span data-ttu-id="37750-135">次の図に、複数のツリーがある単一のフォレストを示します。</span><span class="sxs-lookup"><span data-stu-id="37750-135">The following figure illustrates a single forest with multiple trees.</span></span> <span data-ttu-id="37750-136">この図では、ユーザーアイコンは、ユーザーアカウントが所属しているドメイン、同一または別のドメインに存在する Lync Server プールを示す破線、および異なるツリーに存在する Lync Server プールを指す破線を示しています。</span><span class="sxs-lookup"><span data-stu-id="37750-136">In this figure, a user icon shows the domain where the user account is homed, a solid line points to a Lync Server pool that resides in the same or a different domain, and a dashed line points to Lync Server pool that resides in a different tree.</span></span> <span data-ttu-id="37750-137">ユーザー アカウントには次の種類があります。</span><span class="sxs-lookup"><span data-stu-id="37750-137">User accounts include the following:</span></span>

  - <span data-ttu-id="37750-138">Lync Server プールと同じドメイン内のユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="37750-138">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="37750-139">別のドメインのユーザーアカウント (ただし、Lync Server プールと同じツリー)</span><span class="sxs-lookup"><span data-stu-id="37750-139">User accounts in a different domain from (but the same tree as) the Lync Server pool</span></span>

  - <span data-ttu-id="37750-140">Lync Server プールの異なるツリーにあるユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="37750-140">User accounts in a different tree from the Lync Server pool</span></span>

<span data-ttu-id="37750-141">**複数のツリーを含む単一のフォレスト**</span><span class="sxs-lookup"><span data-stu-id="37750-141">**Single forest with multiple trees**</span></span>

<span data-ttu-id="37750-142">![複数のツリーを含む単一のフォレスト](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "複数のツリーを含む単一のフォレスト")</span><span class="sxs-lookup"><span data-stu-id="37750-142">![Single forest with multiple trees](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Single forest with multiple trees")</span></span>

</div>

<div>

## <a name="multiple-forests-central-forest"></a><span data-ttu-id="37750-143">複数フォレスト、中央フォレスト</span><span class="sxs-lookup"><span data-stu-id="37750-143">Multiple Forests, Central Forest</span></span>

<span data-ttu-id="37750-144">Lync Server は、中央フォレストトポロジで構成されている複数のフォレストをサポートします。</span><span class="sxs-lookup"><span data-stu-id="37750-144">Lync Server supports multiple forests that are configured in a central forest topology.</span></span> <span data-ttu-id="37750-145">中央フォレストトポロジは、中央フォレストの連絡先オブジェクトを使用して、他のフォレスト内のユーザーを表します。</span><span class="sxs-lookup"><span data-stu-id="37750-145">Central forest topologies use contact objects in the central forest to represent users in the other forests.</span></span> <span data-ttu-id="37750-146">中央フォレストは、このフォレスト内のすべてのユーザーのユーザーアカウントもホストします。</span><span class="sxs-lookup"><span data-stu-id="37750-146">The central forest also hosts user accounts for any users in this forest.</span></span> <span data-ttu-id="37750-147">Microsoft Identity Integration Server (MIIS)、Microsoft Forefront Identity Manager (FIM) 2010、または Microsoft Identity cycle Manager (ILM) 2007 Feature Pack 1 (FP1) などのディレクトリ同期製品は、でのユーザーアカウントのライフサイクルを管理します。組織: フォレストの1つに新しいユーザーアカウントが作成されるか、またはユーザーアカウントがフォレストから削除されると、ディレクトリ同期製品によって、中央フォレスト内の対応する連絡先が同期されます。</span><span class="sxs-lookup"><span data-stu-id="37750-147">A directory synchronization product, such as Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts within the organization: When a new user account is created in one of the forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding contact in the central forest.</span></span>

<span data-ttu-id="37750-148">中央フォレストには、次に示す利点があります。</span><span class="sxs-lookup"><span data-stu-id="37750-148">A central forest has the following advantages:</span></span>

  - <span data-ttu-id="37750-149">Lync Server を実行しているサーバーは、単一フォレスト内で集中管理されます。</span><span class="sxs-lookup"><span data-stu-id="37750-149">Servers running Lync Server are centralized within a single forest.</span></span>

  - <span data-ttu-id="37750-150">ユーザーは、任意のフォレストのユーザーを検索して通信できます。</span><span class="sxs-lookup"><span data-stu-id="37750-150">Users can search for and communicate with other users in any forest.</span></span>

  - <span data-ttu-id="37750-151">ユーザーは、任意のフォレストの他のユーザーのプレゼンスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="37750-151">Users can view presence of other users in any forest.</span></span>

  - <span data-ttu-id="37750-152">ユーザー アカウントが作成または削除されると、ディレクトリ同期製品によって、中央フォレストの連絡先オブジェクトが自動的に追加および削除されます。</span><span class="sxs-lookup"><span data-stu-id="37750-152">The directory synchronization product automates the addition and deletion of contact objects in the central forest as user accounts are created or removed.</span></span>

<span data-ttu-id="37750-153">次の図に、中央フォレスト トポロジを示します。</span><span class="sxs-lookup"><span data-stu-id="37750-153">The following figure illustrates a central forest topology.</span></span> <span data-ttu-id="37750-154">この図では、中央フォレストにある Lync Server をホストするドメインと、別のフォレストにある各ユーザー専用ドメインとの間に双間の信頼関係があります。</span><span class="sxs-lookup"><span data-stu-id="37750-154">In this figure, there are two-way trust relationships between the domain that hosts Lync Server, which is in the central forest, and each user-only domain, which is in a separate forest.</span></span> <span data-ttu-id="37750-155">別のユーザー フォレストのスキーマは、拡張する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="37750-155">The schema in the separate user forests does not need to be extended.</span></span>

<span data-ttu-id="37750-156">**中央フォレスト トポロジ**</span><span class="sxs-lookup"><span data-stu-id="37750-156">**Central forest topology**</span></span>

<span data-ttu-id="37750-157">![中央フォレスト トポロジ](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "中央フォレスト トポロジ")</span><span class="sxs-lookup"><span data-stu-id="37750-157">![Central forest topology](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Central forest topology")</span></span>

</div>

<div>

## <a name="multiple-forests-resource-forest"></a><span data-ttu-id="37750-158">複数フォレスト、リソース フォレスト</span><span class="sxs-lookup"><span data-stu-id="37750-158">Multiple Forests, Resource Forest</span></span>

<span data-ttu-id="37750-159">リソースフォレストのトポロジでは、1つのフォレストは Microsoft Exchange Server および Lync Server などのサーバーアプリケーションの実行専用になります。</span><span class="sxs-lookup"><span data-stu-id="37750-159">In a resource forest topology, one forest is dedicated to running server applications, such as Microsoft Exchange Server and Lync Server.</span></span> <span data-ttu-id="37750-160">リソース フォレストは、サーバー アプリケーションとアクティブ ユーザー オブジェクトの同期表現をホストしますが、ログオン可能なユーザー アカウントはホストしません。</span><span class="sxs-lookup"><span data-stu-id="37750-160">The resource forest hosts the server applications and a synchronized representation of the active user object, but it does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="37750-161">リソース フォレストは、ユーザー オブジェクトが存在する他のフォレストのための共有サービス環境として動作します。</span><span class="sxs-lookup"><span data-stu-id="37750-161">The resource forest acts as a shared services environment for the other forests where user objects reside.</span></span> <span data-ttu-id="37750-162">ユーザー フォレストは、リソース フォレストとの間にフォレスト レベルの信頼関係を持ちます。</span><span class="sxs-lookup"><span data-stu-id="37750-162">The user forests have a forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="37750-163">この種類のトポロジで Lync Server を展開する場合は、ユーザーフォレスト内のすべてのユーザーアカウントについて、リソースフォレスト内に無効なユーザーオブジェクトを1つ作成します。</span><span class="sxs-lookup"><span data-stu-id="37750-163">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="37750-164">Microsoft Exchange がリソースフォレストに既に展開されている場合は、無効になっているユーザーアカウントが既に存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="37750-164">If Microsoft Exchange is already deployed in the resource forest, the disabled user accounts might already exist.</span></span> <span data-ttu-id="37750-165">MIIS、Microsoft Forefront Identity Manager (FIM) 2010、または Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1) などのディレクトリ同期製品は、ユーザー アカウントのライフ サイクルを管理します。</span><span class="sxs-lookup"><span data-stu-id="37750-165">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="37750-166">いずれかのユーザー フォレストで新しいユーザー アカウントが作成されるか、フォレストからユーザー アカウントが削除されると、ディレクトリ同期製品がリソース フォレスト内の対応するユーザー表現を同期します。</span><span class="sxs-lookup"><span data-stu-id="37750-166">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span>

<span data-ttu-id="37750-p108">このトポロジは、組織のサービスに対して、複数のフォレストを管理する共有インフラストラクチャを提供するためや、Active Directory オブジェクトの管理を他の管理から切り離すために使用できます。セキュリティ上の理由から Active Directory の管理を分離する必要がある会社は、多くの場合、このトポロジを選択します。</span><span class="sxs-lookup"><span data-stu-id="37750-p108">This topology can be used to provide a shared infrastructure for services in organizations that manage multiple forests or to separate the administration of Active Directory objects from other administration. Companies that need to isolate Active Directory administration for security reasons often choose this topology.</span></span>

<span data-ttu-id="37750-169">このトポロジには、Active Directory スキーマの拡張の必要性が単一のフォレスト (リソース フォレスト) に限定されるという利点があります。</span><span class="sxs-lookup"><span data-stu-id="37750-169">This topology provides the benefit of limiting the need to extend the Active Directory schema to a single forest (that is, the resource forest).</span></span>

<span data-ttu-id="37750-170">次の図に、リソース フォレスト トポロジを示します。</span><span class="sxs-lookup"><span data-stu-id="37750-170">The following diagram illustrates a resource forest topology.</span></span>

<span data-ttu-id="37750-171">**リソース フォレスト トポロジ**</span><span class="sxs-lookup"><span data-stu-id="37750-171">**Resource forest topology**</span></span>

<span data-ttu-id="37750-172">![Active Directory リソースフォレストトポロジ](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory リソースフォレストトポロジ")</span><span class="sxs-lookup"><span data-stu-id="37750-172">![Active Directory Resource Forest Topology](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory Resource Forest Topology")</span></span>

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a><span data-ttu-id="37750-173">Exchange Online を使用する Lync リソースフォレストトポロジ内の複数のフォレスト</span><span class="sxs-lookup"><span data-stu-id="37750-173">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="37750-174">このトポロジでは、1つ以上のフォレストが社内に配置されており、Active Directory のユーザーアカウントをホストするために専用になっています。</span><span class="sxs-lookup"><span data-stu-id="37750-174">In this topology, one or more forests are located on-premises and are dedicated to hosting Active Directory user accounts.</span></span> <span data-ttu-id="37750-175">リソースフォレストはオフプレミスにあり、サードパーティのホスティングプロバイダーによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="37750-175">The resource forest is located off-premises and is maintained by a third-party hosting provider.</span></span> <span data-ttu-id="37750-176">リソースフォレストには、Lync Server の展開と、オンプレミスのユーザーアカウントフォレストからのユーザーアカウントの同期レプリケーションのみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="37750-176">The resource forest contains only the Lync Server deployment and a synchronized replication of the user accounts from the on-premises user accounts forest(s).</span></span> <span data-ttu-id="37750-177">ログオンが有効なユーザーアカウントは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="37750-177">It does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="37750-178">Exchange は、exchange Online (ハイブリッド) と共に統合されたオンプレミスのユーザーアカウントフォレストに展開されるか、または社内ユーザーアカウントの電子メールサービスが Exchange Online によってのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="37750-178">Exchange is deployed either in the on-premises user account forest(s) integrated along with Exchange Online (Hybrid), or email services for the on-premises user accounts are provided exclusively by Exchange Online.</span></span>

<span data-ttu-id="37750-179">リソースフォレストは、ユーザーオブジェクトが存在するオンプレミスの Active Directory フォレストの共有サービス環境として機能します。</span><span class="sxs-lookup"><span data-stu-id="37750-179">The resource forest acts as a shared services environment for the on-premises Active Directory forest(s) where user objects reside.</span></span> <span data-ttu-id="37750-180">ユーザーアカウントのフォレストには、1つの方法でリソースフォレストとのフォレストレベルの信頼関係があります。</span><span class="sxs-lookup"><span data-stu-id="37750-180">The user account forest(s) have a one way forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="37750-181">この種類のトポロジで Lync Server を展開する場合は、ユーザーフォレスト内のすべてのユーザーアカウントについて、リソースフォレスト内に無効なユーザーオブジェクトを1つ作成します。</span><span class="sxs-lookup"><span data-stu-id="37750-181">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="37750-182">MIIS、Microsoft Forefront Identity Manager (FIM) 2010、または Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1) などのディレクトリ同期製品は、ユーザー アカウントのライフ サイクルを管理します。</span><span class="sxs-lookup"><span data-stu-id="37750-182">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="37750-183">いずれかのユーザー フォレストで新しいユーザー アカウントが作成されるか、フォレストからユーザー アカウントが削除されると、ディレクトリ同期製品がリソース フォレスト内の対応するユーザー表現を同期します。</span><span class="sxs-lookup"><span data-stu-id="37750-183">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span> <span data-ttu-id="37750-184">複数フォレスト展開の構成の詳細については、「[複数フォレストアーキテクチャでの lync の展開 (Exchange ハイブリッドを使用したパートナーホスト](https://go.microsoft.com/fwlink/p/?linkid=513216)された lync)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37750-184">For more information about configuring a multi-forest deployment, see [Deploying Lync in a Multi-Forest Architecture (Partner Hosted Lync with Exchange Hybrid)](https://go.microsoft.com/fwlink/p/?linkid=513216).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


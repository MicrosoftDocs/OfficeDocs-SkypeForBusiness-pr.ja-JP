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
ms.openlocfilehash: 3e4aca368f6ea7d5b31a1cfe74273dfbd42a6594
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764363"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-active-directory-topologies-in-lync-server-2013"></a><span data-ttu-id="7af68-102">Lync Server 2013 でサポートされている Active Directory トポロジ</span><span class="sxs-lookup"><span data-stu-id="7af68-102">Supported Active Directory topologies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7af68-103">_**最終更新日:** 2014-10-02_</span><span class="sxs-lookup"><span data-stu-id="7af68-103">_**Topic Last Modified:** 2014-10-02_</span></span>

<span data-ttu-id="7af68-104">Lync Server 2013 は、Microsoft Lync Server 2010 と Microsoft Office Communications Server 2007 R2 と同じ Active Directory ドメインサービストポロジをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7af68-104">Lync Server 2013 supports the same Active Directory Domain Services topologies as Microsoft Lync Server 2010 and Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="7af68-105">次のトポロジがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7af68-105">The following topologies are supported:</span></span>

  - <span data-ttu-id="7af68-106">単一のドメインを含む単一のフォレスト</span><span class="sxs-lookup"><span data-stu-id="7af68-106">Single forest with single domain</span></span>

  - <span data-ttu-id="7af68-107">単一のツリーと複数のドメインを含む単一のフォレスト</span><span class="sxs-lookup"><span data-stu-id="7af68-107">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="7af68-108">複数のツリーと不整合の名前空間を含む単一のフォレスト</span><span class="sxs-lookup"><span data-stu-id="7af68-108">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="7af68-109">中央フォレスト トポロジの複数のフォレスト</span><span class="sxs-lookup"><span data-stu-id="7af68-109">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="7af68-110">リソース フォレスト トポロジの複数のフォレスト</span><span class="sxs-lookup"><span data-stu-id="7af68-110">Multiple forests in a resource forest topology</span></span>

  - <span data-ttu-id="7af68-111">Exchange Online を使用した Lync リソースフォレストトポロジの複数フォレスト</span><span class="sxs-lookup"><span data-stu-id="7af68-111">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="7af68-112">次の図は、このセクションの図で使われているアイコンを示しています。</span><span class="sxs-lookup"><span data-stu-id="7af68-112">The following figure identifies the icons used in the illustrations in this section.</span></span>

<span data-ttu-id="7af68-113">**トポロジ図の重要な説明**</span><span class="sxs-lookup"><span data-stu-id="7af68-113">**Key to topology illustrations**</span></span>

<span data-ttu-id="7af68-114">![トポロジ図の重要な説明](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "トポロジ図の重要な説明")</span><span class="sxs-lookup"><span data-stu-id="7af68-114">![Key to topology illustrations](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Key to topology illustrations")</span></span>

<div>

## <a name="single-forest-single-domain"></a><span data-ttu-id="7af68-115">1つのフォレスト、単一ドメイン</span><span class="sxs-lookup"><span data-stu-id="7af68-115">Single Forest, Single Domain</span></span>

<span data-ttu-id="7af68-116">Lync Server (単一ドメインフォレスト) でサポートされる最も簡単な Active Directory トポロジは、一般的なトポロジです。</span><span class="sxs-lookup"><span data-stu-id="7af68-116">The simplest Active Directory topology supported by Lync Server, a single domain forest, is a common topology.</span></span>

<span data-ttu-id="7af68-117">次の図は、1つのドメインの Active Directory トポロジでの Lync Server の展開を示しています。</span><span class="sxs-lookup"><span data-stu-id="7af68-117">The following figure illustrates a Lync Server deployment in a single domain Active Directory topology.</span></span>

<span data-ttu-id="7af68-118">**単一ドメイン トポロジ**</span><span class="sxs-lookup"><span data-stu-id="7af68-118">**Single domain topology**</span></span>

<span data-ttu-id="7af68-119">![単一ドメイン トポロジ](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "単一ドメイン トポロジ")</span><span class="sxs-lookup"><span data-stu-id="7af68-119">![Single domain topology](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Single domain topology")</span></span>

</div>

<div>

## <a name="single-forest-multiple-domains"></a><span data-ttu-id="7af68-120">1つのフォレスト、複数のドメイン</span><span class="sxs-lookup"><span data-stu-id="7af68-120">Single Forest, Multiple Domains</span></span>

<span data-ttu-id="7af68-121">Lync Server でサポートされるもう1つの Active Directory トポロジは、ルートドメインと1つ以上の子ドメインで構成される単一フォレストです。</span><span class="sxs-lookup"><span data-stu-id="7af68-121">Another Active Directory topology supported by Lync Server is a single forest that consists of a root domain and one or more child domains.</span></span> <span data-ttu-id="7af68-122">この種類の Active Directory トポロジでは、ユーザーを作成するドメインは、Lync Server を展開するドメインとは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7af68-122">In this type of Active Directory topology, the domain where you create users can be different from the domain where you deploy Lync Server.</span></span> <span data-ttu-id="7af68-123">ただし、フロントエンドプールを展開する場合は、1つのドメイン内のプールにすべてのフロントエンドサーバーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7af68-123">However, if you deploy a Front End pool, you must deploy all the Front End Servers in the pool within a single domain.</span></span> <span data-ttu-id="7af68-124">Windows ユニバーサル管理者グループの Lync Server のサポートにより、ドメイン間管理が可能になります。</span><span class="sxs-lookup"><span data-stu-id="7af68-124">Lync Server support for Windows universal administrator groups enables cross-domain administration.</span></span>

<span data-ttu-id="7af68-125">次の図は、複数のドメインを持つ単一フォレストでの展開を示しています。</span><span class="sxs-lookup"><span data-stu-id="7af68-125">The following figure illustrates a deployment in a single forest with multiple domains.</span></span> <span data-ttu-id="7af68-126">この図では、ユーザーのアイコンには、ユーザーアカウントが所属しているドメインが表示され、矢印は Lync Server プールが存在するドメインを指しています。</span><span class="sxs-lookup"><span data-stu-id="7af68-126">In this figure, a user icon shows the domain where the user account is homed, and the arrow points to the domain where the Lync Server pool resides.</span></span> <span data-ttu-id="7af68-127">ユーザーアカウントには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7af68-127">User accounts include the following:</span></span>

  - <span data-ttu-id="7af68-128">Lync Server プールと同じドメイン内のユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="7af68-128">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="7af68-129">Lync Server プールとは異なるドメイン内のユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="7af68-129">User accounts in a different domain from the Lync Server pool</span></span>

  - <span data-ttu-id="7af68-130">Lync Server プールを持つドメインの子ドメインのユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="7af68-130">User accounts in a child domain of the domain with the Lync Server pool</span></span>

<span data-ttu-id="7af68-131">**複数のドメインを含む単一フォレスト**</span><span class="sxs-lookup"><span data-stu-id="7af68-131">**Single forest with multiple domains**</span></span>

<span data-ttu-id="7af68-132">![複数のドメインを含む単一フォレスト](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "複数のドメインを含む単一フォレスト")</span><span class="sxs-lookup"><span data-stu-id="7af68-132">![Single forest with multiple domains](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Single forest with multiple domains")</span></span>

</div>

<div>

## <a name="single-forest-multiple-trees"></a><span data-ttu-id="7af68-133">1つのフォレスト、複数のツリー</span><span class="sxs-lookup"><span data-stu-id="7af68-133">Single Forest, Multiple Trees</span></span>

<span data-ttu-id="7af68-134">複数ツリーのフォレストトポロジは、独立したツリー構造と個別の Active Directory 名前空間を定義する2つ以上のドメインで構成されます。</span><span class="sxs-lookup"><span data-stu-id="7af68-134">A multiple-tree forest topology consists of two or more domains that define independent tree structures and separate Active Directory namespaces.</span></span>

<span data-ttu-id="7af68-135">次の図は、複数のツリーを持つ単一フォレストを示しています。</span><span class="sxs-lookup"><span data-stu-id="7af68-135">The following figure illustrates a single forest with multiple trees.</span></span> <span data-ttu-id="7af68-136">この図では、ユーザーのアイコンには、ユーザーアカウントが所属しているドメイン、同一または別のドメインに存在する Lync Server プールの実線が表示されていて、別のツリーに存在する Lync Server プールを示す破線が表示されています。</span><span class="sxs-lookup"><span data-stu-id="7af68-136">In this figure, a user icon shows the domain where the user account is homed, a solid line points to a Lync Server pool that resides in the same or a different domain, and a dashed line points to Lync Server pool that resides in a different tree.</span></span> <span data-ttu-id="7af68-137">ユーザーアカウントには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7af68-137">User accounts include the following:</span></span>

  - <span data-ttu-id="7af68-138">Lync Server プールと同じドメイン内のユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="7af68-138">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="7af68-139">別のドメインのユーザーアカウント (ただし、Lync サーバープールと同じツリー)</span><span class="sxs-lookup"><span data-stu-id="7af68-139">User accounts in a different domain from (but the same tree as) the Lync Server pool</span></span>

  - <span data-ttu-id="7af68-140">Lync Server プールの異なるツリー内のユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="7af68-140">User accounts in a different tree from the Lync Server pool</span></span>

<span data-ttu-id="7af68-141">**複数のツリーを持つ単一フォレスト**</span><span class="sxs-lookup"><span data-stu-id="7af68-141">**Single forest with multiple trees**</span></span>

<span data-ttu-id="7af68-142">![複数のツリーを持つ単一フォレスト](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "複数のツリーを持つ単一フォレスト")</span><span class="sxs-lookup"><span data-stu-id="7af68-142">![Single forest with multiple trees](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Single forest with multiple trees")</span></span>

</div>

<div>

## <a name="multiple-forests-central-forest"></a><span data-ttu-id="7af68-143">複数フォレスト、中央フォレスト</span><span class="sxs-lookup"><span data-stu-id="7af68-143">Multiple Forests, Central Forest</span></span>

<span data-ttu-id="7af68-144">Lync Server は、中央フォレストトポロジで構成されている複数のフォレストをサポートします。</span><span class="sxs-lookup"><span data-stu-id="7af68-144">Lync Server supports multiple forests that are configured in a central forest topology.</span></span> <span data-ttu-id="7af68-145">中央フォレストトポロジは、中央フォレストの連絡先オブジェクトを使って、他のフォレストのユーザーを表します。</span><span class="sxs-lookup"><span data-stu-id="7af68-145">Central forest topologies use contact objects in the central forest to represent users in the other forests.</span></span> <span data-ttu-id="7af68-146">中央のフォレストでも、このフォレスト内のユーザーのユーザーアカウントがホストされます。</span><span class="sxs-lookup"><span data-stu-id="7af68-146">The central forest also hosts user accounts for any users in this forest.</span></span> <span data-ttu-id="7af68-147">Microsoft Identity Integration Server (MIIS)、Microsoft Forefront Identity Manager (FIM) 2010、Microsoft Identity cycle manager (ILM) 2007 Feature Pack 1 (FP1) などのディレクトリ同期製品では、ユーザーアカウントのライフサイクルを管理します。組織: フォレストのいずれかで新しいユーザーアカウントを作成するか、またはユーザーアカウントがフォレストから削除されると、ディレクトリ同期の製品によって中央フォレストの対応する連絡先が同期されます。</span><span class="sxs-lookup"><span data-stu-id="7af68-147">A directory synchronization product, such as Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts within the organization: When a new user account is created in one of the forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding contact in the central forest.</span></span>

<span data-ttu-id="7af68-148">中央フォレストには、次のような利点があります。</span><span class="sxs-lookup"><span data-stu-id="7af68-148">A central forest has the following advantages:</span></span>

  - <span data-ttu-id="7af68-149">Lync Server を実行しているサーバーは、1つのフォレスト内で一元管理されます。</span><span class="sxs-lookup"><span data-stu-id="7af68-149">Servers running Lync Server are centralized within a single forest.</span></span>

  - <span data-ttu-id="7af68-150">ユーザーは、任意のフォレストの他のユーザーを検索して通信することができます。</span><span class="sxs-lookup"><span data-stu-id="7af68-150">Users can search for and communicate with other users in any forest.</span></span>

  - <span data-ttu-id="7af68-151">ユーザーは、任意のフォレストの他のユーザーのプレゼンスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="7af68-151">Users can view presence of other users in any forest.</span></span>

  - <span data-ttu-id="7af68-152">ディレクトリ同期製品を利用すると、ユーザーアカウントが作成または削除されたときに、中央フォレストの連絡先オブジェクトの追加と削除が自動化されます。</span><span class="sxs-lookup"><span data-stu-id="7af68-152">The directory synchronization product automates the addition and deletion of contact objects in the central forest as user accounts are created or removed.</span></span>

<span data-ttu-id="7af68-153">次の図は、中央のフォレストトポロジを示しています。</span><span class="sxs-lookup"><span data-stu-id="7af68-153">The following figure illustrates a central forest topology.</span></span> <span data-ttu-id="7af68-154">この図では、Lync Server をホストしているドメイン (中央のフォレスト) と、別々のフォレストにあるユーザーのみのドメインとの間に双方向の信頼関係があります。</span><span class="sxs-lookup"><span data-stu-id="7af68-154">In this figure, there are two-way trust relationships between the domain that hosts Lync Server, which is in the central forest, and each user-only domain, which is in a separate forest.</span></span> <span data-ttu-id="7af68-155">個別のユーザーのフォレストのスキーマを拡張する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7af68-155">The schema in the separate user forests does not need to be extended.</span></span>

<span data-ttu-id="7af68-156">**中央フォレストトポロジ**</span><span class="sxs-lookup"><span data-stu-id="7af68-156">**Central forest topology**</span></span>

<span data-ttu-id="7af68-157">![中央フォレストトポロジ](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "中央フォレストトポロジ")</span><span class="sxs-lookup"><span data-stu-id="7af68-157">![Central forest topology](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Central forest topology")</span></span>

</div>

<div>

## <a name="multiple-forests-resource-forest"></a><span data-ttu-id="7af68-158">複数のフォレスト、リソースフォレスト</span><span class="sxs-lookup"><span data-stu-id="7af68-158">Multiple Forests, Resource Forest</span></span>

<span data-ttu-id="7af68-159">リソースフォレストトポロジでは、1つのフォレストが、Microsoft Exchange Server や Lync Server などのサーバーアプリケーションの実行専用になります。</span><span class="sxs-lookup"><span data-stu-id="7af68-159">In a resource forest topology, one forest is dedicated to running server applications, such as Microsoft Exchange Server and Lync Server.</span></span> <span data-ttu-id="7af68-160">リソースフォレストは、サーバーアプリケーションをホストしており、アクティブなユーザーオブジェクトの同期表現をホストしていますが、ログオン可能なユーザーアカウントは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="7af68-160">The resource forest hosts the server applications and a synchronized representation of the active user object, but it does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="7af68-161">リソースフォレストは、ユーザーオブジェクトが存在する他のフォレストの共有サービス環境として機能します。</span><span class="sxs-lookup"><span data-stu-id="7af68-161">The resource forest acts as a shared services environment for the other forests where user objects reside.</span></span> <span data-ttu-id="7af68-162">ユーザーフォレストには、リソースフォレストとのフォレストレベルの信頼関係があります。</span><span class="sxs-lookup"><span data-stu-id="7af68-162">The user forests have a forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="7af68-163">この種類のトポロジで Lync Server を展開する場合は、ユーザーのフォレスト内のすべてのユーザーアカウントについて、リソースフォレスト内の無効なユーザーオブジェクトを1つ作成します。</span><span class="sxs-lookup"><span data-stu-id="7af68-163">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="7af68-164">Microsoft Exchange が既にリソースフォレストに展開されている場合は、無効になっているユーザーアカウントが既に存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7af68-164">If Microsoft Exchange is already deployed in the resource forest, the disabled user accounts might already exist.</span></span> <span data-ttu-id="7af68-165">MIIS、Microsoft Forefront Identity Manager (FIM) 2010、Microsoft Identity cycle Manager (ILM) 2007 Feature Pack 1 (FP1) などのディレクトリ同期製品は、ユーザーアカウントのライフサイクルを管理します。</span><span class="sxs-lookup"><span data-stu-id="7af68-165">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="7af68-166">いずれかのユーザーフォレストで新しいユーザーアカウントを作成するか、またはユーザーアカウントがフォレストから削除されると、ディレクトリ同期の製品によって、リソースフォレスト内の対応するユーザー表現が同期されます。</span><span class="sxs-lookup"><span data-stu-id="7af68-166">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span>

<span data-ttu-id="7af68-167">このトポロジは、複数のフォレストを管理する組織、または Active Directory オブジェクトの管理を他の管理から分離するために、サービスの共有インフラストラクチャを提供するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="7af68-167">This topology can be used to provide a shared infrastructure for services in organizations that manage multiple forests or to separate the administration of Active Directory objects from other administration.</span></span> <span data-ttu-id="7af68-168">セキュリティ上の理由で Active Directory 管理を分離する必要がある企業は、多くの場合、このトポロジを選択します。</span><span class="sxs-lookup"><span data-stu-id="7af68-168">Companies that need to isolate Active Directory administration for security reasons often choose this topology.</span></span>

<span data-ttu-id="7af68-169">このトポロジでは、Active Directory スキーマを1つのフォレスト (つまりリソースフォレスト) に拡張する必要があるかを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="7af68-169">This topology provides the benefit of limiting the need to extend the Active Directory schema to a single forest (that is, the resource forest).</span></span>

<span data-ttu-id="7af68-170">次の図は、リソースフォレストのトポロジを示しています。</span><span class="sxs-lookup"><span data-stu-id="7af68-170">The following diagram illustrates a resource forest topology.</span></span>

<span data-ttu-id="7af68-171">**リソースフォレストのトポロジ**</span><span class="sxs-lookup"><span data-stu-id="7af68-171">**Resource forest topology**</span></span>

<span data-ttu-id="7af68-172">![Active Directory リソース フォレスト トポロジ](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory リソース フォレスト トポロジ")</span><span class="sxs-lookup"><span data-stu-id="7af68-172">![Active Directory Resource Forest Topology](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory Resource Forest Topology")</span></span>

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a><span data-ttu-id="7af68-173">Exchange Online を使用した Lync リソースフォレストトポロジの複数フォレスト</span><span class="sxs-lookup"><span data-stu-id="7af68-173">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="7af68-174">このトポロジでは、1つ以上のフォレストがオンプレミスであり、Active Directory ユーザーアカウントのホスト専用になっています。</span><span class="sxs-lookup"><span data-stu-id="7af68-174">In this topology, one or more forests are located on-premises and are dedicated to hosting Active Directory user accounts.</span></span> <span data-ttu-id="7af68-175">リソースフォレストはオフプレミスであり、サードパーティのホスティングプロバイダーによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="7af68-175">The resource forest is located off-premises and is maintained by a third-party hosting provider.</span></span> <span data-ttu-id="7af68-176">リソースフォレストには、Lync Server の展開と、オンプレミスのユーザーアカウントのフォレストからのユーザーアカウントの同期されたレプリケーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7af68-176">The resource forest contains only the Lync Server deployment and a synchronized replication of the user accounts from the on-premises user accounts forest(s).</span></span> <span data-ttu-id="7af68-177">ログオン可能なユーザーアカウントが含まれていません。</span><span class="sxs-lookup"><span data-stu-id="7af68-177">It does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="7af68-178">Exchange は Exchange Online (ハイブリッド) と共に統合されたオンプレミスのユーザーアカウントフォレストに展開されます。または、オンプレミスのユーザーアカウントのメールサービスは、Exchange Online によってのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="7af68-178">Exchange is deployed either in the on-premises user account forest(s) integrated along with Exchange Online (Hybrid), or email services for the on-premises user accounts are provided exclusively by Exchange Online.</span></span>

<span data-ttu-id="7af68-179">リソースフォレストは、ユーザーオブジェクトが存在するオンプレミスの Active Directory フォレストの共有サービス環境として機能します。</span><span class="sxs-lookup"><span data-stu-id="7af68-179">The resource forest acts as a shared services environment for the on-premises Active Directory forest(s) where user objects reside.</span></span> <span data-ttu-id="7af68-180">ユーザーアカウントフォレストには、リソースフォレストとの一方向のフォレストレベルの信頼関係があります。</span><span class="sxs-lookup"><span data-stu-id="7af68-180">The user account forest(s) have a one way forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="7af68-181">この種類のトポロジで Lync Server を展開する場合は、ユーザーのフォレスト内のすべてのユーザーアカウントについて、リソースフォレスト内の無効なユーザーオブジェクトを1つ作成します。</span><span class="sxs-lookup"><span data-stu-id="7af68-181">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="7af68-182">MIIS、Microsoft Forefront Identity Manager (FIM) 2010、Microsoft Identity cycle Manager (ILM) 2007 Feature Pack 1 (FP1) などのディレクトリ同期製品は、ユーザーアカウントのライフサイクルを管理します。</span><span class="sxs-lookup"><span data-stu-id="7af68-182">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="7af68-183">いずれかのユーザーフォレストで新しいユーザーアカウントを作成するか、またはユーザーアカウントがフォレストから削除されると、ディレクトリ同期の製品によって、リソースフォレスト内の対応するユーザー表現が同期されます。</span><span class="sxs-lookup"><span data-stu-id="7af68-183">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span> <span data-ttu-id="7af68-184">複数フォレスト展開の構成の詳細については、「[マルチフォレストアーキテクチャでの lync の展開 (Exchange ハイブリッドを使用した Lync ホスト型 lync)](http://go.microsoft.com/fwlink/p/?linkid=513216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7af68-184">For more information about configuring a multi-forest deployment, see [Deploying Lync in a Multi-Forest Architecture (Partner Hosted Lync with Exchange Hybrid)](http://go.microsoft.com/fwlink/p/?linkid=513216).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


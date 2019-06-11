---
title: 'Lync Server 2013: Active Directory ドメイン サービスの準備の概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26636846ce7b985a33af3175d51798c4c12c5ea7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a><span data-ttu-id="69d9d-102">Lync Server 2013 の Active Directory ドメイン サービスの準備の概要</span><span class="sxs-lookup"><span data-stu-id="69d9d-102">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69d9d-103">_**最終更新日:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="69d9d-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="69d9d-104">Lync Server 2013 の展開用に Active Directory ドメインサービスを準備するには、次の3つの手順を特定の順序で行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d9d-104">To prepare Active Directory Domain Services for your Lync Server 2013 deployment, you must perform three steps in a specific sequence.</span></span>

<span data-ttu-id="69d9d-105">次の表では、Lync Server 用の AD DS を準備するために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="69d9d-105">The following table describes the steps required to prepare AD DS for Lync Server.</span></span>

### <a name="active-directory-preparation-steps"></a><span data-ttu-id="69d9d-106">Active Directory の準備手順</span><span class="sxs-lookup"><span data-stu-id="69d9d-106">Active Directory Preparation Steps</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="69d9d-107">ステップ</span><span class="sxs-lookup"><span data-stu-id="69d9d-107">Step</span></span></th>
<th><span data-ttu-id="69d9d-108">説明</span><span class="sxs-lookup"><span data-stu-id="69d9d-108">Description</span></span></th>
<th><span data-ttu-id="69d9d-109">実行場所</span><span class="sxs-lookup"><span data-stu-id="69d9d-109">Where run</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><span data-ttu-id="69d9d-110"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Lync Server 2013 での Active Directory スキーマの準備</a></span><span class="sxs-lookup"><span data-stu-id="69d9d-110"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Preparing the Active Directory schema in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69d9d-111">Lync Server によって使用される新しいクラスと属性を追加して、Active Directory スキーマを拡張します。</span><span class="sxs-lookup"><span data-stu-id="69d9d-111">Extends the Active Directory schema by adding new classes and attributes that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="69d9d-112">Lync Server が展開されている展開で、フォレストごとに1回実行します。</span><span class="sxs-lookup"><span data-stu-id="69d9d-112">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="69d9d-113">Lync Server を展開する各フォレストのルートドメインのスキーママスターに対して。</span><span class="sxs-lookup"><span data-stu-id="69d9d-113">Against the schema master in the root domain of each forest where Lync Server will be deployed.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="69d9d-114">スキーママスターに対してアクセス許可を持っているが、ルートドメインで Schema Admins グループのメンバーであり、かつスキーママスターの Enterprise Admins グループのメンバーである必要がある場合は、ルートドメインでこの手順を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="69d9d-114">You do not need to run this step in the root domain if you have permissions on the schema master, but you must be a member of the Schema Admins group in the root domain and a member of the Enterprise Admins group on the schema master.</span></span> <span data-ttu-id="69d9d-115">リソースフォレストのトポロジでは、この手順は、ユーザーのフォレスト内ではなく、リソースフォレストでのみ実行します。</span><span class="sxs-lookup"><span data-stu-id="69d9d-115">In a resource forest topology, run this step only in the resource forest, not in any user forests.</span></span> <span data-ttu-id="69d9d-116">中央フォレストトポロジでは、この手順は、ユーザーのフォレストではなく中央のフォレストでのみ実行します。</span><span class="sxs-lookup"><span data-stu-id="69d9d-116">In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><span data-ttu-id="69d9d-117"><a href="lync-server-2013-preparing-the-forest.md">Lync Server 2013 でのフォレストの準備</a></span><span class="sxs-lookup"><span data-stu-id="69d9d-117"><a href="lync-server-2013-preparing-the-forest.md">Preparing the forest for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69d9d-118">Lync Server で使用されるグローバル設定とユニバーサルグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="69d9d-118">Creates global settings and universal groups that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="69d9d-119">Lync Server が展開されている展開で、フォレストごとに1回実行します。</span><span class="sxs-lookup"><span data-stu-id="69d9d-119">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="69d9d-120">Lync Server を展開する各フォレストのルートドメイン。</span><span class="sxs-lookup"><span data-stu-id="69d9d-120">In the root domain of each forest where Lync Server will be deployed.</span></span> <span data-ttu-id="69d9d-121">この手順を実行するには、Enterprise Admins グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d9d-121">To run this step, you must be a member of the Enterprise Admins group.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="69d9d-122">リソースフォレストのトポロジでは、この手順は、ユーザーのフォレスト内ではなく、リソースフォレストでのみ実行します。</span><span class="sxs-lookup"><span data-stu-id="69d9d-122">In a resource forest topology, run this step only in the resource forest, not in any user forests.</span></span> <span data-ttu-id="69d9d-123">中央フォレストトポロジでは、この手順は、ユーザーのフォレストではなく中央のフォレストでのみ実行します。</span><span class="sxs-lookup"><span data-stu-id="69d9d-123">In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><span data-ttu-id="69d9d-124"><a href="lync-server-2013-preparing-domains.md">Lync Server 2013 のドメインの準備</a></span><span class="sxs-lookup"><span data-stu-id="69d9d-124"><a href="lync-server-2013-preparing-domains.md">Preparing domains for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="69d9d-125">ユニバーサルグループのメンバーによって使用されるオブジェクトにアクセス許可を追加します。</span><span class="sxs-lookup"><span data-stu-id="69d9d-125">Adds permissions on objects to be used by members of universal groups.</span></span></p>
<p><span data-ttu-id="69d9d-126">ユーザードメインまたはサーバードメインごとに1回実行します。</span><span class="sxs-lookup"><span data-stu-id="69d9d-126">Run once per user domain or server domain.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="69d9d-127">Lync Server 2010 から Lync Server 2013 に移行している場合、展開ウィザードでは、ドメインの準備が既に完了していることが示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="69d9d-127">If you are migrating from Lync Server 2010 to Lync Server 2013, the Deployment Wizard may indicate that domain preparation is already complete.</span></span> <span data-ttu-id="69d9d-128">ドメインの準備をもう一度実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="69d9d-128">You do not need to run domain preparation again.</span></span> <span data-ttu-id="69d9d-129">Lync Server 2010 から Lync Server 2013 へのアクセス許可が変更されていない。</span><span class="sxs-lookup"><span data-stu-id="69d9d-129">Permissions were not changed from Lync Server 2010 to Lync Server 2013.</span></span>


</div></td>
<td><p><span data-ttu-id="69d9d-130">Lync Server を展開する各ドメインのメンバーサーバー上。</span><span class="sxs-lookup"><span data-stu-id="69d9d-130">On a member server in each domain where Lync Server will be deployed.</span></span> <span data-ttu-id="69d9d-131">この手順を実行するには、Domain Admins グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d9d-131">To run this step, you must be a member of the Domain Admins group.</span></span></p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

<span data-ttu-id="69d9d-132">Lync server 2010 などの lync Server 2013 では、Office Communications Server 2007 R2 の場合と同様に、AD DS ではなく、中央管理ストアに構成情報が保存されます。</span><span class="sxs-lookup"><span data-stu-id="69d9d-132">Lync Server 2013, like Lync Server 2010, stores much of the configuration information in the Central Management store instead of in AD DS as was the case in Office Communications Server 2007 R2.</span></span> <span data-ttu-id="69d9d-133">ただし、次の情報は AD DS に保存されています。</span><span class="sxs-lookup"><span data-stu-id="69d9d-133">However, the following information is stored in AD DS:</span></span>

  - <span data-ttu-id="69d9d-134">**スキーマの拡張機能**:</span><span class="sxs-lookup"><span data-stu-id="69d9d-134">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="69d9d-135">ユーザー オブジェクトの拡張</span><span class="sxs-lookup"><span data-stu-id="69d9d-135">User object extensions</span></span>
    
      - <span data-ttu-id="69d9d-136">下位互換性を維持するための Office Communications Server 2007 R2 クラスの拡張機能</span><span class="sxs-lookup"><span data-stu-id="69d9d-136">Extensions for Office Communications Server 2007 R2 classes to maintain backward compatibility</span></span>

<!-- end list -->

  - <span data-ttu-id="69d9d-137">**データ**(Lync Server 拡張スキーマと既存のスキーマクラスに保存されています):</span><span class="sxs-lookup"><span data-stu-id="69d9d-137">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="69d9d-138">ユーザー SIP の Uniform Resource Identifier (URI) とその他のユーザー設定</span><span class="sxs-lookup"><span data-stu-id="69d9d-138">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="69d9d-139">返信グループ、会議アテンダントなどのアプリケーションの連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="69d9d-139">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="69d9d-140">中央管理ストアへのポインター</span><span class="sxs-lookup"><span data-stu-id="69d9d-140">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="69d9d-141">Kerberos 認証アカウント (オプションのコンピューターオブジェクト)</span><span class="sxs-lookup"><span data-stu-id="69d9d-141">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="69d9d-142">Lync Server 2013 では、RTCUniversalServerAdmins ユニバーサルグループにセットアップアクセス許可を付与して、そのグループのメンバーがローカルサーバーに Lync Server 2013 をインストールしてライセンス認証を行うことができるように、セットアップと管理を委任します (サーバーを追加した後で、トポロジ、公開済み、有効)。</span><span class="sxs-lookup"><span data-stu-id="69d9d-142">In Lync Server 2013, you delegate setup and administration by granting setup permissions to the RTCUniversalServerAdmins universal group so that members of that group can install and activate Lync Server 2013 on a local server (after the server has been added to the topology, published, and enabled).</span></span> <span data-ttu-id="69d9d-143">委任されたユーザーは、Lync Server 2013 をインストールしてアクティブ化するコンピューターのローカル管理者である必要がありますが、Domain Admins グループのメンバーである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="69d9d-143">The delegated users must be local administrators on the computer where they are installing and activating Lync Server 2013, but they do not need to be members of the Domain Admins group.</span></span> <span data-ttu-id="69d9d-144">また、特定の組織単位 (Ou) 内のオブジェクトに対するアクセス許可を付与して、フォレストの準備中に作成されたユニバーサルグループのメンバーが、Domain Admins グループのメンバーにならずにそれらのオブジェクトにアクセスできるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="69d9d-144">You can also grant permissions for objects in specified organizational units (OUs) so that members of the universal groups created during forest preparation can access those objects without being members of the Domain Admins group.</span></span>

<span data-ttu-id="69d9d-145">Lync Server 2013 の新しい展開の場合、グローバル設定は構成コンテナーに保存されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d9d-145">For new deployments of Lync Server 2013, global settings must be stored in the Configuration container.</span></span> <span data-ttu-id="69d9d-146">組織が以前のバージョンからアップグレードしていて、システムコンテナーでまだグローバル設定を使用している場合は、システムコンテナーは引き続きサポートされます。</span><span class="sxs-lookup"><span data-stu-id="69d9d-146">If your organization is upgrading from an earlier version and you still have global settings in the System container, the System container is still supported.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="69d9d-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="69d9d-147">See Also</span></span>


[<span data-ttu-id="69d9d-148">Lync Server 2013 での Active Directory スキーマの準備</span><span class="sxs-lookup"><span data-stu-id="69d9d-148">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
[<span data-ttu-id="69d9d-149">Lync Server 2013 が使用する Active Directory のスキーマ拡張、クラス、属性</span><span class="sxs-lookup"><span data-stu-id="69d9d-149">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[<span data-ttu-id="69d9d-150">Lync Server 2013 でのフォレストの準備</span><span class="sxs-lookup"><span data-stu-id="69d9d-150">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="69d9d-151">Lync Server 2013 のドメインの準備</span><span class="sxs-lookup"><span data-stu-id="69d9d-151">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


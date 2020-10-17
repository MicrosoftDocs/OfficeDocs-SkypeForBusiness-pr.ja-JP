---
title: 'Lync Server 2013: Active Directory ドメインサービスの準備の概要'
description: 'Lync Server 2013: Active Directory ドメインサービスの準備の概要。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18b22e11a73ad7a181e2eaf887b1b49b934d9db5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566843"
---
# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a><span data-ttu-id="547dc-103">Lync Server 2013 での Active Directory ドメインサービスの準備の概要</span><span class="sxs-lookup"><span data-stu-id="547dc-103">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="547dc-104">_**トピックの最終更新日:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="547dc-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="547dc-105">Lync Server 2013 の展開用に Active Directory ドメインサービスを準備するには、特定の順序で3つの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="547dc-105">To prepare Active Directory Domain Services for your Lync Server 2013 deployment, you must perform three steps in a specific sequence.</span></span>

<span data-ttu-id="547dc-106">次の表では、Lync Server 用の AD DS を準備するために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="547dc-106">The following table describes the steps required to prepare AD DS for Lync Server.</span></span>

### <a name="active-directory-preparation-steps"></a><span data-ttu-id="547dc-107">Active Directory の準備のステップ</span><span class="sxs-lookup"><span data-stu-id="547dc-107">Active Directory Preparation Steps</span></span>

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
<th><span data-ttu-id="547dc-108">手順</span><span class="sxs-lookup"><span data-stu-id="547dc-108">Step</span></span></th>
<th><span data-ttu-id="547dc-109">説明</span><span class="sxs-lookup"><span data-stu-id="547dc-109">Description</span></span></th>
<th><span data-ttu-id="547dc-110">実行場所</span><span class="sxs-lookup"><span data-stu-id="547dc-110">Where run</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><span data-ttu-id="547dc-111"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Lync Server 2013 での Active Directory スキーマの準備</a></span><span class="sxs-lookup"><span data-stu-id="547dc-111"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Preparing the Active Directory schema in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="547dc-112">Lync Server で使用される新しいクラスと属性を追加して、Active Directory スキーマを拡張します。</span><span class="sxs-lookup"><span data-stu-id="547dc-112">Extends the Active Directory schema by adding new classes and attributes that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="547dc-113">Lync Server が展開されている展開内の各フォレストに対して1回実行します。</span><span class="sxs-lookup"><span data-stu-id="547dc-113">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="547dc-114">Lync Server を展開する各フォレストのルートドメインのスキーママスターに対して。</span><span class="sxs-lookup"><span data-stu-id="547dc-114">Against the schema master in the root domain of each forest where Lync Server will be deployed.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="547dc-p101">スキーマ マスターでのアクセス許可を持っている場合は、ルート ドメインでこのステップを実行する必要はありませんが、そのルート ドメインの Schema Admins グループのメンバーに、またスキーマ マスターでの Enterprise Admins グループのメンバーになっている必要があります。リソース フォレスト トポロジでは、ユーザー フォレストではなく、リソース フォレストのみでこのステップを実行します。中央フォレスト トポロジでは、ユーザー フォレストではなく、中央フォレストのみでこのステップを実行します。</span><span class="sxs-lookup"><span data-stu-id="547dc-p101">You do not need to run this step in the root domain if you have permissions on the schema master, but you must be a member of the Schema Admins group in the root domain and a member of the Enterprise Admins group on the schema master. In a resource forest topology, run this step only in the resource forest, not in any user forests. In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><span data-ttu-id="547dc-118"><a href="lync-server-2013-preparing-the-forest.md">Lync Server 2013 のフォレストの準備</a></span><span class="sxs-lookup"><span data-stu-id="547dc-118"><a href="lync-server-2013-preparing-the-forest.md">Preparing the forest for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="547dc-119">Lync Server で使用されるグローバル設定とユニバーサルグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="547dc-119">Creates global settings and universal groups that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="547dc-120">Lync Server が展開されている展開内の各フォレストに対して1回実行します。</span><span class="sxs-lookup"><span data-stu-id="547dc-120">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="547dc-121">Lync Server を展開する各フォレストのルートドメイン。</span><span class="sxs-lookup"><span data-stu-id="547dc-121">In the root domain of each forest where Lync Server will be deployed.</span></span> <span data-ttu-id="547dc-122">このステップを実行するには、Enterprise Admins グループのメンバーになっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="547dc-122">To run this step, you must be a member of the Enterprise Admins group.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="547dc-p103">リソース フォレスト トポロジでは、ユーザー フォレストではなく、リソース フォレストのみでこのステップを実行します。中央フォレスト トポロジでは、ユーザー フォレストではなく、中央フォレストのみでこのステップを実行します。</span><span class="sxs-lookup"><span data-stu-id="547dc-p103">In a resource forest topology, run this step only in the resource forest, not in any user forests. In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><span data-ttu-id="547dc-125"><a href="lync-server-2013-preparing-domains.md">Lync Server 2013 のドメインの準備</a></span><span class="sxs-lookup"><span data-stu-id="547dc-125"><a href="lync-server-2013-preparing-domains.md">Preparing domains for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="547dc-126">ユニバーサル グループのメンバーが使用するオブジェクトに対するアクセス許可を追加する。</span><span class="sxs-lookup"><span data-stu-id="547dc-126">Adds permissions on objects to be used by members of universal groups.</span></span></p>
<p><span data-ttu-id="547dc-127">ユーザー ドメインまたはサーバー ドメインあたり 1 回実行する。</span><span class="sxs-lookup"><span data-stu-id="547dc-127">Run once per user domain or server domain.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="547dc-128">Lync Server 2010 から Lync Server 2013 に移行する場合、展開ウィザードはドメインの準備が既に完了していることを示している場合があります。</span><span class="sxs-lookup"><span data-stu-id="547dc-128">If you are migrating from Lync Server 2010 to Lync Server 2013, the Deployment Wizard may indicate that domain preparation is already complete.</span></span> <span data-ttu-id="547dc-129">ドメインの準備を再度実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="547dc-129">You do not need to run domain preparation again.</span></span> <span data-ttu-id="547dc-130">アクセス許可が Lync Server 2010 から Lync Server 2013 に変更されていません。</span><span class="sxs-lookup"><span data-stu-id="547dc-130">Permissions were not changed from Lync Server 2010 to Lync Server 2013.</span></span>


</div></td>
<td><p><span data-ttu-id="547dc-131">Lync Server が展開される各ドメインのメンバーサーバー上。</span><span class="sxs-lookup"><span data-stu-id="547dc-131">On a member server in each domain where Lync Server will be deployed.</span></span> <span data-ttu-id="547dc-132">このステップを実行するには、Domain Admins グループのメンバーになっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="547dc-132">To run this step, you must be a member of the Domain Admins group.</span></span></p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

<span data-ttu-id="547dc-133">Lync server 2013 (Lync Server 2010 など) は、Office Communications Server 2007 R2 の場合と同様に、AD DS ではなく中央管理ストアに構成情報の大部分を格納します。</span><span class="sxs-lookup"><span data-stu-id="547dc-133">Lync Server 2013, like Lync Server 2010, stores much of the configuration information in the Central Management store instead of in AD DS as was the case in Office Communications Server 2007 R2.</span></span> <span data-ttu-id="547dc-134">ただし、次の情報は AD DS に格納されています。</span><span class="sxs-lookup"><span data-stu-id="547dc-134">However, the following information is stored in AD DS:</span></span>

  - <span data-ttu-id="547dc-135">**スキーマ拡張**:</span><span class="sxs-lookup"><span data-stu-id="547dc-135">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="547dc-136">ユーザー オブジェクトの拡張</span><span class="sxs-lookup"><span data-stu-id="547dc-136">User object extensions</span></span>
    
      - <span data-ttu-id="547dc-137">下位互換性を維持するための Office Communications Server 2007 R2 クラスの拡張機能</span><span class="sxs-lookup"><span data-stu-id="547dc-137">Extensions for Office Communications Server 2007 R2 classes to maintain backward compatibility</span></span>

<!-- end list -->

  - <span data-ttu-id="547dc-138">**データ** (Lync Server 拡張スキーマおよび既存のスキーマクラスに格納されている):</span><span class="sxs-lookup"><span data-stu-id="547dc-138">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="547dc-139">ユーザーの SIP URI (Uniform Resource Identifier) と他のユーザー設定</span><span class="sxs-lookup"><span data-stu-id="547dc-139">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="547dc-140">リソース グループ、会議アテンダントなどのアプリケーションの連絡先オブジェクト</span><span class="sxs-lookup"><span data-stu-id="547dc-140">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="547dc-141">中央管理ストアへのポインター</span><span class="sxs-lookup"><span data-stu-id="547dc-141">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="547dc-142">Kerberos 認証のアカウント (オプションのコンピューター オブジェクト)</span><span class="sxs-lookup"><span data-stu-id="547dc-142">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="547dc-143">Lync Server 2013 では、RTCUniversalServerAdmins ユニバーサルグループに対してセットアップのアクセス許可を付与することにより、セットアップと管理を委任します。これにより、そのグループのメンバーは、ローカルサーバー (トポロジに追加された後、公開された後、および有効にした後) に Lync Server 2013 をインストールしてアクティブ化できます。</span><span class="sxs-lookup"><span data-stu-id="547dc-143">In Lync Server 2013, you delegate setup and administration by granting setup permissions to the RTCUniversalServerAdmins universal group so that members of that group can install and activate Lync Server 2013 on a local server (after the server has been added to the topology, published, and enabled).</span></span> <span data-ttu-id="547dc-144">委任されたユーザーは、Lync Server 2013 をインストールしてアクティブ化するコンピューターのローカル管理者である必要がありますが、Domain Admins グループのメンバーである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="547dc-144">The delegated users must be local administrators on the computer where they are installing and activating Lync Server 2013, but they do not need to be members of the Domain Admins group.</span></span> <span data-ttu-id="547dc-145">また、フォレストの準備中に作成したユニバーサル グループのメンバーが Domain Admins グループのメンバーでなくてもそれらのオブジェクトにアクセスできるよう、指定された組織単位 (OU) 内のオブジェクトに対するアクセス許可を与えることもできます。</span><span class="sxs-lookup"><span data-stu-id="547dc-145">You can also grant permissions for objects in specified organizational units (OUs) so that members of the universal groups created during forest preparation can access those objects without being members of the Domain Admins group.</span></span>

<span data-ttu-id="547dc-146">Lync Server 2013 の新しい展開では、グローバル設定を構成コンテナーに格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="547dc-146">For new deployments of Lync Server 2013, global settings must be stored in the Configuration container.</span></span> <span data-ttu-id="547dc-147">以前のバージョンからアップグレードしていて、システムコンテナーにグローバル設定がある場合でも、システムコンテナーは引き続きサポートされます。</span><span class="sxs-lookup"><span data-stu-id="547dc-147">If your organization is upgrading from an earlier version and you still have global settings in the System container, the System container is still supported.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="547dc-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="547dc-148">See Also</span></span>


[<span data-ttu-id="547dc-149">Lync Server 2013 での Active Directory スキーマの準備</span><span class="sxs-lookup"><span data-stu-id="547dc-149">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
[<span data-ttu-id="547dc-150">Lync Server 2013 で使用される Active Directory スキーマの拡張、クラス、属性</span><span class="sxs-lookup"><span data-stu-id="547dc-150">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[<span data-ttu-id="547dc-151">Lync Server 2013 のフォレストの準備</span><span class="sxs-lookup"><span data-stu-id="547dc-151">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="547dc-152">Lync Server 2013 のドメインの準備</span><span class="sxs-lookup"><span data-stu-id="547dc-152">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


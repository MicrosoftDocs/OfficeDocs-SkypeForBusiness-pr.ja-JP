---
title: 'Lync Server 2013: Active Directory ドメインサービスのサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services support
ms:assetid: aeb62d5e-e424-473a-b795-9452150c98dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412831(v=OCS.15)
ms:contentKeyID: 48185136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44f427486756895f1bff5330075f4c323f944afd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529634"
---
# <a name="active-directory-domain-services-support-in-lync-server-2013"></a><span data-ttu-id="3273c-102">Lync Server 2013 での Active Directory ドメインサービスのサポート</span><span class="sxs-lookup"><span data-stu-id="3273c-102">Active Directory Domain Services support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3273c-103">_**トピックの最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="3273c-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="3273c-104">Lync Server 2013 は、中央管理ストアを使用して、この情報の Active Directory ドメインサービスに依存するのではなく、サーバーとサービスの構成データを格納します。</span><span class="sxs-lookup"><span data-stu-id="3273c-104">Lync Server 2013 uses the Central Management store to store configuration data for servers and services, instead of relying on Active Directory Domain Services for this information, as in the past.</span></span> <span data-ttu-id="3273c-105">Lync Server 2013 では、引き続き AD DS に次のものが格納されます。</span><span class="sxs-lookup"><span data-stu-id="3273c-105">Lync Server 2013 still stores the following in AD DS:</span></span>

  - <span data-ttu-id="3273c-106">**スキーマ拡張**</span><span class="sxs-lookup"><span data-stu-id="3273c-106">**Schema extensions**</span></span>
    
      - <span data-ttu-id="3273c-107">ユーザー オブジェクトの拡張</span><span class="sxs-lookup"><span data-stu-id="3273c-107">User object extensions</span></span>
    
      - <span data-ttu-id="3273c-108">以前サポートされていたバージョンとの下位互換性を維持するための Lync Server 2010 および Office Communications Server 2007 R2 クラスの拡張機能</span><span class="sxs-lookup"><span data-stu-id="3273c-108">Extensions for Lync Server 2010 and Office Communications Server 2007 R2 classes to maintain backward compatibility with previous supported versions</span></span>

  - <span data-ttu-id="3273c-109">**データ** (Lync Server 2013 の拡張スキーマおよび既存のクラスに格納されている)</span><span class="sxs-lookup"><span data-stu-id="3273c-109">**Data** (stored in Lync Server 2013 extended schema and in existing classes)</span></span>
    
      - <span data-ttu-id="3273c-110">ユーザーの SIP URI と他のユーザー設定</span><span class="sxs-lookup"><span data-stu-id="3273c-110">User SIP URI and other user settings</span></span>
    
      - <span data-ttu-id="3273c-111">アプリケーションの連絡先オブジェクト (たとえば、応答グループアプリケーションや会議アテンダントアプリケーション)</span><span class="sxs-lookup"><span data-stu-id="3273c-111">Contact objects for applications (for example, the Response Group application and the Conferencing Attendant application)</span></span>
    
      - <span data-ttu-id="3273c-112">下位互換性について公開されたデータ</span><span class="sxs-lookup"><span data-stu-id="3273c-112">Data published for backward compatibility</span></span>
    
      - <span data-ttu-id="3273c-113">中央管理ストアのサービスコントロールポイント (SCP)</span><span class="sxs-lookup"><span data-stu-id="3273c-113">A service control point (SCP) for the Central Management store</span></span>
    
      - <span data-ttu-id="3273c-114">Kerberos 認証のアカウント (オプションのコンピューター オブジェクト)</span><span class="sxs-lookup"><span data-stu-id="3273c-114">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="3273c-115">このセクションでは、Lync Server 2013 の AD DS のサポート要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="3273c-115">This section describes the AD DS support requirements for Lync Server 2013.</span></span> <span data-ttu-id="3273c-116">トポロジのサポートの詳細については、「サポート」のドキュメントの「 [Lync Server 2013 でサポートされている Active Directory トポロジ](lync-server-2013-supported-active-directory-topologies.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3273c-116">For details about topology support, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span>

<div>

## <a name="supported-domain-controller-operating-systems"></a><span data-ttu-id="3273c-117">サポートされるドメイン コントローラー オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="3273c-117">Supported Domain Controller Operating Systems</span></span>

<span data-ttu-id="3273c-118">Lync Server 2013 は、次のオペレーティングシステムを実行しているドメインコントローラーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="3273c-118">Lync Server 2013 supports domain controllers running the following operating systems:</span></span>

  - <span data-ttu-id="3273c-119">Windows Server 2012 R2 オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="3273c-119">Windows Server 2012 R2 operating system</span></span>

  - <span data-ttu-id="3273c-120">Windows Server 2012 オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="3273c-120">Windows Server 2012 operating system</span></span>

  - <span data-ttu-id="3273c-121">Windows Server 2008 R2 オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="3273c-121">Windows Server 2008 R2 operating system</span></span>

  - <span data-ttu-id="3273c-122">Windows Server 2008 オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="3273c-122">Windows Server 2008 operating system</span></span>

  - <span data-ttu-id="3273c-123">Windows Server 2008 Enterprise 32-Bit</span><span class="sxs-lookup"><span data-stu-id="3273c-123">Windows Server 2008 Enterprise 32-Bit</span></span>

  - <span data-ttu-id="3273c-124">Windows Server 2003 R2 オペレーティング システムの 32 ビット版または 64 ビット版</span><span class="sxs-lookup"><span data-stu-id="3273c-124">The 32-bit or 64-bit versions of the Window Server 2003 R2 operating system</span></span>

  - <span data-ttu-id="3273c-125">Windows Server 2003 オペレーティングシステムの32ビット版または64ビット版</span><span class="sxs-lookup"><span data-stu-id="3273c-125">The 32-bit or 64-bit versions of the Windows Server 2003 operating system</span></span>

</div>

<div>

## <a name="forest-and-domain-functional-level"></a><span data-ttu-id="3273c-126">フォレストおよびドメインの機能レベル</span><span class="sxs-lookup"><span data-stu-id="3273c-126">Forest and Domain Functional Level</span></span>

<span data-ttu-id="3273c-127">Lync Server 2013 を展開するすべてのドメインを、Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008、または少なくとも Windows Server 2003 のドメイン機能レベルに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3273c-127">You must raise all domains in which you deploy Lync Server 2013 to a domain functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

<span data-ttu-id="3273c-128">Lync Server 2013 を展開するすべてのフォレストは、Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008、または少なくとも Windows Server 2003 のフォレスト機能レベルに上げられる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3273c-128">All forests in which you deploy Lync Server 2013 must be raised to a forest functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a><span data-ttu-id="3273c-129">読み取り専用ドメイン コントローラーのサポート</span><span class="sxs-lookup"><span data-stu-id="3273c-129">Support for Read-Only Domain Controllers</span></span>

<span data-ttu-id="3273c-130">Lync Server 2013 は、書き込み可能なドメインコントローラーがある限り、読み取り専用ドメインコントローラーまたは読み取り専用グローバルカタログサーバーが含まれる Active Directory ドメインサービスの展開をサポートします。</span><span class="sxs-lookup"><span data-stu-id="3273c-130">Lync Server 2013 supports Active Directory Domain Services deployments that include read-only domain controllers or read-only global catalog servers, as long as there are writable domain controllers available.</span></span>

</div>

<div>

## <a name="domain-names"></a><span data-ttu-id="3273c-131">ドメイン名</span><span class="sxs-lookup"><span data-stu-id="3273c-131">Domain Names</span></span>

<span data-ttu-id="3273c-132">Lync Server は、単一ラベルのドメインをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3273c-132">Lync Server does not support single-labeled domains.</span></span> <span data-ttu-id="3273c-133">たとえば、ルート ドメイン名が **contoso.local** であるフォレストはサポートされますが、**local** という名前のルート ドメインはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="3273c-133">For example, a forest with a root domain named **contoso.local** is supported, but a root domain named **local** is not supported.</span></span> <span data-ttu-id="3273c-134">詳細については、「Microsoft サポート技術情報の記事300684」を参照してください。単一ラベル DNS 名のドメインに対する Windows の構成については、「」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=143752](https://go.microsoft.com/fwlink/p/?linkid=143752) 。</span><span class="sxs-lookup"><span data-stu-id="3273c-134">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at [https://go.microsoft.com/fwlink/p/?linkId=143752](https://go.microsoft.com/fwlink/p/?linkid=143752).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3273c-135">Lync Server は、ドメイン名の変更をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3273c-135">Lync Server does not support renaming domains.</span></span> <span data-ttu-id="3273c-136">Lync Server が展開されているドメインの名前を変更する必要がある場合は、まず Lync Server をアンインストールしてから、ドメインの名前を変更してから Lync Server を再インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3273c-136">If you need to rename a domain where Lync Server is deployed, you need to first uninstall Lync Server, then rename the domain, and then reinstall Lync Server.</span></span>



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a><span data-ttu-id="3273c-137">ロックダウンされた AD DS 環境</span><span class="sxs-lookup"><span data-stu-id="3273c-137">Locked Down AD DS Environments</span></span>

<span data-ttu-id="3273c-138">ロックダウンされた AD DS 環境では、アクセス許可の継承が無効になっている特定の組織単位 (Ou) にユーザーとコンピューターのオブジェクトが配置されることが多く、セキュリティポリシーを適用するために、グループポリシーオブジェクト (Gpo) の使用を有効にするために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3273c-138">In a locked-down AD DS environment, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span> <span data-ttu-id="3273c-139">Lync Server 2013 は、ロックダウンされた Active Directory 環境に展開できます。</span><span class="sxs-lookup"><span data-stu-id="3273c-139">Lync Server 2013 can be deployed in a locked-down Active Directory environment.</span></span> <span data-ttu-id="3273c-140">ロックダウンされた環境で Lync Server を展開するために必要な事項の詳細については、「展開」のドキュメントの「 [Lync server 2013 でのロックダウンされた Active Directory ドメインサービスの準備](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3273c-140">For details about what is required to deploy Lync Server in a locked-down environment, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


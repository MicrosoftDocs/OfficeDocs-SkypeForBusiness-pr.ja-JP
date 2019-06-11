---
title: 'Lync Server 2013: Active Directory ドメイン サービスのサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory Domain Services support
ms:assetid: aeb62d5e-e424-473a-b795-9452150c98dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412831(v=OCS.15)
ms:contentKeyID: 48185136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b264abefb1234892df355fee123dd6ce68b4dfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-support-in-lync-server-2013"></a><span data-ttu-id="9e971-102">Lync Server 2013 での Active Directory ドメイン サービスのサポート</span><span class="sxs-lookup"><span data-stu-id="9e971-102">Active Directory Domain Services support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e971-103">_**最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="9e971-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="9e971-104">Lync Server 2013 は、この情報について Active Directory ドメインサービスに依存するのではなく、サーバーとサービスの構成データを保存するために、中央管理ストアを使用しています。</span><span class="sxs-lookup"><span data-stu-id="9e971-104">Lync Server 2013 uses the Central Management store to store configuration data for servers and services, instead of relying on Active Directory Domain Services for this information, as in the past.</span></span> <span data-ttu-id="9e971-105">Lync Server 2013 では、引き続き次の内容が AD DS に保存されています。</span><span class="sxs-lookup"><span data-stu-id="9e971-105">Lync Server 2013 still stores the following in AD DS:</span></span>

  - <span data-ttu-id="9e971-106">**スキーマ拡張**</span><span class="sxs-lookup"><span data-stu-id="9e971-106">**Schema extensions**</span></span>
    
      - <span data-ttu-id="9e971-107">ユーザー オブジェクトの拡張</span><span class="sxs-lookup"><span data-stu-id="9e971-107">User object extensions</span></span>
    
      - <span data-ttu-id="9e971-108">以前サポートされているバージョンとの下位互換性を維持するための、Lync Server 2010 および Office Communications Server 2007 R2 クラス用の拡張機能</span><span class="sxs-lookup"><span data-stu-id="9e971-108">Extensions for Lync Server 2010 and Office Communications Server 2007 R2 classes to maintain backward compatibility with previous supported versions</span></span>

  - <span data-ttu-id="9e971-109">**データ**(Lync Server 2013 の拡張スキーマと既存のクラスに保存されています)</span><span class="sxs-lookup"><span data-stu-id="9e971-109">**Data** (stored in Lync Server 2013 extended schema and in existing classes)</span></span>
    
      - <span data-ttu-id="9e971-110">ユーザーの SIP URI と他のユーザー設定</span><span class="sxs-lookup"><span data-stu-id="9e971-110">User SIP URI and other user settings</span></span>
    
      - <span data-ttu-id="9e971-111">アプリケーションの連絡先オブジェクト (たとえば、応答グループのアプリケーション、会議アテンダントアプリケーションなど)</span><span class="sxs-lookup"><span data-stu-id="9e971-111">Contact objects for applications (for example, the Response Group application and the Conferencing Attendant application)</span></span>
    
      - <span data-ttu-id="9e971-112">下位互換性のために公開されたデータ</span><span class="sxs-lookup"><span data-stu-id="9e971-112">Data published for backward compatibility</span></span>
    
      - <span data-ttu-id="9e971-113">中央管理ストアのサービス制御ポイント (SCP)</span><span class="sxs-lookup"><span data-stu-id="9e971-113">A service control point (SCP) for the Central Management store</span></span>
    
      - <span data-ttu-id="9e971-114">Kerberos 認証アカウント (オプションのコンピューターオブジェクト)</span><span class="sxs-lookup"><span data-stu-id="9e971-114">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="9e971-115">このセクションでは、Lync Server 2013 の AD DS のサポート要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="9e971-115">This section describes the AD DS support requirements for Lync Server 2013.</span></span> <span data-ttu-id="9e971-116">トポロジのサポートの詳細については、サポートドキュメントの「 [Lync Server 2013 でサポートされている Active Directory トポロジ](lync-server-2013-supported-active-directory-topologies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e971-116">For details about topology support, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span>

<div>

## <a name="supported-domain-controller-operating-systems"></a><span data-ttu-id="9e971-117">サポートされているドメインコントローラーオペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="9e971-117">Supported Domain Controller Operating Systems</span></span>

<span data-ttu-id="9e971-118">Lync Server 2013 は、次のオペレーティングシステムを実行しているドメインコントローラーをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9e971-118">Lync Server 2013 supports domain controllers running the following operating systems:</span></span>

  - <span data-ttu-id="9e971-119">Windows Server 2012 R2 オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="9e971-119">Windows Server 2012 R2 operating system</span></span>

  - <span data-ttu-id="9e971-120">Windows Server 2012 オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="9e971-120">Windows Server 2012 operating system</span></span>

  - <span data-ttu-id="9e971-121">Windows Server 2008 R2 オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="9e971-121">Windows Server 2008 R2 operating system</span></span>

  - <span data-ttu-id="9e971-122">Windows Server 2008 オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="9e971-122">Windows Server 2008 operating system</span></span>

  - <span data-ttu-id="9e971-123">Windows Server 2008 Enterprise 32 ビット</span><span class="sxs-lookup"><span data-stu-id="9e971-123">Windows Server 2008 Enterprise 32-Bit</span></span>

  - <span data-ttu-id="9e971-124">Windows Server 2003 R2 オペレーティングシステムの32ビットまたは64ビットバージョン</span><span class="sxs-lookup"><span data-stu-id="9e971-124">The 32-bit or 64-bit versions of the Window Server 2003 R2 operating system</span></span>

  - <span data-ttu-id="9e971-125">Windows Server 2003 オペレーティングシステムの32ビットまたは64ビットバージョン</span><span class="sxs-lookup"><span data-stu-id="9e971-125">The 32-bit or 64-bit versions of the Windows Server 2003 operating system</span></span>

</div>

<div>

## <a name="forest-and-domain-functional-level"></a><span data-ttu-id="9e971-126">フォレストとドメインの機能レベル</span><span class="sxs-lookup"><span data-stu-id="9e971-126">Forest and Domain Functional Level</span></span>

<span data-ttu-id="9e971-127">Lync Server 2013 を展開するすべてのドメインを、windows server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008、または Windows Server 2003 以上のドメインの機能レベルに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e971-127">You must raise all domains in which you deploy Lync Server 2013 to a domain functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

<span data-ttu-id="9e971-128">Lync Server 2013 を展開するすべてのフォレストは、Windows Server 2012 R2、windows Server 2012、Windows Server 2008 R2、Windows Server 2008、または Windows Server 2003 以上のフォレストの機能レベルに上げる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e971-128">All forests in which you deploy Lync Server 2013 must be raised to a forest functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a><span data-ttu-id="9e971-129">読み取り専用ドメインコントローラーのサポート</span><span class="sxs-lookup"><span data-stu-id="9e971-129">Support for Read-Only Domain Controllers</span></span>

<span data-ttu-id="9e971-130">Lync Server 2013 は、書き込み可能なドメインコントローラーが利用可能であれば、読み取り専用のドメインコントローラーまたは読み取り専用のグローバルカタログサーバーを含む Active Directory ドメインサービスの展開をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9e971-130">Lync Server 2013 supports Active Directory Domain Services deployments that include read-only domain controllers or read-only global catalog servers, as long as there are writable domain controllers available.</span></span>

</div>

<div>

## <a name="domain-names"></a><span data-ttu-id="9e971-131">ドメイン名</span><span class="sxs-lookup"><span data-stu-id="9e971-131">Domain Names</span></span>

<span data-ttu-id="9e971-132">Lync Server では、単一ラベルのドメインはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9e971-132">Lync Server does not support single-labeled domains.</span></span> <span data-ttu-id="9e971-133">たとえば、 **local**という名前のルートドメインを持つフォレストはサポートされていますが、 **local**という名前のルートドメインはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9e971-133">For example, a forest with a root domain named **contoso.local** is supported, but a root domain named **local** is not supported.</span></span> <span data-ttu-id="9e971-134">詳細については、「Microsoft サポート技術情報の記事300684」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=143752](http://go.microsoft.com/fwlink/p/?linkid=143752)。 "単一ラベルの DNS 名でドメイン用に Windows を構成する" について説明します。</span><span class="sxs-lookup"><span data-stu-id="9e971-134">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at [http://go.microsoft.com/fwlink/p/?linkId=143752](http://go.microsoft.com/fwlink/p/?linkid=143752).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9e971-135">Lync Server では、ドメイン名の変更はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9e971-135">Lync Server does not support renaming domains.</span></span> <span data-ttu-id="9e971-136">Lync Server が展開されているドメインの名前を変更する必要がある場合は、まず Lync Server をアンインストールしてから、ドメインの名前を変更してから、Lync Server を再インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e971-136">If you need to rename a domain where Lync Server is deployed, you need to first uninstall Lync Server, then rename the domain, and then reinstall Lync Server.</span></span>



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a><span data-ttu-id="9e971-137">ロックダウンされた AD DS 環境</span><span class="sxs-lookup"><span data-stu-id="9e971-137">Locked Down AD DS Environments</span></span>

<span data-ttu-id="9e971-138">ロックダウンされた AD DS 環境では、管理者の委任を保護し、グループポリシーオブジェクト (Gpo) の使用を有効にするために、ユーザーとコンピューターオブジェクトが特定の組織単位 (Ou) に配置されることがよくあります。セキュリティポリシー。</span><span class="sxs-lookup"><span data-stu-id="9e971-138">In a locked-down AD DS environment, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span> <span data-ttu-id="9e971-139">Lync Server 2013 は、ロックダウンされた Active Directory 環境に展開できます。</span><span class="sxs-lookup"><span data-stu-id="9e971-139">Lync Server 2013 can be deployed in a locked-down Active Directory environment.</span></span> <span data-ttu-id="9e971-140">ロックダウン環境での Lync Server の展開に必要なものについて詳しくは、「展開ドキュメントの[Lync server 2013 でロックダウンされた Active Directory ドメインサービスの準備](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9e971-140">For details about what is required to deploy Lync Server in a locked-down environment, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


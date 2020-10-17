---
title: 'Lync Server 2013: Active Directory インフラストラクチャの要件'
description: 'Lync Server 2013: Active Directory インフラストラクチャの要件。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory infrastructure requirements
ms:assetid: c2086f7b-662f-4179-ab99-2c0311ebd903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412955(v=OCS.15)
ms:contentKeyID: 48185318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62218605c9b3fac20743d0b6bb475515c9498f9a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552363"
---
# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="d36bb-103">Lync Server 2013 の Active Directory インフラストラクチャの要件</span><span class="sxs-lookup"><span data-stu-id="d36bb-103">Active Directory infrastructure requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d36bb-104">_**トピックの最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="d36bb-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="d36bb-105">Lync Server 2013 の Active Directory ドメインサービスを準備するプロセスを開始する前に、Active Directory インフラストラクチャが次の前提条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d36bb-105">Before you start the process of preparing Active Directory Domain Services for Lync Server 2013, make sure that your Active Directory infrastructure meets the following prerequisites:</span></span>

  - <span data-ttu-id="d36bb-106">Lync Server を展開するフォレスト内のすべてのドメインコントローラー (すべてのグローバルカタログサーバーを含む) は、次のいずれかのオペレーティングシステムを実行します。</span><span class="sxs-lookup"><span data-stu-id="d36bb-106">All domain controllers (which include all global catalog servers) in the forest where you deploy Lync Server run one of the following operating systems:</span></span>
    
      - <span data-ttu-id="d36bb-107">Windows Server 2012 R2 オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="d36bb-107">Windows Server 2012 R2 operating system</span></span>
    
      - <span data-ttu-id="d36bb-108">Windows Server 2012 オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="d36bb-108">Windows Server 2012 operating system</span></span>
    
      - <span data-ttu-id="d36bb-109">Windows Server 2008 R2 オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="d36bb-109">Windows Server 2008 R2 operating system</span></span>
    
      - <span data-ttu-id="d36bb-110">Windows Server 2008 オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="d36bb-110">Windows Server 2008 operating system</span></span>
    
      - <span data-ttu-id="d36bb-111">Windows Server 2008 Enterprise 32-Bit</span><span class="sxs-lookup"><span data-stu-id="d36bb-111">Windows Server 2008 Enterprise 32-Bit</span></span>
    
      - <span data-ttu-id="d36bb-112">32 ビットまたは 64 ビット版の Windows Server 2003 R2 オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="d36bb-112">32-bit or 64-bit versions of the Windows Server 2003 R2 operating system</span></span>
    
      - <span data-ttu-id="d36bb-113">32ビットまたは64ビットバージョンの Windows Server 2003 オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="d36bb-113">32-bit or 64-bit versions of the Windows Server 2003 operating system</span></span>

  - <span data-ttu-id="d36bb-114">Lync Server を展開するすべてのドメインは、Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008、または少なくとも Windows Server 2003 のドメイン機能レベルに上げられます。</span><span class="sxs-lookup"><span data-stu-id="d36bb-114">All domains in which you deploy Lync Server are raised to a domain functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

  - <span data-ttu-id="d36bb-115">Lync Server を展開するフォレストは、Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008、または少なくとも Windows Server 2003 のフォレスト機能レベルに上げられます。</span><span class="sxs-lookup"><span data-stu-id="d36bb-115">The forest in which you deploy Lync Server is raised to a forest functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d36bb-116">ドメインまたはフォレストの機能レベルを変更するには、TechNet ライブラリの「ドメインとフォレストの機能レベルを上げる」を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=263775">https://go.microsoft.com/fwlink/p/?LinkId=263775</A> 。</span><span class="sxs-lookup"><span data-stu-id="d36bb-116">To change your domain or forest functional level, see "Raising domain and forest functional levels" in the TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=263775">https://go.microsoft.com/fwlink/p/?LinkId=263775</A>.</span></span>

    
    </div>

  - <span data-ttu-id="d36bb-117">グローバルカタログは、Lync Server コンピューターまたはユーザーを展開するすべてのドメインに展開されます。</span><span class="sxs-lookup"><span data-stu-id="d36bb-117">A global catalog is deployed in every domain where you deploy Lync Server computers or users.</span></span>

<span data-ttu-id="d36bb-118">Lync Server 2013 では、Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008、および Windows Server 2003 オペレーティングシステムのユニバーサルグループがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d36bb-118">Lync Server 2013 supports the universal groups in the Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, and Windows Server 2003 operating systems.</span></span> <span data-ttu-id="d36bb-119">ユニバーサルグループのメンバーには、ドメインツリーまたはフォレスト内の任意のドメインの他のグループとアカウントを含めることができます。また、ドメインツリーまたはフォレスト内の任意のドメインでアクセス許可を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d36bb-119">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="d36bb-120">ユニバーサルグループのサポートを管理者の委任と組み合わせて使用すると、Lync Server の展開の管理が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="d36bb-120">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="d36bb-121">たとえば、あるドメインを別のドメインに追加して、管理者が両方を管理できるようにする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d36bb-121">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


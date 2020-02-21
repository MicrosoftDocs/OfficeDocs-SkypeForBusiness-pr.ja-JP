---
title: 'Lync Server 2013: Active Directory インフラストラクチャの要件'
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
ms.openlocfilehash: 0747957a42c07c987f3123608d35fb86b5d4c036
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a>Lync Server 2013 の Active Directory インフラストラクチャの要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-11-07_

Lync Server 2013 の Active Directory ドメインサービスを準備するプロセスを開始する前に、Active Directory インフラストラクチャが次の前提条件を満たしていることを確認してください。

  - Lync Server を展開するフォレスト内のすべてのドメインコントローラー (すべてのグローバルカタログサーバーを含む) は、次のいずれかのオペレーティングシステムを実行します。
    
      - Windows Server 2012 R2 オペレーティングシステム
    
      - Windows Server 2012 オペレーティングシステム
    
      - Windows Server 2008 R2 オペレーティング システム
    
      - Windows Server 2008 オペレーティング システム
    
      - Windows Server 2008 Enterprise 32-Bit
    
      - 32 ビットまたは 64 ビット版の Windows Server 2003 R2 オペレーティング システム
    
      - 32ビットまたは64ビットバージョンの Windows Server 2003 オペレーティングシステム

  - Lync Server を展開するすべてのドメインは、Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008、または少なくとも Windows Server 2003 のドメイン機能レベルに上げられます。

  - Lync Server を展開するフォレストは、Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008、または少なくとも Windows Server 2003 のフォレスト機能レベルに上げられます。
    
    <div>
    

    > [!NOTE]  
    > ドメインまたはフォレストの機能レベルを変更するには、TechNet ライブラリの「ドメインとフォレストの機能レベル<A href="https://go.microsoft.com/fwlink/p/?linkid=263775">https://go.microsoft.com/fwlink/p/?LinkId=263775</A>を上げる」を参照してください。

    
    </div>

  - グローバルカタログは、Lync Server コンピューターまたはユーザーを展開するすべてのドメインに展開されます。

Lync Server 2013 では、Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008、および Windows Server 2003 オペレーティングシステムのユニバーサルグループがサポートされています。 ユニバーサルグループのメンバーには、ドメインツリーまたはフォレスト内の任意のドメインの他のグループとアカウントを含めることができます。また、ドメインツリーまたはフォレスト内の任意のドメインでアクセス許可を割り当てることができます。 ユニバーサルグループのサポートを管理者の委任と組み合わせて使用すると、Lync Server の展開の管理が簡単になります。 たとえば、あるドメインを別のドメインに追加して、管理者が両方を管理できるようにする必要はありません。

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Active Directory インフラストラクチャの要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory infrastructure requirements
ms:assetid: c2086f7b-662f-4179-ab99-2c0311ebd903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412955(v=OCS.15)
ms:contentKeyID: 48185318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c583fd751bf70814f9aa2fae5f6cfe08bec0202
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a>Lync Server 2013 に関する Active Directory インフラストラクチャの要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-11-07_

Lync Server 2013 用の Active Directory ドメインサービスの準備プロセスを開始する前に、Active Directory インフラストラクチャが次の前提条件を満たしていることを確認してください。

  - Lync Server を展開したフォレストのすべてのドメインコントローラー (すべてのグローバルカタログサーバーを含む) は、次のいずれかのオペレーティングシステムを実行します。
    
      - Windows Server 2012 R2 オペレーティングシステム
    
      - Windows Server 2012 オペレーティングシステム
    
      - Windows Server 2008 R2 オペレーティング システム
    
      - Windows Server 2008 オペレーティング システム
    
      - Windows Server 2008 Enterprise 32 ビット
    
      - 32ビット版または64ビット版の Windows Server 2003 R2 オペレーティングシステム
    
      - 32ビット版または64ビット版の Windows Server 2003 オペレーティングシステム

  - Lync Server を展開するすべてのドメインは、Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008、または少なくとも Windows Server 2003 のドメイン機能レベルに発生します。

  - Lync Server を展開するフォレストは、Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008、または Windows server 2003 以上のフォレストの機能レベルに上げられます。
    
    <div>
    

    > [!NOTE]  
    > ドメインまたはフォレストの機能レベルを変更するには、TechNet ライブラリの「ドメインとフォレストの機能レベル<A href="http://go.microsoft.com/fwlink/p/?linkid=263775">http://go.microsoft.com/fwlink/p/?LinkId=263775</A>を上げる」を参照してください。

    
    </div>

  - グローバルカタログは、Lync Server コンピューターまたはユーザーを展開するすべてのドメインに展開されます。

Lync Server 2013 は、Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008、Windows Server 2003 オペレーティングシステムのユニバーサルグループをサポートしています。 ユニバーサルグループのメンバーには、ドメインツリーまたはフォレスト内の任意のドメインの他のグループとアカウントを含めることができ、ドメインツリーまたはフォレスト内の任意のドメインでアクセス許可を割り当てることができます。 ユニバーサルグループのサポートは、管理者の委任と組み合わせて、Lync Server の展開の管理を簡素化します。 たとえば、あるドメインを別のドメインに追加して、管理者が両方を管理できるようにする必要はありません。

</div>

<span> </span>

</div>

</div>

</div>


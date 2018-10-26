---
title: 'Lync Server 2013: Active Directory インフラストラクチャの要件'
TOCTitle: Active Directory インフラストラクチャの要件
ms:assetid: c2086f7b-662f-4179-ab99-2c0311ebd903
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412955(v=OCS.15)
ms:contentKeyID: 48273494
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 に関する Active Directory インフラストラクチャの要件

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server 2013 用の Active Directory ドメイン サービス の準備プロセスを開始する前に、 Active Directory インフラストラクチャが次の前提条件を満たしていることを確認してください。

  - Lync Server を展開するフォレストのすべてのドメイン コントローラー (すべてのグローバル カタログ サーバーを含む) で、次のオペレーティング システムのいずれかが稼働している。
    
      - Windows Server 2012 R2 オペレーティング システム
    
      - Windows Server 2012 オペレーティング システム
    
      - Windows Server 2008 R2 オペレーティング システム
    
      - Windows Server 2008 オペレーティング システム
    
      - Windows Server 2008 Enterprise 32 ビット版
    
      - 32 ビット版または 64 ビット版の Windows Server 2003 R2 オペレーティング システム
    
      - 32 ビット版または 64 ビット版の Windows Server 2003 オペレーティング システム

  - Lync Server を展開するすべてのドメインが、Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008、または最低でも Windows Server 2003 のドメイン機能レベルに上げられている。

  - Lync Server を展開するフォレストが、Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008、または最低でも Windows Server 2003 のフォレスト機能レベルに上げられている。
    
    > [!NOTE]
    > ドメインまたはフォレストの機能レベルを変更するには、TechNet ライブラリの「ドメインとフォレストの機能レベルを上げる」( <a href="http://go.microsoft.com/fwlink/?linkid=263775" class="uri">http://go.microsoft.com/fwlink/?linkid=263775</a>) を参照してください。


  - グローバル カタログが、 Lync Server のコンピューターまたはユーザーを展開するすべてのドメインで展開されている。

Lync Server 2013 は、Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008、および Windows Server 2003 オペレーティング システムのユニバーサル グループをサポートしています。ユニバーサル グループには、ドメイン ツリーまたはフォレストの任意のドメインの他のグループやアカウントをメンバーとして含めることができます。また、ドメイン ツリーまたはフォレストの任意のドメインのアクセス許可を割り当てることができます。ユニバーサル グループのサポートと管理者の委任との組み合わせにより、Lync Server の展開の管理が簡略化されます。たとえば、ドメインを別のドメインに追加することなく、管理者に両方のドメインを管理させることができます。


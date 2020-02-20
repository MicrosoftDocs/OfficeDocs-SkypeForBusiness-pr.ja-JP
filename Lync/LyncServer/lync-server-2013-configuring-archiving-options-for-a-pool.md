---
title: 'Lync Server 2013: プールのアーカイブオプションの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options for a pool
ms:assetid: b7cb0fd8-3d31-4858-a75c-c66a7742556e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205200(v=OCS.15)
ms:contentKeyID: 48185230
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f59ad3c768db0ea133337b747c073ee2e0c56b1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-pool-in-lync-server-2013"></a>Lync Server 2013 でのプールのアーカイブオプションの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-10_

特定のプールそれぞれのアーカイブ構成を作成してオプションを構成することによって、これらのプールに適用するアーカイブ オプションを指定できます。プール構成はグローバル構成とサイト構成より優先されますが、プール構成で指定したプールにのみ適用されます。

グローバル構成、サイト構成、およびプール構成の階層など、アーカイブ構成のしくみの詳細については、「計画」、「展開」、または「操作」のドキュメントの「 [Lync Server 2013 でのアーカイブの仕組み](lync-server-2013-how-archiving-works.md)」を参照してください。

<div>


> [!NOTE]  
> アーカイブを有効にするには、その前にアーカイブ構成で適切なオプションをすべて指定する必要があります。 詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 のアーカイブオプションの構成</A>」を参照してください。



</div>

<div>

## <a name="to-configure-archiving-options-at-the-pool-level"></a>プール レベルでアーカイブ オプションを構成するには

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server 2013 コントロールパネルを開きます。 Lync Server 2013 コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。

4.  [**アーカイブ構成**] ページで、[**新規**]、[**プール構成**] の順にクリックします。

5.  [**サービスの選択**] で、アーカイブ用に構成するプールを選択します。

6.  [**新規 アーカイブ設定**] の [**アーカイブ設定**] ドロップダウン リストで、次のアーカイブ オプションのいずれかを選択します。
    
      - [**アーカイブを無効にする**]
    
      - [**IM セッションをアーカイブする**]
    
      - [**IM および Web 会議セッションをアーカイブする**]

7.  また、[**新規 アーカイブ設定**] ページで、次の操作を実行します。
    
      - アーカイブを使用できない場合にアクティビティをブロックするには、[**アーカイブ失敗時はインスタント メッセージング (IM) または Web 会議セッションを禁止する**] チェック ボックスをオンにします。
    
      - Microsoft Exchange Server を使用してアーカイブデータを保存するには、[ **Microsoft exchange 統合**] チェックボックスをオンにします。
    
      - データの削除を有効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにし、次のどちらかの操作を実行します。
        
          - 一定の日数が経過した後に削除されるよう指定するには、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックして、日数を指定します。
        
          - エクスポートされたアーカイブ データに削除対象を限定するには、[**エクスポートされたアーカイブ データのみを削除する**] をクリックします。

8.  [**確定**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>


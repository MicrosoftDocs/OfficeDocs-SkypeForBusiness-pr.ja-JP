---
title: 'Lync Server 2013: グローバルレベルでのアーカイブオプションの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options at the global level
ms:assetid: bfe415f7-2abf-41ee-a1cb-cf48b2d59c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205233(v=OCS.15)
ms:contentKeyID: 48185303
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 939928b99c4372f3dafe9536365481fb737478a6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517544"
---
# <a name="configuring-archiving-options-at-the-global-level-in-lync-server-2013"></a>Lync Server 2013 のグローバルレベルでのアーカイブオプションの構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-10_

トポロジにアーカイブを追加してトポロジを公開すると、Lync Server はアーカイブ用のグローバル構成を作成します。 既定では、グローバル構成で有効になっているアーカイブ オプションはありません。 グローバル構成より優先されるサイト構成またはプール構成を設定しない限り、グローバル構成は、展開全体に対して有効化されるオプションを制御します。

グローバル構成、サイト構成、およびプール構成の階層など、アーカイブ構成のしくみの詳細については、「計画」、「展開」、または「操作」のドキュメントの「 [Lync Server 2013 でのアーカイブの仕組み](lync-server-2013-how-archiving-works.md) 」を参照してください。

<div>


> [!NOTE]  
> アーカイブを有効にするには、その前にアーカイブ構成で適切なオプションをすべて指定する必要があります。



</div>

<div>

## <a name="to-configure-archiving-options-at-the-global-level"></a>グローバル レベルでアーカイブ オプションを構成するには

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server 2013 コントロールパネルを開きます。 Lync Server 2013 コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。

4.  [**アーカイブ構成**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] の順にクリックします。

5.  [**編集 アーカイブ設定 - Global**] の [**アーカイブ設定**] ドロップダウン リストで、次のいずれかのアーカイブ オプションを選択します。
    
      - [**アーカイブを無効にする**]
    
      - [**IM セッションをアーカイブする**]
    
      - [**IM および Web 会議セッションをアーカイブする**]

6.  また、[**アーカイブ設定 - グローバル**] ページで、次の操作を実行します。
    
      - アーカイブを使用できない場合にアクティビティをブロックするには、[**アーカイブ失敗時はインスタント メッセージング (IM) または Web 会議セッションを禁止する**] チェック ボックスをオンにします。
    
      - Microsoft Exchange Server を使用してアーカイブデータを保存するには、[ **Microsoft exchange 統合** ] チェックボックスをオンにします。
    
      - データの削除を有効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにし、次のどちらかの操作を実行します。
        
          - 一定の日数が経過した後に削除されるよう指定するには、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックして、日数を指定します。
        
          - エクスポートされたアーカイブ データに削除対象を限定するには、[**エクスポートされたアーカイブ データのみを削除する**] をクリックします。

7.  [**確定**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: アーカイブオプションをグローバルレベルで構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Archiving options at the global level
ms:assetid: bfe415f7-2abf-41ee-a1cb-cf48b2d59c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205233(v=OCS.15)
ms:contentKeyID: 48185303
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21653d38c7b56fa93395422a2e20906afd0cc3e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-at-the-global-level-in-lync-server-2013"></a>Lync Server 2013 のグローバルレベルでアーカイブオプションを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-10_

トポロジにアーカイブを追加してトポロジを公開すると、Lync Server によってアーカイブ用のグローバル構成が作成されます。 既定では、グローバル構成ではアーカイブオプションが有効になっていません。 グローバル構成より優先されるサイト構成またはプール構成を設定しない限り、グローバル構成は、展開全体に対して有効化されるオプションを制御します。

アーカイブ構成のしくみ (グローバル、サイト、プールの構成の階層など) について詳しくは、「計画ドキュメント、展開ドキュメント、または運用ドキュメント」の「 [Lync Server 2013 でのアーカイブの動作](lync-server-2013-how-archiving-works.md)」をご覧ください。.

<div>


> [!NOTE]  
> アーカイブを有効にする前に、アーカイブ構成ですべての適切なオプションを指定する必要があります。



</div>

<div>

## <a name="to-configure-archiving-options-at-the-global-level"></a>グローバルレベルでアーカイブオプションを構成するには

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server 2013 コントロールパネルを開きます。 Lync Server 2013 コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。

4.  [**アーカイブ構成**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] の順にクリックします。

5.  [**編集アーカイブ設定 - Global**] の [**アーカイブ設定**] ボックスの一覧で、次のいずれかのアーカイブ オプションを選択します。
    
      - **[アーカイブを無効にする]**
    
      - **[IM セッションをアーカイブする]**
    
      - **[IM および Web 会議セッションをアーカイブする]**

6.  また、[**アーカイブ設定 - グローバル**] ページで、次の操作を実行します。
    
      - アーカイブを使用できない場合にアクティビティをブロックするには、[**アーカイブ失敗時はインスタント メッセージング (IM) または Web 会議セッションを禁止する**] チェック ボックスをオンにします。
    
      - アーカイブデータの保存に Microsoft Exchange Server を使用するには、[ **Microsoft exchange 統合**] チェックボックスをオンにします。
    
      - データの削除を有効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにし、次のどちらかの操作を実行します。
        
          - 一定の日数が経過した後に削除されるよう指定するには、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックし、日数を指定します。
        
          - エクスポートされたアーカイブ データに削除対象を限定するには、[**エクスポートされたアーカイブ データのみを削除する**] をクリックします。

7.  [**確定**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>


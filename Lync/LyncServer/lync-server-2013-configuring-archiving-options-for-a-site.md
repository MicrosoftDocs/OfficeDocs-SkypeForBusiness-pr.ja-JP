---
title: 'Lync Server 2013: サイトのアーカイブオプションの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options for a site
ms:assetid: 59b48fd9-d5fc-40b4-abae-e9cf89ee5573
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204930(v=OCS.15)
ms:contentKeyID: 48184247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5f081cd802bc0427748244890816a7708c82e47
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-site-in-lync-server-2013"></a>Lync Server 2013 でのサイトのアーカイブオプションの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-09_

個々のサイトに適用するアーカイブ オプションを指定できます。それには、それらのサイトの各々について、アーカイブ構成でオプションを作成して構成します。サイト構成は、そのサイト構成で指定されたサイトについてのみ、グローバル構成よりも優先されます。プール構成はサイト構成よりも優先されます。

グローバル構成、サイト構成、およびプール構成の階層など、アーカイブ構成のしくみの詳細については、「計画」、「展開」、または「操作」のドキュメントの「 [Lync Server 2013 でのアーカイブの仕組み](lync-server-2013-how-archiving-works.md)」を参照してください。

<div>


> [!NOTE]  
> アーカイブを有効にするには、その前にアーカイブ構成で適切なオプションをすべて指定する必要があります。



</div>

<div>


> [!IMPORTANT]  
> アーカイブを有効にするには、内部または外部の通信のアーカイブを管理するためのアーカイブ ポリシーを、グローバル レベル (必要に応じて、サイト レベルおよびユーザー レベル) で指定する必要があります。 ユーザー レベルのポリシーを構成する場合は、ユーザー ポリシーをユーザーに割り当てる必要もあります。 アーカイブポリシーの作成および構成の詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Lync Server 2013 での内部および外部通信のアーカイブの管理</A>」を参照してください。



</div>

<div>

## <a name="to-configure-archiving-options-at-the-site-level"></a>サイト レベルでアーカイブ オプションを構成するには

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server 2013 コントロールパネルを開きます。 Lync Server 2013 コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。

4.  [**アーカイブ構成**] ページで、[**新規作成**] をクリックし、[**サイト構成**] をクリックします。

5.  [**サイトの選択**] で、アーカイブ用に構成するサイトを選択します。

6.  [**新しいアーカイブ設定**] の [**アーカイブ設定**] ドロップダウン リスト ボックスで、次のいずれかの操作を実行します。
    
      - インスタント メッセージング (IM) セッションのアーカイブだけを有効にするには、[**IM セッションをアーカイブする**] をクリックします。
    
      - IM セッションと会議の両方のアーカイブを有効にするには、[**IM および Web 会議セッションをアーカイブする**] をクリックします。
    
      - ポリシーのアーカイブを無効にするには、[**アーカイブを無効にする**] をクリックします。

7.  [**新しいアーカイブ設定**] で、次の操作も実行します。
    
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


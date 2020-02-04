---
title: 'Lync Server 2013: サイトのアーカイブオプションを構成する'
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
ms.openlocfilehash: cb2b70242388ca00a7bf43ec535ae1231fb77644
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734987"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-site-in-lync-server-2013"></a>Lync Server 2013 でサイトのアーカイブオプションを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-09_

特定のサイトに適用されるアーカイブオプションを指定するには、各サイトのアーカイブ構成でオプションを作成して構成します。 サイト構成はグローバル構成より優先されますが、その対象はサイト構成に指定されているサイトに限定されます。 プール構成がサイト構成を上書きする

アーカイブ構成のしくみ (グローバル、サイト、プール構成の階層など) について詳しくは、「計画ドキュメント、展開ドキュメント、または運用ドキュメント」の「 [Lync Server 2013 でのアーカイブの動作](lync-server-2013-how-archiving-works.md)」をご覧ください。

<div>


> [!NOTE]  
> アーカイブを有効にする前に、アーカイブ構成ですべての適切なオプションを指定する必要があります。



</div>

<div>


> [!IMPORTANT]  
> アーカイブを有効にするには、内部または外部の通信のアーカイブを管理するためのアーカイブ ポリシーを、グローバル レベル (必要に応じて、サイト レベルおよびユーザー レベル) で指定する必要があります。 ユーザー レベルのポリシーを構成する場合は、ユーザー ポリシーをユーザーに割り当てる必要もあります。 アーカイブポリシーの作成と構成の詳細については、「運用ドキュメントの「 <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Lync Server 2013 での社内および社外の通信のアーカイブを管理する</A>」を参照してください。



</div>

<div>

## <a name="to-configure-archiving-options-at-the-site-level"></a>サイトレベルでアーカイブオプションを構成するには

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server 2013 コントロールパネルを開きます。 Lync Server 2013 コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。

4.  [**アーカイブ構成**] ページで、[**新規作成**] をクリックし、[**サイト構成**] をクリックします。

5.  [**サイトの選択**] で、アーカイブ用に構成するサイトを選択します。

6.  [**新しいアーカイブ設定**] の [**アーカイブ設定**] ボックスの一覧で、次のいずれかの操作を実行します。
    
      - インスタント メッセージング (IM) セッションのアーカイブだけを有効にするには、[**IM セッションをアーカイブする**] をクリックします。
    
      - IM セッションと会議の両方のアーカイブを有効にするには、[**IM および Web 会議セッションをアーカイブする**] をクリックします。
    
      - ポリシーのアーカイブを無効にするには、[**アーカイブを無効にする**] をクリックします。

7.  [**新しいアーカイブ設定**] で、次の操作も実行します。
    
      - アーカイブを使用できない場合にアクティビティをブロックするには、[**アーカイブ失敗時はインスタント メッセージング (IM) または Web 会議セッションを禁止する**] チェック ボックスをオンにします。
    
      - アーカイブデータの保存に Microsoft Exchange Server を使用するには、[ **Microsoft exchange 統合**] チェックボックスをオンにします。
    
      - データの削除を有効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにし、次のどちらかの操作を実行します。
        
          - 一定の日数が経過した後に削除されるよう指定するには、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックし、日数を指定します。
        
          - エクスポートされたアーカイブ データに削除対象を限定するには、[**エクスポートされたアーカイブ データのみを削除する**] をクリックします。

8.  [**確定**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>


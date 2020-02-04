---
title: IM または会議セッションのアーカイブを有効または無効にする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling Archiving of IM or conferencing sessions
ms:assetid: aa4b5983-dbe1-4d64-8a18-fe2c33994e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182567(v=OCS.15)
ms:contentKeyID: 48185104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be9782bfa73f30fbefaec0a51d91024b3c40ba55
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-archiving-of-im-or-conferencing-sessions-in-lync-server-2013"></a>Lync Server 2013 での IM または会議セッションのアーカイブを有効または無効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-10_

Lync Server 2013 コントロールパネルで、[アーカイブ構成] を使って、IM、会議セッション、またはその両方のアーカイブを有効または無効にします。 これには、次のアーカイブ構成が含まれます。

  - Lync Server 2013 を展開するときに既定で作成されるグローバル構成。

  - 作成および使用して、特定のサイトまたはプールに対するアーカイブの実装方法を指定することができる、オプションのサイトレベルとプールレベルの構成。

アーカイブの展開時にアーカイブ構成を最初に設定しましたが、展開後に構成の変更、追加、削除を行うことができます。 アーカイブ構成の実装方法について詳しくは、「指定できるオプションやアーカイブ構成の階層」をご覧ください。「計画ドキュメント、展開ドキュメント、または操作のドキュメントでの[Lync Server 2013 でのアーカイブの動作](lync-server-2013-how-archiving-works.md)」を参照してください。

<div>


> [!NOTE]
> アーカイブを使用するには、内部通信のアーカイブを有効にするか、外部通信を有効にするか、または Lync Server 2013 を使用しているユーザーに対してアーカイブを有効にするかを指定するようにアーカイブポリシーを構成する必要があります。 既定では、内部または外部の通信でアーカイブは有効になっていません。 すべてのポリシーでアーカイブを有効にする前に、このセクションで説明するように、展開に適したアーカイブ構成を指定し、必要に応じて特定のサイトとプールを指定する必要があります。 アーカイブを有効にする方法の詳細については、展開ドキュメントの「 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013 でアーカイブポリシーを構成して割り当てる</A>」を参照してください。<BR>Microsoft Exchange 統合を使用して Exchange 2013 サーバー上のアーカイブデータとファイルを保存し、すべてのユーザーが Exchange 2013 サーバー上にある場合は、アーカイブを展開した後に、SQL Server データベースの構成を削除する必要があります。を選びます。 この操作を行うには、トポロジビルダーを使用する必要があります。 詳細については、「運用ドキュメントの「 <A href="lync-server-2013-changing-archiving-database-options.md">Lync Server 2013 でアーカイブデータベースのオプションを変更する</A>」を参照してください。



</div>

<div>

## <a name="to-enable-or-disable-archiving-of-im-or-conferencing-sessions"></a>IM または会議セッションのアーカイブを有効または無効にするには

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。

4.  アーカイブ構成の一覧から適切なグローバル、サイト、またはプール構成を選択し、[**編集**] をクリックし、[**詳細の表示**] をクリックしてから次の操作を実行します。
    
      - インスタント メッセージング (IM) セッションのアーカイブだけを有効にするには、[**IM セッションをアーカイブする**] をクリックします。
    
      - IM セッションと会議の両方のアーカイブを有効にするには、[**IM および Web 会議セッションをアーカイブする**] をクリックします。
    
      - ポリシーのアーカイブを無効にするには、[**アーカイブを無効にする**] をクリックします。

5.  [**コミット**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[組織、サイト、およびプールの Lync Server 2013 でアーカイブ構成オプションを管理する](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
[Lync Server 2013 でアーカイブポリシーを構成して割り当てる](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


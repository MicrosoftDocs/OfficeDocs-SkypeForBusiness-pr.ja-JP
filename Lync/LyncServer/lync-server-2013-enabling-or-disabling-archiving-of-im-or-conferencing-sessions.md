---
title: IM または電話会議セッションのアーカイブを有効または無効にする
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
ms.openlocfilehash: e97c88214d5480c36bbff88890e6960e930dd937
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-archiving-of-im-or-conferencing-sessions-in-lync-server-2013"></a>Lync Server 2013 での IM または電話会議セッションのアーカイブを有効または無効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-10_

Lync Server 2013 コントロールパネルでは、アーカイブ構成を使用して、IM、会議セッション、またはその両方のアーカイブを有効または無効にします。 これには、次のアーカイブ構成が含まれます。

  - Lync Server 2013 を展開するときに既定で作成されるグローバル構成。

  - 特定のサイトまたはプールに対するアーカイブの実装方法を指定するために作成して使用できる、オプションのサイトレベルおよびプールレベルのポリシー。

アーカイブ構成は、最初はアーカイブの展開時に設定しますが、展開後に変更、追加、および削除できます。 指定できるオプションやアーカイブ構成の階層など、アーカイブ構成の実装方法の詳細については、「計画」のドキュメント、「展開」、または「操作」のドキュメントの「 [Lync Server 2013 でのアーカイブの仕組み](lync-server-2013-how-archiving-works.md)」を参照してください。

<div>


> [!NOTE]
> アーカイブを使用するには、アーカイブポリシーを構成して、内部通信、外部通信、または Lync Server 2013 に所属するユーザーの両方に対してアーカイブを有効にするかどうかを指定する必要があります。 既定では、アーカイブは内部通信および外部通信のどちらに対しても有効になっていません。 ポリシーでアーカイブを有効にする前に、このセクションの説明に従って、展開に対して、また必要に応じて特定のサイトやプールに対して、適切なアーカイブ構成を指定する必要があります。 アーカイブを有効にする方法の詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013 でのアーカイブポリシーの構成と割り当て</A>」を参照してください。<BR>Microsoft Exchange 統合を使用してアーカイブデータおよびファイルを Exchange 2013 サーバーに保存し、すべてのユーザーが Exchange 2013 サーバーに所属している場合は、アーカイブを展開した後に、SQL Server データベース構成を削除する必要があります。トポロジから。 これを行うには、トポロジビルダーを使用する必要があります。 詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-changing-archiving-database-options.md">Lync Server 2013 でのアーカイブデータベースオプションの変更</A>」を参照してください。



</div>

<div>

## <a name="to-enable-or-disable-archiving-of-im-or-conferencing-sessions"></a>IM または電話会議セッションのアーカイブを有効または無効にするには

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。

4.  アーカイブ構成の一覧から適切なグローバル、サイト、またはプール構成を選択し、[**編集**]、[**詳細の表示**] の順にクリックして、次の操作を行います。
    
      - インスタント メッセージング (IM) セッションのアーカイブだけを有効にするには、**[IM セッションのアーカイブ]** をクリックします。
    
      - IM セッションと会議の両方のアーカイブを有効にするには、[**IM および Web 会議セッションをアーカイブする**] をクリックします。
    
      - ポリシーのアーカイブを無効にするには、[**アーカイブを無効にする**] をクリックします。

5.  **[確定]** をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[組織、サイト、およびプールの Lync Server 2013 でのアーカイブ構成オプションの管理](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
[Lync Server 2013 でのアーカイブポリシーの構成と割り当て](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


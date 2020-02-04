---
title: 'Lync Server 2013: 組織、サイト、プールのアーカイブ構成オプションを管理する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Archiving configuration options for your organization, sites, and pools
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48183830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59db9765b9e9ee0b453268ea9c22d897f10ba662
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a>組織、サイト、およびプールの Lync Server 2013 でアーカイブ構成オプションを管理する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

Lync Server 2013 コントロールパネルで、アーカイブの実装方法を指定するには、アーカイブ構成を使います。 これには、次のアーカイブ構成が含まれます。

  - Lync Server 2013 を展開するときに既定で作成されるグローバル構成。

  - 作成および使用して、特定のサイトまたはプールに対するアーカイブの実装方法を指定することができる、オプションのサイトレベルとプールレベルの構成。

アーカイブの展開時にアーカイブ構成を最初に設定しましたが、展開後に構成の変更、追加、削除を行うことができます。 Lync Server 2013 コントロールパネルで、[**アーカイブと監視**] グループの [**アーカイブの構成**] ページを使用して、グローバルレベル、サイトレベル、プールレベルで構成を管理できます。 アーカイブ構成の実装方法について詳しくは、「指定できるオプションやアーカイブ構成の階層」をご覧ください。計画ドキュメント、展開ドキュメント、または運用マニュアルの「 [Lync Server 2013 でのアーカイブの動作](lync-server-2013-how-archiving-works.md)」を参照してください。

<div>


> [!NOTE]  
> アーカイブを使用するには、Lync Server 2013 に所属しているすべてのユーザーに対して、内部通信のアーカイブを有効にするか、外部通信を有効にするかを指定するようにアーカイブポリシーを構成する必要があります。 既定では、内部または外部の通信でアーカイブは有効になっていません。 Microsoft Exchange 統合を使用している場合は、exchange 2013 で、メールボックスがインプレース保持されているすべてのユーザーのアーカイブをサポートするように Exchange 2013 を有効にして構成する必要があります。<BR>アーカイブを有効にする前に、このセクションで説明するように、展開に適したアーカイブ構成を指定し、必要に応じて特定のサイトとプールを指定する必要があります。 アーカイブを有効にする方法の詳細については、展開ドキュメントの「 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013 でアーカイブポリシーを構成して割り当てる</A>」を参照してください。



</div>

**Windows PowerShell コマンドレットを使用してアーカイブ構成情報を表示するには**

  - Windows PowerShell と**CsArchivingConfiguration**コマンドレットを使用して、アーカイブ構成情報を表示できます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。
    
    Lync Server 管理シェルで、次のコマンドを使用して、すべてのアーカイブ構成設定に関する情報を表示します。
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 でアーカイブ構成を作成して、特定のサイトまたはプールのアーカイブを管理する](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [Lync Server 2013 での IM または会議セッションのアーカイブを有効または無効にする](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [Lync Server 2013 でアーカイブデータの削除を有効または無効にする](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [アーカイブに失敗した場合に IM および web 会議セッションをブロックまたは許可するための、Lync Server 2013 でのクリティカルモードの有効化または無効化](lync-server-2013-enable-disable-critical-mode.md)

  - [Lync Server 2013 でのフェデレーション パートナーに対するアーカイブ免責事項の送信の有効化または無効化](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Lync Server 2013 と Exchange ストレージの統合を有効または無効にする](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [Lync Server 2013 でアーカイブ構成を削除する](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 アーカイブの管理](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: 組織、サイト、およびプールのアーカイブ構成オプションの管理'
description: 'Lync Server 2013: 組織、サイト、およびプールのアーカイブ構成オプションを管理します。'
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
ms.openlocfilehash: 41eca448fcb9863f117bcb7e52e3290270fefa47
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576623"
---
# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a>組織、サイト、およびプールの Lync Server 2013 でのアーカイブ構成オプションの管理

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

Lync Server 2013 コントロールパネルでは、アーカイブ構成を使用してアーカイブの実装方法を指定します。 これには、次のアーカイブ構成が含まれます。

  - Lync Server 2013 を展開するときに既定で作成されるグローバル構成。

  - 特定のサイトまたはプールに対するアーカイブの実装方法を指定するために作成して使用できる、オプションのサイトレベルおよびプールレベルのポリシー。

アーカイブ構成は、最初はアーカイブの展開時に設定しますが、展開後に変更、追加、および削除できます。 Lync Server 2013 コントロールパネルでは、**アーカイブおよび監視**グループの [**アーカイブ構成**] ページを使用して、グローバルレベル、サイトレベル、およびプールレベルで構成を管理できます。 指定できるオプションやアーカイブ構成の階層など、アーカイブ構成の実装方法の詳細については、「計画」、「展開」、または「操作」のドキュメントの「 [Lync Server 2013 でのアーカイブの仕組み](lync-server-2013-how-archiving-works.md) 」を参照してください。

<div>


> [!NOTE]  
> アーカイブを使用するには、アーカイブポリシーを構成して、Lync Server 2013 に所属するすべてのユーザーに対して、内部通信、外部通信、または両方のアーカイブを有効にするかどうかを指定する必要があります。 既定では、アーカイブは内部通信および外部通信のどちらに対しても有効になっていません。 Microsoft Exchange 統合を使用する場合は、exchange 2013 に所属するすべてのユーザーのアーカイブをサポートするように Exchange 2013 を有効にし、構成する必要があります。メールボックスが In-Place 保持に配置されています。<BR>アーカイブを有効にする前に、このセクションの説明に従って、展開および必要に応じて特定のサイトやプールに対して適切なアーカイブ構成を指定する必要があります。 アーカイブを有効にする方法の詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013 でのアーカイブポリシーの構成と割り当て</A> 」を参照してください。



</div>

**Windows PowerShell コマンドレットを使用してアーカイブ構成情報を表示するには**

  - Windows PowerShell と **set-csarchivingconfiguration** コマンドレットを使用して、アーカイブ構成情報を表示できます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。
    
    Lync Server 管理シェルで、次のコマンドを使用して、すべてのアーカイブ構成設定に関する情報を表示します。
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 でのアーカイブ構成を作成して、特定のサイトまたはプールのアーカイブを管理する](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [Lync Server 2013 での IM または電話会議セッションのアーカイブを有効または無効にする](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [Lync Server 2013 でのアーカイブされたデータの削除を有効または無効にする](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [アーカイブが失敗した場合に IM および web 会議セッションを禁止または許可するために Lync Server 2013 の重要モードを有効または無効にする](lync-server-2013-enable-disable-critical-mode.md)

  - [Lync Server 2013 でのフェデレーションパートナーへのアーカイブ免責事項の送信を有効または無効にする](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Lync Server 2013 と Exchange ストレージの統合を有効または無効にする](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [Lync Server 2013 でのアーカイブ構成の削除](lync-server-2013-deleting-an-archiving-configuration.md)

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


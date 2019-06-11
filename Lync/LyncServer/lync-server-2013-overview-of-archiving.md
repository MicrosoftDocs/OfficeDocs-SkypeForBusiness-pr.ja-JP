---
title: 'Lync Server 2013: アーカイブの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Archiving
ms:assetid: 1e3c2ef1-f561-4f57-8b6a-7d78addc1ed1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204729(v=OCS.15)
ms:contentKeyID: 48183570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba4aa88f94f0e32b35ab3fc5f71359e5a1c00d99
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-archiving-in-lync-server-2013"></a>Lync Server 2013 のアーカイブの概要

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-09-30_

Lync server 2013 でのアーカイブは、Lync Server 2013 経由で送信された通信をアーカイブするための手段を提供します。

最初の Lync Server 2013 の展開の一部としてアーカイブを実装することも、既存の展開に追加することもできます。 Lync Server 2013 アーカイブデータベース (SQL Server データベース) を使用してアーカイブデータを保存するには、トポロジビルダーを使用してデータベースをトポロジに追加してから、もう一度トポロジを公開します。 すべてのユーザーが Exchange 2013 を使用していて、メールボックスがインプレース保持されている場合、トポロジを更新する必要はありませんが、Microsoft Exchange の統合を有効にして、アーカイブされたデータを Exchange 2013 に保存する必要があります。

アーカイブを実装するときに、アーカイブの内容を指定するように構成します。 既定では、何もアーカイブされません。 アーカイブの構成と管理は、Lync Server 2013 コントロールパネルを使用して行います。 内部通信、外部通信、またはその両方のアーカイブを実装することができます。 組織全体のアーカイブ設定を構成することができます。また、必要に応じて、特定のサイト、特定のプール、特定のユーザーとユーザーグループのアーカイブ設定を構成することもできます。 組織で適切なオプションを決定する方法の詳細については、計画ドキュメントの「 [Lync Server 2013 でアーカイブするための要件を定義](lync-server-2013-defining-your-requirements-for-archiving.md)する」を参照してください。 アーカイブポリシーと構成の実装方法、およびアーカイブできない情報の詳細については、「計画のドキュメント、展開ドキュメント、または「 [Lync Server 2013 でのアーカイブの動作](lync-server-2013-how-archiving-works.md)」を参照してください。操作のドキュメント。

</div>

<span> </span>

</div>

</div>

</div>


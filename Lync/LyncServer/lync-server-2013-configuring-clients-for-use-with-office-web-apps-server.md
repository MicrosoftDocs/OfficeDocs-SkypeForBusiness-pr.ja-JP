---
title: 'Lync Server 2013: Office Web Apps サーバーで使用するためのクライアントの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring clients for use with Office Web Apps Server
ms:assetid: e5eaead7-0b32-42fb-97eb-ca203af59a9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205339(v=OCS.15)
ms:contentKeyID: 48185668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10ec5ddaca5a8409a18504cb73912d107c9a6455
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146970"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a>Office Web Apps サーバーで使用する Lync Server 2013 のクライアントの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-25_

ユーザーが Office Web App Server のすべての機能を使用できるようにするには、これらのユーザーを Microsoft Lync 2013 にアップグレードする必要があります。実際の PowerPoint プレゼンテーションに依存しない PowerPoint スライドをスクロールするなどの操作を、Lync 2013 のユーザーのみが行うことができます。 (つまり、これらのユーザーは、実際のプレゼンテーションに影響を与えることなく、いつでもプレゼンテーションの任意のスライドを見ることができます)。Lync 2013 を使用していないユーザーは、引き続きオンライン会議に参加して PowerPoint プレゼンテーションを表示することができます。ただし、これらのユーザーは、スライドを個別にスクロールすることはできません。また、スライドの切り替えを表示したり、埋め込みビデオを表示したりすることもできなくなります。

これらの機能は、Lync 2013 のユーザーがいつでも利用できることに注意してください。これは、PowerPoint 発表者が Microsoft Lync 2010 を実行している場合でも同様です。 PowerPoint プレゼンテーションが Lync 2010 を実行しているユーザーによってホストされている場合、lync Server 2013 は Office Web Apps サーバーと連携して、Lync 2013 ユーザーがそのプレゼンテーションの Office Web Apps サーバーバージョンを表示できるようにします。 Office Web Apps サーバーでは、Lync 2013 以外のクライアントを実行しているユーザーには PowerPoint services は提供されません。 代わりに、これらのユーザーは、Microsoft Lync Server 2010 の場合と同じ方法で、会議サーバーサービスに接続し、PowerPoint プレゼンテーションを表示します。 これは、これらのユーザーが、Lync Server 2010 で提供される制限のある機能にのみアクセスできることも意味します。

Office Web Apps サーバーにはクライアント構成は必要ありませんが (ユーザーを Lync 2013 にアップグレードすることはできません)、電話会議の出席者を Internet Explorer 9 にアップグレードすることをお勧めします。 電話会議には、Internet Explorer 8 を使用してアクセスできますが、その Web ブラウザーを使用するにはいくつかの制限があります。 たとえば、Internet Explorer 8 のユーザーは、PowerPoint のステージをユーザー設定のサイズに変更することはできません。代わりに、3つの定義済みステージサイズのうちの1つを使用するように制限されます。 同様に、Internet Explorer 8 ユーザーがメディアファイルを再生することはできません。

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Office Web Apps サーバーを使用するためのクライアントの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring clients for use with Office Web Apps Server
ms:assetid: e5eaead7-0b32-42fb-97eb-ca203af59a9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205339(v=OCS.15)
ms:contentKeyID: 48185668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 263f53b61aa609c4385af2a9646bf84da2dea3cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a>Lync Server 2013 のクライアントで Office Web Apps サーバーを使用するように構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-25_

ユーザーが Office Web App Server の全機能を使用できるようにする場合は、これらのユーザーを Microsoft Lync 2013 にアップグレードする必要があります。Lync 2013 のユーザーのみが、実際の PowerPoint プレゼンテーションに依存しない PowerPoint スライドをスクロールして、そのような作業を行うことができます。 (つまり、これらのユーザーはプレゼンテーションの任意のスライドをいつでも見ることができ、実際のプレゼンテーションに影響を及ぼすことはありません)。Lync 2013 を使っていないユーザーは、引き続きオンライン会議に参加し、PowerPoint プレゼンテーションを表示することができます。ただし、それらのユーザーはスライドを個別にスクロールすることはできません。また、スライドの画面切り替えを表示したり、埋め込みビデオを表示したりすることはできません。

これらの機能は、Lync 2013 のユーザーがいつでも利用できることに注意してください。これは、PowerPoint の発表者が Microsoft Lync 2010 を実行している場合でも同様です。 PowerPoint プレゼンテーションが Lync 2010 を実行しているユーザーによってホストされている場合、lync Server 2013 では Office Web Apps サーバーを使用して、Lync 2013 ユーザーに Office Web Apps サーバーバージョンのプレゼンテーションが表示されるようにします。 Office Web Apps サーバーは、Lync 2013 以外のクライアントを実行しているユーザー向けの PowerPoint サービスを提供していません。 代わりに、これらのユーザーは会議サーバーサービスに接続し、Microsoft Lync Server 2010 と同じように PowerPoint プレゼンテーションを表示します。 また、これらのユーザーは、Lync Server 2010 によって提供される制限のある機能にのみアクセスできます。

Office Web Apps Server にはクライアントの構成は必要ありませんが (ユーザーを Lync 2013 にアップグレードすることはできません)、会議の出席者が Internet Explorer 9 にアップグレードすることをお勧めします。 電話会議には、Internet Explorer 8 を使ってアクセスできますが、その Web ブラウザーの使用にはいくつかの制限があります。 たとえば、Internet Explorer 8 のユーザーは、PowerPoint ステージのサイズをユーザー設定のサイズに変更することはできません。代わりに、3つの定義済みステージサイズのいずれかを使用するように制限されます。 同様に、Internet Explorer 8 ユーザーがメディアファイルを再生することはできません。

</div>

<span> </span>

</div>

</div>

</div>


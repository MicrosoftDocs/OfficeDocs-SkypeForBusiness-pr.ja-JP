---
title: 'Lync Server 2013: 場所データベースの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the location database
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398679(v=OCS.15)
ms:contentKeyID: 48184704
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ff565c1d884fe2af9a49da6798e8c3e52cb38da
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-location-database-in-lync-server-2013"></a>Lync Server 2013 で場所データベースを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-17_

クライアントがネットワーク内の各自の場所を自動検出できるようにするには、まず場所データベースを構成する必要があります。場所データベースを構成しておらず、場所のポリシーで [**場所は必須**] が [**はい**] または [**免責事項**] に設定されている場合、ユーザーは場所を手動で入力するよう求められます。

場所データベースを構成するには、次のタスクを実行します。

1.  ネットワーク要素と場所のマッピングをデータベースに設定します。 緊急位置識別番号 (ELIN) ゲートウェイを使用する場合は、[会社\<名\> ] フィールドに ELIN を含める必要があります。

2.  E9-1-1 サービス プロバイダーで保持されている主要道路住所案内 (MSAG) と照らし合わせて住所を確認します。

3.  更新したデータベースを公開します。

<div>


> [!NOTE]  
> または、場所データベースの代わりに使用できるセカンダリ場所データベースを定義することもできます。 詳細については、「 <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a Secondary Location Information service In Lync Server 2013</A>」を参照してください。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 で場所データベースを設定する](lync-server-2013-populate-the-location-database.md)

  - [Lync Server 2013 での住所の検証](lync-server-2013-validate-addresses.md)

  - [Lync Server 2013 からの場所データベースの公開](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


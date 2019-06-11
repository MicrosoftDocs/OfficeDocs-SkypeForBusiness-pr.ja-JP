---
title: 'Lync Server 2013: 場所データベースを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the location database
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398679(v=OCS.15)
ms:contentKeyID: 48184704
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15a9456cc79e02735fe94c24748674944722b49c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-location-database-in-lync-server-2013"></a>Configure the location database in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-17_

クライアントがネットワーク内の各自の場所を自動検出できるようにするには、まず場所データベースを構成する必要があります。 場所のデータベースを構成せず、場所のポリシーで**必要な場所**が **[はい]** または [**免責**] に設定されている場合は、場所を手動で入力するように求められます。

場所データベースを構成するには、次のタスクを実行します。

1.  ネットワーク要素と場所のマッピングをデータベースに設定します。 緊急対応の所在地識別番号 (ELIN) を使用している場合、[会社\<名\> ] フィールドに ELIN を含める必要があります。

2.  E9-1-1 サービス プロバイダーで保持されている主要道路住所案内 (MSAG) と照らし合わせて住所を確認します。

3.  更新したデータベースを公開します。

<div>


> [!NOTE]  
> または、場所データベースの配置で使用できるセカンダリの場所ソースデータベースを定義することもできます。 詳細については、「 <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Lync Server 2013 でセカンダリ場所情報サービスを構成する</A>」を参照してください。



</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 で位置情報データベースを設定する](lync-server-2013-populate-the-location-database.md)

  - [Lync Server 2013 で住所を検証する](lync-server-2013-validate-addresses.md)

  - [Lync Server 2013 からロケーションデータベースを発行する](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


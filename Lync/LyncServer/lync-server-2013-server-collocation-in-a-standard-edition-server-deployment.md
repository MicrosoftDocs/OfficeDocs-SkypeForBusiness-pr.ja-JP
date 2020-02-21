---
title: Standard Edition サーバー展開における Lync Server 2013 サーバーの併置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in a Standard Edition server deployment
ms:assetid: 0763ffab-4fd6-463a-8e62-d97876b376d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398131(v=OCS.15)
ms:contentKeyID: 48183314
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1122605aabea32d86fbacd1f23675fcdef687539
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a>Lync Server 2013 の Standard Edition サーバー展開でのサーバーの併置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-01-20_

このセクションでは、Lync Server 2013 Standard Edition サーバー展開で併置できるサーバーの役割、データベース、およびファイル共有について説明します。

<div>

## <a name="server-roles"></a>サーバーの役割

Lync Server 2013 では、音声ビデオ会議サービス、仲介サービス、監視、およびアーカイブが Standard Edition サーバーに併置されていますが、これを有効にするには追加の構成が必要です。 仲介サービスを別のサーバーに展開することを選択できます。

信頼されたアプリケーションサーバーと Standard Edition サーバーを併置して検索することができます。

次のサーバーの役割は、それぞれ別のコンピューターに展開する必要があります。

  - ディレクター

  - エッジ サーバー

  - 仲介サーバー (Standard Edition サーバーと併置されていない場合)

  - Office Web Apps サーバー

</div>

<div>

## <a name="databases"></a>Databases

既定では、SQL Server Express バックエンドデータベースは Standard Edition サーバーに併置されています。 別のコンピューターに移動することはできません。 1つの例外を除き、Standard Edition サーバーで他のデータベースを併置することはできません。 常設チャットサーバーを Standard Edition サーバーに展開する場合は、同一の Standard Edition サーバーで常設チャットデータベースと常設チャットコンプライアンスデータベースを併置して検索できます。

1つのデータベースサーバー上で、次の各データベースを併置できます。

  - 監視データベース

  - アーカイブ データベース

  - Enterprise Edition フロントエンドプールのバックエンドデータベース

これらのデータベースのいずれかまたはすべてを1つの SQL インスタンスで併置したり、それぞれに個別の SQL インスタンスを使用したりするには、次のような制限があります。

  - 各 SQL インスタンスには、1つのバックエンドデータベース (Enterprise Edition フロントエンドプールの場合)、単一の監視データベース、単一のアーカイブデータベース、単一の常設チャットデータベース、および単一の常設チャットコンプライアンスデータベースのみを含めることができます。

  - データベースサーバーは、複数の Enterprise Edition フロントエンドプール、アーカイブを実行している1台のサーバー、監視を実行している1台のサーバー、単一の常設チャットデータベース、および単一の常設チャットコンプライアンスデータベースをサポートできませんが、それぞれの1つをサポートできます。データベースが SQL Server の同じインスタンスを使用するか、SQL Server の別のインスタンスを使用するかに関係なく、

このセクションで後述するように、ファイル共有をデータベースと併置できます。

<div>


> [!NOTE]  
> Lync Server 2013 では、展開内の一部またはすべてのユーザーについて、監視およびアーカイブストレージと Exchange 2013 ストレージを統合するオプションがあります。 Exchange ストレージと同じサーバーに Lync Server またはコンポーネントを実行しているサーバーを展開することはできません。



</div>

<div>


> [!IMPORTANT]  
> データベースの併置がサポートされていても、データベースのサイズはすぐに大きくなることがあります。 たとえば、アーカイブ データベースと他のデータベースを併置することを考慮するときには、数名以上のユーザーのメッセージをアーカイブすると、アーカイブ データベースが必要とするディスク容量が非常に大きくなる可能性があることに注意してください。 このため、エンタープライズプールのバックエンドデータベースを使用して、アーカイブデータベース、常設チャットデータベース、および常設チャットコンプライアンスデータベースなど、複数のデータベースを併置することはお勧めしません。



</div>

</div>

<div>

## <a name="file-shares"></a>ファイル共有

ファイル共有は、別個のサーバーを使用することも、次のいくつか、またはすべてと同じサーバーに併置することもできます。

  - データベース サーバー (Enterprise Edition フロントエンド プールのバック エンド サーバーを含む)

  - アーカイブ データベース

  - 監視データベース

  - 常設チャットデータベース

  - 常設チャットコンプライアンスデータベース

単一のファイル共有を複数のフロントエンド プール、および複数の Standard Edition サーバーで使用できます (これらのプールやサーバーはすべて同じサイトに存在)。

<div>


> [!NOTE]  
> Lync Server 2013 の監視およびアーカイブでは、Lync Server のファイル共有を Standard Edition サーバーとして使用します。



</div>

</div>

<div>

## <a name="other-components"></a>その他のコンポーネント

Lync server 2013 コンポーネントではないリバースプロキシサーバーを併置することはできませんが、任意の Lync Server 2013 サーバーの役割を持つフェデレーションユーザーに対して web コンテンツの共有をサポートする必要がある場合は、展開で必要になります。 ただし、他のアプリケーションで使用されている組織内の既存のリバースプロキシサーバーのサポートを構成することによって、Lync Server 2013 展開のリバースプロキシサポートを実装できます。

任意の Exchange UM コンポーネントまたは SharePoint コンポーネントを任意の Lync Server 2013 の役割で併置することはできません。

</div>

</div>

<span> </span>

</div>

</div>

</div>


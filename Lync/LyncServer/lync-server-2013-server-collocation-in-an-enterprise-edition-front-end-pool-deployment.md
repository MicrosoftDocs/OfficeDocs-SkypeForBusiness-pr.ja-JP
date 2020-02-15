---
title: Enterprise Edition フロントエンドプール展開における Lync Server 2013 サーバーの併置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74afcdd9212ebced9d93f0f699b90dd7a89edefd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a>Lync Server 2013 の Enterprise Edition フロントエンドプール展開でのサーバーの併置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-11-11_

このセクションでは、Lync Server 2013 のフロントエンドプール展開で併置できるサーバーの役割、データベース、およびファイル共有について説明します。

<div>

## <a name="server-roles"></a>サーバーの役割

Lync Server 2013 では、音声ビデオ会議サービス、仲介サービス、監視、およびアーカイブはフロントエンドサーバーに併置されていますが、これを有効にするには追加の構成が必要です。 仲介サーバーは、フロントエンド サーバーと併置しない場合、スタンドアロンの仲介サーバーとして別のコンピューター上に展開できます。

信頼されたアプリケーション サーバーは、フロントエンド サーバーと併置できます。

次のサーバーの役割は、それぞれ別のコンピューターに展開する必要があります。

  - ディレクター

  - エッジ サーバー

  - 仲介サーバー (フロントエンド サーバーと併置しない場合)

  - Office Web Apps サーバー

常設チャットサーバーの役割をフロントエンドサーバーと併置することはできません。

</div>

<div>

## <a name="databases"></a>Databases

次のそれぞれのデータベースは、同じデータベース サーバーに併置できます。

  - バック エンド データベース

  - 監視データベース

  - アーカイブ データベース

  - 常設チャットデータベース

  - 常設チャットコンプライアンスデータベース

これらのデータベースのいずれかまたはすべてを1つの SQL Server インスタンスで併置するか、または SQL Server の個別のインスタンスを使用することができます。これには次の制限があります。

  - SQL Server の各インスタンスには、1つのバックエンドデータベース、単一の監視データベース、1つのアーカイブデータベース、1つの常設チャットデータベース、および1つの常設チャットコンプライアンスデータベースのみを含めることができます。

  - データベースサーバーは、複数のフロントエンドプール、1つのアーカイブ展開、および1つの監視展開をサポートできませんが、データベースが SQL Server の同じインスタンスを使用するか、SQL Server の別のインスタンスを使用するかに関係なく、それぞれの1つをサポートできます。

このセクションで後述するように、ファイル共有をデータベースと併置できます。

<div>


> [!NOTE]  
> Lync Server 2013 では、展開内の一部またはすべてのユーザーに対してアーカイブストレージを Exchange 2013 ストレージと統合するオプションがあります。 Exchange ストレージと同じサーバーに Lync Server またはコンポーネントを実行しているサーバーを展開することはできません。



</div>

<div>


> [!IMPORTANT]  
> データベースの併置がサポートされていても、データベースのサイズはすぐに大きくなることがあります。 たとえば、アーカイブ データベースと他のデータベースを併置することを考慮するときには、数名以上のユーザーのメッセージをアーカイブすると、アーカイブ データベースが必要とするディスク容量が非常に大きくなる可能性があることに注意してください。 このため、複数のデータベース (特に、アーカイブデータベース、常設チャットデータベース、または常設チャットコンプライアンスデータベースとバックエンドデータベース) を併置することはお勧めしません。



</div>

</div>

<div>

## <a name="file-share"></a>ファイル共有

ファイル共有は、別個のサーバーを使用することも、次のいくつか、またはすべてと同じサーバーに併置することもできます。

  - データベース サーバー (Enterprise Edition フロントエンド プールのバック エンド サーバーを含む)

  - アーカイブ データベース

  - 監視データベース

  - 常設チャットデータベース

  - 常設チャットコンプライアンスデータベース

単一のファイル共有を複数のフロントエンド プール、および複数の Standard Edition サーバーで使用できます (これらのプールやサーバーはすべて同じサイトに存在)。

<div>


> [!NOTE]  
> Lync Server 2013 の監視およびアーカイブでは、Lync Server のファイル共有をフロントエンドサーバーとして使用します。



</div>

</div>

<div>

## <a name="other-components"></a>その他のコンポーネント

Lync server 2013 コンポーネントではないリバースプロキシサーバーを併置することはできませんが、任意の Lync Server 2013 サーバーの役割を持つフェデレーションユーザーに対して web コンテンツの共有をサポートする必要がある場合は、展開で必要になります。 ただし、他のアプリケーションで使用されている組織内の既存のリバースプロキシサーバーのサポートを構成することによって、Lync Server 2013 展開のリバースプロキシサポートを実装できます。

Exchange ユニファイドメッセージング (UM) コンポーネントまたは SharePoint コンポーネントを任意の SharePoint Server の役割と併置することはできません。

</div>

</div>

<span> </span>

</div>

</div>

</div>


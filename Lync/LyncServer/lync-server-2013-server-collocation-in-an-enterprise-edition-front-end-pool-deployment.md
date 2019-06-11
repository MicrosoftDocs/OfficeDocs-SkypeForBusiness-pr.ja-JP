---
title: Lync Server 2013 の Enterprise Edition フロント エンド プール展開でのサーバーの併置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6947d732cf17cc053e48596ffd310f5df3b11636
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a>Lync Server 2013 の Enterprise Edition フロント エンド プール展開でのサーバーの併置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-11-11_

このセクションでは、Lync Server 2013 フロントエンドプールの展開で検索できるサーバーの役割、データベース、およびファイル共有について説明します。

<div>

## <a name="server-roles"></a>サーバーの役割

Lync Server 2013 では、A/V 会議サービス、仲介サービス、監視、およびアーカイブはフロントエンドサーバーに併置されますが、有効にするには追加の構成が必要です。 フロントエンドサーバーで仲介サーバーを検索したくない場合は、スタンドアロンの仲介サーバーとして別のコンピューターに展開することができます。

サーバーを使用して、信頼できるアプリケーションサーバーを検索することができます。

次のサーバーロールはそれぞれ別のコンピューターに展開する必要があります。

  - ディレクター

  - エッジ サーバー

  - 仲介サーバー (フロントエンドサーバーに併置されていない場合)

  - Office Web Apps サーバー

フロントエンドサーバーで常設チャットサーバーの役割を検索することはできません。

</div>

<div>

## <a name="databases"></a>データベース

同じデータベースサーバー上で、次の各データベースを検索することができます。

  - バックエンドデータベース

  - 監視データベース

  - アーカイブ データベース

  - 常設チャットデータベース

  - 常設チャットのコンプライアンスデータベース

SQL Server の1つのインスタンスでこれらのデータベースのいずれかまたはすべてを検索することも、SQL Server の個別のインスタンスを使用することもできます。次の制限があります。

  - SQL Server の各インスタンスには、1つのバックエンドデータベース、単一の監視データベース、単一のアーカイブデータベース、1つの常設チャットデータベース、1つの常設チャットのコンプライアンスデータベースのみを含めることができます。

  - データベースサーバーでは、複数のフロントエンドプール、1つのアーカイブ展開、および1つの監視展開をサポートすることはできませんが、データベースが SQL Server の同じインスタンスと SQL Server の別のインスタンスのどちらを使うかに関係なく、どちらか1つをサポートできます。

このセクションの後半で説明するように、データベースとのファイル共有を検索することができます。

<div>


> [!NOTE]  
> Lync Server 2013 では、展開内の一部またはすべてのユーザーについて、アーカイブストレージと Exchange 2013 ストレージを統合するオプションがあります。 Lync Server やコンポーネントを実行しているサーバーを Exchange ストレージと同じサーバー上に展開することはできません。



</div>

<div>


> [!IMPORTANT]  
> データベースの collocation はサポートされていますが、データベースのサイズが急速に増大する可能性があります。 たとえば、アーカイブデータベースを他のデータベースとの間で検索することを検討している場合、アーカイブデータベースに必要なディスク領域が非常に大きくなる可能性があることに注意してください。 このため、複数のデータベース、特にアーカイブデータベース、常設チャットデータベース、またはバックエンドデータベースを含む永続的なチャットのコンプライアンスデータベースを検索することはお勧めしません。



</div>

</div>

<div>

## <a name="file-share"></a>ファイル共有

ファイル共有は、個別のサーバーにすることも、次のいずれか、またはすべてを同じサーバー上に置いておくこともできます。

  - データベースサーバー (Enterprise Edition フロントエンドプールのバックエンドサーバーを含む)

  - アーカイブ データベース

  - 監視データベース

  - 常設チャットデータベース

  - 常設チャットのコンプライアンスデータベース

1つのファイル共有は、複数のフロントエンドプール、標準エディションサーバー (すべて同じサイト内) に使用できます。

<div>


> [!NOTE]  
> Lync Server 2013 の [監視とアーカイブ] では、Lync Server のファイル共有をフロントエンドサーバーとして使用します。



</div>

</div>

<div>

## <a name="other-components"></a>その他のコンポーネント

Lync server 2013 コンポーネントではないリバースプロキシサーバーを検索することはできませんが、Lync Server 2013 サーバーの役割を持つフェデレーションユーザーの web コンテンツの共有をサポートする場合は、展開で必要になります。 ただし、他のアプリケーションで使用されている既存のリバースプロキシサーバーのサポートを構成することによって、Lync Server 2013 の展開にリバースプロキシサポートを実装することはできます。

任意の SharePoint Server の役割で Exchange ユニファイドメッセージング (UM) コンポーネントまたは SharePoint コンポーネントを検索することはできません。

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013 の Standard Edition サーバー展開でのサーバーの併置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server collocation in a Standard Edition server deployment
ms:assetid: 0763ffab-4fd6-463a-8e62-d97876b376d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398131(v=OCS.15)
ms:contentKeyID: 48183314
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 950f2ab06a146ec99ef9ebb2ecbc64c885c82d70
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a>Lync Server 2013 の Standard Edition サーバー展開でのサーバーの併置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-01-20_

このセクションでは、Lync Server 2013 Standard Edition サーバーの展開で検索できるサーバーの役割、データベース、およびファイル共有について説明します。

<div>

## <a name="server-roles"></a>サーバーの役割

Lync Server 2013 では、A/V 会議サービス、仲介サービス、監視、およびアーカイブは Standard Edition サーバーに併置されますが、有効にするには追加の構成が必要です。 別々のサーバーに仲介サービスを展開することを選択できます。

標準エディションのサーバーを使用して、信頼できるアプリケーションサーバーを検索できます。

次のサーバーロールはそれぞれ別のコンピューターに展開する必要があります。

  - ディレクター

  - エッジ サーバー

  - 仲介サーバー (Standard Edition サーバーに付属していない場合)

  - Office Web Apps サーバー

</div>

<div>

## <a name="databases"></a>データベース

既定では、SQL Server Express バックエンドデータベースは Standard Edition サーバーに併置されます。 別のコンピュータに移動することはできません。 1つの例外を除き、Standard Edition サーバー上で他のデータベースを検索することはできません。 標準エディションのサーバーに常設チャットサーバーを展開することを選択した場合は、同一の Standard Edition サーバー上で常設チャットデータベースと常設チャットのコンプライアンスデータベースを検索することができます。

1つのデータベースサーバー上で、次の各データベースを検索することができます。

  - 監視データベース

  - アーカイブ データベース

  - Enterprise Edition フロントエンドプールのバックエンドデータベース

次の制限があります。これらのデータベースの任意または一部を1つの SQL インスタンスで検索したり、個別に SQL インスタンスを使用したりすることができます。

  - 各 SQL インスタンスには、1つのバックエンドデータベース (Enterprise Edition フロントエンドプール用)、単一の監視データベース、単一のアーカイブデータベース、単一の常設チャットデータベース、および1つの常設チャットのコンプライアンスデータベースのみを含めることができます。

  - データベースサーバーでは、複数の Enterprise Edition フロントエンドプール、アーカイブを実行している1台のサーバー、単一の常設チャットデータベース、1つの永続的なチャットのコンプライアンスデータベースをサポートできませんが、いずれか1つをサポートできます。データベースで SQL Server の同じインスタンスと SQL Server の別のインスタンスのどちらを使うかに関係なく、

このセクションの後半で説明するように、データベースとのファイル共有を検索することができます。

<div>


> [!NOTE]  
> Lync Server 2013 では、展開内の一部またはすべてのユーザーに対して、監視とアーカイブストレージを Exchange 2013 ストレージと統合するオプションが用意されています。 Lync Server やコンポーネントを実行しているサーバーを Exchange ストレージと同じサーバー上に展開することはできません。



</div>

<div>


> [!IMPORTANT]  
> データベースの collocation はサポートされていますが、データベースのサイズが急速に増大する可能性があります。 たとえば、アーカイブデータベースを他のデータベースとの間で検索することを検討している場合、アーカイブデータベースに必要なディスク領域が非常に大きくなる可能性があることに注意してください。 このため、エンタープライズプールのバックエンドデータベースを使用して、複数のデータベース、特にアーカイブデータベース、常設チャットデータベース、常設チャットのコンプライアンスデータベースを検索することはお勧めしません。



</div>

</div>

<div>

## <a name="file-shares"></a>ファイル共有

ファイル共有は、個別のサーバーにすることも、次のいずれか、またはすべてを同じサーバー上に置いておくこともできます。

  - データベースサーバー (Enterprise Edition フロントエンドプールのバックエンドサーバーを含む)

  - アーカイブ データベース

  - 監視データベース

  - 常設チャットデータベース

  - 常設チャットのコンプライアンスデータベース

1つのファイル共有は、複数のフロントエンドプール、標準エディションサーバー (すべて同じサイト内) に使用できます。

<div>


> [!NOTE]  
> Lync Server 2013 の [監視とアーカイブ] では、Lync Server のファイル共有を Standard Edition サーバーとして使用します。



</div>

</div>

<div>

## <a name="other-components"></a>その他のコンポーネント

Lync server 2013 コンポーネントではないリバースプロキシサーバーを検索することはできませんが、Lync Server 2013 サーバーの役割を持つフェデレーションユーザーの web コンテンツの共有をサポートする場合は、展開で必要になります。 ただし、他のアプリケーションで使用されている既存のリバースプロキシサーバーのサポートを構成することによって、Lync Server 2013 の展開にリバースプロキシサポートを実装することはできます。

任意の Lync Server 2013 の役割を持つ Exchange UM コンポーネントまたは SharePoint コンポーネントを検索することはできません。

</div>

</div>

<span> </span>

</div>

</div>

</div>


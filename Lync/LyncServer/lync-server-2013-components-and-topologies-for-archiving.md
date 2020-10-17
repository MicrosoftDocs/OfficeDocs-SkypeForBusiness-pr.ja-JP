---
title: 'Lync Server 2013: アーカイブ用のコンポーネントとトポロジ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Archiving
ms:assetid: 5893063d-a44a-4034-aba9-cbe883ecf710
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204916(v=OCS.15)
ms:contentKeyID: 48184213
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec153b237df086f3622acc70c104bddc64fef28a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502614"
---
# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a>Lync Server 2013 でのアーカイブ用のコンポーネントとトポロジ

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-09_

Lync Server 2013 IM および会議コンテンツをアーカイブする場合は、Lync Server でのアーカイブを実装できます。

<div>

## <a name="archiving-components"></a>アーカイブ コンポーネント

アーカイブ機能には次のコンポーネントが含まれています。

  - **アーカイブ エージェント:** 統合データ収集エージェントとも呼ばれます。すべてのフロントエンド プールと Standard Edition サーバーに自動的にインストールされ、アクティブ化されます。アーカイブ エージェントは自動的にアクティブ化されますが、アーカイブを有効にし、適切に構成するまで、実際にはメッセージは取得されません。

  - **アーカイブデータストレージ**。 Lync Server 2013 のデータ記憶域には、次のいずれかを指定できます。
    
      - Exchange 2013 ストレージ。 Microsoft Exchange 統合オプションを有効にした場合、Exchange 2013 サーバーに所属するユーザーメールボックスは、アーカイブされたデータに Exchange 2013 ストレージを使用します。ただし、メールボックスが In-Place ホールドに設定されている場合に限ります。
    
      - SQL Server ストレージ。 Lync Server 2013 に所属している展開にユーザーがいる場合、サポートされているバージョンの SQL Server を実行するアーカイブデータベースをセットアップして、それらのユーザーのアーカイブを有効にすることができます。

アーカイブにはファイル記憶域 ストレージも必要ですが、アーカイブはフロントエンド サーバーまたは Standard Edition サーバーと同じファイル ストレージを使用します。

アーカイブのハードウェアとソフトウェアの要件の一覧については、「サポート」のドキュメントの「lync server [2013 の場合はサポートされるハードウェア](lync-server-2013-supported-hardware.md) 」および「 [lync Server 2013 のサーバーソフトウェアとインフラストラクチャのサポート](lync-server-2013-server-software-and-infrastructure-support.md) 」を参照してください。

</div>

<div>

## <a name="supported-topologies"></a>サポートされるトポロジ

アーカイブのサポートを必要とするユーザーを持つ各プールでアーカイブを展開します。 アーカイブは、Enterprise Edition プールおよび Standard Edition サーバーのフロントエンドサーバー上で実行されます。 アーカイブ データ ストレージでは以下が可能です。

  - Exchange 2013 ストレージとの統合

  - 個別の SQL Server データベースを使用して展開されている

Exchange 2013 展開に Lync Server 展開のすべてのユーザーが含まれていない場合は、Exchange 2013 サーバー上のメールボックスを持つユーザーに対して Microsoft Exchange 統合を使用する必要があります。また、アーカイブに使用するために他のすべての Lync ユーザーに対して個別の SQL Server データベースを展開する必要があります。

</div>

<div>

## <a name="supported-collocation"></a>サポートされる配置

Lync Server 2013 では、さまざまな併置シナリオがサポートされており、1台のサーバーで複数のコンポーネントを実行 (小規模な組織の場合)、または個別のコンポーネントを異なるサーバーで実行することによって、ハードウェアコストを節約することができます (スケーラビリティとパフォーマンスを必要とする組織が大規模な場合)。 コンポーネントを併置するかどうかを決定する前に、スケーラビリティの要因を必ず検討する必要があります。

アーカイブは、プールまたは Standard Edition サーバーのフロントエンドサーバーに展開されます。 そこに併置できるコンポーネントの詳細については、「サポート」のドキュメントの「supported [server 併置 in Lync server 2013](lync-server-2013-supported-server-collocation.md) 」を参照してください。

ストレージを Exchange 2013 ストレージと統合するのではなく、アーカイブに個別の SQL Server データベースを使用する場合は、アーカイブデータベースを次のいずれかの場所で併置できます。

  - 監視データベース

  - Enterprise Edition フロントエンド プールのバックエンド データベース

<div>


> [!NOTE]  
> アーカイブ データベースをホストするサーバーでは、他のデータベースもホストできます。ただし、アーカイブ データベースと他のデータベースを併置することを考慮するときには、数名以上のユーザーのメッセージをアーカイブすると、アーカイブ データベースに必要なディスク領域が非常に大きくなる可能性があることに注意してください。そのため、アーカイブ データベースとバックエンド データベースを併置することはお勧めしません。



</div>

アーカイブ データベースを、監視データベースとバックエンド データベースのどちらか一方または両方と併置する場合は、一部のデータベースまたはすべてのデータベースに対して 1 つの SQL インスタンスを使用することも、各データベースに個別の SQL インスタンスを使用することもできます。ただし、次のような制限があります。

  - 各 SQL インスタンスは、単一のバックエンド データベース、単一の監視データベース、および単一のアーカイブ データベースのみを含むことができます。

すべてのサーバーの役割およびデータベースの併置の詳細については、「サポート」のドキュメントの「supported [server 併置 in Lync server 2013](lync-server-2013-supported-server-collocation.md) 」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>


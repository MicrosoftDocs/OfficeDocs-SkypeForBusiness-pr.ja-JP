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
ms.openlocfilehash: b3ccb77d8d2d0b7bd7d4d564087a69b7605863fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a>Lync Server 2013 のアーカイブ用のコンポーネントとトポロジ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-09_

Lync Server 2013 IM と会議のコンテンツをアーカイブする場合は、Lync Server でアーカイブを実装できます。

<div>

## <a name="archiving-components"></a>アーカイブコンポーネント

アーカイブ機能には、次のコンポーネントが含まれています。

  - **アーカイブ エージェント**。 アーカイブエージェント (統合データ収集エージェントとも呼ばれます) は、すべてのフロントエンドプールおよび標準エディションのサーバーに自動的にインストールされ、ライセンス認証されます。 アーカイブエージェントは自動的に有効になりますが、アーカイブが有効になって適切に構成されるまで、実際にはメッセージはキャプチャされません。

  - **データストレージのアーカイブ**。 Lync Server 2013 用のデータストレージは、次のいずれかにすることができます。
    
      - Exchange 2013 ストレージ。 Microsoft Exchange 統合オプションを有効にした場合、Exchange 2013 サーバー上にあるユーザーのメールボックスでは、アーカイブデータに Exchange 2013 ストレージが使用されます。ただし、メールボックスがインプレースホールドに配置されている場合のみです。
    
      - SQL Server ストレージ。 組織内のユーザーが Lync Server 2013 を使っている場合は、サポートされているバージョンの SQL Server を実行するアーカイブデータベースをセットアップして、それらのユーザーのアーカイブを有効にすることができます。

アーカイブにもファイルストレージが必要ですが、アーカイブでは、フロントエンドサーバーまたは Standard Edition サーバーと同じファイルストレージが使用されます。

アーカイブのためのハードウェアとソフトウェアの要件の一覧については、[サポートされているハードウェア (Lync server 2013](lync-server-2013-supported-hardware.md)および[サーバーソフトウェアおよびサーバーソフトウェアと](lync-server-2013-server-software-and-infrastructure-support.md)、サポートされているドキュメントの「サーバーソフトウェアとインフラストラクチャの2013サポート)」を参照してください。

</div>

<div>

## <a name="supported-topologies"></a>サポートされるトポロジ

アーカイブサポートが必要なユーザーがいる各プールにアーカイブを展開します。 アーカイブは、Enterprise Edition プールのフロントエンドサーバーと Standard Edition サーバー上で実行されます。 データ記憶域のアーカイブは、次のようになります。

  - Exchange 2013 ストレージとの統合

  - 個別の SQL Server データベースを使用して展開する

使用している Exchange 2013 の展開に Lync Server の展開におけるすべてのユーザーが含まれていない場合は、Exchange 2013 サーバー上のメールボックスを使用しているユーザーには Microsoft Exchange 統合を使用する必要があります。また、その他の場合は、別の SQL Server データベースを展開する必要があります。アーカイブに使用する Lync ユーザー。

</div>

<div>

## <a name="supported-collocation"></a>サポートされている Collocation

Lync Server 2013 は、さまざまな collocation シナリオをサポートしており、1台のサーバーに複数のコンポーネントを実行して (小規模組織の場合)、または異なるサーバーで個別のコンポーネントを実行することにより、ハードウェアコストを節約することができます (サイズが多い場合)。スケーラビリティとパフォーマンスが必要な組織。 コンポーネントを検索するかどうかを決定する前に、スケーラビリティの要因を考慮する必要があります。

アーカイブは、プールまたは Standard Edition サーバーのフロントエンドサーバーに展開されます。 併置できるコンポーネントの詳細については、サポート対象ドキュメントの「 [Lync server 2013 でサポートされているサーバーの場所](lync-server-2013-supported-server-collocation.md)」を参照してください。

アーカイブ用に別の SQL Server データベースを使用している場合、またはストレージを Exchange 2013 ストレージと統合するのではなく、次のいずれかでアーカイブデータベースを検索することができます。

  - 監視データベース

  - Enterprise Edition フロントエンド プールのバックエンド データベース

<div>


> [!NOTE]  
> アーカイブ データベースをホストするサーバーでは、他のデータベースもホストできます。ただし、アーカイブ データベースと他のデータベースを併置することを考慮するときには、数名以上のユーザーのメッセージをアーカイブすると、アーカイブ データベースに必要なディスク領域が非常に大きくなる可能性があることに注意してください。そのため、アーカイブ データベースとバックエンド データベースを併置することはお勧めしません。



</div>

監視データベース、バックエンドデータベース、またはこれら両方のデータベースの両方でアーカイブデータベースを検索する場合は、データベースのいずれかまたはすべてに1つの SQL インスタンスを使用するか、データベースごとに個別の SQL インスタンスを使用することができます。次のような方法があります。限度

  - 各 SQL インスタンスには、1つのバックエンドデータベース、単一の監視データベース、単一のアーカイブデータベースのみを含めることができます。

すべてのサーバーの役割とデータベースの collocation の詳細については、サポートドキュメントの「 [Lync server 2013 でサポートされているサーバーの場所](lync-server-2013-supported-server-collocation.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>


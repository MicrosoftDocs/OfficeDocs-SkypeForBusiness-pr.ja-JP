---
title: 'Lync Server 2013: サポートされている Active Directory トポロジ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported Active Directory topologies
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398173(v=OCS.15)
ms:contentKeyID: 48183391
ms.date: 10/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dc15cea3d07dc4e00f1d2a5527c862d90a078c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848640"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-active-directory-topologies-in-lync-server-2013"></a>Lync Server 2013 でサポートされている Active Directory トポロジ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-10-02_

Lync Server 2013 は、Microsoft Lync Server 2010 と Microsoft Office Communications Server 2007 R2 と同じ Active Directory ドメインサービストポロジをサポートしています。 次のトポロジがサポートされています。

  - 単一のドメインを含む単一のフォレスト

  - 単一のツリーと複数のドメインを含む単一のフォレスト

  - 複数のツリーと不整合の名前空間を含む単一のフォレスト

  - 中央フォレスト トポロジの複数のフォレスト

  - リソース フォレスト トポロジの複数のフォレスト

  - Exchange Online を使用した Lync リソースフォレストトポロジの複数フォレスト

次の図は、このセクションの図で使われているアイコンを示しています。

**トポロジ図の重要な説明**

![トポロジ図の重要]な説明(images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "トポロジ図の重要")な説明

<div>

## <a name="single-forest-single-domain"></a>1つのフォレスト、単一ドメイン

Lync Server (単一ドメインフォレスト) でサポートされる最も簡単な Active Directory トポロジは、一般的なトポロジです。

次の図は、1つのドメインの Active Directory トポロジでの Lync Server の展開を示しています。

**単一ドメイン トポロジ**

![単一ドメイントポロジ](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "単一ドメイントポロジ")

</div>

<div>

## <a name="single-forest-multiple-domains"></a>1つのフォレスト、複数のドメイン

Lync Server でサポートされるもう1つの Active Directory トポロジは、ルートドメインと1つ以上の子ドメインで構成される単一フォレストです。 この種類の Active Directory トポロジでは、ユーザーを作成するドメインは、Lync Server を展開するドメインとは異なる場合があります。 ただし、フロントエンドプールを展開する場合は、1つのドメイン内のプールにすべてのフロントエンドサーバーを展開する必要があります。 Windows ユニバーサル管理者グループの Lync Server のサポートにより、ドメイン間管理が可能になります。

次の図は、複数のドメインを持つ単一フォレストでの展開を示しています。 この図では、ユーザーのアイコンには、ユーザーアカウントが所属しているドメインが表示され、矢印は Lync Server プールが存在するドメインを指しています。 ユーザーアカウントには、次のものが含まれます。

  - Lync Server プールと同じドメイン内のユーザーアカウント

  - Lync Server プールとは異なるドメイン内のユーザーアカウント

  - Lync Server プールを持つドメインの子ドメインのユーザーアカウント

**複数のドメインを含む単一フォレスト**

![複数のドメインを含む単一フォレスト](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "複数のドメインを含む単一フォレスト")

</div>

<div>

## <a name="single-forest-multiple-trees"></a>1つのフォレスト、複数のツリー

複数ツリーのフォレストトポロジは、独立したツリー構造と個別の Active Directory 名前空間を定義する2つ以上のドメインで構成されます。

次の図は、複数のツリーを持つ単一フォレストを示しています。 この図では、ユーザーのアイコンには、ユーザーアカウントが所属しているドメイン、同一または別のドメインに存在する Lync Server プールの実線が表示されていて、別のツリーに存在する Lync Server プールを示す破線が表示されています。 ユーザーアカウントには、次のものが含まれます。

  - Lync Server プールと同じドメイン内のユーザーアカウント

  - 別のドメインのユーザーアカウント (ただし、Lync サーバープールと同じツリー)

  - Lync Server プールの異なるツリー内のユーザーアカウント

**複数のツリーを持つ単一フォレスト**

![複数のツリーを持つ単一フォレスト](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "複数のツリーを持つ単一フォレスト")

</div>

<div>

## <a name="multiple-forests-central-forest"></a>複数フォレスト、中央フォレスト

Lync Server は、中央フォレストトポロジで構成されている複数のフォレストをサポートします。 中央フォレストトポロジは、中央フォレストの連絡先オブジェクトを使って、他のフォレストのユーザーを表します。 中央のフォレストでも、このフォレスト内のユーザーのユーザーアカウントがホストされます。 Microsoft Identity Integration Server (MIIS)、Microsoft Forefront Identity Manager (FIM) 2010、Microsoft Identity cycle manager (ILM) 2007 Feature Pack 1 (FP1) などのディレクトリ同期製品では、ユーザーアカウントのライフサイクルを管理します。組織: フォレストのいずれかで新しいユーザーアカウントを作成するか、またはユーザーアカウントがフォレストから削除されると、ディレクトリ同期の製品によって中央フォレストの対応する連絡先が同期されます。

中央フォレストには、次のような利点があります。

  - Lync Server を実行しているサーバーは、1つのフォレスト内で一元管理されます。

  - ユーザーは、任意のフォレストの他のユーザーを検索して通信することができます。

  - ユーザーは、任意のフォレストの他のユーザーのプレゼンスを表示できます。

  - ディレクトリ同期製品を利用すると、ユーザーアカウントが作成または削除されたときに、中央フォレストの連絡先オブジェクトの追加と削除が自動化されます。

次の図は、中央のフォレストトポロジを示しています。 この図では、Lync Server をホストしているドメイン (中央のフォレスト) と、別々のフォレストにあるユーザーのみのドメインとの間に双方向の信頼関係があります。 個別のユーザーのフォレストのスキーマを拡張する必要はありません。

**中央フォレストトポロジ**

![中央フォレストトポロジ](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "中央フォレストトポロジ")

</div>

<div>

## <a name="multiple-forests-resource-forest"></a>複数のフォレスト、リソースフォレスト

リソースフォレストトポロジでは、1つのフォレストが、Microsoft Exchange Server や Lync Server などのサーバーアプリケーションの実行専用になります。 リソースフォレストは、サーバーアプリケーションをホストしており、アクティブなユーザーオブジェクトの同期表現をホストしていますが、ログオン可能なユーザーアカウントは含まれていません。 リソースフォレストは、ユーザーオブジェクトが存在する他のフォレストの共有サービス環境として機能します。 ユーザーフォレストには、リソースフォレストとのフォレストレベルの信頼関係があります。 この種類のトポロジで Lync Server を展開する場合は、ユーザーのフォレスト内のすべてのユーザーアカウントについて、リソースフォレスト内の無効なユーザーオブジェクトを1つ作成します。 Microsoft Exchange が既にリソースフォレストに展開されている場合は、無効になっているユーザーアカウントが既に存在する可能性があります。 MIIS、Microsoft Forefront Identity Manager (FIM) 2010、Microsoft Identity cycle Manager (ILM) 2007 Feature Pack 1 (FP1) などのディレクトリ同期製品は、ユーザーアカウントのライフサイクルを管理します。 いずれかのユーザーフォレストで新しいユーザーアカウントを作成するか、またはユーザーアカウントがフォレストから削除されると、ディレクトリ同期の製品によって、リソースフォレスト内の対応するユーザー表現が同期されます。

このトポロジは、複数のフォレストを管理する組織、または Active Directory オブジェクトの管理を他の管理から分離するために、サービスの共有インフラストラクチャを提供するために使用できます。 セキュリティ上の理由で Active Directory 管理を分離する必要がある企業は、多くの場合、このトポロジを選択します。

このトポロジでは、Active Directory スキーマを1つのフォレスト (つまりリソースフォレスト) に拡張する必要があるかを制限することができます。

次の図は、リソースフォレストのトポロジを示しています。

**リソースフォレストのトポロジ**

![Active Directory リソースフォレストトポロジ](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory リソースフォレストトポロジ")

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a>Exchange Online を使用した Lync リソースフォレストトポロジの複数フォレスト

このトポロジでは、1つ以上のフォレストがオンプレミスであり、Active Directory ユーザーアカウントのホスト専用になっています。 リソースフォレストはオフプレミスであり、サードパーティのホスティングプロバイダーによって管理されます。 リソースフォレストには、Lync Server の展開と、オンプレミスのユーザーアカウントのフォレストからのユーザーアカウントの同期されたレプリケーションが含まれています。 ログオン可能なユーザーアカウントが含まれていません。 Exchange は Exchange Online (ハイブリッド) と共に統合されたオンプレミスのユーザーアカウントフォレストに展開されます。または、オンプレミスのユーザーアカウントのメールサービスは、Exchange Online によってのみ提供されます。

リソースフォレストは、ユーザーオブジェクトが存在するオンプレミスの Active Directory フォレストの共有サービス環境として機能します。 ユーザーアカウントフォレストには、リソースフォレストとの一方向のフォレストレベルの信頼関係があります。 この種類のトポロジで Lync Server を展開する場合は、ユーザーのフォレスト内のすべてのユーザーアカウントについて、リソースフォレスト内の無効なユーザーオブジェクトを1つ作成します。 MIIS、Microsoft Forefront Identity Manager (FIM) 2010、Microsoft Identity cycle Manager (ILM) 2007 Feature Pack 1 (FP1) などのディレクトリ同期製品は、ユーザーアカウントのライフサイクルを管理します。 いずれかのユーザーフォレストで新しいユーザーアカウントを作成するか、またはユーザーアカウントがフォレストから削除されると、ディレクトリ同期の製品によって、リソースフォレスト内の対応するユーザー表現が同期されます。 複数フォレスト展開の構成の詳細については、「[マルチフォレストアーキテクチャでの lync の展開 (Exchange ハイブリッドを使用した Lync ホスト型 lync)](http://go.microsoft.com/fwlink/p/?linkid=513216)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>


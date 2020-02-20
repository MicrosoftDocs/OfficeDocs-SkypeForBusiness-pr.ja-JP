---
title: 'Lync Server 2013: サポートされている Active Directory トポロジ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported Active Directory topologies
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398173(v=OCS.15)
ms:contentKeyID: 48183391
ms.date: 10/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6eb9a3db2f9b3a14726fb7ffbec05b96b15ec81
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-active-directory-topologies-in-lync-server-2013"></a>Lync Server 2013 でサポートされている Active Directory トポロジ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-10-02_

Lync Server 2013 は、Microsoft Lync Server 2010 および Microsoft Office Communications Server 2007 R2 と同じ Active Directory ドメインサービストポロジをサポートしています。 次のトポロジがサポートされています。

  - 単一のドメインを含む単一のフォレスト

  - 単一のツリーと複数のドメインを含む単一のフォレスト

  - 複数のツリーと不整合の名前空間を含む単一のフォレスト

  - 中央フォレスト トポロジの複数のフォレスト

  - リソース フォレスト トポロジの複数のフォレスト

  - Exchange Online を使用する Lync リソースフォレストトポロジ内の複数のフォレスト

次の図に、このセクションで使用されるアイコンを示します。

**トポロジに関する重要点**

![トポロジに関する重要点](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "トポロジに関する重要点")

<div>

## <a name="single-forest-single-domain"></a>単一フォレスト、単一ドメイン

単一のドメインフォレストである Lync Server でサポートされている最も簡単な Active Directory トポロジは、一般的なトポロジです。

次の図は、1つのドメインの Active Directory トポロジにおける Lync Server の展開を示しています。

**単一ドメイントポロジ**

![単一ドメイントポロジ](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "単一ドメイン トポロジ")

</div>

<div>

## <a name="single-forest-multiple-domains"></a>単一フォレスト、複数ドメイン

Lync Server でサポートされている他の Active Directory トポロジは、1つのフォレストで、1つのルートドメインと1つ以上の子ドメインから構成されます。 この種類の Active Directory トポロジでは、ユーザーを作成するドメインは、Lync Server を展開するドメインとは異なる場合があります。 ただし、フロントエンド プールを展開する場合、プール内のすべてのフロントエンド サーバーを 1 つのドメインに展開する必要があります。 Windows ユニバーサル管理者グループの Lync Server のサポートにより、ドメインを越えた管理が可能になります。

次の図に、複数のドメインを持つ単一フォレストの展開を示します。 この図では、ユーザーアカウントが所属しているドメインがユーザーアイコンに表示され、矢印は Lync Server プールが存在するドメインを指しています。 ユーザー アカウントには次の種類があります。

  - Lync Server プールと同じドメイン内のユーザーアカウント

  - Lync Server プールとは別のドメインにあるユーザーアカウント

  - Lync Server プールを使用するドメインの子ドメイン内のユーザーアカウント

**複数のドメインを含む単一のフォレスト**

![複数のドメインを含む単一のフォレスト](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "複数のドメインを含む単一のフォレスト")

</div>

<div>

## <a name="single-forest-multiple-trees"></a>単一フォレスト、複数ツリー

複数ツリーのフォレスト トポロジは、独立したツリー構造を定義し、Active Directory 名前空間を分ける 2 つ以上のドメインで構成されます。

次の図に、複数のツリーがある単一のフォレストを示します。 この図では、ユーザーアイコンは、ユーザーアカウントが所属しているドメイン、同一または別のドメインに存在する Lync Server プールを示す破線、および異なるツリーに存在する Lync Server プールを指す破線を示しています。 ユーザー アカウントには次の種類があります。

  - Lync Server プールと同じドメイン内のユーザーアカウント

  - 別のドメインのユーザーアカウント (ただし、Lync Server プールと同じツリー)

  - Lync Server プールの異なるツリーにあるユーザーアカウント

**複数のツリーを含む単一のフォレスト**

![複数のツリーを含む単一のフォレスト](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "複数のツリーを含む単一のフォレスト")

</div>

<div>

## <a name="multiple-forests-central-forest"></a>複数フォレスト、中央フォレスト

Lync Server は、中央フォレストトポロジで構成されている複数のフォレストをサポートします。 中央フォレストトポロジは、中央フォレストの連絡先オブジェクトを使用して、他のフォレスト内のユーザーを表します。 中央フォレストは、このフォレスト内のすべてのユーザーのユーザーアカウントもホストします。 Microsoft Identity Integration Server (MIIS)、Microsoft Forefront Identity Manager (FIM) 2010、または Microsoft Identity cycle Manager (ILM) 2007 Feature Pack 1 (FP1) などのディレクトリ同期製品は、でのユーザーアカウントのライフサイクルを管理します。組織: フォレストの1つに新しいユーザーアカウントが作成されるか、またはユーザーアカウントがフォレストから削除されると、ディレクトリ同期製品によって、中央フォレスト内の対応する連絡先が同期されます。

中央フォレストには、次に示す利点があります。

  - Lync Server を実行しているサーバーは、単一フォレスト内で集中管理されます。

  - ユーザーは、任意のフォレストのユーザーを検索して通信できます。

  - ユーザーは、任意のフォレストの他のユーザーのプレゼンスを表示できます。

  - ユーザー アカウントが作成または削除されると、ディレクトリ同期製品によって、中央フォレストの連絡先オブジェクトが自動的に追加および削除されます。

次の図に、中央フォレスト トポロジを示します。 この図では、中央フォレストにある Lync Server をホストするドメインと、別のフォレストにある各ユーザー専用ドメインとの間に双間の信頼関係があります。 別のユーザー フォレストのスキーマは、拡張する必要がありません。

**中央フォレスト トポロジ**

![中央フォレスト トポロジ](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "中央フォレスト トポロジ")

</div>

<div>

## <a name="multiple-forests-resource-forest"></a>複数フォレスト、リソース フォレスト

リソースフォレストのトポロジでは、1つのフォレストは Microsoft Exchange Server および Lync Server などのサーバーアプリケーションの実行専用になります。 リソース フォレストは、サーバー アプリケーションとアクティブ ユーザー オブジェクトの同期表現をホストしますが、ログオン可能なユーザー アカウントはホストしません。 リソース フォレストは、ユーザー オブジェクトが存在する他のフォレストのための共有サービス環境として動作します。 ユーザー フォレストは、リソース フォレストとの間にフォレスト レベルの信頼関係を持ちます。 この種類のトポロジで Lync Server を展開する場合は、ユーザーフォレスト内のすべてのユーザーアカウントについて、リソースフォレスト内に無効なユーザーオブジェクトを1つ作成します。 Microsoft Exchange がリソースフォレストに既に展開されている場合は、無効になっているユーザーアカウントが既に存在する可能性があります。 MIIS、Microsoft Forefront Identity Manager (FIM) 2010、または Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1) などのディレクトリ同期製品は、ユーザー アカウントのライフ サイクルを管理します。 いずれかのユーザー フォレストで新しいユーザー アカウントが作成されるか、フォレストからユーザー アカウントが削除されると、ディレクトリ同期製品がリソース フォレスト内の対応するユーザー表現を同期します。

このトポロジは、組織のサービスに対して、複数のフォレストを管理する共有インフラストラクチャを提供するためや、Active Directory オブジェクトの管理を他の管理から切り離すために使用できます。セキュリティ上の理由から Active Directory の管理を分離する必要がある会社は、多くの場合、このトポロジを選択します。

このトポロジには、Active Directory スキーマの拡張の必要性が単一のフォレスト (リソース フォレスト) に限定されるという利点があります。

次の図に、リソース フォレスト トポロジを示します。

**リソース フォレスト トポロジ**

![Active Directory リソースフォレストトポロジ](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory リソースフォレストトポロジ")

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a>Exchange Online を使用する Lync リソースフォレストトポロジ内の複数のフォレスト

このトポロジでは、1つ以上のフォレストが社内に配置されており、Active Directory のユーザーアカウントをホストするために専用になっています。 リソースフォレストはオフプレミスにあり、サードパーティのホスティングプロバイダーによって管理されます。 リソースフォレストには、Lync Server の展開と、オンプレミスのユーザーアカウントフォレストからのユーザーアカウントの同期レプリケーションのみが含まれています。 ログオンが有効なユーザーアカウントは含まれていません。 Exchange は、exchange Online (ハイブリッド) と共に統合されたオンプレミスのユーザーアカウントフォレストに展開されるか、または社内ユーザーアカウントの電子メールサービスが Exchange Online によってのみ提供されます。

リソースフォレストは、ユーザーオブジェクトが存在するオンプレミスの Active Directory フォレストの共有サービス環境として機能します。 ユーザーアカウントのフォレストには、1つの方法でリソースフォレストとのフォレストレベルの信頼関係があります。 この種類のトポロジで Lync Server を展開する場合は、ユーザーフォレスト内のすべてのユーザーアカウントについて、リソースフォレスト内に無効なユーザーオブジェクトを1つ作成します。 MIIS、Microsoft Forefront Identity Manager (FIM) 2010、または Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1) などのディレクトリ同期製品は、ユーザー アカウントのライフ サイクルを管理します。 いずれかのユーザー フォレストで新しいユーザー アカウントが作成されるか、フォレストからユーザー アカウントが削除されると、ディレクトリ同期製品がリソース フォレスト内の対応するユーザー表現を同期します。 複数フォレスト展開の構成の詳細については、「[複数フォレストアーキテクチャでの lync の展開 (Exchange ハイブリッドを使用したパートナーホスト](https://go.microsoft.com/fwlink/p/?linkid=513216)された lync)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>


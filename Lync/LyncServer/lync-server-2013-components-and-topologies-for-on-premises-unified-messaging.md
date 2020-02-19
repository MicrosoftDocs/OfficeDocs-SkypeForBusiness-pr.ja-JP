---
title: 'Lync Server 2013: オンプレミスのユニファイドメッセージングのコンポーネントとトポロジ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for on-premises Unified Messaging
ms:assetid: 22fc87cf-a7e5-4c8c-bb9b-101e5380cdcf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425711(v=OCS.15)
ms:contentKeyID: 48183619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 543af1cc9b4dbb437b36273945f9f2cb6112c6b6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a>Lync Server 2013 でのオンプレミスのユニファイドメッセージングのコンポーネントとトポロジ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-25_

このトピックでは、Exchange ユニファイドメッセージング (UM) 機能を Lync Server 2013 展開に提供するために必要な Microsoft Exchange Server 2013 コンポーネントについて説明します。 また、オンプレミスの Exchange UM 統合に対してサポートされているトポロジについても説明します。

<div>

## <a name="exchange-server-components"></a>Exchange Server コンポーネント

統合された[ユニファイドメッセージングと Lync Server 2013 の機能](lync-server-2013-features-of-integrated-unified-messaging.md)について説明されている exchange UM の機能とサービスを組織のエンタープライズ voip ユーザーに提供するには、ユーザーメールボックスをホストする Microsoft Exchange メールボックスサーバーとクライアントアクセスサーバーを展開し、電子メールとボイスメール用の単一の格納場所を提供する必要があります。 Exchange UM は、Exchange メールボックスサーバーおよびクライアントアクセスサーバー上のサービスとして実行されます。

Microsoft Exchange Server 2007 と Microsoft Exchange Server 2010 の Exchange UM コンポーネントの詳細については、「展開」のドキュメントの「[社内 EXCHANGE um を展開して Lync Server 2013 ボイスメールを提供する](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)」を参照してください。

</div>

<div>

## <a name="supported-topologies"></a>サポートされるトポロジ

Lync Server 2013 と Exchange ユニファイドメッセージング (UM) を同じフォレストまたは複数のフォレストに展開できます。 複数のフォレストにまたがる展開の場合は、exchange UM フォレストごとに Exchange 統合の手順を実行する必要があります。 さらに、Lync Server 2013 フォレストと Lync Server 2013 フォレストを信頼して各 Exchange UM フォレストを信頼するように、各 Microsoft Exchange フォレストを構成する必要があります。 このフォレストの信頼に加えて、Lync Server 2013 フォレスト内のユーザーオブジェクトに対して、すべてのユーザーの Exchange UM 設定を設定する必要があります。

Lync Server 2013 は、Exchange UM 統合のために次のトポロジをサポートしています。

  - 単一のフォレスト

  - 単一ドメイン (すなわち、単一ドメインを含む単一フォレスト)。 Lync Server 2013、Microsoft Exchange、およびユーザーはすべて同じドメインに存在します。

  - 複数のドメイン (つまり、1つ以上の子ドメインを持つルートドメイン)。 Lync Server 2013 と Microsoft Exchange サーバーは、ユーザーを作成するドメインとは異なるドメインに展開されます。 Exchange UM サーバーは、サポートする Lync Server 2013 プールとは異なるドメインに展開できます。

  - 複数のフォレスト (すなわち、リソース フォレスト)。 Lync Server 2013 は単一のフォレストに展開され、ユーザーは複数のフォレスト間で分散されます。 ユーザーの Exchange UM 属性は、Lync Server 2013 フォレストにレプリケートする必要があります。
    
    <div>
    

    > [!NOTE]  
    > Exchange は複数のフォレストに展開できます。 各 Exchange 組織は Exchange UM をユーザーに提供できます。または、Exchange UM を Lync Server 2013 と同じフォレストに展開できます。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


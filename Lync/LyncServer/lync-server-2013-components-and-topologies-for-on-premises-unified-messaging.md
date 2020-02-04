---
title: 'Lync Server 2013: 社内ユニファイド メッセージングのコンポーネントとトポロジ'
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
ms.openlocfilehash: 1739dbb7d603f112af72c78032c46b94470302bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a>Lync Server 2013 の社内ユニファイド メッセージングのコンポーネントとトポロジ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-25_

このトピックでは、Lync Server 2013 の展開に Exchange ユニファイドメッセージング (UM) 機能を提供するために必要な Microsoft Exchange Server 2013 コンポーネントについて説明します。 また、オンプレミスの Exchange UM との統合でサポートされているトポロジについても説明します。

<div>

## <a name="exchange-server-components"></a>Exchange Server コンポーネント

統合された[ユニファイドメッセージングおよび Lync Server 2013 の機能](lync-server-2013-features-of-integrated-unified-messaging.md)について説明した exchange UM の機能とサービスを組織内のエンタープライズボイスユーザーに提供するには、Microsoft Exchange メールボックスサーバーとクライアントアクセスサーバーを展開して、ユーザーのメールボックスをホストし、メールやボイスメール用の1つの保存場所を提供する必要があります。 Exchange UM は、Exchange メールボックスとクライアントアクセスサーバーでサービスとして実行されます。

Microsoft Exchange Server 2007 および Microsoft Exchange Server 2010 の Exchange UM コンポーネントの詳細については、「展開ドキュメントで[Lync Server 2013 ボイスメールを提供するためのオンプレミスの EXCHANGE UM の展開」を](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)参照してください。

</div>

<div>

## <a name="supported-topologies"></a>サポートされるトポロジ

Lync Server 2013 と Exchange ユニファイドメッセージング (UM) は、同じフォレストまたは複数のフォレストに展開できます。 展開が複数のフォレストにまたがる場合は、各 Exchange UM フォレストの Exchange 統合手順を実行する必要があります。 さらに、Lync Server 2013 フォレストと Lync Server 2013 フォレストを信頼するように Microsoft Exchange フォレストを構成し、各 Exchange UM フォレストを信頼するようにする必要があります。 このフォレストの信頼に加えて、Lync Server 2013 フォレストのユーザーオブジェクトに対して、すべてのユーザーの Exchange UM 設定を設定する必要があります。

Lync Server 2013 は、Exchange UM との統合のために次のトポロジをサポートしています。

  - 1つのフォレスト

  - 単一ドメイン (つまり、単一のドメインを持つ単一フォレスト)。 Lync Server 2013、Microsoft Exchange、およびユーザーはすべて同じドメインに存在します。

  - 複数のドメイン (つまり、1つ以上の子ドメインを持つルートドメイン)。 Lync Server 2013、および Microsoft Exchange サーバーは、ユーザーを作成するドメインとは異なるドメインに展開されます。 Exchange UM サーバーは、サポートされている Lync Server 2013 プールとは異なるドメインに展開できます。

  - 複数のフォレスト (リソースフォレスト)。 Lync Server 2013 は1つのフォレストに展開され、ユーザーは複数のフォレストに分散されます。 ユーザーの Exchange UM 属性は、Lync Server 2013 フォレストにレプリケートする必要があります。
    
    <div>
    

    > [!NOTE]  
    > Exchange は複数のフォレストに展開できます。 各 Exchange 組織は、Exchange UM をそのユーザーに提供することができます。また、Exchange UM を Lync Server 2013 と同じフォレストに展開することもできます。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


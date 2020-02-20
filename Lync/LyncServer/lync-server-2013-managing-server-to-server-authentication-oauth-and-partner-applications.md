---
title: サーバー間認証 (OAuth) およびパートナーアプリケーションの管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing server-to-server authentication (OAuth) and partner applications
ms:assetid: 38848373-c8c6-4097-bf7f-699fe471348d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204817(v=OCS.15)
ms:contentKeyID: 48183894
ms.date: 05/15/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bb3ef1bdd01a7c5be5e8d32610a754c54f896c2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-server-to-server-authentication-oauth-and-partner-applications-in-lync-server-2013"></a>Lync Server 2013 でのサーバー間認証 (OAuth) およびパートナーアプリケーションの管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2015-05-14_

Microsoft Lync Server 2013 は、安全かつシームレスに、他のアプリケーションやサーバー製品と通信できる必要があります。 たとえば、Lync Server 2013 を構成して、連絡先データやアーカイブデータを Microsoft Exchange Server 2013 に保存することができます。ただし、これは、Lync Server と Exchange が相互に安全に通信できる場合にのみ実行できます。 同様に、Lync Server 会議を Microsoft SharePoint Server 内からスケジュールすることができます。ただし、これは、2台のサーバー (SharePoint と Lync Server) が相互に信頼している場合にのみ実行できます。 Lync から Exchange への通信に対して1つの認証機構を使用することもできますが、Lync から SharePoint への通信については個別のメカニズムを使用することもできますが、すべてのサーバー間で標準化された方法を使用することをお勧めします。認証と承認。

単一の標準化された方法を使用してサーバー間認証を実行することは、Lync Server 2013 による方法です。 2013リリースでは、Lync Server 2013 (および Exchange 2013 および Microsoft SharePoint Server を含むその他の Microsoft Server 製品) は、サーバー間の認証と承認のために OAuth (オープン認証) プロトコルをサポートしています。 OAuth では、多くの主要な web サイトで使用される標準の認証プロトコルであるコンピューターから別のコンピューターにユーザーの資格情報とパスワードが渡されることはありません。 代わりに、認証と承認はセキュリティトークンの交換に基づいています。これらのトークンは、特定の時間に特定のリソースのセットへのアクセスを許可します。

OAuth 認証には、通常、1つの承認サーバーと、互いに通信する必要がある2つの領域の3つの関係者が関与します。 (このドキュメントで後述するプロセスを使用して、認証サーバーを使用せずにサーバー間認証を実行することもできます)。セキュリティトークンは、通信する必要がある2つの領域に対して、認証サーバー (セキュリティトークンサーバーとも呼ばれる) によって発行されます。これらのトークンは、あるレルムから発信された通信が他のレルムによって信頼されることを確認します。 たとえば、認証サーバーは、特定の Lync Server 2013 領域のユーザーが、指定された Exchange 2013 領域にアクセスできることを確認するトークンを発行することがあります。また、その逆もあります。

<div>


> [!NOTE]
> 領域とは、セキュリティ コンテナーのことです。 既定では、Lync Server 2013 は既定の SIP ドメインを OAuth 領域として使用します。 その他の SIP 名前空間は、OAuth 証明書のサブジェクト代替名リストに追加されます。



</div>

Lync Server 2013 は、3つのサーバー間認証シナリオをサポートします。 Lync Server 2013 では、次のことができます。

  - Lync Server 2013 の社内インストールと、Exchange 2013 または Microsoft SharePoint Server の社内インストールとの間のサーバー間認証を構成します。

  - Office 365 コンポーネントのペア (Microsoft Exchange と Microsoft Lync Server 間、microsoft Lync Server と microsoft SharePoint との間など) の間でサーバー間認証を構成します。

  - クロスプレミス環境 (つまり、社内サーバーと Office 365 コンポーネント間のサーバー間認証) でサーバー間認証を構成します。

この時点では、Exchange 2013、SharePoint Server、Lync Server 2013 のみがサーバー間認証をサポートすることに注意してください。これらのサーバーのいずれかを実行していない場合、OAuth 認証を完全に実装することはできません。

また、サーバー間認証を使用する必要がないことを指摘する必要があります。 Lync Server 2013 を展開するためには、サーバー間認証は必要ありません。 Lync Server 2013 が他のサーバー (Exchange 2013 など) と通信する必要がない場合は、サーバー間認証は必要ありません。

ただし、「統合連絡先ストア」などの Lync Server の新機能の一部を使用する場合は、サーバー間認証が必要です。 統合連絡先ストアの場合、Lync server 2013 の連絡先情報は、Lync Server ではなく Exchange 2013 に格納されます。これにより、ユーザーは、Lync、Microsoft Outlook、または Microsoft Outlook Web Access 内から簡単にアクセスできる単一の連絡先セットを使用できるようになります。 統合連絡先ストアでは、Lync Server 2013 で情報を Exchange 2013 と共有する必要があるため、機能を展開するには、サーバー間認証を使用する必要があります。 Exchange アーカイブを使用することを選択した場合も、サーバー間認証が必要になります。これにより、インスタントメッセージングセッションのトランスクリプトは、個別のデータベースレコードとしてではなく、Exchange 2013 メールとして保存されます。

Office 365 バージョンの Lync Server が Exchange の対応するバージョンと通信するには、まず、Lync Server 2013 が承認サーバーからセキュリティトークンを取得する必要があります。 Lync Server は、そのセキュリティトークンを使用して Exchange に自分自身を識別します。 Office 365 バージョンの Exchange は、Lync Server 2013 と通信するために同じプロセスを経由する必要があります。

ただし、2つの Microsoft サーバー間でのオンプレミスのサーバー間認証の場合は、サードパーティのトークンサーバーを使用する必要はありません。 Lync Server 2013 および Exchange 2013 などのサーバー製品には、サーバー間認証をサポートする他の Microsoft サーバー (SharePoint Server など) との認証のために使用できる組み込みのトークンサーバーがあります。 たとえば、Lync Server 2013 はセキュリティトークンを自ら発行して署名し、そのトークンを使用して Exchange 2013 と通信できます。 このような場合、サード パーティのトークン サーバーは不要です。

Lync Server 2013 の社内実装に対してサーバー間認証を構成するには、次の2つの作業を行う必要があります。

  - Lync Server の組み込みトークン発行者に証明書を割り当てます。

  - Lync Server 2013 が通信するサーバーを "パートナーアプリケーション" として構成します。 たとえば、Lync Server 2013 が Exchange 2013 と通信する必要がある場合は、Exchange をパートナーアプリケーションとして構成する必要があります。

<div>


> [!NOTE]
> "パートナーアプリケーション" とは、サードパーティのセキュリティトークンサーバーを使用せずに、Lync Server 2013 がセキュリティトークンを直接交換できるアプリケーションです。



</div>

OAuth は製品のコア部分であり、無効化または削除することはできないことに注意してください。

<div>

## <a name="see-also"></a>関連項目


[サーバー間認証証明書を Microsoft Lync Server 2013 に割り当てる](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[クロスプレミス環境での Microsoft Lync Server 2013 の構成](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


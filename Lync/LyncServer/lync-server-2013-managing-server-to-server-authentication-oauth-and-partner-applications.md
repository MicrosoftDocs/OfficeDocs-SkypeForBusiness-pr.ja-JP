---
title: サーバー間認証 (OAuth) とパートナーアプリケーションの管理
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
ms.openlocfilehash: 01de2856b8923fff76cf33dda7d7e6ba21889c2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765688"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-server-to-server-authentication-oauth-and-partner-applications-in-lync-server-2013"></a>Lync Server 2013 でのサーバー間認証 (OAuth) とパートナーアプリケーションの管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2015-05-14_

Microsoft Lync Server 2013 は、安全かつシームレスに、他のアプリケーションやサーバー製品と通信できるようにする必要があります。 たとえば、連絡先データやアーカイブデータが Microsoft Exchange Server 2013 に保存されるように Lync Server 2013 を構成することができます。ただし、これを行うことができるのは、Lync Server と Exchange が相互に安全に通信できる場合のみです。 同様に、Lync Server 会議を Microsoft SharePoint Server 内でスケジュールすることもできます。ただし、この操作は、2台のサーバー (SharePoint と Lync Server) が相互に信頼している場合にのみ実行できます。 Lync 間の通信には1つの認証メカニズムを使用できますが、Lync 間の通信には個別のメカニズムを使うこともできますが、より良い方法として、すべてのサーバー間での標準化された方法を使用することをお勧めします。認証と承認。

サーバー間認証に単一の標準化された方法を使用することは、Lync Server 2013 によって行われる方法です。 2013リリースの Lync Server 2013 (および Exchange 2013 および Microsoft SharePoint Server を含むその他の Microsoft サーバー製品) では、サーバー間の認証と承認のために OAuth (Open Authorization) プロトコルがサポートされています。 多くの主要 web サイトで使用されている標準の認証プロトコルである OAuth を使用している場合、ユーザーの資格情報とパスワードは、あるコンピューターから別のコンピューターに渡されることはありません。 代わりに、認証と承認はセキュリティトークンの交換に基づいています。これらのトークンによって、特定の時間に対して特定のリソースのセットへのアクセスが許可されます。

OAuth 認証には、通常、単一の承認サーバーと、互いに通信する必要がある2つの領域の3つの当事者が関係します。 (このドキュメントの後半で説明するプロセスである承認サーバーを使用せずに、サーバー間認証を実行することもできます)。セキュリティトークンは、通信する必要がある2つの領域に対して、承認サーバー (セキュリティトークンサーバーとも呼ばれます) によって発行されます。これらのトークンは、あるレルムから発信された通信が他のレルムによって信頼される必要があることを確認します。 たとえば、承認サーバーは、特定の Lync Server 2013 領域のユーザーに対して、指定された Exchange 2013 領域へのアクセスを許可するかどうかを確認するトークンを発行する場合があります。

<div>


> [!NOTE]
> 領域とは、セキュリティ コンテナーのことです。 既定では、Lync Server 2013 は、既定の SIP ドメインを OAuth レルムとして使用します。 追加の SIP 名前空間が OAuth 証明書のサブジェクト代替名に追加されます。



</div>

Lync Server 2013 は、サーバー間認証の3つのシナリオをサポートしています。 Lync Server 2013 では、次のことができます。

  - オンプレミスでの Lync Server 2013 とオンプレミスインストールとの間で、サーバー間認証を構成します。 Exchange 2013 および Microsoft SharePoint Server のオンプレミスインストール。

  - 1組の Office 365 コンポーネント間 (たとえば、Microsoft Exchange と Microsoft Lync Server、または Microsoft Lync Server と Microsoft SharePoint 間) 間でサーバー間認証を構成します。

  - クロスプレミス環境でサーバー間認証を構成する (つまり、オンプレミスのサーバーと Office の365コンポーネントの間のサーバー間認証)。

この時点では、Exchange 2013、SharePoint Server、Lync Server 2013 のみがサーバー間認証をサポートしていることに注意してください。これらのサーバーのいずれかを実行していない場合は、OAuth 認証を完全に実装することはできません。

また、サーバー間認証を使用する必要がないことも指摘されます。 Lync Server 2013 を展開するためにサーバー間認証は必要ありません。 Lync Server 2013 が他のサーバー (Exchange 2013 など) と通信する必要がない場合は、サーバー間認証は必要ありません。

ただし、Lync Server の新機能の一部 ("統合連絡先ストア" など) を使用する場合は、サーバー間認証が必要です。 統合連絡先ストアでは、Lync Server 2013 の連絡先情報は、Lync Server の代わりに Exchange 2013 に保存されます。これにより、ユーザーは Lync、Microsoft Outlook、または Microsoft Outlook Web Access の中から、簡単にアクセスできる単一の連絡先セットを使用できます。 ユニファイド連絡先ストアでは、Lync Server 2013 で Exchange 2013 と情報を共有する必要があるため、機能を展開するには、サーバー間認証を使用する必要があります。 インスタントメッセージングセッションのトランスクリプトは、個別のデータベースレコードとしてではなく Exchange 2013 のメールとして保存されるため、Exchange アーカイブの使用を選択する場合も、サーバー間認証が必要になります。

Office 365 バージョンの Lync Server で Exchange と通信するためには、まず2013、承認サーバーからセキュリティトークンを取得する必要があります。 次に、Lync Server がそのセキュリティトークンを使用して Exchange に対して身元を確認します。 Lync Server 2013 と通信するためには、Office 365 バージョンの Exchange が同じ手順を実行している必要があります。

ただし、2つの Microsoft サーバー間でのオンプレミスのサーバー間認証の場合、サードパーティのトークンサーバーを使用する必要はありません。 Lync Server 2013 や Exchange 2013 などのサーバー製品には、サーバー間認証をサポートする他の Microsoft サーバー (SharePoint Server など) との認証目的で使用できる組み込みのトークンサーバーがあります。 たとえば、Lync Server 2013 は、セキュリティトークンを単独で発行して署名し、そのトークンを使って Exchange 2013 と通信することができます。 このような場合は、サードパーティのトークンサーバーは必要ありません。

Lync Server 2013 のオンプレミス実装用にサーバー間認証を構成するには、次の2つの操作を行う必要があります。

  - Lync Server の組み込みトークン発行者に証明書を割り当てます。

  - Lync Server 2013 で通信するサーバーを "パートナーアプリケーション" として構成します。 たとえば、Lync Server 2013 が Exchange 2013 と通信する必要がある場合、Exchange をパートナーアプリケーションとして構成する必要があります。

<div>


> [!NOTE]
> "パートナーアプリケーション" は、サードパーティのセキュリティトークンサーバーを経由せずに、Lync Server 2013 がセキュリティトークンを直接交換できるアプリケーションです。



</div>

OAuth は製品の中核部分なので、無効化したり削除したりすることはできません。

<div>

## <a name="see-also"></a>関連項目


[サーバー間認証証明書を Microsoft Lync Server 2013 に割り当てる](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[クロスプレミス環境で Microsoft Lync Server 2013 を構成する](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


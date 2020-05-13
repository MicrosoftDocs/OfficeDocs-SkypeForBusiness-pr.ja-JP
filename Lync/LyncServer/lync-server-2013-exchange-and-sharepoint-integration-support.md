---
title: 'Lync Server 2013: Exchange と SharePoint の統合のサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange and SharePoint integration support
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205005(v=OCS.15)
ms:contentKeyID: 48184504
ms.date: 01/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 262e31ac6049920ca4e327f50dccaae18d69a2f5
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a>Lync Server 2013 での Exchange と SharePoint の統合のサポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2017-01-18_

Lync Server 2013 および Lync 2013 は、これらの製品を統合すると、Office 2013、Exchange Server 2013、Exchange Server 2016、および SharePoint を含む他のアプリケーションやサーバー製品と安全かつシームレスに通信することができます。 Lync Server 2013 と Office を統合することにより、ユーザーは、インスタントメッセージング (IM)、拡張プレゼンス、テレフォニー、および Lync の会議機能に対して、コンテキストに依存したアクセスが可能になります。 Office ユーザーは、Outlook 2013 メッセージングおよびコラボレーションクライアントおよびその他の Office プログラム内から、または SharePoint ページから Lync 機能にアクセスできます。 ユーザーは、Outlook の [会話履歴] フォルダーで Lync 会話のレコードを表示することもできます。 Exchange 2013、Exchange 2016、または Exchange Online と統合されている場合、Lync Server 2013 は次の機能もサポートします。

  - 統合連絡先ストア。これにより、ユーザーはすべての連絡先情報を Exchange または Exchange Online に保存できるようになり、Lync 2013、Exchange、Outlook、および Outlook Web App 間で情報をグローバルに利用できるようになります。

  - Exchange ユーザーフォルダーに格納されている会話履歴と Web 会議履歴。

  - Lync からのアーカイブされたコンテンツ (IM、会議コンテンツなど) は、Exchange ストレージに保存できます。

<div>


> [!NOTE]  
> Lync Server 2013 は、以前のバージョンの Microsoft Exchange Server および SharePoint Server との統合をサポートしていますが、Microsoft Exchange とのアーカイブストレージの統合など、以前のバージョンではサポートされない機能もあります。<BR>ユーザーを Exchange 2013 または Exchange 2016 に移行している場合は、移行を完了する間、Exchange ストレージと Lync Server ストレージの両方を中間に使用することができます。 Exchange と Lync Server の両方のストレージを恒久的に使用することはサポートされていません。



</div>

Lync server 2013 と Exchange Server および SharePoint Server との統合では、Lync Server 2013、Exchange Server、および SharePoint Server を実行しているサーバー間でのサーバー間認証が必要です。 Lync Server 2013 は、サーバー間の認証と承認に OAuth (オープン認証) プロトコルをサポートしています。 2つの Microsoft サーバー間でのオンプレミスのサーバー間認証の場合は、サードパーティのトークンサーバーを使用する必要はありません。 Lync Server 2013、Exchange Server、および SharePoint Server には、互いに認証の目的で使用できる組み込みのトークンサーバーがあります。 たとえば、Lync Server 2013 は、セキュリティトークンを単独で発行して署名し、Exchange と通信するときにそのトークンを使用できます。 この場合、サードパーティのトークンサーバーを使用する必要はありません。

Lync Server 2013 は、2台のサーバー間認証シナリオをサポートします。 これには、次のようなサーバー間認証の構成が含まれます。

  - Lync Server 2013 の社内インストールと、Exchange Server 2013、Exchange Server 2016、または SharePoint Server のオンプレミスのインストール。

  - Office コンポーネントのペア (たとえば、Microsoft Exchange 365 と Microsoft Lync Server 365 の間、または Microsoft Lync Server 365 と Microsoft SharePoint 365 の間)。

<div>


> [!NOTE]  
> オンプレミスのサーバーと Microsoft 365 または Office 365 コンポーネントとの間のサーバー間認証は、この Lync Server 2013 リリースではサポートされていません。 これは特に、Lync Server 2013 と Microsoft Exchange 365 の社内インストールとの間でサーバー間認証をセットアップできないことを意味します。



</div>

サーバー間認証の詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「 [Lync server 2013 でのサーバー間認証 (OAuth) およびパートナーアプリケーションの管理](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

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
ms.openlocfilehash: 198df79f63415affa4fb9b41d55265b58ae00a8a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756261"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a>Lync Server 2013 での Exchange と SharePoint の統合のサポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2017-01-18_

Lync Server 2013 および Lync 2013 では、これらの製品を統合すると、Office 2013、Exchange Server 2013、Exchange Server 2016、SharePoint などの他のアプリケーションやサーバー製品との安全かつシームレスな通信を行うことができます。 Lync Server 2013 と Office を統合すると、ユーザーは、Lync のインスタントメッセージング (IM)、拡張プレゼンス、電話、電話会議などの機能にコンテキストでアクセスできるようになります。 Office ユーザーは、Outlook 2013 メッセージングおよび共同作業クライアント、および他の Office プログラムまたは SharePoint ページから Lync 機能にアクセスできます。 ユーザーは、Outlook の [会話履歴] フォルダーで Lync の会話のレコードを表示することもできます。 Lync Server 2013 は、Exchange 2013、Exchange 2016、または Exchange Online と統合されている場合に、次の機能もサポートしています。

  - 統合連絡先ストア: Lync 2013、Exchange、Outlook、Outlook Web App で情報をグローバルに使用できるように、ユーザーは Exchange または Exchange Online のすべての連絡先情報を保存できます。

  - Exchange ユーザーフォルダーに保存された会話履歴と Web 会議履歴。

  - IM や会議の内容など、Lync からアーカイブされたコンテンツは、Exchange ストレージに保存することができます。

<div>


> [!NOTE]  
> Lync Server 2013 は、以前のバージョンの Microsoft Exchange Server と SharePoint Server との統合をサポートしていますが、Microsoft Exchange とのアーカイブストレージの統合など、以前のバージョンではすべての機能がサポートされているわけではありません。<BR>Exchange 2013 または Exchange 2016 にユーザーを移行する場合は、移行の完了時に Exchange ストレージと Lync Server ストレージの両方を暫定的な方法で使うことができます。 Exchange と Lync の両方のサーバーストレージを永続的に使用することはサポートされていません。



</div>

Lync server 2013 と Exchange Server および SharePoint server との統合には、Lync Server 2013、Exchange Server、および SharePoint Server を実行しているサーバー間のサーバー間認証が必要です。 Lync Server 2013 は、サーバー間の認証と承認のための OAuth (Open Authorization) プロトコルをサポートしています。 2つの Microsoft サーバー間でのオンプレミスのサーバー間認証の場合、サードパーティのトークンサーバーを使用する必要はありません。 Lync Server 2013、Exchange Server、および SharePoint Server には、相互に認証目的で使用できる組み込みのトークンサーバーがあります。 たとえば、Lync Server 2013 は、セキュリティトークンを単独で発行して署名し、Exchange と通信するときにそのトークンを使うことができます。 この場合、サードパーティのトークンサーバーを使用する必要はありません。

Lync Server 2013 は、サーバー間認証の2つのシナリオをサポートしています。 これには、次のようなサーバー間認証の構成が含まれます。

  - オンプレミスでの Lync Server 2013 および exchange server 2013、Exchange Server 2016、または SharePoint Server のオンプレミスインストール。

  - Office コンポーネントのペア (たとえば、Microsoft Exchange 365 と Microsoft Lync Server 365、または Microsoft Lync Server 365 と Microsoft SharePoint 365 の間)。

<div>


> [!NOTE]  
> この Lync Server 2013 リリースでは、オンプレミスサーバーと Office 365 コンポーネント間のサーバー間認証はサポートされていません。 特に、Lync Server 2013 と Microsoft Exchange 365 のオンプレミスインストールとの間でサーバー間認証をセットアップできないことを意味します。



</div>

サーバー間認証の詳細については、展開ドキュメントまたは操作のドキュメントの「 [Lync server 2013 でのサーバー間認証 (OAuth) とパートナーアプリケーションの管理](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>


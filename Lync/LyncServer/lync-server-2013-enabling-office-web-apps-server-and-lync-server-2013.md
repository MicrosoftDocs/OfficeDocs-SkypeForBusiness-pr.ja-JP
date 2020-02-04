---
title: 'Lync Server 2013: Lync Server 2013 と Office Web Apps サーバーの有効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Office Web Apps Server and Lync Server 2013
ms:assetid: 3370ab55-9949-4f32-b88b-5cffed6aaad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204792(v=OCS.15)
ms:contentKeyID: 48183790
ms.date: 08/19/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37715182ba704f71bad463044ec9b47cea8f777b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a>Lync Server 2013 と Office Web Apps サーバーの統合の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-08-19_

Lync Server 2013 は、PowerPoint プレゼンテーションを処理するために Office Web Apps サーバーを採用しています。 この方法の利点については、「 [Lync Server 2013 での web 会議の概要](lync-server-2013-web-conferencing-overview.md)」を参照してください。

これらの新機能を使用するには、管理者が Office Web Apps サーバーをインストールしている必要があります。また、管理者は、Office Web Apps サーバーと通信するように Lync Server 2013 を構成する必要があります。 このドキュメントでは、Lync Server 2013 を Office Web Apps サーバーと連携するように構成する方法について説明します。 このドキュメントでは、Office Web Apps サーバー自体をインストールする方法について説明していません。この情報については、の Microsoft Office Web Apps 展開<http://go.microsoft.com/fwlink/p/?linkid=257525>web サイトを参照してください。 このガイドには、Office Web Apps サーバーの必要な情報がすべて含まれています。Office Web Apps サーバーは、Lync Server、Microsoft SQL Server、またはその他のサーバーアプリケーションを実行していないスタンドアロンコンピューターにインストールする必要があることに注意してください。 (そのコンピューターには Microsoft Office のバージョンがインストールされていない必要があります)。Office Web Apps サーバーを実行するために使用するコンピューターには、特定のソフトウェアセット (.NET Framework 4.5 および Windows PowerShell 3.0 を含む) がインストールされている必要もあります。これらの要件と、証明書およびインターネットインフォメーションサービス (IIS) を構成する方法については、Microsoft Office Web Apps 展開の web <http://go.microsoft.com/fwlink/p/?linkid=257525>サイトで詳しく説明します。

<div>


> [!NOTE]  
> Office Web Apps サーバーの最新のイテレーションは、Lync Server 2013 でサポートされている Office Online Server という名前です。 詳細については、「 <A href="https://technet.microsoft.com/en-us/library/jj219456(v=office.16).aspx">Office Online Server のドキュメント</A>」を参照してください。



</div>

このドキュメントでは、次のトピック領域について説明します。

  - [Office Web Apps サーバーで動作するように Lync Server 2013 を構成する](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [リバースプロキシサーバーを使用して Lync Server 2013 で Office Web Apps サーバーを発行する](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [Lync Server 2013 で Office Web Apps サーバーの構成を検証する](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [Lync Server 2013 のクライアントで Office Web Apps サーバーを使用するように構成する](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

</div>

<span> </span>

</div>

</div>

</div>


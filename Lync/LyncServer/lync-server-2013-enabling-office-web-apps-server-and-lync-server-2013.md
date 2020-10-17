---
title: 'Lync Server 2013: Office Web Apps サーバーと Lync Server 2013 の有効化'
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
ms.openlocfilehash: 89ec4337bd4bc728f9737ecb75bb29075831bc09
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528544"
---
# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a>Office Web Apps Server および Lync Server 2013 との統合の構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-08-19_

Lync Server 2013 は、Office Web Apps サーバーを採用して PowerPoint プレゼンテーションを処理します。 このアプローチの利点については、「 [Lync Server 2013 の web 会議の概要](lync-server-2013-web-conferencing-overview.md)」を参照してください。

これらの新機能を使用するには、管理者が Office Web Apps サーバーをインストールする必要があります。また、Office Web Apps サーバーと通信するように Lync Server 2013 を構成する必要があります。 このドキュメントでは、Office Web Apps サーバーを使用するように Lync Server 2013 を構成する方法について説明します。 このドキュメントでは、Office Web Apps サーバー自体をインストールする方法について説明します。その情報については、「Microsoft Office Web Apps 展開 web サイト」を参照してください <https://go.microsoft.com/fwlink/p/?linkid=257525> 。 このガイドには、Office Web Apps サーバーの完全な前提条件に関する情報が含まれています。Office Web Apps サーバーは、Lync Server、Microsoft SQL Server、またはその他のサーバーアプリケーションを実行していないスタンドアロンのコンピューターにインストールする必要があることに注意してください。 (そのコンピューターに Microsoft Office のバージョンがインストールされていないことが必要です。)Office Web Apps サーバーを実行するために使用するコンピューターには、(.NET Framework 4.5 および Windows PowerShell 3.0 を含む) 特定のソフトウェアセットがインストールされている必要もあります。これらの要件と、証明書およびインターネットインフォメーションサービス (IIS) の構成に関する情報については、「Microsoft Office Web Apps 展開 web サイト」を参照して <https://go.microsoft.com/fwlink/p/?linkid=257525> ください。

<div>


> [!NOTE]  
> Office Web Apps サーバーの最新のイテレーションは、Lync Server 2013 でサポートされている Office Online Server と呼ばれています。 詳細については、 <A href="https://technet.microsoft.com/library/jj219456(v=office.16).aspx">Office Online Server のドキュメント</A>を参照してください。



</div>

このドキュメントでは、次のトピックの分野について説明します。

  - [Office Web Apps サーバーで動作するように Lync Server 2013 を構成する](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [Lync Server 2013 でのリバースプロキシサーバーを使用した Office Web Apps サーバーの発行](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [Lync Server 2013 での Office Web Apps サーバーの構成の検証](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [Office Web Apps サーバーで使用する Lync Server 2013 のクライアントの構成](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

</div>

<span> </span>

</div>

</div>

</div>


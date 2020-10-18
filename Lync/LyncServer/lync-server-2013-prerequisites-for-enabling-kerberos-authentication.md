---
title: 'Lync Server 2013: Kerberos 認証を有効にするための前提条件'
description: 'Lync Server 2013: Kerberos 認証を有効にするための前提条件。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65a45bad0eb249fdbc717fe05f080ce737c87c6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579923"
---
# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a>Lync Server 2013 で Kerberos 認証を有効にするための前提条件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

Kerberos 認証を有効にする前に、すべての前提条件の構成とインフラストラクチャの準備を完了していることを確認してください。

  - Lync Server 2013 に対して Active Directory スキーマが拡張されます。

  - Lync Server 2013 の Active Directory フォレストの準備が完了しました。

  - Lync Server 2013 の Active Directory ドメインの準備が完了しました。

  - 中央管理ストアが正常にインストールされ、使用可能になります。

  - トポロジは、トポロジビルダーを使用して作成および発行されています。

  - Web サービスを必要とするサーバーと役割 (フロントエンドサーバー、Standard Edition サーバー、ディレクターなど) が定義および展開されている。

  - Lync Server 2013 の Web サービスをサポートするために推奨される役割サービスを使用して、インターネットインフォメーションサービス (IIS) が構成および展開されている。

前提条件が満たされていない場合は、展開で Kerberos 認証に使用する Web サービスのアカウントを1つ以上作成することができます。 少なくとも、展開ごとに Kerberos 認証アカウントを1つ作成する必要があります。 ただし、サイトごとにローカル Kerberos 認証を提供するために、サイトごとにアカウントを作成することができます。 サイトごとに1つの Kerberos 認証アカウントのみを指定できます。

</div>

<span> </span>

</div>

</div>

</div>


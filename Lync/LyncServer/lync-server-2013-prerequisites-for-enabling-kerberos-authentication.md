---
title: 'Lync Server 2013: Kerberos 認証を有効にするための前提条件'
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
ms.openlocfilehash: adb722f69dcd975d7f346b6e4db8f8ff140f4ac3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a>Lync Server 2013 で Kerberos 認証を有効にするための前提条件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-21_

Kerberos 認証を有効にする前に、必要な構成とインフラストラクチャの準備がすべて完了していることを確認してください。

  - Lync Server 2013 の Active Directory スキーマが拡張されています。

  - Lync Server 2013 の Active Directory フォレストの準備が完了しました。

  - Lync Server 2013 の Active Directory ドメインの準備が完了しました。

  - 中央管理ストアが正常にインストールされ、使用できるようになりました。

  - トポロジは、トポロジビルダーを使用して作成および公開されています。

  - Web サービスを必要とするサーバーと役割は、フロントエンドサーバー、標準エディションサーバー、およびディレクターなど、定義および展開されています。

  - Lync Server 2013 で Web サービスをサポートするために推奨される役割サービスを使用して、インターネットインフォメーションサービス (IIS) を構成し、展開します。

前提条件が満たされた後で、展開のために Kerberos 認証に使用する1つ以上のアカウントを Web サービス用に作成する準備ができている必要があります。 少なくとも、展開ごとに1つの Kerberos 認証アカウントを作成する必要があります。 ただし、サイトにローカルの Kerberos 認証を提供するために、各サイトのアカウントを作成することができます。 1つのサイトにつき1つの Kerberos 認証アカウントのみを指定できます。

</div>

<span> </span>

</div>

</div>

</div>


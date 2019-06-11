---
title: 'Lync Server 2013: IIS の保護'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Protecting IIS in Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518332(v=OCS.15)
ms:contentKeyID: 62625492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 711adaec00e37cbd826f8aabcadc45948548c3f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="protecting-iis-in-lync-server-2013"></a>Lync Server 2013 での IIS の保護

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-12-05_

Microsoft Office Communications Server 2007 および Microsoft Office Communications Server 2007 R2 で、インターネットインフォメーションサービス (IIS) は標準ユーザーアカウントで実行されました。 この問題の原因となっている可能性があります。パスワードの有効期限が切れた場合、Web サービスが失われることがあります。これは、診断が困難な問題です。 有効期限が切れたパスワードの問題を回避するために、Microsoft Lync Server 2013 では、IIS を実行しているサイトのすべてのコンピューターの認証プリンシパルとして機能するコンピューターアカウント (実際に存在しないコンピューターの場合) を作成できます。 これらのアカウントは Kerberos 認証プロトコルを使用するため、アカウントは Kerberos アカウントと呼ばれ、新しい認証プロセスが Kerberos Web 認証として認識されます。 このため、1 つのアカウントを使用してすべての IIS サーバーを管理できます。

この認証プリンシパルでサーバーを実行するには、まず、新しい-Csker":" アカウントコマンドレットを使用してコンピューターアカウントを作成する必要があります。このアカウントは、1つ以上のサイトに割り当てられます。 割り当てが行われた後、Enable-CsTopology コマンドレットを実行することで、アカウントと Lync Server 2013 サイト間の関連付けが有効になります。 この操作を行うと、Active Directory ドメインサービス (AD DS) に必要なサービスプリンシパル名 (SPN) が作成されます。 SPN は、クライアント アプリケーションが特定のサービスを検出するためのものです。 詳細については、操作のドキュメントに記載されている「[新](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount)機能」を参照してください。

<div>

## <a name="best-practices"></a>ベスト プラクティス

IIS のセキュリティを強化するために、IIS 用の Kerberos アカウントを実装することをお勧めします。 Kerberos アカウントを実装しない場合、IIS は標準のユーザーアカウントで実行されます。

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: IIS を保護する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Protecting IIS in Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518332(v=OCS.15)
ms:contentKeyID: 62625492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d53797c490ba53872786311b51e310e6400addf5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="protecting-iis-in-lync-server-2013"></a>Lync Server 2013 での IIS の保護

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-12-05_

Microsoft Office Communications Server 2007 および Microsoft Office Communications Server 2007 R2 では、インターネットインフォメーションサービス (IIS) は標準のユーザーアカウントで実行されました。 これにより、問題が発生する可能性がありました。パスワードが期限切れになると、Web サービスが失われる可能性があります。これは、診断が困難な問題です。 有効期限が切れたパスワードの問題を回避するために、Microsoft Lync Server 2013 では、IIS を実行しているサイト内のすべてのコンピューターの認証プリンシパルとして機能するコンピューターアカウント (実際に存在しないコンピューターの場合) を作成できます。 これらのアカウントは Kerberos 認証プロトコルを使用するため、アカウントは Kerberos アカウントと呼ばれ、新しい認証プロセスは Kerberos web 認証と呼ばれます。 これにより、1つのアカウントを使用してすべての IIS サーバーを管理できるようになります。

この認証プリンシパルでサーバーを実行するには、最初に New-CsKerberosAccount コマンドレットを使用してコンピューター アカウントを作成し、次にこのアカウントを 1 つ以上のサイトに割り当てます。 割り当てが行われた後、Enable-CsTopology コマンドレットを実行することによって、アカウントと Lync Server 2013 サイト間の関連付けが有効になります。 特に重要なのは、これによって必要なサービス プリンシパル名 (SPN) が Active Directory ドメイン サービス (AD DS) 内に作成されることです。 SPN は、クライアント アプリケーションが特定のサービスを見つけるために利用されます。 詳細については、「操作」のドキュメントの「[New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount)」を参照してください。

<div>

## <a name="best-practices"></a>ベスト プラクティス

IIS のセキュリティを強化するために、IIS 用の Kerberos アカウントを実装することをお勧めします。Kerberos アカウントを実装しない場合、IIS は標準のユーザー アカウントで実行されます。

</div>

</div>

<span> </span>

</div>

</div>

</div>


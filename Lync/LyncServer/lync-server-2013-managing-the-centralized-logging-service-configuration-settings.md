---
title: 集中ログサービスの構成設定の管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Centralized Logging Service configuration settings
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49733875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99d496bf211abe2c9ccab04c45eb0fd0fba7439d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524954"
---
# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 での集中ログサービスの構成設定の管理

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

集中ログサービスは、個々のコンピューターの集中ログサービスエージェント (CLSController) にコマンドを送信するために、集中ログサービスコントローラー (CLSController) によって作成および使用される設定とパラメーターによって制御および構成されます。 このエージェントは送信されたコマンドを処理し、シナリオ、プロバイダー、ログ サイズ、トレース期間、およびフラグの構成を使用して、提供された構成情報に従うトレース ログの収集を開始します。

<div>


> [!IMPORTANT]
> 集中ログサービス用に一覧表示されているすべての Windows PowerShell コマンドレットは、Lync Server 2013 社内展開で使用することを目的としたものではありません。 次のコマンドレットは、稼働しているように見える場合がありますが、Lync Server 2013 の社内展開で機能するようには設計されていません。 
> <UL>
> <LI>
> <P><STRONG>CsClsRegion コマンドレット:</STRONG> <A href="https://technet.microsoft.com/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>、<A href="https://technet.microsoft.com/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>、<A href="https://technet.microsoft.com/library/JJ204658(v=OCS.15)">New-CsClsRegion</A>、および <A href="https://technet.microsoft.com/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>。</P>
> <LI>
> <P><STRONG>CsClsSearchTerm コマンドレット:</STRONG> <A href="https://technet.microsoft.com/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> および <A href="https://technet.microsoft.com/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>。</P>
> <LI>
> <P><STRONG>CsClsSecurityGroup コマンドレット:</STRONG> <A href="https://technet.microsoft.com/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>、<A href="https://technet.microsoft.com/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>、<A href="https://technet.microsoft.com/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>、および <A href="https://technet.microsoft.com/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>。</P></LI></UL>これらのコマンドレットで定義されている設定は、悪影響を及ぼすことはありませんが、Microsoft 365 で使用するように設計されており、オンプレミスの展開で予期した結果をもたらすことはありません。 これは、内部設置型展開ではこれらのコマンドレットが役に立たないという意味ではありませんが、その用途はより高度なトピックであるため、このドキュメントでは扱われません。


</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

このセクションのトピックでは、集中ログサービスの構成オプション、パラメーター、および設定を定義します。 集中ログサービスの構成方法、構成設定の取得方法、シナリオの作成方法、集中ログサービスのためのセキュリティグループの管理、検索などについては、以下のトピックを参照してください。

  - [Lync Server 2013 でのコンピューター、サイト、およびグローバルな集中ログサービスの構成の管理](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [Lync Server 2013 での集中ログサービスのプロバイダーの構成](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [Lync Server 2013 での集中ログサービスのシナリオの構成](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の集中ログサービスの概要](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[Lync Server 2013 での集中ログのコマンドレット](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


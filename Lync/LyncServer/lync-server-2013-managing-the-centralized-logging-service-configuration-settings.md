---
title: 中央集中ログサービスの構成設定を管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Centralized Logging Service configuration settings
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49733875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cb3b16210b3fac64c0c5bd7886849da7dd0d065
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 で中央集中ログサービスの構成設定を管理する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

一元化されたログサービスは、一元管理サービスコントローラー (CLSController) によって作成および使用される設定とパラメーターによって制御および構成され、個々のコンピューターの集中ログサービスエージェントにコマンドを送信します (CLSAgent)。 エージェントは、送信されたコマンドを処理し、開始コマンドの場合は、提供された構成情報に従って、シナリオ、プロバイダー、ログサイズ、トレースの継続時間、フラグの構成を使ってトレースログの収集を開始します。

<div>


> [!IMPORTANT]
> 一元管理のログサービス用に一覧表示されているすべての Windows PowerShell コマンドレットは、Lync Server 2013 オンプレミスの展開で使用することを目的としていません。 機能しているように見えても、次のコマンドレットは Lync Server 2013 オンプレミスの展開で機能するように設計されていません。 
> <UL>
> <LI>
> <P><STRONG>Csclsregion コマンドレット:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ204879(v=OCS.15)">Get-csclsregion</A>、 <A href="https://technet.microsoft.com/en-us/library/JJ204746(v=OCS.15)">Set-csclsregion</A>、 <A href="https://technet.microsoft.com/en-us/library/JJ204658(v=OCS.15)">New-</A>CsClsRegion、および削除された<A href="https://technet.microsoft.com/en-us/library/JJ204971(v=OCS.15)">csclsregion</A>。</P>
> <LI>
> <P><STRONG>Csclssearchterm コマンドレット:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205061(v=OCS.15)">取得-csclssearchterm</A>と<A href="https://technet.microsoft.com/en-us/library/JJ204911(v=OCS.15)">Set-csclssearchterm</A>。</P>
> <LI>
> <P><STRONG>CsClsSecurityGroup コマンドレット:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205285(v=OCS.15)">CsClsSecurityGroup</A>、 <A href="https://technet.microsoft.com/en-us/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>、 <A href="https://technet.microsoft.com/en-us/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>、および<A href="https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15)">CsClsSecurityGroup を削除</A>します。</P></LI></UL>これらのコマンドレットで定義された設定により、悪影響を及ぼす可能性はありませんが、Microsoft Office 365 で使用するように設計されていますが、オンプレミスの展開で予期しない結果が返されることはありません。 これは、内部設置型展開ではこれらのコマンドレットが役に立たないという意味ではありませんが、その用途はより高度なトピックであるため、このドキュメントでは扱われません。



</div>

<div>

## <a name="in-this-section"></a>このセクション中

このセクションのトピックでは、一元管理サービスの構成オプション、パラメーター、設定を定義します。 一元管理サービスを構成する方法、構成設定の取得方法、シナリオの作成方法、一元ログサービスのためのセキュリティグループの管理、検索などについては、次のトピックを参照してください。

  - [Lync Server 2013 でのコンピューター、サイト、グローバルな集中ログサービスの構成の管理](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [Lync Server 2013 での中央集中ログサービスのプロバイダーの構成](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [Lync Server 2013 の一元ログサービスのシナリオを構成する](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の一元管理されたログサービスの概要](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[Lync Server 2013 の集中化されたログコマンドレット](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


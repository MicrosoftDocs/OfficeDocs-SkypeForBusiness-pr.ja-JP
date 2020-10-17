---
title: 'Lync Server 2013: ボイスメール再ルーティング設定の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure voice mail rerouting settings
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398606(v=OCS.15)
ms:contentKeyID: 48184593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b51a529ee7bc4fd1148413058ceaf1f1f6d61e06
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520184"
---
# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a>Lync Server 2013 でボイスメールの再ルーティング設定を構成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-18_

存続可能 Branch アプライアンスおよび存続可能ブランチサーバーは、Exchange ユニファイドメッセージング (UM) が中央サイトにインストールされていて、Exchange UM メッセージ自動応答 (AA) が展開されている場合、WAN の停止時にブランチユーザーにボイスメール存続性を提供できます。 Exchange 管理者は、メッセージのみを受け入れるように AA を構成することをお勧めします。これは、ユーザーへの転送、またはオペレーターへの転送など、他の一般的な機能を無効にします。 または、通話をルーティングするために汎用 AA または AA をカスタマイズして使用することもできます。

詳細については、「計画」のドキュメントの「 [Lync Server 2013 のブランチサイトの復元要件](lync-server-2013-branch-site-resiliency-requirements.md) 」セクションの「ボイスメールの存続性の準備」を参照してください。

<div>

## <a name="to-configure-voice-mail-survivability"></a>ボイス メールの存続性を構成するには

1.  Exchange 管理者に、メッセージのみを受信するように AA を構成するように依頼します (Exchange シェルでは、次のコマンドレットを使用します。 **Set-UMAutoAttendant \<AA name\> -call$false** メッセージを残すことを許可するかどうかを指定するパラメーター (*SendVoiceMsgEnabled*) は、既定では true になっています。

2.  Lync Server 管理シェルで、 **get-csvoicemailreroutingconfiguration** コマンドレットを使用して、存続可能 branch Appliance または存続可能ブランチサーバーのボイスメール再ルーティング構成で、Exchange UM 自動応答の電話番号として AA 電話番号を設定します。
    
    <div>
    

    > [!NOTE]  
    > ボイス メール再ルーティング設定を後で変更する必要がある場合は、<STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG> コマンドレットを使用して変更します。 <STRONG>New-</STRONG> および <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG> の詳細については、シェル ヘルプ トピックを参照してください。

    
    </div>

3.  ブランチユーザーの Exchange UM ダイヤルプランに対応する Exchange UM サブスクライバーアクセス番号を、存続可能 Branch Appliance または存続可能ブランチサーバーのボイスメール再ルーティング構成の Exchange um サブスクライバーアクセス番号として設定します。
    
    <div>
    

    > [!NOTE]  
    > WAN の停止時にボイスメール機能にアクセスする必要があるすべてのブランチユーザーに関連付けられたダイヤルプランが1つだけになるように、Exchange UM ユーザーのダイヤルプランを構成します。

    
    </div>

存続可能 Branch Appliance または存続可能ブランチサーバーの**次のステップ**: [Lync Server 2013 の存続可能ブランチアプライアンスまたはサーバーのホームユーザー](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>


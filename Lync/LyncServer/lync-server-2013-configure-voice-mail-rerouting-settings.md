---
title: 'Lync Server 2013: ボイス メール再ルーティング設定の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure voice mail rerouting settings
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398606(v=OCS.15)
ms:contentKeyID: 48184593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73aa16f7c18665c0b74c1e31e2ce888abdbe1c5a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840307"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a>Lync Server 2013 でのボイス メール再ルーティング設定の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-18_

Exchange ユニファイドメッセージング (UM) がセントラルサイトにインストールされていて、Exchange UM メッセージ自動応答 (AA) が展開されている場合は、Survivable Branch アプライアンスと Survivable ブランチサーバーで、WAN の停止中に、支店のユーザーに対してボイスメール survivability を提供できます。 Exchange 管理者がメッセージのみを受け取るように AA を構成することをお勧めします。これは、ユーザーへの転送や、オペレーターへの転送などの一般的な機能を無効にすることをお勧めします。 または、一般的な AA またはカスタマイズした AA を使って通話をルーティングすることもできます。

詳細については、計画ドキュメントの「 [Lync Server 2013 のブランチサイトの回復要件](lync-server-2013-branch-site-resiliency-requirements.md)」セクションの「ボイスメールの Survivability の準備」を参照してください。

<div>

## <a name="to-configure-voice-mail-survivability"></a>ボイスメールの survivability を構成するには

1.  Exchange 管理者に、メッセージのみを受け取るように AA を構成するように依頼します (Exchange Shell では、次のコマンドレットを使用します。 **Set-UMAutoAttendant \<AA 名\> -calla oneenabled $false**。 メッセージを残すことを許可するように指定するパラメーター (*SendVoiceMsgEnabled*) は、既定では true です。

2.  Lync Server 管理シェルで、 **CSVoiceMailReroutingConfiguration**コマンドレットを使用して、Survivable Branch アプライアンスのボイスメール再ルーティング構成の Exchange UM 自動応答の電話番号として AA 電話番号を設定します。Survivable Branch Server。
    
    <div>
    

    > [!NOTE]  
    > 後でボイスメールの再ルーティング設定を変更する必要がある場合は、 <STRONG>CsVoiceMailReRoutingConfiguration</STRONG>コマンドレットを使用します。 詳細について<STRONG></STRONG>は、Shell のヘルプトピックを参照してください。 <STRONG>CSVoiceMailReroutingConfiguration</STRONG>の詳細については、こちらを参照してください。

    
    </div>

3.  ブランチユーザーの Exchange UM ダイヤルプランに対応する Exchange um サブスクライバーアクセス番号を、Survivable Branch Appliance または Survivable ブランチサーバーのボイスメール再ルーティング構成の Exchange UM サブスクライバーアクセス番号として設定します。
    
    <div>
    

    > [!NOTE]  
    > WAN の停止中にボイスメール機能にアクセスする必要があるすべての支店ユーザーに関連付けられたダイヤルプランが1つだけになるように、Exchange UM ユーザーのダイヤルプランを構成します。

    
    </div>

Survivable Branch Appliance または Survivable ブランチサーバーの**次の手順**: [Lync Server 2013 で Survivable ブランチアプライアンスまたはサーバーのホームユーザー](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>


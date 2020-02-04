---
title: 'Lync Server 2013: ブランチ ユーザー用の VoIP ルーティング ポリシーの作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the VoIP routing policy for branch users
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398196(v=OCS.15)
ms:contentKeyID: 48183435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1cc8f0a6c4d960b4dacf6f62f283d806a6dd6f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a>Lync Server 2013 でのブランチ ユーザー用の VoIP ルーティング ポリシーの作成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-23_

ブランチサイトのユーザーに対して、個別のボイスオーバー IP (VoIP) ポリシーを作成することをお勧めします。 このポリシーには、Survivable Branch Appliance ゲートウェイまたは Survivable ブランチサーバーの外部ゲートウェイからの出口へのルート、および中央サイトのゲートウェイからの出口へのバックアップルートを含める必要があります。 ユーザーが登録されている場所に関係なく、Survivable Branch Appliance または Survivable Branch Server のレジストラー、またはセントラルサイトのバックアップレジストラークラスターでは、ユーザーの VoIP ポリシーが常に有効になります。

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a>ブランチユーザーの VoIP ルーティングポリシーを構成するには

1.  ユーザーレベルのダイヤルプランを作成して、ブランチユーザーに割り当てる。 (操作のドキュメントにある「 [Lync Server 2013 でダイヤルプランを作成](lync-server-2013-create-a-dial-plan.md)する」を参照してください)。

2.  そのサイトのユーザーのダイヤルの傾向に対応する正規化ルールを割り当てます。 Survivable Branch Appliance または Survivable Branch Server ユーザーがセントラルサイトのバックアップレジストラープールにフェールオーバーした場合、同じダイヤルプランが有効になります。 (操作のドキュメントにある「 [Lync Server 2013 でダイヤルプランを作成](lync-server-2013-create-a-dial-plan.md)する」を参照してください)。

3.  Survivable Branch Appliance ゲートウェイまたは Survivable ブランチサーバー外部ゲートウェイから egresses されるボイスルートを構成します。 (操作のドキュメントの「 [Lync Server 2013 での音声ルートの作成](lync-server-2013-create-a-voice-route.md)」を参照してください)。

4.  Survivable Branch Appliance または Survivable Branch Server ゲートウェイでバックアップのレジストラープール (仲介サーバーに接続されている) をセントラルサイトで参照するように設定します。 (Survivable Branch Appliance または Survivable Branch Server ベンダーのマニュアルを参照してください。)
    
    <div>
    

    > [!NOTE]  
    > このバックアップ通話ルーティングのセットアップは、Survivable Branch Appliance または Survivable Branch Server が利用できない場合 (たとえば、メンテナンスのために停止している場合など) に、ブランチユーザーへの着信通話が機能するようにするために役立ちます。 Survivable Branch Appliance または Survivable ブランチサーバー上のレジストラーと仲介サーバーが使用できず、ユーザーがセントラルサイトのバックアップレジストラープールに登録されている場合は、着信通話をユーザーにルーティングすることができます。

    
    </div>

**次の手順**: [Lync Server 2013 でボイスメールの再ルーティング設定を構成する](lync-server-2013-configure-voice-mail-rerouting-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: ブランチユーザーの VoIP ルーティングポリシーの作成'
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
ms.openlocfilehash: 7cc958e5f643a18c45989d5835fd786c001899db
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a>Lync Server 2013 でのブランチユーザーの VoIP ルーティングポリシーの作成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-23_

ブランチ サイトのユーザーを対象に独立したボイス オーバー IP (VoIP) ポリシーを作成することをお勧めします。 このポリシーには、存続可能 Branch Appliance gateway または存続可能ブランチサーバーの外部ゲートウェイから出口へのルートと、中央サイトのゲートウェイから出力されるバックアップルートを含める必要があります。 ユーザーが登録されている場所に関係なく、存続可能 Branch Appliance または存続可能 Branch Server または中央サイトのバックアップレジストラークラスターのレジストラーでは、ユーザーの VoIP ポリシーが常に有効になります。

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a>ブランチ ユーザーの VoIP ルーティング ポリシーを構成するには

1.  ユーザーレベルのダイヤルプランを作成して、ブランチユーザーに割り当てます。 (「操作」のドキュメントの「 [Lync Server 2013 でダイヤルプランを作成](lync-server-2013-create-a-dial-plan.md)する」を参照してください)。

2.  そのサイトのユーザーのダイヤル傾向に対応する正規化ルールを割り当てます。 存続可能 Branch Appliance または存続可能 Branch Server ユーザーがセントラルサイトのバックアップレジストラープールにフェールオーバーすると、同じダイヤルプランが有効になります。 (「操作」のドキュメントの「 [Lync Server 2013 でダイヤルプランを作成](lync-server-2013-create-a-dial-plan.md)する」を参照してください)。

3.  存続可能 Branch Appliance gateway または存続可能ブランチサーバーの外部ゲートウェイから egresses する音声ルートを構成します。 (「操作」のドキュメントの「 [Create a voice route In Lync Server 2013](lync-server-2013-create-a-voice-route.md) 」を参照してください)。

4.  中央サイトにあるバックアップレジストラープール (仲介サーバーと併置されている) を指すように、存続可能 Branch Appliance または存続可能 Branch Server gateway でバックアップ呼び出しルートを設定します。 (存続可能 Branch Appliance または存続可能 Branch Server ベンダーのドキュメントを参照してください)。
    
    <div>
    

    > [!NOTE]  
    > このバックアップ通話ルートの設定は、存続可能 Branch Appliance または存続可能ブランチサーバーが使用できない場合 (たとえば、メンテナンスのため) にブランチユーザーへの着信呼び出しが動作するようにするために使用します。 存続可能ブランチアプライアンスまたは存続可能ブランチサーバー上のレジストラーと仲介サーバーが使用できず、ユーザーがセントラルサイトのバックアップレジストラープールに登録されている場合でも、ユーザーに着信呼び出しをルーティングできます。

    
    </div>

**次のステップ**: [Lync Server 2013 でのボイスメール再ルーティング設定の構成](lync-server-2013-configure-voice-mail-rerouting-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


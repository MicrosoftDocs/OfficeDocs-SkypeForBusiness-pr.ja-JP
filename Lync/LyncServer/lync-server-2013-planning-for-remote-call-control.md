---
title: 'Lync Server 2013: リモート通話コントロールの計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for remote call control
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558658(v=OCS.15)
ms:contentKeyID: 48184371
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee463a93afdb32e4c9cd8e90b068a6d03220cb22
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-remote-call-control-in-lync-server-2013"></a>Lync Server 2013 でのリモート通話コントロールの計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-05_

Lync Server 2013 では、リモート通話コントロールシナリオのサポートにより、ユーザーは自分のデスクトップコンピューター上で Lync 2013 を使用して、構内交換機 (PBX) 電話を制御できます。 このセクションでは、リモート通話コントロール機能およびリモート通話コントロールを展開するための要件について説明します。

PBX と Lync Server 2013 との統合により、リモート通話コントロールが有効になっているユーザーは、次の方法で Lync 2013 ユーザーインターフェイス (UI) を使用して PBX 電話機の呼び出しを制御することができます。

<div>


> [!NOTE]  
> 最終的には、ユーザーの PBX 電話をホストする PBX の機能が、そのユーザーが利用することができるリモート通話コントロールの機能を決定します。



</div>

  - 通話を発信する

  - 着信通話に応答する

  - インスタント メッセージで着信した通話に応答する
    
    <div>
    

    > [!NOTE]  
    > つまり、発信者の電話番号は、組織のグローバルアドレス一覧 (GAL)、呼び出し先の Lync 連絡先リスト、またはフェデレーションパートナーの組織のインスタントメッセージアドレスに関連付けることができます。

    
    </div>

  - 通話の転送

  - 着信の転送

  - 通話の保留

  - 複数の同時通話間の切り替え

  - すでに通話中である時に 2 番目の通話に応答する (つまり、通話中の着信)

  - デュアルトーン多重周波数 (DTMF) 電話番号をダイヤルする

  - [会話] ウィンドウで、Microsoft Office OneNote メモ プログラムにメモを入力する

さらに、ユーザーのリモート通話コントロールが有効になっている場合、Lync 2013 は次の呼び出し情報をユーザーに提供します。

  - 呼び出し元の電話番号が、リモート通話コントロールが有効なユーザーの Microsoft Office Outlook メッセージングおよびコラボレーションクライアント、Lync 連絡先リスト、または組織の GAL の連絡先リストに存在する場合の、名前による発信者の id。

  - Outlook の [会話履歴] フォルダーに保存されている、過去の着信および発信通話。

  - 不在着信通知は、ユーザーの Outlook 受信トレイフォルダーに送信されますが、着信呼び出しの受信時に Lync が実行されている場合にのみ生成されます。

<div>

## <a name="remote-call-control-and-enterprise-voice"></a>リモート通話コントロールとエンタープライズ VoIP

リモート通話コントロール機能はエンタープライズ Voip 機能とは分離されていますが、両方のユーザーが有効にすることはできませんが、エンタープライズ Voip では、リモート通話コントロールが有効になっているユーザーも使用できる機能のサブセットが提供されます。 エンタープライズ Voip が展開されている場合、リモート通話コントロールが有効になっているユーザーは、Lync を使用して次のエンタープライズ Voip 機能にアクセスできます。

  - 別の Lync クライアントに対する音声通話の作成と受信

  - エンタープライズ Voip が有効になっているユーザーが作成した会議のオーディオ部分に参加する

</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 でのリモート通話コントロールの展開タスク](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


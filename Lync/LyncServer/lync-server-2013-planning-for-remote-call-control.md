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
ms.openlocfilehash: b4c07674be037c7d2fe06d6e2811dcd3264cc6db
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725227"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-remote-call-control-in-lync-server-2013"></a>Lync Server 2013 でのリモート通話コントロールの計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-05_

Lync Server 2013 では、リモート通話コントロールのシナリオがサポートされているため、ユーザーは自分のデスクトップコンピューターで Lync 2013 を使用して、プライベート支店の exchange (PBX) 電話を制御することができます。 このセクションでは、リモート通話コントロールの機能と、リモート通話コントロールを展開するための要件について説明します。

PBX と Lync Server 2013 を統合すると、リモート通話2013コントロールが有効になっているユーザーは、次のようにして、PBX 電話での通話を制御できるようになります。

<div>


> [!NOTE]  
> 最終的には、ユーザーの PBX 携帯電話をホストしている PBX の機能によって、そのユーザーが使用できるリモート通話コントロール機能が決定されます。



</div>

  - 発信通話を行う

  - 着信通話に応答する

  - インスタントメッセージで着信に応答する
    
    <div>
    

    > [!NOTE]  
    > つまり、発信者の電話番号は、組織のグローバルアドレス一覧 (GAL)、呼び出し元の Lync 連絡先リスト、またはフェデレーションパートナーの組織内のインスタントメッセージアドレスに関連付けることができます。

    
    </div>

  - 通話の転送

  - 着信通話を転送する

  - 通話を保留にする

  - 複数の同時通話の切り替え

  - すでに通話中 (通話待ち) 中に2回目の通話に応答する

  - Dial dual トーン (DTMF) 数字

  - [会話] ウィンドウで、Microsoft Office OneNote のノート作成プログラムにノートを入力する

さらに、ユーザーがリモート通話コントロールを有効にしている場合は、Lync 2013 によって次の通話情報がユーザーに提供されます。

  - 呼び出し元の電話番号が、リモート通話コントロール対応ユーザーの Microsoft Office Outlook メッセージングおよびコラボレーションクライアント、Lync 連絡先リスト、または組織の GAL の連絡先リストに存在する場合の、名前による発信者の識別。

  - Outlook の [会話履歴] フォルダーに保存されている、過去の着信と発信の通話。

  - 不在着信通知。ユーザーの Outlook 受信トレイフォルダーに送信されますが、着信呼び出しの受信時に Lync が実行されている場合にのみ生成されます。

<div>

## <a name="remote-call-control-and-enterprise-voice"></a>リモート通話コントロールとエンタープライズボイス

リモート通話コントロール機能はエンタープライズボイス機能とは異なりますが、どちらのユーザーも有効にすることはできませんが、エンタープライズボイスは、リモート通話コントロールが有効になっているユーザーが利用できる機能のサブセットを提供します。 エンタープライズボイスが展開されている場合、リモート通話コントロールが有効になっているユーザーは、Lync を使って次のエンタープライズ Voip 機能にアクセスできます。

  - 別の Lync クライアントに対して音声通話を発信および受信する

  - エンタープライズ Voip が有効になっているユーザーによって作成された会議のオーディオ部分に参加する

</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 のリモート通話コントロールの展開タスク](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: リモート通話コントロールと電話番号正規化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remote call control and phone number normalization
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558630(v=OCS.15)
ms:contentKeyID: 48183696
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6eff9fb48e9730549d67638c69d8655d8f04d710
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a>Lync Server 2013 でのリモート通話コントロールと電話番号正規化

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-22_

Lync クライアントは、アドレス帳サービス (ABS) ファイルのダウンロードの一部として、電話番号の正規化ルールをダウンロードします。 リモート通話コントロールのシナリオでは、アドレス帳サービスの電話番号の正規化ルールは、着信と発信の両方のリモート通話コントロールの呼び出しに適用されます。 リモート通話コントロールが有効になっているユーザーへの着信通話の場合、発信者の電話番号は、SIP/CSTA ゲートウェイまたは構内交換機 (PBX) のいずれかによって、最初に164形式に正規化されます。 Lync Server 2013 は、ゲートウェイから通話を受信するときに、呼び出し元の Microsoft Office Outlook 連絡先リストの正規化された数値、またはに保存されているグローバルアドレス一覧 (GAL) に対して、発信者の電話番号に対して逆番号参照 (RNL) を実行します。アドレス帳サービス。 番号を逆参照すると一致するものが見つかると、着信呼び出し通知の名前で呼び出し元が識別されます。

発信リモート通話制御通話の場合、Lync は、SIP/CSTA ゲートウェイへの通話をルーティングする前に、アドレス帳サービスの電話番号の正規化ルールをダイヤルされた番号に適用します。

リモート通話コントロールの電話番号正規化ルールの作成の詳細については、計画ドキュメントの「 [Lync Server 2013 でのダイヤルプランと正規化ルール](lync-server-2013-dial-plans-and-normalization-rules.md)」を参照してください。

<div>

## <a name="migrating-phone-number-normalization-rules"></a>電話番号の正規化ルールを移行する

リモート通話コントロールに対して以前有効にしたユーザーを移行する場合は、移行ドキュメントの次のトピックを参照してください。

  - Lync Server 2010 の場合は、「移行ドキュメントで[アドレス帳を移行](migrate-address-book.md)する」を参照してください。

  - Communications Server 2007 R2 については、「移行ドキュメントで[アドレス帳を移行](migrate-address-book_1.md)する」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>


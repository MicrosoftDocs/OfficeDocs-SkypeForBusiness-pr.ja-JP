---
title: 'Lync Server 2013: リモート通話コントロールと電話番号の正規化'
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
ms.openlocfilehash: 76d7ffb386f6b565fc00b866072bfab6390bc8d9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048738"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a>Lync Server 2013 でのリモート通話コントロールと電話番号の正規化

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-22_

Lync クライアントは、アドレス帳サービス (ABS) ファイルのダウンロードの一部として電話番号の正規化ルールをダウンロードします。 リモート通話コントロール シナリオでは、アドレス帳サービスの電話番号正規化ルールはリモート通話コントロールの着信通話および発信通話の両方に適用されます。 リモート通話コントロールが有効化されているユーザーへの着信通話の場合、発信者の電話番号は SIP/CSTA ゲートウェイまたは構内交換機 (PBX) によってまずは E.164 形式に正規化されます。 Lync Server 2013 は、ゲートウェイからの呼び出しを受信すると、呼び出し先の Microsoft Office Outlook 連絡先リストまたはに格納されているグローバルアドレス一覧 (GAL) の正規化された番号に対して、発信者の電話番号で逆引き参照 (RNL) を実行します。アドレス帳サービス。 逆引き番号検索によって一致する番号が正常に発見された場合、発信者は着信通知を名前で識別されます。

発信リモート通話制御呼び出しの場合、Lync は、SIP/CSTA ゲートウェイに通話をルーティングする前に、アドレス帳サービスの電話番号の正規化ルールをダイヤル番号に適用します。

リモート通話コントロールの電話番号正規化ルールの詳細については、「計画」のドキュメントの「[ダイヤルプランと正規化ルール (Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) )」を参照してください。

<div>

## <a name="migrating-phone-number-normalization-rules"></a>電話番号正規化ルールの移行

リモート通話コントロールに対して既に有効になっているユーザーを移行する場合、「移行」のドキュメントの次のトピックを参照してください。

  - Lync Server 2010 については、「移行」のドキュメントの「 [Migrate Address Book](migrate-address-book.md) 」を参照してください。

  - Communications Server 2007 R2 の場合は、「移行」のドキュメントの「 [Migrate Address Book](migrate-address-book_1.md) 」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>


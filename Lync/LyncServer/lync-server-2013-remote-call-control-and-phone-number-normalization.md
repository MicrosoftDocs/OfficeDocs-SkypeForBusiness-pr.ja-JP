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
ms.openlocfilehash: 211f0f717f7c40895cdbbad75bd98ae0ff90af89
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536554"
---
# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a><span data-ttu-id="b2f89-102">Lync Server 2013 でのリモート通話コントロールと電話番号の正規化</span><span class="sxs-lookup"><span data-stu-id="b2f89-102">Remote call control and phone number normalization in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2f89-103">_**トピックの最終更新日:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="b2f89-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="b2f89-104">Lync クライアントは、アドレス帳サービス (ABS) ファイルのダウンロードの一部として電話番号の正規化ルールをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b2f89-104">Lync clients download phone number normalization rules as part of the Address Book Service (ABS) file download.</span></span> <span data-ttu-id="b2f89-105">リモート通話コントロール シナリオでは、アドレス帳サービスの電話番号正規化ルールはリモート通話コントロールの着信通話および発信通話の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b2f89-105">In remote call control scenarios, Address Book Service phone number normalization rules are applied to both incoming and outgoing remote call control calls.</span></span> <span data-ttu-id="b2f89-106">リモート通話コントロールが有効化されているユーザーへの着信通話の場合、発信者の電話番号は SIP/CSTA ゲートウェイまたは構内交換機 (PBX) によってまずは E.164 形式に正規化されます。</span><span class="sxs-lookup"><span data-stu-id="b2f89-106">For incoming calls to a remote call control-enabled user, the phone number of the caller is first normalized to E.164 format by either the SIP/CSTA gateway or private branch exchange (PBX).</span></span> <span data-ttu-id="b2f89-107">Lync Server 2013 は、ゲートウェイからの呼び出しを受信するときに、発信者の電話番号に対して、アドレス帳サービスに格納されている Microsoft Office Outlook の連絡先リストまたはグローバルアドレス一覧 (GAL) の正規化された番号に対して、逆引き番号検索 (RNL) を実行します。</span><span class="sxs-lookup"><span data-stu-id="b2f89-107">When Lync Server 2013 receives the call from the gateway, it performs reverse number lookup (RNL) on the phone number of the caller against the normalized number in the callee’s Microsoft Office Outlook Contacts list or the global address list (GAL) that is stored in the Address Book Service.</span></span> <span data-ttu-id="b2f89-108">逆引き番号検索によって一致する番号が正常に発見された場合、発信者は着信通知を名前で識別されます。</span><span class="sxs-lookup"><span data-stu-id="b2f89-108">If reverse number lookup successfully finds a match, the caller is identified by name in the incoming call notification.</span></span>

<span data-ttu-id="b2f89-109">発信リモート通話制御呼び出しの場合、Lync は、SIP/CSTA ゲートウェイに通話をルーティングする前に、アドレス帳サービスの電話番号の正規化ルールをダイヤル番号に適用します。</span><span class="sxs-lookup"><span data-stu-id="b2f89-109">For outgoing remote call control calls, Lync applies the Address Book Service phone number normalization rules to the dialed number before routing the call to the SIP/CSTA gateway.</span></span>

<span data-ttu-id="b2f89-110">リモート通話コントロールの電話番号正規化ルールの詳細については、「計画」のドキュメントの「 [ダイヤルプランと正規化ルール (Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) )」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2f89-110">For details about creating phone number normalization rules for remote call control, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<div>

## <a name="migrating-phone-number-normalization-rules"></a><span data-ttu-id="b2f89-111">電話番号正規化ルールの移行</span><span class="sxs-lookup"><span data-stu-id="b2f89-111">Migrating Phone Number Normalization Rules</span></span>

<span data-ttu-id="b2f89-112">リモート通話コントロールに対して既に有効になっているユーザーを移行する場合、「移行」のドキュメントの次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2f89-112">If you are migrating users previously enabled for remote call control, see the following topics in the Migration documentation:</span></span>

  - <span data-ttu-id="b2f89-113">Lync Server 2010 については、「移行」のドキュメントの「 [Migrate Address Book](migrate-address-book.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2f89-113">For Lync Server 2010, see [Migrate Address Book](migrate-address-book.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="b2f89-114">Communications Server 2007 R2 の場合は、「移行」のドキュメントの「 [Migrate Address Book](migrate-address-book_1.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2f89-114">For Communications Server 2007 R2, see [Migrate Address Book](migrate-address-book_1.md) in the Migration documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


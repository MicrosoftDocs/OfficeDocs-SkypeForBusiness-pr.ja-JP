---
title: 'Lync Server 2013: リモート通話コントロールと電話番号正規化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remote call control and phone number normalization
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558630(v=OCS.15)
ms:contentKeyID: 48183696
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86de318cb1e72fce8fb6f42ff7698db5974034fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a><span data-ttu-id="2ed9a-102">Lync Server 2013 でのリモート通話コントロールと電話番号正規化</span><span class="sxs-lookup"><span data-stu-id="2ed9a-102">Remote call control and phone number normalization in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ed9a-103">_**最終更新日:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="2ed9a-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="2ed9a-104">Lync クライアントは、アドレス帳サービス (ABS) ファイルのダウンロードの一部として、電話番号の正規化ルールをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="2ed9a-104">Lync clients download phone number normalization rules as part of the Address Book Service (ABS) file download.</span></span> <span data-ttu-id="2ed9a-105">リモート通話コントロールのシナリオでは、アドレス帳サービスの電話番号の正規化ルールは、着信と発信の両方のリモート通話コントロールの呼び出しに適用されます。</span><span class="sxs-lookup"><span data-stu-id="2ed9a-105">In remote call control scenarios, Address Book Service phone number normalization rules are applied to both incoming and outgoing remote call control calls.</span></span> <span data-ttu-id="2ed9a-106">リモート通話コントロールが有効になっているユーザーへの着信通話の場合、発信者の電話番号は、SIP/CSTA ゲートウェイまたは構内交換機 (PBX) のいずれかによって、最初に164形式に正規化されます。</span><span class="sxs-lookup"><span data-stu-id="2ed9a-106">For incoming calls to a remote call control-enabled user, the phone number of the caller is first normalized to E.164 format by either the SIP/CSTA gateway or private branch exchange (PBX).</span></span> <span data-ttu-id="2ed9a-107">Lync Server 2013 は、ゲートウェイから通話を受信するときに、呼び出し元の Microsoft Office Outlook 連絡先リストの正規化された数値、またはに保存されているグローバルアドレス一覧 (GAL) に対して、発信者の電話番号に対して逆番号参照 (RNL) を実行します。アドレス帳サービス。</span><span class="sxs-lookup"><span data-stu-id="2ed9a-107">When Lync Server 2013 receives the call from the gateway, it performs reverse number lookup (RNL) on the phone number of the caller against the normalized number in the callee’s Microsoft Office Outlook Contacts list or the global address list (GAL) that is stored in the Address Book Service.</span></span> <span data-ttu-id="2ed9a-108">番号を逆参照すると一致するものが見つかると、着信呼び出し通知の名前で呼び出し元が識別されます。</span><span class="sxs-lookup"><span data-stu-id="2ed9a-108">If reverse number lookup successfully finds a match, the caller is identified by name in the incoming call notification.</span></span>

<span data-ttu-id="2ed9a-109">発信リモート通話制御通話の場合、Lync は、SIP/CSTA ゲートウェイへの通話をルーティングする前に、アドレス帳サービスの電話番号の正規化ルールをダイヤルされた番号に適用します。</span><span class="sxs-lookup"><span data-stu-id="2ed9a-109">For outgoing remote call control calls, Lync applies the Address Book Service phone number normalization rules to the dialed number before routing the call to the SIP/CSTA gateway.</span></span>

<span data-ttu-id="2ed9a-110">リモート通話コントロールの電話番号正規化ルールの作成の詳細については、計画ドキュメントの「 [Lync Server 2013 でのダイヤルプランと正規化ルール](lync-server-2013-dial-plans-and-normalization-rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ed9a-110">For details about creating phone number normalization rules for remote call control, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<div>

## <a name="migrating-phone-number-normalization-rules"></a><span data-ttu-id="2ed9a-111">電話番号の正規化ルールを移行する</span><span class="sxs-lookup"><span data-stu-id="2ed9a-111">Migrating Phone Number Normalization Rules</span></span>

<span data-ttu-id="2ed9a-112">リモート通話コントロールに対して以前有効にしたユーザーを移行する場合は、移行ドキュメントの次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ed9a-112">If you are migrating users previously enabled for remote call control, see the following topics in the Migration documentation:</span></span>

  - <span data-ttu-id="2ed9a-113">Lync Server 2010 の場合は、「移行ドキュメントで[アドレス帳を移行](migrate-address-book.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ed9a-113">For Lync Server 2010, see [Migrate Address Book](migrate-address-book.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="2ed9a-114">Communications Server 2007 R2 については、「移行ドキュメントで[アドレス帳を移行](migrate-address-book_1.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ed9a-114">For Communications Server 2007 R2, see [Migrate Address Book](migrate-address-book_1.md) in the Migration documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


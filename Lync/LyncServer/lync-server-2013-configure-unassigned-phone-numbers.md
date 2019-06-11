---
title: 'Lync Server 2013: 未割り当ての電話番号を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure unassigned phone numbers
ms:assetid: a0650659-dce7-455f-8977-02454bbfa400
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182559(v=OCS.15)
ms:contentKeyID: 48185009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22441573c22a932c383c7821cce16d79b9767a7c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unassigned-phone-numbers-in-lync-server-2013"></a><span data-ttu-id="0bf24-102">Lync Server 2013 で割り当てられていない電話番号を構成する</span><span class="sxs-lookup"><span data-stu-id="0bf24-102">Configure unassigned phone numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0bf24-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0bf24-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0bf24-104">Lync Server を使用すると、組織で有効であるが、ユーザーまたは電話に割り当てられていない電話番号への着信通話に対する処理を構成できます。</span><span class="sxs-lookup"><span data-stu-id="0bf24-104">Lync Server lets you configure what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="0bf24-105">このような通話の処理を構成するには、未割り当ての番号テーブルを設定します。</span><span class="sxs-lookup"><span data-stu-id="0bf24-105">To configure the handling of such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="0bf24-106">テーブルを使用して、通話をアナウンスメントアプリケーションまたは Exchange UM サーバーにルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="0bf24-106">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>

<span data-ttu-id="0bf24-p102">割り当てられていない番号の表の構成方法は、その使用方法によって異なります。組織の有効な内線番号すべて、割り当てられていない内線番号のみ、または両方の種類の番号の組み合わせで、この表を構成できます。割り当てられていない番号の表には、割り当てられている番号と割り当てられていない番号を両方入れることができますが、現在割り当てられていない番号を発信者がダイヤルしたときのみ呼び出されます。有効な内線番号すべてを割り当てられていない番号の表に入れる場合、テーブルを再構成しなくても、ユーザーが組織を離れたとき必ず行う処理を指定できます。割り当てられていない内線番号を表に入れる場合、特定の番号について行う処理を調整できます。たとえば、顧客サービス デスクの内線番号を変更する場合、古い顧客サービス番号を表に入れ、新しい番号を知らせるアナウンスをそれに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="0bf24-p102">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0bf24-113">[割り当てられていない番号] テーブルを構成する前に、1つ以上のアナウンス、または Exchange UM 自動応答を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bf24-113">Before you configure the unassigned number table, you must already have either one or more announcements defined or an Exchange UM Auto Attendant set up.</span></span> <span data-ttu-id="0bf24-114">お知らせの作成の詳細については、「 <A href="lync-server-2013-create-an-announcement.md">Lync Server 2013 でお知らせを作成</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bf24-114">For details about creating announcements, see <A href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</A>.</span></span> <span data-ttu-id="0bf24-115">Exchange UM 設定が構成されているかどうかを確認するには、 <STRONG>Get-Csexcontact</STRONG>コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="0bf24-115">To see if you have configured Exchange UM settings, run the <STRONG>Get-CsExUmContact</STRONG> cmdlet.</span></span> <span data-ttu-id="0bf24-116">詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bf24-116">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0bf24-117">このセクション中</span><span class="sxs-lookup"><span data-stu-id="0bf24-117">In This Section</span></span>

  - [<span data-ttu-id="0bf24-118">Lync Server 2013 で、割り当てられていない番号範囲を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="0bf24-118">Create or modify an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-unassigned-number-range.md)

  - [<span data-ttu-id="0bf24-119">Lync Server 2013 で、割り当てられていない番号範囲を削除する</span><span class="sxs-lookup"><span data-stu-id="0bf24-119">Delete an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-delete-an-unassigned-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: 別のアプリケーションからの Lync の起動'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d10e70615083796baa0934c6291b377dcd18005
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519514"
---
# <a name="starting-lync-from-another-application"></a><span data-ttu-id="c2c94-102">別のアプリケーションからの Lync の起動</span><span class="sxs-lookup"><span data-stu-id="c2c94-102">Starting Lync from another application</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2c94-103">_**トピックの最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="c2c94-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="c2c94-104">コマンドラインパラメーターを使用して、Lync 2013 をクイックスタートすることができます。</span><span class="sxs-lookup"><span data-stu-id="c2c94-104">You can use command-line parameters to quick-start Lync 2013.</span></span> <span data-ttu-id="c2c94-105">たとえば、ユーザーが別のアプリケーションで電話番号をクリックすると、アプリケーションは Lync 2013 のインスタンスを開始し、その番号への呼び出しを開始することができます。</span><span class="sxs-lookup"><span data-stu-id="c2c94-105">For example, if a user clicks a phone number in another application, the application can start an instance of Lync 2013 and initiate a call to that number.</span></span>

<span data-ttu-id="c2c94-106">Lync 2013 は、マルチパーティ会議の連絡先名のセミコロンで区切られたリストを認識することもできます。</span><span class="sxs-lookup"><span data-stu-id="c2c94-106">Lync 2013 can also recognize a semicolon-delimited list of contact names for multiparty conferencing.</span></span>

<span data-ttu-id="c2c94-107">Lync 2013 が開始時に自動的にサインインするように構成されている場合、lync 2013 をコマンドラインパラメーター付きで開始すると、Lync のメインウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="c2c94-107">If Lync 2013 is configured to automatically sign in when started, then starting Lync 2013 with command-line parameters will open the Lync main window.</span></span> <span data-ttu-id="c2c94-108">Lync で起動時の自動的なサインインが構成されていない場合は、サインイン ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="c2c94-108">If Lync is not configured to automatically sign in when started, the sign-in window opens.</span></span>

<span data-ttu-id="c2c94-109">次の表に、使用可能なパラメーターを示します。</span><span class="sxs-lookup"><span data-stu-id="c2c94-109">The following table shows the available parameters.</span></span>

### <a name="lync-2013-command-line-parameters"></a><span data-ttu-id="c2c94-110">Lync 2013 Command-Line のパラメーター</span><span class="sxs-lookup"><span data-stu-id="c2c94-110">Lync 2013 Command-Line Parameters</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c2c94-111">拡張子</span><span class="sxs-lookup"><span data-stu-id="c2c94-111">Extension</span></span></th>
<th><span data-ttu-id="c2c94-112">データ形式</span><span class="sxs-lookup"><span data-stu-id="c2c94-112">Format of Data</span></span></th>
<th><span data-ttu-id="c2c94-113">アクション</span><span class="sxs-lookup"><span data-stu-id="c2c94-113">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2c94-114">電話</span><span class="sxs-lookup"><span data-stu-id="c2c94-114">tel:</span></span></p></td>
<td><p><span data-ttu-id="c2c94-115">tel URI</span><span class="sxs-lookup"><span data-stu-id="c2c94-115">tel URI</span></span></p></td>
<td><p><span data-ttu-id="c2c94-116">音声通話用に [会話] ウィンドウを開きますが、指定の番号はダイヤルしません。</span><span class="sxs-lookup"><span data-stu-id="c2c94-116">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2c94-117">callto</span><span class="sxs-lookup"><span data-stu-id="c2c94-117">callto:</span></span></p></td>
<td><p><span data-ttu-id="c2c94-118">tel:、sip:、または入力可能な tel URI</span><span class="sxs-lookup"><span data-stu-id="c2c94-118">tel:, sip:, or typeable tel URI</span></span></p></td>
<td><p><span data-ttu-id="c2c94-119">音声通話用に [会話] ウィンドウを開きますが、指定の番号はダイヤルしません。</span><span class="sxs-lookup"><span data-stu-id="c2c94-119">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2c94-120">sip</span><span class="sxs-lookup"><span data-stu-id="c2c94-120">sip:</span></span></p></td>
<td><p><span data-ttu-id="c2c94-121">SIP URI</span><span class="sxs-lookup"><span data-stu-id="c2c94-121">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="c2c94-122">参加者リストの指定の SIP 一意リソース識別子 (URI) で、[会話] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="c2c94-122">Opens the Conversation window with the specified SIP Uniform Resource Identifier (URI) in the participant list.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2c94-123">Sips</span><span class="sxs-lookup"><span data-stu-id="c2c94-123">Sips:</span></span></p></td>
<td><p><span data-ttu-id="c2c94-124">SIP URI</span><span class="sxs-lookup"><span data-stu-id="c2c94-124">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="c2c94-125">Lync 2013 がトランスポート層セキュリティ (TLS) プロトコルを使用するように構成されている場合は、sip: とまったく同じように機能します。</span><span class="sxs-lookup"><span data-stu-id="c2c94-125">If Lync 2013 is configured to use the Transport Layer Security (TLS) protocol, functions exactly like sip:.</span></span> <span data-ttu-id="c2c94-126">TLS が使用されていない場合は、より高いセキュリティ レベルが必要であることをユーザーに通知するダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2c94-126">If TLS is not being used, displays a dialog box informing the user that a higher level of security is required.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2c94-127">conf</span><span class="sxs-lookup"><span data-stu-id="c2c94-127">conf:</span></span></p></td>
<td><p><span data-ttu-id="c2c94-128">参加する会議の SIP URI</span><span class="sxs-lookup"><span data-stu-id="c2c94-128">SIP URI of conference to join</span></span></p></td>
<td><p><span data-ttu-id="c2c94-p104">自己の URI の場合は、フォーカスをインスタンス化して名簿のみを表示します。 名簿を表示しない場合は、INVITE を送信しないでください。</span><span class="sxs-lookup"><span data-stu-id="c2c94-p104">If URI is self, instantiates the focus and brings up roster-only view. Otherwise, brings up roster view but does not send INVITE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2c94-131">メッセージング</span><span class="sxs-lookup"><span data-stu-id="c2c94-131">im:</span></span></p></td>
<td><p><span data-ttu-id="c2c94-132">SIP URI</span><span class="sxs-lookup"><span data-stu-id="c2c94-132">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="c2c94-133">SIP URI でインスタント メッセージング (IM) のみの [会話] ウィンドウを表示します。</span><span class="sxs-lookup"><span data-stu-id="c2c94-133">Displays an instant messaging (IM)-only Conversation window with the SIP URI.</span></span> <span data-ttu-id="c2c94-134">山かっこ () 内で指定した複数の SIP Uri &lt; &gt; を区切り記号なしで受け入れます。</span><span class="sxs-lookup"><span data-stu-id="c2c94-134">Accepts multiple SIP URIs specified inside angle brackets (&lt;&gt;) without any separator.</span></span></p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c2c94-135">次の表にこれらコマンドライン パラメーターの例を示します。</span><span class="sxs-lookup"><span data-stu-id="c2c94-135">The following table provides examples of these command-line parameters.</span></span>

### <a name="command-line-parameter-examples"></a><span data-ttu-id="c2c94-136">コマンドライン パラメーターの例</span><span class="sxs-lookup"><span data-stu-id="c2c94-136">Command-Line Parameter Examples</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c2c94-137">Instance</span><span class="sxs-lookup"><span data-stu-id="c2c94-137">Instance</span></span></th>
<th><span data-ttu-id="c2c94-138">結果</span><span class="sxs-lookup"><span data-stu-id="c2c94-138">Results</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2c94-139">Tel: + 14255550101</span><span class="sxs-lookup"><span data-stu-id="c2c94-139">Tel:+14255550101</span></span></p></td>
<td><p><span data-ttu-id="c2c94-140">+14255550101 の電話のみの表示を開きます。</span><span class="sxs-lookup"><span data-stu-id="c2c94-140">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2c94-141">Callto:tel:+ 14255550101</span><span class="sxs-lookup"><span data-stu-id="c2c94-141">Callto:tel:+ 14255550101</span></span></p></td>
<td><p><span data-ttu-id="c2c94-142">+14255550101 の電話のみの表示を開きます。</span><span class="sxs-lookup"><span data-stu-id="c2c94-142">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2c94-143">Callto:sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c2c94-143">Callto:sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="c2c94-144">kazuto@litwareinc.com との電話のみの表示を開きます。</span><span class="sxs-lookup"><span data-stu-id="c2c94-144">Opens a phone-only view with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2c94-145">sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c2c94-145">sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="c2c94-146">kazuto@litwareinc.com との [会話] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="c2c94-146">Opens a Conversation window with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2c94-147">conf: sip:https://meet.contoso.com/kazuto/7322994</span><span class="sxs-lookup"><span data-stu-id="c2c94-147">conf:sip:https://meet.contoso.com/kazuto/7322994</span></span></p></td>
<td><p><span data-ttu-id="c2c94-148">会話ウィンドウが開き、会議のオーディオ参加オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2c94-148">Opens a Conversation window and displays meeting audio join options.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


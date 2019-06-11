---
title: サードパーティのコラボレーションアプリケーションと Lync の統合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Integrating a third-party collaboration application with Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398068(v=OCS.15)
ms:contentKeyID: 48183224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0b56fabbc1bd341e3ba2c5fe535d147c09335b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a><span data-ttu-id="cfe1b-102">サードパーティコラボレーションアプリケーションと Lync Server 2013 の統合</span><span class="sxs-lookup"><span data-stu-id="cfe1b-102">Integrating a third-party collaboration application with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cfe1b-103">_**最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="cfe1b-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="cfe1b-104">アプリケーションに関する情報をレジストリに追加することで、Lync 2013 をサードパーティのオンラインコラボレーションアプリケーションと統合することができます。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-104">You can integrate Lync 2013 with any third-party online collaboration application by adding information about the application to the registry.</span></span> <span data-ttu-id="cfe1b-105">Lync 2013 を使用すると、社内のサーバー、インターネットベースのサービス、またはその両方でホストされているデータ会議セッションを開始できます。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-105">You can use Lync 2013 to start data conferencing sessions hosted on an in-house server, an Internet-based service, or both.</span></span> <span data-ttu-id="cfe1b-106">コラボレーションまたはデータ会議セッションは、連絡先リストから、または既存のインスタントメッセージング、音声、またはビデオセッションから開始できます。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-106">The collaboration or data conferencing session can be started from the Contacts list or from an existing instant messaging, voice, or video session.</span></span> <span data-ttu-id="cfe1b-107">Lync 2013 は、アプリケーションを起動するための車両としてのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-107">Lync 2013 acts only as the vehicle for starting the application.</span></span> <span data-ttu-id="cfe1b-108">オンラインコラボレーションセッションが開始された後も、既存の Lync 2013 の会話はアクティブなままになります。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-108">Any existing Lync 2013 conversations remain active after the online collaboration session has begun.</span></span>

<span data-ttu-id="cfe1b-109">以下のセクションでは、Lync 2013 をインターネットベースおよびサーバーベースのコラボレーションアプリケーションと統合する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-109">The following sections describe how to integrate Lync 2013 with Internet-based and server-based collaboration applications.</span></span>

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="cfe1b-110">インターネットベースのコラボレーションアプリケーションと Lync 2013 の統合</span><span class="sxs-lookup"><span data-stu-id="cfe1b-110">Integrating an Internet-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="cfe1b-111">一般的に、サードパーティ製のコラボレーションアプリケーションを統合するために必要な手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-111">Generally, the steps involved in integrating a third-party collaboration application are as follows:</span></span>

1.  <span data-ttu-id="cfe1b-112">アプリケーションに関する情報がレジストリに追加されます。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-112">Information about the application is added to the registry.</span></span>

2.  <span data-ttu-id="cfe1b-113">開催者は Lync 2013 にサインインし、データ共有と共同作業のために連絡先を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-113">The organizer signs in to Lync 2013 and selects contacts for data sharing and collaboration.</span></span> <span data-ttu-id="cfe1b-114">または、開催者が既に会話に入っている場合は、[データ会議の追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-114">Or, the organizer may already be in a conversation and decide to add data conferencing.</span></span>

3.  <span data-ttu-id="cfe1b-115">Lync 2013 は、レジストリを読み取り、共同作業アプリケーションを開始してから、ユーザー設定の SIP メッセージ (appINVITE) を選択した参加者に送信します。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-115">Lync 2013 reads the registry, starts the collaboration application, and then sends a custom SIP message—an appINVITE—to the selected participants.</span></span>

4.  <span data-ttu-id="cfe1b-116">参加者が招待状を承諾し、共同作業アプリケーションが各ユーザーのコンピューターで開始されます。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-116">Participants accept the invitation, and the collaboration application is started on each person’s computer.</span></span> <span data-ttu-id="cfe1b-117">Lync 2013 は、レジストリを使って、どのコラボレーションアプリケーションを使うかを決定し、appINVITE メッセージに含まれるパラメーターを使ってそのアプリケーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-117">Lync 2013 uses the registry to determine which collaboration application to use, and then starts that application by using the parameters included in the appINVITE message.</span></span>

<span data-ttu-id="cfe1b-118">次の表では、インターネットベースのコラボレーションアプリケーションと Lync 2013 を統合するために必要なレジストリエントリについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-118">The following table describes the registry entries required to integrate an Internet-based collaboration application with Lync 2013.</span></span> <span data-ttu-id="cfe1b-119">これらのエントリは、レジストリの次の場所に配置されます。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-119">These entries are placed in the registry in the following location:</span></span>

  - <span data-ttu-id="cfe1b-120">HKEY\_ローカル\_コンピューター\\ソフトウェア\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\パラメーター</span><span class="sxs-lookup"><span data-stu-id="cfe1b-120">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="cfe1b-121">インターネットベースのコラボレーションアプリケーションのレジストリエントリ</span><span class="sxs-lookup"><span data-stu-id="cfe1b-121">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cfe1b-122">名前</span><span class="sxs-lookup"><span data-stu-id="cfe1b-122">Name</span></span></th>
<th><span data-ttu-id="cfe1b-123">種類</span><span class="sxs-lookup"><span data-stu-id="cfe1b-123">Type</span></span></th>
<th><span data-ttu-id="cfe1b-124">データ</span><span class="sxs-lookup"><span data-stu-id="cfe1b-124">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cfe1b-125">名前</span><span class="sxs-lookup"><span data-stu-id="cfe1b-125">Name</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-126">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="cfe1b-126">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-127">Lync 2013 メニューのアプリケーション名。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-127">The application name for Lync 2013 menus.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfe1b-128">SmallIcon</span><span class="sxs-lookup"><span data-stu-id="cfe1b-128">SmallIcon</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-129">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="cfe1b-129">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-130">16ピクセル x 16 ピクセルのアイコン、BMP、または PNG へのパス。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-130">Path to 16-pixel x 16-pixel icon, BMP or PNG.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfe1b-131">Path</span><span class="sxs-lookup"><span data-stu-id="cfe1b-131">Path</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-132">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="cfe1b-132">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-133">オンラインコラボレーションアプリケーションを開始するための参加者のパス。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-133">Participant path for starting the online collaboration application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfe1b-134">発信先のパス</span><span class="sxs-lookup"><span data-stu-id="cfe1b-134">OriginatorPath</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="cfe1b-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-136">オンライングループ作業アプリケーションを開始するための開催者のパス。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-136">Organizer path for starting the online collaboration application.</span></span> <span data-ttu-id="cfe1b-137">このパスには、Parameters サブキーで定義されている1つ以上のカスタムパラメーターを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-137">This path can contain one or more custom parameters as defined in the Parameters subkey.</span></span> <span data-ttu-id="cfe1b-138">例えば<code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span><span class="sxs-lookup"><span data-stu-id="cfe1b-138">For example, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfe1b-139">SessionType</span><span class="sxs-lookup"><span data-stu-id="cfe1b-139">SessionType</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-140">DWORD</span><span class="sxs-lookup"><span data-stu-id="cfe1b-140">DWORD</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-141">0 = ローカルセッション。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-141">0 = Local session.</span></span> <span data-ttu-id="cfe1b-142">アプリケーションがローカルコンピューターで開始されます。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-142">The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="cfe1b-143">1 = 2 パーティセッション (既定)。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-143">1 = Two-party session (default).</span></span> <span data-ttu-id="cfe1b-144">Lync 2013 によってアプリケーションがローカルで開始され、他のユーザーにシステム通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-144">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="cfe1b-145">他のユーザーが通知をクリックして、指定されたアプリケーションを自分のコンピューターで開始します。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-145">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="cfe1b-146">2 = マルチパーティセッション。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-146">2 = Multiparty session.</span></span> <span data-ttu-id="cfe1b-147">Lync 2013 は、アプリケーションをローカルで開始した後、システム通知を他のユーザーに送信して、自分のコンピューターで指定されたアプリケーションを起動するように指示します。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-147">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their own computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfe1b-148">ExensibleMenu</span><span class="sxs-lookup"><span data-stu-id="cfe1b-148">ExensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-149">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="cfe1b-149">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-150">このコマンドが表示されるメニューの一覧。セミコロンで区切ります。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-150">A list of the menus where this command will appear, separated by semi-colons.</span></span> <span data-ttu-id="cfe1b-151">値の例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-151">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="cfe1b-152">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="cfe1b-152">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="cfe1b-153">MainWindowRightClick 上</span><span class="sxs-lookup"><span data-stu-id="cfe1b-153">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="cfe1b-154">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="cfe1b-154">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="cfe1b-155">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="cfe1b-155">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="cfe1b-156">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="cfe1b-156">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="cfe1b-157">ExtensibleMenu が定義されていない場合は、MainWindowRightClick と ConversationWindowActions の既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-157">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cfe1b-158">次の表では、パラメーターのレジストリエントリについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-158">The following table describes the registry entries for parameters.</span></span> <span data-ttu-id="cfe1b-159">これら\_のエントリは、現在\_のユーザー\\ソフトウェア\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\のパラメーターに設定されています。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-159">These entries are place at HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters.</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="cfe1b-160">インターネットベースのコラボレーションアプリケーションのレジストリエントリ</span><span class="sxs-lookup"><span data-stu-id="cfe1b-160">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cfe1b-161">名前</span><span class="sxs-lookup"><span data-stu-id="cfe1b-161">Name</span></span></th>
<th><span data-ttu-id="cfe1b-162">種類</span><span class="sxs-lookup"><span data-stu-id="cfe1b-162">Type</span></span></th>
<th><span data-ttu-id="cfe1b-163">データ</span><span class="sxs-lookup"><span data-stu-id="cfe1b-163">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cfe1b-164">Param1</span><span class="sxs-lookup"><span data-stu-id="cfe1b-164">Param1</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-165">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="cfe1b-165">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-166">トークン形式 (<code>%Parm1%</code>) で、ユーザー固有の値を、指定された形式のレジストリキーに追加します。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-166">Used in tokenized format (<code>%Parm1%</code>) to add user-specific values to the OriginatorPath registry key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfe1b-167">Param2</span><span class="sxs-lookup"><span data-stu-id="cfe1b-167">Param2</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-168">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="cfe1b-168">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-169">「Param1」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-169">See Param1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfe1b-170">Param3</span><span class="sxs-lookup"><span data-stu-id="cfe1b-170">Param3</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-171">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="cfe1b-171">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-172">「Param1」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-172">See Param1.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cfe1b-173">次のレジストリ設定の例では、ADatum コラボレーションクライアントと Lync 2013 を統合しています。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-173">The following example registry settings integrate ADatum Collaboration Client with Lync 2013:</span></span>

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Path"="https://meetingservice.adatum.com/cc/%param1%/meet/%param2%"
    "OriginatorPath"="https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&role=present&pw=%param3%"
    "SessionType"=dword:00000002
    "ApplicationType"=dword:00000001
    "LiveServerIntegration"=dword:00000000
    "Name"="ADatum Online Collaboration Service"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"
    
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Param1"="meetserv"
    "Param2"="admin"
    "Param3"="abcdefg123"

</div>

<div>

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="cfe1b-174">サーバーベースのコラボレーションアプリケーションと Lync 2013 の統合</span><span class="sxs-lookup"><span data-stu-id="cfe1b-174">Integrating a Server-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="cfe1b-175">Lync 2013 内からサーバーベースのコラボレーションアプリケーションを起動するためのコマンドを追加するための設定は、前のセクションで説明したものと同じであり、インターネットベースのコラボレーションアプリケーションを Lync 2013 と統合しています。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-175">The settings to add commands for starting a server-based collaboration application from within Lync 2013 are similar to those described in the previous section, Integrating an Internet-Based Collaboration Application with Lync 2013.</span></span> <span data-ttu-id="cfe1b-176">ただし、原点の Path は必須ではなく、一部の値が変更されます。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-176">However, the OriginatorPath is not required, and some values are changed.</span></span> <span data-ttu-id="cfe1b-177">レジストリエントリは次の場所に配置されます。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-177">Registry entries are placed in the following location:</span></span>

  - <span data-ttu-id="cfe1b-178">HKEY\_ローカル\_コンピューター\\ソフトウェア\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\パラメーター</span><span class="sxs-lookup"><span data-stu-id="cfe1b-178">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-a-server-based-collaboration-application"></a><span data-ttu-id="cfe1b-179">サーバーベースのコラボレーションアプリケーションのレジストリエントリ</span><span class="sxs-lookup"><span data-stu-id="cfe1b-179">Registry Entries for a Server-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cfe1b-180">名前</span><span class="sxs-lookup"><span data-stu-id="cfe1b-180">Name</span></span></th>
<th><span data-ttu-id="cfe1b-181">種類</span><span class="sxs-lookup"><span data-stu-id="cfe1b-181">Type</span></span></th>
<th><span data-ttu-id="cfe1b-182">データ</span><span class="sxs-lookup"><span data-stu-id="cfe1b-182">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cfe1b-183">名前</span><span class="sxs-lookup"><span data-stu-id="cfe1b-183">Name</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-184">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="cfe1b-184">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-185">メニューに表示されるアプリケーションの名前。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-185">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfe1b-186">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="cfe1b-186">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-187">DWORD</span><span class="sxs-lookup"><span data-stu-id="cfe1b-187">DWORD</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-188">値 = 1。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-188">Value = 1.</span></span> <span data-ttu-id="cfe1b-189">アプリケーションの種類を protocol に設定します。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-189">Sets the application type to protocol.</span></span> <span data-ttu-id="cfe1b-190">この場合、その他の可能な値は適用されません。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-190">The other possible values do not apply in this case.</span></span> <span data-ttu-id="cfe1b-191">存在しない場合、ApplicationType は 0 (実行可能ファイル) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-191">If not present, ApplicationType is set to 0 (executable).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfe1b-192">Path</span><span class="sxs-lookup"><span data-stu-id="cfe1b-192">Path</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-193">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="cfe1b-193">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-194">コラボレーションアプリケーションを開始するために使用されるプロトコル。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-194">Protocol used to start the collaboration application.</span></span> <span data-ttu-id="cfe1b-195">Live Meeting 2007 の場合、Path の値はに<code>meet:%conf-uri%</code>設定されます。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-195">For Live Meeting 2007, the value of Path is set to <code>meet:%conf-uri%</code>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfe1b-196">SessionType</span><span class="sxs-lookup"><span data-stu-id="cfe1b-196">SessionType</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-197">DWORD</span><span class="sxs-lookup"><span data-stu-id="cfe1b-197">DWORD</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-198">0 = ローカルセッション。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-198">0 = Local session.</span></span> <span data-ttu-id="cfe1b-199">アプリケーションがローカルコンピューターで開始されます。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-199">The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="cfe1b-200">1 = 2 パーティセッション (既定)。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-200">1 = Two-party session (default).</span></span> <span data-ttu-id="cfe1b-201">Lync 2013 によってアプリケーションがローカルで開始され、他のユーザーにシステム通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-201">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="cfe1b-202">他のユーザーが通知をクリックして、指定されたアプリケーションを自分のコンピューターで開始します。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-202">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="cfe1b-203">2 = マルチパーティセッション。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-203">2 = Multiparty session.</span></span> <span data-ttu-id="cfe1b-204">Lync 2013 は、アプリケーションをローカルで開始した後、システム通知を他のユーザーに送信して、コンピューターで指定されたアプリケーションを開始するように求めます。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-204">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfe1b-205">MCUType</span><span class="sxs-lookup"><span data-stu-id="cfe1b-205">MCUType</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-206">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="cfe1b-206">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-207">データ = サーバーの種類。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-207">DATA = The type of server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfe1b-208">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="cfe1b-208">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-209">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="cfe1b-209">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="cfe1b-210">このコマンドが表示されるメニューの一覧。セミコロンで区切ります。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-210">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="cfe1b-211">値の例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-211">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="cfe1b-212">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="cfe1b-212">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="cfe1b-213">MainWindowRightClick 上</span><span class="sxs-lookup"><span data-stu-id="cfe1b-213">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="cfe1b-214">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="cfe1b-214">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="cfe1b-215">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="cfe1b-215">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="cfe1b-216">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="cfe1b-216">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="cfe1b-217">ExtensibleMenu が定義されていない場合は、MainWindowRightClick と ConversationWindowActions の既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-217">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cfe1b-218">次の例では、Lync 2013 内から ADatum コラボレーションクライアントを開始するためのコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="cfe1b-218">The following example adds commands to start ADatum Collaboration Client from within Lync 2013:</span></span>

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{27877e66-615c-4582-ab88-0cb2ca05d951}]
    "Path"="meet:%conf-uri%"
    "SessionType"=dword:00000002
    "LiveServerIntegration"=dword:00000001
    "ApplicationType"=dword:00000001
    "Name"="ADatum Collaboration Client"
    "MCUType"="Data"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"

</div>

</div>

<span> </span>

</div>

</div>

</div>


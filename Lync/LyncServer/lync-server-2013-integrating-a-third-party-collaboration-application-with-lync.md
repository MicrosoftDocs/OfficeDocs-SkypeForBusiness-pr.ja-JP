---
title: サードパーティ製のコラボレーションアプリケーションと Lync との統合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating a third-party collaboration application with Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398068(v=OCS.15)
ms:contentKeyID: 48183224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 075c8289a55683b18b0a006319b426c94796f9cd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a><span data-ttu-id="c47dd-102">サードパーティ製コラボレーションアプリケーションと Lync Server 2013 の統合</span><span class="sxs-lookup"><span data-stu-id="c47dd-102">Integrating a third-party collaboration application with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c47dd-103">_**トピックの最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="c47dd-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="c47dd-104">アプリケーションに関する情報をレジストリに追加することによって、Lync 2013 をサードパーティ製のオンライングループ作業アプリケーションと統合することができます。</span><span class="sxs-lookup"><span data-stu-id="c47dd-104">You can integrate Lync 2013 with any third-party online collaboration application by adding information about the application to the registry.</span></span> <span data-ttu-id="c47dd-105">Lync 2013 を使用すると、社内サーバー、インターネットベースのサービス、またはその両方でホストされているデータ会議セッションを開始できます。</span><span class="sxs-lookup"><span data-stu-id="c47dd-105">You can use Lync 2013 to start data conferencing sessions hosted on an in-house server, an Internet-based service, or both.</span></span> <span data-ttu-id="c47dd-106">コラボレーションまたはデータ会議のセッションは、連絡先リストまたは既存のインスタント メッセージング、音声、またはビデオのセッションから開始できます。</span><span class="sxs-lookup"><span data-stu-id="c47dd-106">The collaboration or data conferencing session can be started from the Contacts list or from an existing instant messaging, voice, or video session.</span></span> <span data-ttu-id="c47dd-107">Lync 2013 は、アプリケーションを起動するための手段としてのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="c47dd-107">Lync 2013 acts only as the vehicle for starting the application.</span></span> <span data-ttu-id="c47dd-108">既存の Lync 2013 会話は、オンライングループ作業セッションが開始された後もアクティブなままとなります。</span><span class="sxs-lookup"><span data-stu-id="c47dd-108">Any existing Lync 2013 conversations remain active after the online collaboration session has begun.</span></span>

<span data-ttu-id="c47dd-109">次のセクションでは、Lync 2013 をインターネットベースおよびサーバーベースのコラボレーションアプリケーションと統合する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c47dd-109">The following sections describe how to integrate Lync 2013 with Internet-based and server-based collaboration applications.</span></span>

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="c47dd-110">インターネットベースのコラボレーションアプリケーションと Lync 2013 の統合</span><span class="sxs-lookup"><span data-stu-id="c47dd-110">Integrating an Internet-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="c47dd-111">一般的に、サードパーティ製コラボレーション アプリケーションの統合手順は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c47dd-111">Generally, the steps involved in integrating a third-party collaboration application are as follows:</span></span>

1.  <span data-ttu-id="c47dd-112">アプリケーションに関する情報がレジストリに追加されます。</span><span class="sxs-lookup"><span data-stu-id="c47dd-112">Information about the application is added to the registry.</span></span>

2.  <span data-ttu-id="c47dd-113">開催者は Lync 2013 にサインインし、データ共有と共同作業のための連絡先を選択します。</span><span class="sxs-lookup"><span data-stu-id="c47dd-113">The organizer signs in to Lync 2013 and selects contacts for data sharing and collaboration.</span></span> <span data-ttu-id="c47dd-114">または、開催者が既に会話に参加しており、データ会議の追加を決定する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="c47dd-114">Or, the organizer may already be in a conversation and decide to add data conferencing.</span></span>

3.  <span data-ttu-id="c47dd-115">Lync 2013 は、レジストリを読み取り、グループ作業アプリケーションを起動し、カスタム SIP メッセージ (appINVITE) を選択された参加者に送信します。</span><span class="sxs-lookup"><span data-stu-id="c47dd-115">Lync 2013 reads the registry, starts the collaboration application, and then sends a custom SIP message—an appINVITE—to the selected participants.</span></span>

4.  <span data-ttu-id="c47dd-116">参加者が招待を承諾すると、コラボレーション アプリケーションが各自のコンピューター上で起動します。</span><span class="sxs-lookup"><span data-stu-id="c47dd-116">Participants accept the invitation, and the collaboration application is started on each person’s computer.</span></span> <span data-ttu-id="c47dd-117">Lync 2013 は、レジストリを使用して、どのグループ作業アプリケーションを使用するかを決定し、appINVITE メッセージに含まれるパラメーターを使用してそのアプリケーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="c47dd-117">Lync 2013 uses the registry to determine which collaboration application to use, and then starts that application by using the parameters included in the appINVITE message.</span></span>

<span data-ttu-id="c47dd-118">次の表では、インターネットベースのコラボレーションアプリケーションを Lync 2013 に統合するために必要なレジストリエントリについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c47dd-118">The following table describes the registry entries required to integrate an Internet-based collaboration application with Lync 2013.</span></span> <span data-ttu-id="c47dd-119">これらのエントリは、レジストリの次の場所に配置されます。</span><span class="sxs-lookup"><span data-stu-id="c47dd-119">These entries are placed in the registry in the following location:</span></span>

  - <span data-ttu-id="c47dd-120">HKEY\_ローカル\_コンピューター\\ソフトウェア\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\パラメーター</span><span class="sxs-lookup"><span data-stu-id="c47dd-120">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="c47dd-121">インターネットベースのコラボレーション アプリケーションのレジストリ エントリ</span><span class="sxs-lookup"><span data-stu-id="c47dd-121">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c47dd-122">名前</span><span class="sxs-lookup"><span data-stu-id="c47dd-122">Name</span></span></th>
<th><span data-ttu-id="c47dd-123">種類</span><span class="sxs-lookup"><span data-stu-id="c47dd-123">Type</span></span></th>
<th><span data-ttu-id="c47dd-124">データ</span><span class="sxs-lookup"><span data-stu-id="c47dd-124">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c47dd-125">名前</span><span class="sxs-lookup"><span data-stu-id="c47dd-125">Name</span></span></p></td>
<td><p><span data-ttu-id="c47dd-126">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c47dd-126">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="c47dd-127">Lync 2013 メニューのアプリケーション名。</span><span class="sxs-lookup"><span data-stu-id="c47dd-127">The application name for Lync 2013 menus.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c47dd-128">SmallIcon</span><span class="sxs-lookup"><span data-stu-id="c47dd-128">SmallIcon</span></span></p></td>
<td><p><span data-ttu-id="c47dd-129">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c47dd-129">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="c47dd-130">16 ピクセル x 16 ピクセルのアイコン (BMP または PNG) へのパス。</span><span class="sxs-lookup"><span data-stu-id="c47dd-130">Path to 16-pixel x 16-pixel icon, BMP or PNG.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c47dd-131">Path</span><span class="sxs-lookup"><span data-stu-id="c47dd-131">Path</span></span></p></td>
<td><p><span data-ttu-id="c47dd-132">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c47dd-132">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="c47dd-133">オンライン コラボレーション アプリケーションを起動するための参加者のパス。</span><span class="sxs-lookup"><span data-stu-id="c47dd-133">Participant path for starting the online collaboration application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c47dd-134">原点のパス</span><span class="sxs-lookup"><span data-stu-id="c47dd-134">OriginatorPath</span></span></p></td>
<td><p><span data-ttu-id="c47dd-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c47dd-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="c47dd-136">オンライングループ作業アプリケーションを開始するための開催者のパス。</span><span class="sxs-lookup"><span data-stu-id="c47dd-136">Organizer path for starting the online collaboration application.</span></span> <span data-ttu-id="c47dd-137">このパスには、Parameters サブキーで定義されている1つ以上のカスタムパラメータを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c47dd-137">This path can contain one or more custom parameters as defined in the Parameters subkey.</span></span> <span data-ttu-id="c47dd-138">たとえば、<code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code> などです。</span><span class="sxs-lookup"><span data-stu-id="c47dd-138">For example, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c47dd-139">SessionType</span><span class="sxs-lookup"><span data-stu-id="c47dd-139">SessionType</span></span></p></td>
<td><p><span data-ttu-id="c47dd-140">DWORD</span><span class="sxs-lookup"><span data-stu-id="c47dd-140">DWORD</span></span></p></td>
<td><p><span data-ttu-id="c47dd-p106">0 = ローカル セッション。アプリケーションはローカル コンピュータ上で起動します。</span><span class="sxs-lookup"><span data-stu-id="c47dd-p106">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="c47dd-143">1 = 2 者間セッション (既定値)。</span><span class="sxs-lookup"><span data-stu-id="c47dd-143">1 = Two-party session (default).</span></span> <span data-ttu-id="c47dd-144">Lync 2013 はアプリケーションをローカルで起動し、その他のユーザーにシステム通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="c47dd-144">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="c47dd-145">相手のユーザーは通知をクリックし、指定されたアプリケーションを自分のコンピューター上で起動します。</span><span class="sxs-lookup"><span data-stu-id="c47dd-145">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="c47dd-146">2 = 複数ユーザー間セッション。</span><span class="sxs-lookup"><span data-stu-id="c47dd-146">2 = Multiparty session.</span></span> <span data-ttu-id="c47dd-147">Lync 2013 はアプリケーションをローカルで起動し、その他のユーザーにシステム通知を送信して、自分のコンピューターで指定されたアプリケーションを起動するように指示します。</span><span class="sxs-lookup"><span data-stu-id="c47dd-147">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their own computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c47dd-148">ExensibleMenu</span><span class="sxs-lookup"><span data-stu-id="c47dd-148">ExensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="c47dd-149">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c47dd-149">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="c47dd-p109">(セミコロンで区切られた) このコマンドが表示されるメニューの一覧。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c47dd-p109">A list of the menus where this command will appear, separated by semi-colons. Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="c47dd-152">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="c47dd-152">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="c47dd-153">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="c47dd-153">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="c47dd-154">Conversationwindowactions [</span><span class="sxs-lookup"><span data-stu-id="c47dd-154">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="c47dd-155">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="c47dd-155">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="c47dd-156">Conversationwindowrightclick [</span><span class="sxs-lookup"><span data-stu-id="c47dd-156">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="c47dd-157">ExtensibleMenu が定義されていない場合は、MainWindowRightClick および ConversationWindowContextual の既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c47dd-157">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c47dd-158">次の表は、パラメーターのレジストリ エントリを示します。</span><span class="sxs-lookup"><span data-stu-id="c47dd-158">The following table describes the registry entries for parameters.</span></span> <span data-ttu-id="c47dd-159">これらのエントリは、HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\パラメーターに配置されます。</span><span class="sxs-lookup"><span data-stu-id="c47dd-159">These entries are place at HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters.</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="c47dd-160">インターネットベースのコラボレーション アプリケーションのレジストリ エントリ</span><span class="sxs-lookup"><span data-stu-id="c47dd-160">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c47dd-161">名前</span><span class="sxs-lookup"><span data-stu-id="c47dd-161">Name</span></span></th>
<th><span data-ttu-id="c47dd-162">種類</span><span class="sxs-lookup"><span data-stu-id="c47dd-162">Type</span></span></th>
<th><span data-ttu-id="c47dd-163">データ</span><span class="sxs-lookup"><span data-stu-id="c47dd-163">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c47dd-164">Param1</span><span class="sxs-lookup"><span data-stu-id="c47dd-164">Param1</span></span></p></td>
<td><p><span data-ttu-id="c47dd-165">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c47dd-165">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="c47dd-166">トークン化された<code>%Parm1%</code>形式 () で使用され、ユーザー固有の値を原点の atorpath レジストリキーに追加します。</span><span class="sxs-lookup"><span data-stu-id="c47dd-166">Used in tokenized format (<code>%Parm1%</code>) to add user-specific values to the OriginatorPath registry key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c47dd-167">Param2</span><span class="sxs-lookup"><span data-stu-id="c47dd-167">Param2</span></span></p></td>
<td><p><span data-ttu-id="c47dd-168">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c47dd-168">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="c47dd-169">Param1 を参照。</span><span class="sxs-lookup"><span data-stu-id="c47dd-169">See Param1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c47dd-170">Param3</span><span class="sxs-lookup"><span data-stu-id="c47dd-170">Param3</span></span></p></td>
<td><p><span data-ttu-id="c47dd-171">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c47dd-171">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="c47dd-172">Param1 を参照。</span><span class="sxs-lookup"><span data-stu-id="c47dd-172">See Param1.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c47dd-173">次のレジストリ設定の例では、ADatum コラボレーションクライアントと Lync 2013 を統合しています。</span><span class="sxs-lookup"><span data-stu-id="c47dd-173">The following example registry settings integrate ADatum Collaboration Client with Lync 2013:</span></span>

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

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="c47dd-174">サーバーベースのコラボレーションアプリケーションと Lync 2013 の統合</span><span class="sxs-lookup"><span data-stu-id="c47dd-174">Integrating a Server-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="c47dd-175">Lync 2013 のサーバーベースのコラボレーションアプリケーションを起動するためのコマンドを追加するための設定は、前のセクションで説明したものと似ています。これは、インターネットベースのコラボレーションアプリケーションと Lync 2013 との統合です。</span><span class="sxs-lookup"><span data-stu-id="c47dd-175">The settings to add commands for starting a server-based collaboration application from within Lync 2013 are similar to those described in the previous section, Integrating an Internet-Based Collaboration Application with Lync 2013.</span></span> <span data-ttu-id="c47dd-176">ただし、OriginatorPath は必要ではなく、いくつかの値が変更されます。</span><span class="sxs-lookup"><span data-stu-id="c47dd-176">However, the OriginatorPath is not required, and some values are changed.</span></span> <span data-ttu-id="c47dd-177">レジストリエントリは次の場所に配置されます。</span><span class="sxs-lookup"><span data-stu-id="c47dd-177">Registry entries are placed in the following location:</span></span>

  - <span data-ttu-id="c47dd-178">HKEY\_ローカル\_コンピューター\\ソフトウェア\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\パラメーター</span><span class="sxs-lookup"><span data-stu-id="c47dd-178">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-a-server-based-collaboration-application"></a><span data-ttu-id="c47dd-179">サーバーベースのコラボレーション アプリケーションのレジストリ エントリ</span><span class="sxs-lookup"><span data-stu-id="c47dd-179">Registry Entries for a Server-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c47dd-180">名前</span><span class="sxs-lookup"><span data-stu-id="c47dd-180">Name</span></span></th>
<th><span data-ttu-id="c47dd-181">種類</span><span class="sxs-lookup"><span data-stu-id="c47dd-181">Type</span></span></th>
<th><span data-ttu-id="c47dd-182">データ</span><span class="sxs-lookup"><span data-stu-id="c47dd-182">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c47dd-183">名前</span><span class="sxs-lookup"><span data-stu-id="c47dd-183">Name</span></span></p></td>
<td><p><span data-ttu-id="c47dd-184">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c47dd-184">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="c47dd-185">メニューに表示されるアプリケーション名。</span><span class="sxs-lookup"><span data-stu-id="c47dd-185">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c47dd-186">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="c47dd-186">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="c47dd-187">DWORD</span><span class="sxs-lookup"><span data-stu-id="c47dd-187">DWORD</span></span></p></td>
<td><p><span data-ttu-id="c47dd-188">値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="c47dd-188">Value = 1.</span></span> <span data-ttu-id="c47dd-189">アプリケーションの種類を protocol に設定します。</span><span class="sxs-lookup"><span data-stu-id="c47dd-189">Sets the application type to protocol.</span></span> <span data-ttu-id="c47dd-190">その他の値は、この場合には適用されません。</span><span class="sxs-lookup"><span data-stu-id="c47dd-190">The other possible values do not apply in this case.</span></span> <span data-ttu-id="c47dd-191">存在しない場合、ApplicationType は 0 (実行可能) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="c47dd-191">If not present, ApplicationType is set to 0 (executable).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c47dd-192">Path</span><span class="sxs-lookup"><span data-stu-id="c47dd-192">Path</span></span></p></td>
<td><p><span data-ttu-id="c47dd-193">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c47dd-193">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="c47dd-194">コラボレーション アプリケーションの起動に使用するプロトコル。</span><span class="sxs-lookup"><span data-stu-id="c47dd-194">Protocol used to start the collaboration application.</span></span> <span data-ttu-id="c47dd-195">Live Meeting 2007 の場合、Path の値はに<code>meet:%conf-uri%</code>設定されます。</span><span class="sxs-lookup"><span data-stu-id="c47dd-195">For Live Meeting 2007, the value of Path is set to <code>meet:%conf-uri%</code>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c47dd-196">SessionType</span><span class="sxs-lookup"><span data-stu-id="c47dd-196">SessionType</span></span></p></td>
<td><p><span data-ttu-id="c47dd-197">DWORD</span><span class="sxs-lookup"><span data-stu-id="c47dd-197">DWORD</span></span></p></td>
<td><p><span data-ttu-id="c47dd-p114">0 = ローカル セッション。アプリケーションはローカル コンピュータ上で起動します。</span><span class="sxs-lookup"><span data-stu-id="c47dd-p114">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="c47dd-200">1 = 2 者間セッション (既定値)。</span><span class="sxs-lookup"><span data-stu-id="c47dd-200">1 = Two-party session (default).</span></span> <span data-ttu-id="c47dd-201">Lync 2013 はアプリケーションをローカルで起動し、その他のユーザーにシステム通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="c47dd-201">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="c47dd-202">相手のユーザーは通知をクリックし、指定されたアプリケーションを自分のコンピューター上で起動します。</span><span class="sxs-lookup"><span data-stu-id="c47dd-202">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="c47dd-203">2 = 複数ユーザー間セッション。</span><span class="sxs-lookup"><span data-stu-id="c47dd-203">2 = Multiparty session.</span></span> <span data-ttu-id="c47dd-204">Lync 2013 はアプリケーションをローカルで起動し、その他のユーザーにシステム通知を送信して、コンピューターで指定されたアプリケーションを起動するように指示します。</span><span class="sxs-lookup"><span data-stu-id="c47dd-204">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c47dd-205">MCUType</span><span class="sxs-lookup"><span data-stu-id="c47dd-205">MCUType</span></span></p></td>
<td><p><span data-ttu-id="c47dd-206">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c47dd-206">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="c47dd-207">DATA = サーバーの種類。</span><span class="sxs-lookup"><span data-stu-id="c47dd-207">DATA = The type of server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c47dd-208">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="c47dd-208">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="c47dd-209">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c47dd-209">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="c47dd-210">このコマンドが表示されるメニューの一覧は、セミコロンで区切られています。</span><span class="sxs-lookup"><span data-stu-id="c47dd-210">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="c47dd-211">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c47dd-211">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="c47dd-212">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="c47dd-212">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="c47dd-213">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="c47dd-213">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="c47dd-214">Conversationwindowactions [</span><span class="sxs-lookup"><span data-stu-id="c47dd-214">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="c47dd-215">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="c47dd-215">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="c47dd-216">Conversationwindowrightclick [</span><span class="sxs-lookup"><span data-stu-id="c47dd-216">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="c47dd-217">ExtensibleMenu が定義されていない場合は、MainWindowRightClick および ConversationWindowContextual の既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c47dd-217">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c47dd-218">次の例では、Lync 2013 内から ADatum コラボレーションクライアントを開始するコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="c47dd-218">The following example adds commands to start ADatum Collaboration Client from within Lync 2013:</span></span>

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


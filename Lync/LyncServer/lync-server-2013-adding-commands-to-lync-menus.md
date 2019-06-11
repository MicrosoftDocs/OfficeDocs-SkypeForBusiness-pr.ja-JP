---
title: 'Lync Server 2013: Lync のメニューにコマンドを追加する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding commands to Lync menus
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412788(v=OCS.15)
ms:contentKeyID: 48185091
ms.date: 04/11/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1dfb79a985791e6994d8409339d12b12e1146ec5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a><span data-ttu-id="f799a-102">Lync Server 2013 での Lync メニューへのコマンドの追加</span><span class="sxs-lookup"><span data-stu-id="f799a-102">Adding commands to Lync menus in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f799a-103">_**最終更新日:** 2016-04-11_</span><span class="sxs-lookup"><span data-stu-id="f799a-103">_**Topic Last Modified:** 2016-04-11_</span></span>

<span data-ttu-id="f799a-104">Lync 2013 メニューにカスタムコマンドを追加し、現在のユーザーの SIP Uniform リソース識別子 (URI) を、カスタムコマンドの開始時に選択した連絡先に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="f799a-104">You can add custom commands to Lync 2013 menus and pass the SIP Uniform Resource Identifier (URI) of the current user and selected contacts to the application that the custom command starts.</span></span>

<span data-ttu-id="f799a-105">追加するカスタムコマンドは、次の1つ以上のメニューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f799a-105">The custom commands that you add can appear on one or more of the following menus:</span></span>

  - <span data-ttu-id="f799a-106">Lync メインウィンドウのメニューバーの [ツール] メニュー</span><span class="sxs-lookup"><span data-stu-id="f799a-106">The Tools menu, on the menu bar in the Lync main window</span></span>

  - <span data-ttu-id="f799a-107">連絡先リストの連絡先のショートカットメニュー</span><span class="sxs-lookup"><span data-stu-id="f799a-107">The shortcut menu for contacts in the Contacts list</span></span>

  - <span data-ttu-id="f799a-108">[会話] ウィンドウの [その他のオプション] メニュー</span><span class="sxs-lookup"><span data-stu-id="f799a-108">The More Options menu, in the Conversation window</span></span>

  - <span data-ttu-id="f799a-109">[会話] ウィンドウの参加者リストに一覧表示されたユーザーのショートカットメニュー</span><span class="sxs-lookup"><span data-stu-id="f799a-109">The shortcut menu for people listed in the Conversation window participant list</span></span>

  - <span data-ttu-id="f799a-110">連絡先カードの [オプション] メニュー</span><span class="sxs-lookup"><span data-stu-id="f799a-110">The options menu in a contact card</span></span>

<span data-ttu-id="f799a-111">2種類のアプリケーション (次のいずれかのアプリケーション) のカスタムコマンドを定義できます。</span><span class="sxs-lookup"><span data-stu-id="f799a-111">You can define custom commands for two types of applications—applications that do either of the following:</span></span>

  - <span data-ttu-id="f799a-112">現在のユーザーにのみ適用され、ローカルコンピューターで開始されます。</span><span class="sxs-lookup"><span data-stu-id="f799a-112">Apply only to the current user and are started on the local computer.</span></span>

  - <span data-ttu-id="f799a-113">オンラインコラボレーションプログラムなどの追加のユーザーを参加させると、各ユーザーのコンピューターで開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f799a-113">Involve additional users, such as an online collaboration program, and must be started on each user's computer.</span></span>

<span data-ttu-id="f799a-114">カスタムコマンドは、次の方法で呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="f799a-114">The custom command can be invoked in the following ways:</span></span>

  - <span data-ttu-id="f799a-115">1人以上のユーザーを選択し、[ユーザー設定] コマンドを選択します。</span><span class="sxs-lookup"><span data-stu-id="f799a-115">Select one or more users, and then choose the custom command.</span></span>

  - <span data-ttu-id="f799a-116">2パーティまたはマルチパーティの会話を開始し、[ユーザー設定] コマンドを選択します。</span><span class="sxs-lookup"><span data-stu-id="f799a-116">Start a two-party or multiparty conversation, and then choose the custom command.</span></span>

<div>

## <a name="to-add-a-custom-command"></a><span data-ttu-id="f799a-117">カスタムコマンドを追加するには</span><span class="sxs-lookup"><span data-stu-id="f799a-117">To add a custom command</span></span>

<span data-ttu-id="f799a-118">次の表のレジストリ設定を使用して、メニューにコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="f799a-118">Use the registry settings in the following table to add a command to the menus.</span></span> <span data-ttu-id="f799a-119">これらのエントリは、レジストリの次のいずれかの場所に配置されます。</span><span class="sxs-lookup"><span data-stu-id="f799a-119">These entries are placed in the registry at one of the following locations:</span></span>

  - <span data-ttu-id="f799a-120">32ビット OS の場合\_:\_HKEY\\ローカル\\コンピューター\\ソフトウェア\\Microsoft\\Office\\15.0\\Lync SessionManager アプリ</span><span class="sxs-lookup"><span data-stu-id="f799a-120">For 32bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

  - <span data-ttu-id="f799a-121">64ビット OS の場合\_:\_HKEY\\LOCAL\\MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync SessionManager アプリ</span><span class="sxs-lookup"><span data-stu-id="f799a-121">For 64bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

### <a name="custom-command-registry-entries"></a><span data-ttu-id="f799a-122">カスタムコマンドレジストリエントリ</span><span class="sxs-lookup"><span data-stu-id="f799a-122">Custom Command Registry Entries</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f799a-123">名前</span><span class="sxs-lookup"><span data-stu-id="f799a-123">Name</span></span></th>
<th><span data-ttu-id="f799a-124">種類</span><span class="sxs-lookup"><span data-stu-id="f799a-124">Type</span></span></th>
<th><span data-ttu-id="f799a-125">データ</span><span class="sxs-lookup"><span data-stu-id="f799a-125">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f799a-126">名前</span><span class="sxs-lookup"><span data-stu-id="f799a-126">Name</span></span></p></td>
<td><p><span data-ttu-id="f799a-127">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="f799a-127">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="f799a-128">メニューに表示されるアプリケーションの名前。</span><span class="sxs-lookup"><span data-stu-id="f799a-128">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f799a-129">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="f799a-129">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="f799a-130">DWORD</span><span class="sxs-lookup"><span data-stu-id="f799a-130">DWORD</span></span></p></td>
<td><p><span data-ttu-id="f799a-131">0 = 実行可能ファイル (既定)</span><span class="sxs-lookup"><span data-stu-id="f799a-131">0 = Executable (default)</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="f799a-132">ApplicationInstallPath が必要です。</span><span class="sxs-lookup"><span data-stu-id="f799a-132">Requires ApplicationInstallPath.</span></span>


</div>
<p><span data-ttu-id="f799a-133">1 = プロトコル</span><span class="sxs-lookup"><span data-stu-id="f799a-133">1 = Protocol</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f799a-134">ApplicationInstallPath</span><span class="sxs-lookup"><span data-stu-id="f799a-134">ApplicationInstallPath</span></span></p></td>
<td><p><span data-ttu-id="f799a-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="f799a-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="f799a-136">実行可能ファイルの完全パス。</span><span class="sxs-lookup"><span data-stu-id="f799a-136">Full path of the executable.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="f799a-137">ApplicationType が 0 (実行可能ファイル) の場合は指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f799a-137">Must be specified if ApplicationType is 0 (Executable).</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f799a-138">Path</span><span class="sxs-lookup"><span data-stu-id="f799a-138">Path</span></span></p></td>
<td><p><span data-ttu-id="f799a-139">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="f799a-139">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="f799a-140">既定のパラメーター <em>%、ユーザー id</em> %、<em>連絡先 id</em>% など、すべてのパラメーターと共に開始する完全パス。</span><span class="sxs-lookup"><span data-stu-id="f799a-140">Full path to be started along with any parameters, including the default parameters <em>%user-id%</em> and <em>%contact-id%</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f799a-141">SessionType</span><span class="sxs-lookup"><span data-stu-id="f799a-141">SessionType</span></span></p></td>
<td><p><span data-ttu-id="f799a-142">DWORD</span><span class="sxs-lookup"><span data-stu-id="f799a-142">DWORD</span></span></p></td>
<td><p><span data-ttu-id="f799a-143">0 = ローカルセッション。</span><span class="sxs-lookup"><span data-stu-id="f799a-143">0 = Local session.</span></span> <span data-ttu-id="f799a-144">アプリケーションがローカルコンピューターで開始されます。</span><span class="sxs-lookup"><span data-stu-id="f799a-144">The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="f799a-145">1 = 2 パーティセッション (既定)。</span><span class="sxs-lookup"><span data-stu-id="f799a-145">1 = Two-party session (default).</span></span> <span data-ttu-id="f799a-146">Lync 2013 では、アプリケーションをローカルで開始した後、他のユーザーにデスクトップ通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="f799a-146">Lync 2013 starts the application locally and then sends a desktop notification to the other user.</span></span> <span data-ttu-id="f799a-147">他のユーザーが通知をクリックして、コンピューター上でアプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="f799a-147">The other user clicks the notification to start the application on their computer.</span></span></p>
<p><span data-ttu-id="f799a-148">2 = マルチパーティセッション。</span><span class="sxs-lookup"><span data-stu-id="f799a-148">2 = Multiparty session.</span></span> <span data-ttu-id="f799a-149">Lync 2013 は、アプリケーションをローカルで開始してから、デスクトップ通知を他のユーザーに送信します。</span><span class="sxs-lookup"><span data-stu-id="f799a-149">Lync 2013 starts the application locally and then sends desktop notifications to the other users.</span></span> <span data-ttu-id="f799a-150">他のユーザーが通知をクリックして、指定されたアプリケーションを自分のコンピューターで起動します。</span><span class="sxs-lookup"><span data-stu-id="f799a-150">The other user clicks the notification to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f799a-151">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="f799a-151">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="f799a-152">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="f799a-152">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="f799a-153">このコマンドが表示されるメニューの一覧。セミコロンで区切ります。</span><span class="sxs-lookup"><span data-stu-id="f799a-153">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="f799a-154">値の例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f799a-154">Possible values are:</span></span></p>
<p><span data-ttu-id="f799a-155">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="f799a-155">MainWindowActions</span></span></p>
<p><span data-ttu-id="f799a-156">MainWindowRightClick 上</span><span class="sxs-lookup"><span data-stu-id="f799a-156">MainWindowRightClick</span></span></p>
<p><span data-ttu-id="f799a-157">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="f799a-157">ConversationWindowActions</span></span></p>
<p><span data-ttu-id="f799a-158">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="f799a-158">ConversationWindowRightClick</span></span></p>
<p><span data-ttu-id="f799a-159">連絡先カードメニュー</span><span class="sxs-lookup"><span data-stu-id="f799a-159">ContactCardMenu</span></span></p>
<p><span data-ttu-id="f799a-160">ExtensibleMenu が定義されていない場合は、MainWindowRightClick と ConversationWindowActions の既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f799a-160">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f799a-161">たとえば、次のレジストリエディター (.REG) ファイルには、[会話] ウィンドウの [アクション] メニューに Contoso の営業連絡先マネージャーのメニュー項目を追加した結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f799a-161">For example, the following Registry Editor (.REG) file shows the results of adding a Contoso Sales Contact Manager menu item to Actions menu in the Conversation window:</span></span>

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Office\15.0\Lync\SessionManager\Apps\{1F9F07C6-7E0B-462B-AAD7-98C6DBEA8F69}]
    "Name"="Contoso Sales Contact Manager"
    "HelpMessage"="The Contoso Sales Contact Manager is not installed. Contact the Help Desk for more information."
    "ApplicationType"=dword:00000000
    "ApplicationInstallPath"="C:\\cscm.exe"
    "Path"="C:\\cscm.exe %user-id% %contact-id%"
    "SessionType"=dword:00000001
    "ExtensibleMenu"="ConversationWindowActions;MainWindowRightClick"

</div>

<div>

## <a name="to-access-a-custom-command"></a><span data-ttu-id="f799a-162">カスタムコマンドにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="f799a-162">To access a custom command</span></span>

<span data-ttu-id="f799a-163">追加したカスタムコマンドにアクセスするには、定義した ExtensibleMenu 値に応じて、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f799a-163">To access a custom command after it is added, do one of the following, depending on the ExtensibleMenu values that you define:</span></span>

  - <span data-ttu-id="f799a-164">**[メイン**   ウィンドウ] Lync メインウィンドウで [**ツール**] をクリックし、[ユーザー設定] コマンドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f799a-164">**MainWindowActions**   In the Lync main window, click **Tools**, and then click your custom command.</span></span>

  - <span data-ttu-id="f799a-165">**[Mainwindowrightclick**   メインウィンドウで、連絡先を右クリックし、[ユーザー設定] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f799a-165">**MainWindowRightClick**   In the Lync main window, right-click a contact, and then click your custom command.</span></span>

  - <span data-ttu-id="f799a-166">**ConversationWindowActions**   会話ウィンドウで、[**その他のオプション**] アイコンをクリックし、ユーザー設定のコマンドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f799a-166">**ConversationWindowActions**   In the Conversation window, click the **More Options** icon, and then click your custom command.</span></span>

  - <span data-ttu-id="f799a-167">**ConversationWindowRightClick**   会話ウィンドウで、連絡先の名前を右クリックし、[ユーザー設定] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f799a-167">**ConversationWindowRightClick**   In the Conversation window, right-click a contact name, and then click your custom command.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


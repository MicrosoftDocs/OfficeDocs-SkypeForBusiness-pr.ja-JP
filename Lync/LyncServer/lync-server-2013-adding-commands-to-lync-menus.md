---
title: 'Lync Server 2013: Lync メニューへのコマンドの追加'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding commands to Lync menus
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412788(v=OCS.15)
ms:contentKeyID: 48185091
ms.date: 04/11/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b6377824a7d96e6bb7b0ae6c60c79f3ee4c05b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a><span data-ttu-id="b973f-102">Lync Server 2013 での Lync メニューへのコマンドの追加</span><span class="sxs-lookup"><span data-stu-id="b973f-102">Adding commands to Lync menus in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b973f-103">_**トピックの最終更新日:** 2016-04-11_</span><span class="sxs-lookup"><span data-stu-id="b973f-103">_**Topic Last Modified:** 2016-04-11_</span></span>

<span data-ttu-id="b973f-104">カスタムコマンドを Lync 2013 メニューに追加して、現在のユーザーの SIP URI (Uniform Resource Identifier) と選択した連絡先を、カスタムコマンドを開始するアプリケーションに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="b973f-104">You can add custom commands to Lync 2013 menus and pass the SIP Uniform Resource Identifier (URI) of the current user and selected contacts to the application that the custom command starts.</span></span>

<span data-ttu-id="b973f-105">追加するカスタム コマンドは、次の 1 つ以上のメニューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b973f-105">The custom commands that you add can appear on one or more of the following menus:</span></span>

  - <span data-ttu-id="b973f-106">Lync のメイン ウィンドウのメニュー バー上にある、[ツール] メニュー</span><span class="sxs-lookup"><span data-stu-id="b973f-106">The Tools menu, on the menu bar in the Lync main window</span></span>

  - <span data-ttu-id="b973f-107">連絡先リストの連絡先に対するショートカット メニュー</span><span class="sxs-lookup"><span data-stu-id="b973f-107">The shortcut menu for contacts in the Contacts list</span></span>

  - <span data-ttu-id="b973f-108">[会話] ウィンドウの [その他のオプション] メニュー</span><span class="sxs-lookup"><span data-stu-id="b973f-108">The More Options menu, in the Conversation window</span></span>

  - <span data-ttu-id="b973f-109">[会話] ウィンドウの参加者リストに表示された人に対するショートカット メニュー</span><span class="sxs-lookup"><span data-stu-id="b973f-109">The shortcut menu for people listed in the Conversation window participant list</span></span>

  - <span data-ttu-id="b973f-110">連絡先カードの [オプション] メニュー</span><span class="sxs-lookup"><span data-stu-id="b973f-110">The options menu in a contact card</span></span>

<span data-ttu-id="b973f-111">2 種類のアプリケーション用のカスタム コマンドを定義することができ、そのアプリケーションは次のいずれかを行います。</span><span class="sxs-lookup"><span data-stu-id="b973f-111">You can define custom commands for two types of applications—applications that do either of the following:</span></span>

  - <span data-ttu-id="b973f-112">現在のユーザーのみに適用され、ローカル コンピューター上で起動するアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="b973f-112">Apply only to the current user and are started on the local computer.</span></span>

  - <span data-ttu-id="b973f-113">オンライン コラボレーション プログラムなどの別のユーザーが関与するアプリケーションであり、各ユーザーのコンピューター上で起動される必要があるアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="b973f-113">Involve additional users, such as an online collaboration program, and must be started on each user's computer.</span></span>

<span data-ttu-id="b973f-114">カスタム コマンドは、次の方法で呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="b973f-114">The custom command can be invoked in the following ways:</span></span>

  - <span data-ttu-id="b973f-115">1 人以上のユーザーを選択し、カスタム コマンドを選択します。</span><span class="sxs-lookup"><span data-stu-id="b973f-115">Select one or more users, and then choose the custom command.</span></span>

  - <span data-ttu-id="b973f-116">2 パーティまたはマルチパーティの通話を開始し、カスタム コマンドを選択します。</span><span class="sxs-lookup"><span data-stu-id="b973f-116">Start a two-party or multiparty conversation, and then choose the custom command.</span></span>

<div>

## <a name="to-add-a-custom-command"></a><span data-ttu-id="b973f-117">カスタム コマンドを追加するには</span><span class="sxs-lookup"><span data-stu-id="b973f-117">To add a custom command</span></span>

<span data-ttu-id="b973f-118">メニューにコマンドを追加するには、次の表のレジストリ設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="b973f-118">Use the registry settings in the following table to add a command to the menus.</span></span> <span data-ttu-id="b973f-119">これらのエントリは、次のいずれかの場所にあるレジストリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="b973f-119">These entries are placed in the registry at one of the following locations:</span></span>

  - <span data-ttu-id="b973f-120">32ビット OS の場合\_:\_HKEY\\ローカル\\コンピューター\\ソフトウェア\\Microsoft\\Office\\15.0\\Lync SessionManager アプリ</span><span class="sxs-lookup"><span data-stu-id="b973f-120">For 32bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

  - <span data-ttu-id="b973f-121">64ビット OS の場合\_:\_HKEY\\ローカル\\コンピューター\\ソフトウェア\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync SessionManager アプリ</span><span class="sxs-lookup"><span data-stu-id="b973f-121">For 64bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

### <a name="custom-command-registry-entries"></a><span data-ttu-id="b973f-122">カスタム コマンドのレジストリ エントリ</span><span class="sxs-lookup"><span data-stu-id="b973f-122">Custom Command Registry Entries</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b973f-123">名前</span><span class="sxs-lookup"><span data-stu-id="b973f-123">Name</span></span></th>
<th><span data-ttu-id="b973f-124">型</span><span class="sxs-lookup"><span data-stu-id="b973f-124">Type</span></span></th>
<th><span data-ttu-id="b973f-125">データ</span><span class="sxs-lookup"><span data-stu-id="b973f-125">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b973f-126">名前</span><span class="sxs-lookup"><span data-stu-id="b973f-126">Name</span></span></p></td>
<td><p><span data-ttu-id="b973f-127">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b973f-127">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="b973f-128">メニューに表示されるアプリケーション名。</span><span class="sxs-lookup"><span data-stu-id="b973f-128">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b973f-129">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="b973f-129">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="b973f-130">DWORD</span><span class="sxs-lookup"><span data-stu-id="b973f-130">DWORD</span></span></p></td>
<td><p><span data-ttu-id="b973f-131">0 = 実行可能 (既定値)</span><span class="sxs-lookup"><span data-stu-id="b973f-131">0 = Executable (default)</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b973f-132">ApplicationInstallPath が必要。</span><span class="sxs-lookup"><span data-stu-id="b973f-132">Requires ApplicationInstallPath.</span></span>


</div>
<p><span data-ttu-id="b973f-133">1 = プロトコル</span><span class="sxs-lookup"><span data-stu-id="b973f-133">1 = Protocol</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b973f-134">ApplicationInstallPath</span><span class="sxs-lookup"><span data-stu-id="b973f-134">ApplicationInstallPath</span></span></p></td>
<td><p><span data-ttu-id="b973f-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b973f-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="b973f-136">実行可能ファイルの完全なパス。</span><span class="sxs-lookup"><span data-stu-id="b973f-136">Full path of the executable.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b973f-137">ApplicationType が 0 (実行可能) の場合は指定が必要。</span><span class="sxs-lookup"><span data-stu-id="b973f-137">Must be specified if ApplicationType is 0 (Executable).</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b973f-138">Path</span><span class="sxs-lookup"><span data-stu-id="b973f-138">Path</span></span></p></td>
<td><p><span data-ttu-id="b973f-139">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b973f-139">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="b973f-140">起動する完全なパスと、既定のパラメーターの <em>%user-id%</em> および <em>%contact-id%</em> を含むパラメーター。</span><span class="sxs-lookup"><span data-stu-id="b973f-140">Full path to be started along with any parameters, including the default parameters <em>%user-id%</em> and <em>%contact-id%</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b973f-141">SessionType</span><span class="sxs-lookup"><span data-stu-id="b973f-141">SessionType</span></span></p></td>
<td><p><span data-ttu-id="b973f-142">DWORD</span><span class="sxs-lookup"><span data-stu-id="b973f-142">DWORD</span></span></p></td>
<td><p><span data-ttu-id="b973f-p102">0 = ローカル セッション。アプリケーションはローカル コンピュータ上で起動します。</span><span class="sxs-lookup"><span data-stu-id="b973f-p102">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="b973f-145">1 = 2 者間セッション (既定値)。</span><span class="sxs-lookup"><span data-stu-id="b973f-145">1 = Two-party session (default).</span></span> <span data-ttu-id="b973f-146">Lync 2013 はアプリケーションをローカルで起動し、その他のユーザーにデスクトップ通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="b973f-146">Lync 2013 starts the application locally and then sends a desktop notification to the other user.</span></span> <span data-ttu-id="b973f-147">相手のユーザーが通知をクリックすると、アプリケーションがそのコンピューター上で起動します。</span><span class="sxs-lookup"><span data-stu-id="b973f-147">The other user clicks the notification to start the application on their computer.</span></span></p>
<p><span data-ttu-id="b973f-148">2 = 複数ユーザー間セッション。</span><span class="sxs-lookup"><span data-stu-id="b973f-148">2 = Multiparty session.</span></span> <span data-ttu-id="b973f-149">Lync 2013 は、アプリケーションをローカルで起動してから、デスクトップ通知を他のユーザーに送信します。</span><span class="sxs-lookup"><span data-stu-id="b973f-149">Lync 2013 starts the application locally and then sends desktop notifications to the other users.</span></span> <span data-ttu-id="b973f-150">他のユーザーが通知をクリックすると、指定されたアプリケーションがコンピューター上で起動します。</span><span class="sxs-lookup"><span data-stu-id="b973f-150">The other user clicks the notification to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b973f-151">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="b973f-151">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="b973f-152">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b973f-152">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="b973f-153">このコマンドが表示されるメニューの一覧は、セミコロンで区切られています。</span><span class="sxs-lookup"><span data-stu-id="b973f-153">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="b973f-154">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b973f-154">Possible values are:</span></span></p>
<p><span data-ttu-id="b973f-155">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="b973f-155">MainWindowActions</span></span></p>
<p><span data-ttu-id="b973f-156">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="b973f-156">MainWindowRightClick</span></span></p>
<p><span data-ttu-id="b973f-157">Conversationwindowactions [</span><span class="sxs-lookup"><span data-stu-id="b973f-157">ConversationWindowActions</span></span></p>
<p><span data-ttu-id="b973f-158">Conversationwindowrightclick [</span><span class="sxs-lookup"><span data-stu-id="b973f-158">ConversationWindowRightClick</span></span></p>
<p><span data-ttu-id="b973f-159">ContactCardMenu</span><span class="sxs-lookup"><span data-stu-id="b973f-159">ContactCardMenu</span></span></p>
<p><span data-ttu-id="b973f-160">ExtensibleMenu が定義されていない場合は、MainWindowRightClick および ConversationWindowContextual の既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b973f-160">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b973f-161">たとえば、次のレジストリ エディター (.REG) ファイルは、[Contoso Sales Contact Manager] メニュー項目を [会話] ウィンドウの [操作] メニューに追加した結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="b973f-161">For example, the following Registry Editor (.REG) file shows the results of adding a Contoso Sales Contact Manager menu item to Actions menu in the Conversation window:</span></span>

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

## <a name="to-access-a-custom-command"></a><span data-ttu-id="b973f-162">カスタム コマンドにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="b973f-162">To access a custom command</span></span>

<span data-ttu-id="b973f-163">カスタムコマンドにアクセスするには、定義した ExtensibleMenu の値に応じて、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b973f-163">To access a custom command after it is added, do one of the following, depending on the ExtensibleMenu values that you define:</span></span>

  - <span data-ttu-id="b973f-164">**Mainwindowactions**   Lync のメインウィンドウで、[**ツール**] をクリックし、カスタムコマンドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b973f-164">**MainWindowActions**   In the Lync main window, click **Tools**, and then click your custom command.</span></span>

  - <span data-ttu-id="b973f-165">**Mainwindowrightclick**   Lync のメインウィンドウで、連絡先を右クリックし、カスタムコマンドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b973f-165">**MainWindowRightClick**   In the Lync main window, right-click a contact, and then click your custom command.</span></span>

  - <span data-ttu-id="b973f-166">**Conversationwindowactions [**   [会話] ウィンドウで、[**その他のオプション**] アイコンをクリックし、カスタムコマンドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b973f-166">**ConversationWindowActions**   In the Conversation window, click the **More Options** icon, and then click your custom command.</span></span>

  - <span data-ttu-id="b973f-167">**Conversationwindowrightclick [**   [会話] ウィンドウで、連絡先の名前を右クリックし、カスタムコマンドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b973f-167">**ConversationWindowRightClick**   In the Conversation window, right-click a contact name, and then click your custom command.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


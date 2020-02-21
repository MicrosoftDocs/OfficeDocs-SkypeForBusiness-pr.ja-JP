---
title: 'Lync Server 2013: Lync 2013 の新規および変更された設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New and changed settings for Lync 2013
ms:assetid: bb13789c-7eda-461c-a387-02ea8ca4dabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205204(v=OCS.15)
ms:contentKeyID: 48185241
ms.date: 12/08/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de4a1a82dbefb5a7f55a4c5872a6702933af08c7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a><span data-ttu-id="4a3bf-102">Lync 2013 の新しい設定と変更された設定</span><span class="sxs-lookup"><span data-stu-id="4a3bf-102">New and changed settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a3bf-103">_**トピックの最終更新日:** 2014-12-05_</span><span class="sxs-lookup"><span data-stu-id="4a3bf-103">_**Topic Last Modified:** 2014-12-05_</span></span>

<span data-ttu-id="4a3bf-104">このトピックでは、クライアント管理に直接関連する Lync Server 管理シェルコマンドレットの変更点について説明します。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-104">This topic discusses changes to Lync Server Management Shell cmdlets that relate directly to client management.</span></span> <span data-ttu-id="4a3bf-105">Lync Server 2013 には、いくつかの新しいパラメーターと、他の手段で構成できる機能の deprecates パラメータが導入されています。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-105">Lync Server 2013 introduces several new parameters, and deprecates parameters for features that can be configured through other means.</span></span>

<div>

## <a name="new-client-management-parameters"></a><span data-ttu-id="4a3bf-106">新しいクライアント管理パラメーター</span><span class="sxs-lookup"><span data-stu-id="4a3bf-106">New Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a3bf-107">新</span><span class="sxs-lookup"><span data-stu-id="4a3bf-107">New</span></span></th>
<th><span data-ttu-id="4a3bf-108">Lync Server 管理シェルコマンドレット</span><span class="sxs-lookup"><span data-stu-id="4a3bf-108">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="4a3bf-109">説明</span><span class="sxs-lookup"><span data-stu-id="4a3bf-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a3bf-110">TracingLevel</span><span class="sxs-lookup"><span data-stu-id="4a3bf-110">TracingLevel</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-111">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="4a3bf-111">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-112">True に設定すると、Lync でソフトウェアトレースが有効になります。False に設定されている場合、ソフトウェアトレースは無効になります。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-112">When set to True, software tracing will be enabled in Lync; when set to False, software tracing will be disabled.</span></span> <span data-ttu-id="4a3bf-113">ソフトウェアトレースには、プログラムが実行しているすべて (追跡 API 呼び出しを含む) の詳細な記録が保存されます。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-113">Software tracing involves keeping a detailed record of everything that a program does (including tracking API calls).</span></span> <span data-ttu-id="4a3bf-114">トレースは、開発者やアプリケーションサポート担当者にとって主に役立ちます。この設定は、Communications Server 2007 R2 のグループポリシー設定&quot;と同等です。 Communicator のトレースをオンにします。&quot;設定値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-114">Tracing is mostly useful to developers and to application support personnel.This setting is equivalent to the Communications Server 2007 R2 Group Policy setting &quot;Turn on tracing for Communicator.&quot; The settings are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="4a3bf-115">Off = トレースは無効になっており、ユーザーはこの設定を変更できません。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-115">Off = Tracing is disabled and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="4a3bf-116">Light = 最小のトレースが実行され、ユーザーはこの設定を変更できません。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-116">Light = Minimal tracing is performed, and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="4a3bf-117">On = 詳細なトレースが実行され、ユーザーはこの設定を変更できません。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-117">On = Verbose tracing is performed, and the user cannot change this setting.</span></span></p></li>
</ul>
<p><span data-ttu-id="4a3bf-118">既定では、TracingLevel は null 値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-118">By default TracingLevel is set to a null value.</span></span> <span data-ttu-id="4a3bf-119">これは、最小限のトレースが実行されることを意味しますが、ユーザーはこの最小限のトレースを有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-119">That means that minimal tracing is performed, but the user can enable or disable this minimal tracing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a3bf-120">対して enablemediaredirection</span><span class="sxs-lookup"><span data-stu-id="4a3bf-120">EnableMediaRedirection</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-121">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="4a3bf-121">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-122">True ($True) に設定すると、オーディオおよびビデオストリームが他のネットワークトラフィックから分離されるようになります。これにより、クライアントデバイスはオーディオとビデオをローカルでエンコードおよびデコードできるようになります。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-122">When set to True ($True) allows audio and video streams to be separated from other network traffic, In turn, this allows client devices to do encoding and decoding of audio and video locally.</span></span> <span data-ttu-id="4a3bf-123">通常、メディアのリダイレクトでは、帯域幅の使用率が低くなり、サーバーのスケーラビリティが向上します。また、デバイスのリモート処理やコーデックの圧縮などの同様の手法と比較して、より最適なユーザーの操作が実現されます。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-123">Media redirection typically results in lower bandwidth usage, higher server scalability, and a more-optimal user experience compared to similar techniques such as device remoting or codec compression.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a3bf-124">AllowLargeMeetings</span><span class="sxs-lookup"><span data-stu-id="4a3bf-124">AllowLargeMeetings</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-125">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="4a3bf-125">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-126">True に設定すると、すべての Lync 会議が&quot;大規模な会議として扱われます。&quot;大規模な会議では、既定で送信される会議名簿のサイズに加えて、参加者に送信される通知の数に制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-126">When set to True, all Lync Meetings are treated as &quot;large meetings.&quot; With a large meeting, restrictions are placed on the number of notifications that are sent to participants, in addition to the size of the meeting roster that is transmitted by default.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a3bf-127">DisablePowerPointAnnotations</span><span class="sxs-lookup"><span data-stu-id="4a3bf-127">DisablePowerPointAnnotations</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-128">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="4a3bf-128">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-129">True ($True) に設定すると、ユーザーは会議で使用される PowerPoint スライドにコメントを追加できなくなります。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-129">When set to True ($True) users won’t be able to add annotations to PowerPoint slides used in a conference.</span></span> <span data-ttu-id="4a3bf-130">ただし、AllowAnnotations プロパティの値に応じて、ユーザーは他のホワイトボード機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-130">However (depending on the value of the AllowAnnotations property), users will still have access to other whiteboarding features.</span></span> <span data-ttu-id="4a3bf-131">既定値は False です。これは、PowerPoint の注釈が許可されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-131">The default value is False, meaning that PowerPoint annotations are allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a3bf-132">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="4a3bf-132">AllowSharedNotes</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-133">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="4a3bf-133">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-134">True (既定値) に設定すると、会議にリンクされている開いている OneNote ノートブックはすべて、会議参加者、会議中に共有されるコンテンツの詳細などの情報で自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-134">When set to True (the default value) any open OneNote notebooks linked to the conference will automatically be updated with information such as conference participants and details about content shared during the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a3bf-135">EnableInviteCustomization</span><span class="sxs-lookup"><span data-stu-id="4a3bf-135">EnableInviteCustomization</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-136">Get-csmeetingconfiguration</span><span class="sxs-lookup"><span data-stu-id="4a3bf-136">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-137">他の新しい Csmeeting 構成パラメーターと共に使用して、Lync 2013 用オンラインミーティングアドインによって生成される会議出席依頼をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-137">Used along with the other new CsMeetingConfiguration parameters to customize the meeting invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a3bf-138">LogoURL</span><span class="sxs-lookup"><span data-stu-id="4a3bf-138">LogoURL</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-139">Get-csmeetingconfiguration</span><span class="sxs-lookup"><span data-stu-id="4a3bf-139">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-140">Lync 2013 用のオンラインミーティングアドインによって生成されたすべての招待に組織のロゴを追加します。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-140">Adds your organization’s logo to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="4a3bf-141">GIF または JPG 画像の URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-141">You specify the URL of a GIF or JPG image.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a3bf-142">HelpURL</span><span class="sxs-lookup"><span data-stu-id="4a3bf-142">HelpURL</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-143">Get-csmeetingconfiguration</span><span class="sxs-lookup"><span data-stu-id="4a3bf-143">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-144">Lync 2013 用オンラインミーティングアドインによって生成されたすべての招待に組織のヘルプまたはサポート URL を追加します。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-144">Adds your organization’s help or support URL to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a3bf-145">LegalURL</span><span class="sxs-lookup"><span data-stu-id="4a3bf-145">LegalURL</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-146">Get-csmeetingconfiguration</span><span class="sxs-lookup"><span data-stu-id="4a3bf-146">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-147">Lync 2013 用オンラインミーティングアドインによって生成されたすべての招待に、法的なテキストまたは免責事項のテキストを追加します。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-147">Adds legal text or disclaimer text to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="4a3bf-148">テキストの場所の URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-148">You specify the URL for the location of the text.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a3bf-149">Customフッターテキスト</span><span class="sxs-lookup"><span data-stu-id="4a3bf-149">CustomFooterText</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-150">Get-csmeetingconfiguration</span><span class="sxs-lookup"><span data-stu-id="4a3bf-150">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-151">Lync 2013 用のオンラインミーティングアドインによって生成されたすべての招待にカスタムフッターを追加します。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-151">Adds a custom footer to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="4a3bf-152">カスタムフッターテキストの場所の URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-152">You specify the URL for the location of the custom footer text.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a><span data-ttu-id="4a3bf-153">非推奨のクライアント管理パラメーター</span><span class="sxs-lookup"><span data-stu-id="4a3bf-153">Deprecated Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a3bf-154">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4a3bf-154">Parameter</span></span></th>
<th><span data-ttu-id="4a3bf-155">Lync Server 管理シェルコマンドレット</span><span class="sxs-lookup"><span data-stu-id="4a3bf-155">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="4a3bf-156">説明</span><span class="sxs-lookup"><span data-stu-id="4a3bf-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a3bf-157">CustomizedHelpUrl</span><span class="sxs-lookup"><span data-stu-id="4a3bf-157">CustomizedHelpUrl</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-158">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="4a3bf-158">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-159">このパラメーターは、Lync Server 2013 で使用するために廃止されました。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-159">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="4a3bf-160">このパラメーターを Enableenterprisecustomizedhelp がと組み合わせて使用すると、ユーザーが Lync の [ヘルプ] メニューをクリックしたときに、カスタマイズしたヘルプが表示されるように、組織で URL を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-160">When used in conjunction with EnableEnterpriseCustomizedHelp, this parameter enabled an organization to specify a URL so that when users clicked the Help menu in Lync, customized help would display.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a3bf-161">Enableenterprisecustomizedhelp が</span><span class="sxs-lookup"><span data-stu-id="4a3bf-161">EnableEnterpriseCustomizedHelp</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-162">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="4a3bf-162">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-163">このパラメーターは、Lync Server 2013 で使用するために廃止されました。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-163">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="4a3bf-164">このパラメーターを CustomizedHelpUrl と組み合わせて使用すると、カスタマイズされたヘルプを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-164">When used in conjunction with CustomizedHelpUrl, this parameter enabled organizations to display customized help.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a3bf-165">EnableSQMData</span><span class="sxs-lookup"><span data-stu-id="4a3bf-165">EnableSQMData</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-166">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="4a3bf-166">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-167">EnableSQMData コマンドレットのパラメーターが Lync Server 2013 で削除されました。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-167">The EnableSQMData parameter of the Set-CSClientPolicy cmdlet has been removed in Lync Server 2013.</span></span> <span data-ttu-id="4a3bf-168">代わりに、Software Quality Management (SQM) データの共有グループポリシー設定を使用して、Lync クライアントの [全般オプション] ページの [カスタマーエクスペリエンス向上オプション] のユーザーインターフェイスを決定することができます。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-168">Instead, you can use the shared Group Policy setting for Software Quality Management (SQM) data to determine the user interface for the Customer Experience Improvement option in the Lync client General options page:</span></span></p>
<p><span data-ttu-id="4a3bf-169">HKEY_CURRENT_USER \Software\Policies\Microsoft\Office\Common\QMEnable</span><span class="sxs-lookup"><span data-stu-id="4a3bf-169">HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</span></span></p>
<p><span data-ttu-id="4a3bf-170">数値</span><span class="sxs-lookup"><span data-stu-id="4a3bf-170">Values:</span></span></p>
<p><span data-ttu-id="4a3bf-171">1 = チェックボックスを表示および選択します (ユーザーはチェックボックスをオフにできます)</span><span class="sxs-lookup"><span data-stu-id="4a3bf-171">1 = Display and select the check box (the user can clear the check box)</span></span></p>
<p><span data-ttu-id="4a3bf-172">0 = チェックボックスをオフにし、無効にします (ユーザーは上書きできません)</span><span class="sxs-lookup"><span data-stu-id="4a3bf-172">0 = Turn off and disable the check box (user can't override)</span></span></p>
<p><span data-ttu-id="4a3bf-173">Null = 値は Office セットアップによって決定され、ユーザーが選択したとおりに設定するためのチェックボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-173">Null = The value is determined by Office setup, and the check box is displayed for users to set as they choose</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a3bf-174">AllowExchangeContactStore</span><span class="sxs-lookup"><span data-stu-id="4a3bf-174">AllowExchangeContactStore</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-175">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="4a3bf-175">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-176">このパラメーターは削除されました。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-176">This parameter has been removed.</span></span> <span data-ttu-id="4a3bf-177">その代わりに、Lync Server 2013 を展開してトポロジを公開すると、すべてのユーザーに対して統合連絡先ストアが既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-177">Instead, when you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="4a3bf-178">これは、すべてのユーザーの連絡先が Exchange に保持され、Lync、Outlook、および Outlook Web Access で使用できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-178">This means that all a user’s contacts are kept in Exchange and are available in Lync, Outlook, and Outlook Web Access.</span></span> <span data-ttu-id="4a3bf-179">このコマンドレットを使用して、統合連絡先ストアを使用できるユーザーをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-179">You can use the Set-CsUserServicesPolicy cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="4a3bf-180">ユーザーをグローバルに、サイト、テナント、または個人または個人のグループごとに有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-180">You can enable users globally, by site, by tenant, or by individuals or groups of individuals.</span></span> <span data-ttu-id="4a3bf-181">詳細については、「 <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Lync Server 2013 の統合連絡先ストアでユーザーを有効にする</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-181">For details, see <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Enable users for unified contact store in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a3bf-182">MAPIPollInterval</span><span class="sxs-lookup"><span data-stu-id="4a3bf-182">MAPIPollInterval</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-183">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="4a3bf-183">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-184">このパラメーターは Lync 2013 では使用されません。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-184">This parameter is not used by Lync 2013.</span></span> <span data-ttu-id="4a3bf-185">以前のリリースでは、このパラメーターは、クライアントが Exchange パブリックフォルダーから MAPI データを取得する頻度を指定していました。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-185">In previous releases, this parameter specified how often the client retrieved MAPI data from Exchange public folders</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a3bf-186">DisableICE</span><span class="sxs-lookup"><span data-stu-id="4a3bf-186">DisableICE</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-187">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="4a3bf-187">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="4a3bf-188">このパラメーターは Lync 2013 で廃止されました。</span><span class="sxs-lookup"><span data-stu-id="4a3bf-188">This parameter was deprecated in Lync 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


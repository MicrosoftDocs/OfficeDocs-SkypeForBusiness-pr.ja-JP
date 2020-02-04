---
title: 'Lync Server 2013: Lync 2013 の新しい設定と変更された設定'
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
ms.openlocfilehash: fb5366f7e3d4c2aba81b5b8b25873ea22d54c3a6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a><span data-ttu-id="830bc-102">Lync 2013 の新しい設定と変更された設定</span><span class="sxs-lookup"><span data-stu-id="830bc-102">New and changed settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="830bc-103">_**最終更新日:** 2014-12-05_</span><span class="sxs-lookup"><span data-stu-id="830bc-103">_**Topic Last Modified:** 2014-12-05_</span></span>

<span data-ttu-id="830bc-104">このトピックでは、クライアント管理に直接関連する Lync Server 管理シェルコマンドレットの変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="830bc-104">This topic discusses changes to Lync Server Management Shell cmdlets that relate directly to client management.</span></span> <span data-ttu-id="830bc-105">Lync Server 2013 には、いくつかの新しいパラメーターと、他の手段で構成できる機能の deprecates パラメーターが導入されています。</span><span class="sxs-lookup"><span data-stu-id="830bc-105">Lync Server 2013 introduces several new parameters, and deprecates parameters for features that can be configured through other means.</span></span>

<div>

## <a name="new-client-management-parameters"></a><span data-ttu-id="830bc-106">新しいクライアント管理パラメーター</span><span class="sxs-lookup"><span data-stu-id="830bc-106">New Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="830bc-107">新機能</span><span class="sxs-lookup"><span data-stu-id="830bc-107">New</span></span></th>
<th><span data-ttu-id="830bc-108">Lync Server Management Shell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="830bc-108">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="830bc-109">説明</span><span class="sxs-lookup"><span data-stu-id="830bc-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="830bc-110">TracingLevel</span><span class="sxs-lookup"><span data-stu-id="830bc-110">TracingLevel</span></span></p></td>
<td><p><span data-ttu-id="830bc-111">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="830bc-111">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="830bc-112">True に設定すると、Lync でソフトウェアのトレースが有効になります。False に設定すると、ソフトウェアのトレースが無効になります。</span><span class="sxs-lookup"><span data-stu-id="830bc-112">When set to True, software tracing will be enabled in Lync; when set to False, software tracing will be disabled.</span></span> <span data-ttu-id="830bc-113">ソフトウェアトレースには、プログラムで行われるすべての情報 (追跡 API 呼び出しを含む) の詳細な記録が含まれています。</span><span class="sxs-lookup"><span data-stu-id="830bc-113">Software tracing involves keeping a detailed record of everything that a program does (including tracking API calls).</span></span> <span data-ttu-id="830bc-114">トレースは、ほとんどが開発者やアプリケーションのサポート担当者にとって役立ちます。この設定は、Communications Server 2007 R2 グループポリシー設定&quot;と同じです。 Communicator のトレースを有効にします。&quot;設定は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="830bc-114">Tracing is mostly useful to developers and to application support personnel.This setting is equivalent to the Communications Server 2007 R2 Group Policy setting &quot;Turn on tracing for Communicator.&quot; The settings are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="830bc-115">オフ = トレースは無効になり、ユーザーはこの設定を変更できません。</span><span class="sxs-lookup"><span data-stu-id="830bc-115">Off = Tracing is disabled and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="830bc-116">Light = 最小トレースが実行され、ユーザーはこの設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="830bc-116">Light = Minimal tracing is performed, and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="830bc-117">On = 詳細トレースが実行され、ユーザーはこの設定を変更できません。</span><span class="sxs-lookup"><span data-stu-id="830bc-117">On = Verbose tracing is performed, and the user cannot change this setting.</span></span></p></li>
</ul>
<p><span data-ttu-id="830bc-118">既定では、TracingLevel は null 値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="830bc-118">By default TracingLevel is set to a null value.</span></span> <span data-ttu-id="830bc-119">つまり、最小限のトレースが実行されますが、ユーザーはこの最小トレースを有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="830bc-119">That means that minimal tracing is performed, but the user can enable or disable this minimal tracing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="830bc-120">EnableMediaRedirection</span><span class="sxs-lookup"><span data-stu-id="830bc-120">EnableMediaRedirection</span></span></p></td>
<td><p><span data-ttu-id="830bc-121">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="830bc-121">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="830bc-122">True ($True) に設定すると、オーディオストリームとビデオストリームを他のネットワークトラフィックから分離することができます。これにより、クライアントデバイスはローカルでオーディオとビデオのエンコードとデコードを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="830bc-122">When set to True ($True) allows audio and video streams to be separated from other network traffic, In turn, this allows client devices to do encoding and decoding of audio and video locally.</span></span> <span data-ttu-id="830bc-123">メディアのリダイレクションは、一般的に、帯域幅の使用率が低くなり、サーバーのスケーラビリティも高く、デバイスリモート処理やコーデック圧縮などの同様の手法と比較して、最適なユーザーエクスペリエンスを実現します。</span><span class="sxs-lookup"><span data-stu-id="830bc-123">Media redirection typically results in lower bandwidth usage, higher server scalability, and a more-optimal user experience compared to similar techniques such as device remoting or codec compression.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="830bc-124">AllowLargeMeetings</span><span class="sxs-lookup"><span data-stu-id="830bc-124">AllowLargeMeetings</span></span></p></td>
<td><p><span data-ttu-id="830bc-125">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="830bc-125">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="830bc-126">True に設定すると、すべての Lync 会議が&quot;大規模な会議として扱われます。&quot;大規模な会議では、既定で送信された会議リストのサイズに加えて、参加者に送信される通知の数に制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="830bc-126">When set to True, all Lync Meetings are treated as &quot;large meetings.&quot; With a large meeting, restrictions are placed on the number of notifications that are sent to participants, in addition to the size of the meeting roster that is transmitted by default.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="830bc-127">DisablePowerPointAnnotations</span><span class="sxs-lookup"><span data-stu-id="830bc-127">DisablePowerPointAnnotations</span></span></p></td>
<td><p><span data-ttu-id="830bc-128">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="830bc-128">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="830bc-129">True ($True) に設定すると、ユーザーは会議で使用されている PowerPoint スライドに注釈を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="830bc-129">When set to True ($True) users won’t be able to add annotations to PowerPoint slides used in a conference.</span></span> <span data-ttu-id="830bc-130">ただし、(AllowAnnotations プロパティの値によっては)、ユーザーは他の whiteboarding 機能に引き続きアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="830bc-130">However (depending on the value of the AllowAnnotations property), users will still have access to other whiteboarding features.</span></span> <span data-ttu-id="830bc-131">既定値は False であり、PowerPoint の注釈が許可されていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="830bc-131">The default value is False, meaning that PowerPoint annotations are allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="830bc-132">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="830bc-132">AllowSharedNotes</span></span></p></td>
<td><p><span data-ttu-id="830bc-133">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="830bc-133">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="830bc-134">True (既定値) に設定すると、会議にリンクされている開いている OneNote ノートブックが、会議の参加者や会議中に共有されたコンテンツに関する詳細などの情報で自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="830bc-134">When set to True (the default value) any open OneNote notebooks linked to the conference will automatically be updated with information such as conference participants and details about content shared during the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="830bc-135">EnableInviteCustomization</span><span class="sxs-lookup"><span data-stu-id="830bc-135">EnableInviteCustomization</span></span></p></td>
<td><p><span data-ttu-id="830bc-136">Cs会議構成</span><span class="sxs-lookup"><span data-stu-id="830bc-136">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="830bc-137">他の新しい Csmeeting 構成パラメーターと共に使用して、Lync 2013 用のオンライン会議アドインによって生成された会議出席依頼をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="830bc-137">Used along with the other new CsMeetingConfiguration parameters to customize the meeting invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="830bc-138">LogoURL</span><span class="sxs-lookup"><span data-stu-id="830bc-138">LogoURL</span></span></p></td>
<td><p><span data-ttu-id="830bc-139">Cs会議構成</span><span class="sxs-lookup"><span data-stu-id="830bc-139">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="830bc-140">Lync 2013 用のオンライン会議アドインによって生成されたすべての招待に、組織のロゴを追加します。</span><span class="sxs-lookup"><span data-stu-id="830bc-140">Adds your organization’s logo to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="830bc-141">GIF または JPG イメージの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="830bc-141">You specify the URL of a GIF or JPG image.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="830bc-142">HelpURL</span><span class="sxs-lookup"><span data-stu-id="830bc-142">HelpURL</span></span></p></td>
<td><p><span data-ttu-id="830bc-143">Cs会議構成</span><span class="sxs-lookup"><span data-stu-id="830bc-143">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="830bc-144">Lync 2013 用のオンライン会議アドインによって生成されたすべての招待に、組織のヘルプまたはサポート URL を追加します。</span><span class="sxs-lookup"><span data-stu-id="830bc-144">Adds your organization’s help or support URL to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="830bc-145">LegalURL</span><span class="sxs-lookup"><span data-stu-id="830bc-145">LegalURL</span></span></p></td>
<td><p><span data-ttu-id="830bc-146">Cs会議構成</span><span class="sxs-lookup"><span data-stu-id="830bc-146">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="830bc-147">Lync 2013 用のオンライン会議アドインによって生成されたすべての招待状に法的なテキストまたは免責事項を追加します。</span><span class="sxs-lookup"><span data-stu-id="830bc-147">Adds legal text or disclaimer text to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="830bc-148">テキストの場所の URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="830bc-148">You specify the URL for the location of the text.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="830bc-149">Customフッターのテキスト</span><span class="sxs-lookup"><span data-stu-id="830bc-149">CustomFooterText</span></span></p></td>
<td><p><span data-ttu-id="830bc-150">Cs会議構成</span><span class="sxs-lookup"><span data-stu-id="830bc-150">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="830bc-151">Lync 2013 用のオンライン会議アドインによって生成されたすべての招待にカスタムフッターを追加します。</span><span class="sxs-lookup"><span data-stu-id="830bc-151">Adds a custom footer to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="830bc-152">ユーザー設定のフッターテキストの場所の URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="830bc-152">You specify the URL for the location of the custom footer text.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a><span data-ttu-id="830bc-153">非推奨のクライアント管理パラメーター</span><span class="sxs-lookup"><span data-stu-id="830bc-153">Deprecated Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="830bc-154">パラメーター</span><span class="sxs-lookup"><span data-stu-id="830bc-154">Parameter</span></span></th>
<th><span data-ttu-id="830bc-155">Lync Server Management Shell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="830bc-155">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="830bc-156">説明</span><span class="sxs-lookup"><span data-stu-id="830bc-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="830bc-157">CustomizedHelpUrl</span><span class="sxs-lookup"><span data-stu-id="830bc-157">CustomizedHelpUrl</span></span></p></td>
<td><p><span data-ttu-id="830bc-158">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="830bc-158">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="830bc-159">このパラメーターは、Lync Server 2013 で使用するために廃止されました。</span><span class="sxs-lookup"><span data-stu-id="830bc-159">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="830bc-160">このパラメーターを EnableEnterpriseCustomizedHelp と組み合わせて使うと、ユーザーが Lync の [ヘルプ] メニューをクリックしたときに、カスタマイズされたヘルプが表示されるように、組織が URL を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="830bc-160">When used in conjunction with EnableEnterpriseCustomizedHelp, this parameter enabled an organization to specify a URL so that when users clicked the Help menu in Lync, customized help would display.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="830bc-161">EnableEnterpriseCustomizedHelp</span><span class="sxs-lookup"><span data-stu-id="830bc-161">EnableEnterpriseCustomizedHelp</span></span></p></td>
<td><p><span data-ttu-id="830bc-162">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="830bc-162">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="830bc-163">このパラメーターは、Lync Server 2013 で使用するために廃止されました。</span><span class="sxs-lookup"><span data-stu-id="830bc-163">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="830bc-164">このパラメーターを CustomizedHelpUrl と組み合わせて使用すると、ユーザー設定のヘルプを表示できます。</span><span class="sxs-lookup"><span data-stu-id="830bc-164">When used in conjunction with CustomizedHelpUrl, this parameter enabled organizations to display customized help.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="830bc-165">EnableSQMData</span><span class="sxs-lookup"><span data-stu-id="830bc-165">EnableSQMData</span></span></p></td>
<td><p><span data-ttu-id="830bc-166">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="830bc-166">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="830bc-167">EnableSQMData パラメーターコマンドレットが Lync Server 2013 で削除されました。</span><span class="sxs-lookup"><span data-stu-id="830bc-167">The EnableSQMData parameter of the Set-CSClientPolicy cmdlet has been removed in Lync Server 2013.</span></span> <span data-ttu-id="830bc-168">代わりに、ソフトウェア品質管理 (SQM) データの共有グループポリシー設定を使用して、Lync クライアントの [全般] オプションページのカスタマーエクスペリエンス向上オプションのユーザーインターフェイスを決定することができます。</span><span class="sxs-lookup"><span data-stu-id="830bc-168">Instead, you can use the shared Group Policy setting for Software Quality Management (SQM) data to determine the user interface for the Customer Experience Improvement option in the Lync client General options page:</span></span></p>
<p><span data-ttu-id="830bc-169">HKEY_CURRENT_USER \Software\Policies\Microsoft\Office\Common\QMEnable</span><span class="sxs-lookup"><span data-stu-id="830bc-169">HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</span></span></p>
<p><span data-ttu-id="830bc-170">Values</span><span class="sxs-lookup"><span data-stu-id="830bc-170">Values:</span></span></p>
<p><span data-ttu-id="830bc-171">1 = チェックボックスを表示して選択する (ユーザーはチェックボックスをオフにすることができます)</span><span class="sxs-lookup"><span data-stu-id="830bc-171">1 = Display and select the check box (the user can clear the check box)</span></span></p>
<p><span data-ttu-id="830bc-172">0 = チェックボックスをオフにして無効にします (ユーザーは上書きできません)。</span><span class="sxs-lookup"><span data-stu-id="830bc-172">0 = Turn off and disable the check box (user can't override)</span></span></p>
<p><span data-ttu-id="830bc-173">Null = 値は Office のセットアップによって決定され、ユーザーが選ぶときに設定できるチェックボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="830bc-173">Null = The value is determined by Office setup, and the check box is displayed for users to set as they choose</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="830bc-174">AllowExchangeContactStore</span><span class="sxs-lookup"><span data-stu-id="830bc-174">AllowExchangeContactStore</span></span></p></td>
<td><p><span data-ttu-id="830bc-175">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="830bc-175">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="830bc-176">このパラメーターは削除されました。</span><span class="sxs-lookup"><span data-stu-id="830bc-176">This parameter has been removed.</span></span> <span data-ttu-id="830bc-177">代わりに、Lync Server 2013 を展開してトポロジを公開すると、統合連絡先ストアは既定ですべてのユーザーに対して有効になります。</span><span class="sxs-lookup"><span data-stu-id="830bc-177">Instead, when you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="830bc-178">これは、すべてのユーザーの連絡先が Exchange に保存され、Lync、Outlook、Outlook Web Access で利用できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="830bc-178">This means that all a user’s contacts are kept in Exchange and are available in Lync, Outlook, and Outlook Web Access.</span></span> <span data-ttu-id="830bc-179">設定-Csuserサービスのコマンドレットを使用して、統合連絡先ストアを利用できるユーザーをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="830bc-179">You can use the Set-CsUserServicesPolicy cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="830bc-180">ユーザーは、グローバルに、サイト、テナント、または個人またはグループごとに有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="830bc-180">You can enable users globally, by site, by tenant, or by individuals or groups of individuals.</span></span> <span data-ttu-id="830bc-181">詳細については、「 <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Lync Server 2013 で統合連絡先ストアのユーザーを有効にする</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="830bc-181">For details, see <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Enable users for unified contact store in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="830bc-182">MAPIPollInterval</span><span class="sxs-lookup"><span data-stu-id="830bc-182">MAPIPollInterval</span></span></p></td>
<td><p><span data-ttu-id="830bc-183">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="830bc-183">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="830bc-184">このパラメーターは Lync 2013 では使用されません。</span><span class="sxs-lookup"><span data-stu-id="830bc-184">This parameter is not used by Lync 2013.</span></span> <span data-ttu-id="830bc-185">以前のリリースでは、クライアントが Exchange パブリックフォルダーから MAPI データを取得する頻度を指定しています。</span><span class="sxs-lookup"><span data-stu-id="830bc-185">In previous releases, this parameter specified how often the client retrieved MAPI data from Exchange public folders</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="830bc-186">DisableICE</span><span class="sxs-lookup"><span data-stu-id="830bc-186">DisableICE</span></span></p></td>
<td><p><span data-ttu-id="830bc-187">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="830bc-187">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="830bc-188">このパラメーターは Lync 2013 で廃止されました。</span><span class="sxs-lookup"><span data-stu-id="830bc-188">This parameter was deprecated in Lync 2013.</span></span></p></td>
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


---
title: Lync Server 2013 の概要
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Introduction to Lync Server
ms:assetid: 99dd6b65-e591-421f-852b-ee9fe9588998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398795(v=OCS.15)
ms:contentKeyID: 48184885
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b0b6868486f9486758d2a346dd62339d98ed1e7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction-to-lync-server-2013"></a><span data-ttu-id="e6c6b-102">Lync Server 2013 の概要</span><span class="sxs-lookup"><span data-stu-id="e6c6b-102">Introduction to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6c6b-103">_**トピックの最終更新日:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="e6c6b-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="e6c6b-104">Lync Server 2013 とそのクライアントソフトウェア (Lync 2013 など) により、ユーザーは新しい方法で接続し、物理的な場所に関係なく接続を維持することができます。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-104">Lync Server 2013 and its client software, such as Lync 2013, enable your users to connect in new ways and to stay connected, regardless of their physical location.</span></span> <span data-ttu-id="e6c6b-105">Lync および Lync Server は、ユーザーが1つのクライアントインターフェイスで通信し、統一されたプラットフォームとして展開され、単一の管理インフラストラクチャを通じて管理するさまざまな方法を統合しています。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-105">Lync and Lync Server bring together the different ways that people communicate in a single client interface, are deployed as a unified platform, and are administered through a single management infrastructure.</span></span>

<span data-ttu-id="e6c6b-106">この表と以下のセクションでは、Lync Server がユーザーに提供する主な機能セット (*ワークロード*) について説明します。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-106">This table and the following sections illustrate the major feature sets, or *workloads*, that Lync Server provides for your users.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e6c6b-107">ワークロード</span><span class="sxs-lookup"><span data-stu-id="e6c6b-107">Workload</span></span></th>
<th><span data-ttu-id="e6c6b-108">説明</span><span class="sxs-lookup"><span data-stu-id="e6c6b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e6c6b-109">IM とプレゼンス</span><span class="sxs-lookup"><span data-stu-id="e6c6b-109">IM and presence</span></span></p></td>
<td><p><span data-ttu-id="e6c6b-110">インスタント メッセージング (IM) とプレゼンスにより、ユーザーは効率的かつ効果的に相手を見つけて連絡できます。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-110">Instant messaging (IM) and presence help your users find and communicate with one another efficiently and effectively.</span></span></p>
<p><span data-ttu-id="e6c6b-111">IM は、会話履歴を備えるインスタント メッセージング プラットフォームを提供し、MSN/Windows Live、Yahoo!、AOL、Google Talk などパブリック IM ネットワーク ユーザーとのパブリック IM 接続をサポートします。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-111">IM provides an instant messaging platform with conversation history, and supports public IM connectivity with users of public IM networks such as MSN/Windows Live, Yahoo!, AOL, and Google Talk.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="e6c6b-112">2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規購入時または契約の更新時に購入することができなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-112">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="e6c6b-113">アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-113">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="e6c6b-114">メッセンジャーサービスが終了するまでの期間。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-114">Messenger until the service shut down date.</span></span> <span data-ttu-id="e6c6b-115">AOL および Yahoo! の2014年6月の寿命の終了日</span><span class="sxs-lookup"><span data-stu-id="e6c6b-115">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="e6c6b-116">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-116">has been announced.</span></span> <span data-ttu-id="e6c6b-117">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-117">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="e6c6b-118">PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの月ごとのサブスクリプションライセンスです。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-118">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="e6c6b-119">Messenger.</span><span class="sxs-lookup"><span data-stu-id="e6c6b-119">Messenger.</span></span> <span data-ttu-id="e6c6b-120">このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートに応じて決定されました。これは、使用する基礎となる契約です。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-120">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="e6c6b-121">Lync は、組織間や世界中の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-121">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="e6c6b-122">Windows Live Messenger とのフェデレーションでは、Lync Standard CAL を超えるユーザー/デバイスライセンスを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-122">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="e6c6b-123">Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を使用して数百人のユーザーにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-123">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div>
<p><span data-ttu-id="e6c6b-p105">プレゼンスは、ユーザーの個人的な空き時間や通話応答の意思を、[<strong>連絡可能</strong>] や [<strong>取り込み中</strong>] などの共通のステータス、さらには [<strong>一時退席中</strong>] や [<strong>応答しない</strong>] といったさらに詳細なステータスを使って明確にし、表示します。この豊富なプレゼンス情報により、他のユーザーは効果的な連絡方法をすばやく選択できます。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-p105">Presence establishes and displays a user’s personal availability and willingness to communicate through the use of common states such as <strong>Available</strong> or <strong>Busy</strong>, as well as more detailed states such as <strong>Be Right Back</strong> and <strong>Do Not Disturb</strong>. This rich presence information enables other users to immediately make effective communication choices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6c6b-126">会議</span><span class="sxs-lookup"><span data-stu-id="e6c6b-126">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="e6c6b-127">Lync Server は、スケジュールされた会議と即時の会議の両方について、IM 会議、電話会議、web 会議、ビデオ会議、およびアプリケーション共有のサポートを備えています。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-127">Lync Server includes support for IM conferencing, audio conferencing, web conferencing, video conferencing, and application sharing, for both scheduled and impromptu meetings.</span></span> <span data-ttu-id="e6c6b-128">これらの会議の全種類が 1 つのクライアントでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-128">All these meeting types are supported with a single client.</span></span> <span data-ttu-id="e6c6b-129">Lync Server は、電話会議の音声部分に公衆交換電話網 (PSTN) 電話のユーザーが参加できるように、ダイヤルイン会議もサポートします。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-129">Lync Server also supports dial-in conferencing so that users of public switched telephone network (PSTN) phones can participate in the audio portion of conferences.</span></span></p>
<p><span data-ttu-id="e6c6b-p107">会議はリアル タイムでシームレスに変更および拡大できます。たとえば、1 つの会議を数人のユーザー間のインスタント メッセージのみで開始し、デスクトップ共有を使用するより参加者の多い大規模な音声会議へと、会話の流れを遮ることなくすばやく簡単に切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-p107">Conferences can seamlessly change and grow in real time. For example, a single conference can start as just instant messages between a few users, and escalate to an audio conference with desktop sharing and a larger audience instantly, easily, and without interrupting the conversation flow.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6c6b-132">エンタープライズ VoIP</span><span class="sxs-lookup"><span data-stu-id="e6c6b-132">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="e6c6b-133"><em>エンタープライズ voip</em>は、Lync Server でのボイスオーバー Ip (VoIP) サービスです。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-133"><em>Enterprise Voice</em> is the Voice over Internet Protocol (VoIP) offering in Lync Server.</span></span> <span data-ttu-id="e6c6b-134">従来の構内交換機 (PBX) システムを強化または置き換える音声オプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-134">It delivers a voice option to enhance or replace traditional private branch exchange (PBX) systems.</span></span> <span data-ttu-id="e6c6b-135">IP PBX のすべてのテレフォニー機能に加え、エンタープライズ VoIP は豊富なプレゼンス、IM、共同作業、および会議と統合されています。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-135">In addition to the complete telephony capabilities of an IP PBX, Enterprise Voice is integrated with rich presence, IM, collaboration, and meetings.</span></span> <span data-ttu-id="e6c6b-136">通話応答、保留、再開、着信転送、通話転送、リモート転送などの機能が直接サポートされ、また、個人用短縮ダイヤル キーは連絡先リストに置き換えられ、自動インターコムは IM に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-136">Features such as call answer, hold, resume, transfer, forward and divert are supported directly, while personalized speed dialing keys are replaced by Contacts lists, and automatic intercom is replaced with IM.</span></span></p>
<p><span data-ttu-id="e6c6b-137">エンタープライズ VoIP は、通話受付管理 (CAC) による高い可用性、ブランチ オフィスの存続性、およびデータ復元性の拡張オプションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-137">Enterprise Voice supports high availability through call admission control (CAC), branch office survivability, and extended options for data resiliency.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6c6b-138">リモート ユーザーのサポート</span><span class="sxs-lookup"><span data-stu-id="e6c6b-138">Support for remote users</span></span></p></td>
<td><p><span data-ttu-id="e6c6b-139"><em>エッジ</em>サーバーと呼ばれるサーバーを展開してリモートユーザーに接続を提供することにより、組織のファイアウォールの外側にいるユーザーに Lync Server の完全な機能を提供できます。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-139">You can provide full Lync Server functionality for users who are currently outside your organization’s firewalls by deploying servers called <em>Edge Servers</em> to provide a connection for these remote users.</span></span> <span data-ttu-id="e6c6b-140">これらのリモートユーザーは、Lync 2013 がインストールされたパーソナルコンピューター、電話、または web インターフェイスを使用して、会議に接続できます。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-140">These remote users can connect to conferences by using a personal computer with Lync 2013 installed, the phone, or a web interface.</span></span></p>
<p><span data-ttu-id="e6c6b-p110">エッジ サーバーを展開すると、パートナーやベンダー組織とのフェデレーション<em></em>も有効にできます。フェデレーション関係によって、ユーザーは連絡先リストにフェデレーション ユーザーを追加したり、フェデレーション ユーザーとプレゼンス情報やインスタント メッセージを交換したり、音声通話やビデオ通話、会議にフェデレーション ユーザーを招待したりできます。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-p110">Deploying Edge Servers also enables you to <em>federate</em> with partner or vendor organizations. A federated relationship enables your users to put federated users on their Contacts lists, exchange presence information and instant messages with these users, and invite them to audio calls, video calls, and conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6c6b-143">モバイル クライアントのサポート</span><span class="sxs-lookup"><span data-stu-id="e6c6b-143">Mobile client support</span></span></p></td>
<td><p><span data-ttu-id="e6c6b-144">さらに、Lync Server mobility service では、サポートされている Apple iOS、Android、Windows Phone、または Nokia のモバイルデバイスを使用して Lync 機能にアクセスし、インスタントメッセージの送受信、連絡先の表示などのアクティビティを実行することができます。プレゼンスを表示します。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-144">Additionally, with Lync Server mobility services, your users can access Lync functionality when using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices and perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="e6c6b-145">また、クリックして会議に参加、勤務先から通話、同一番号接続、ボイス メール、不在着信など、モバイル デバイスでいくつかのエンタープライズ VoIP 機能がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-145">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="e6c6b-146">バックグラウンドで実行されるアプリケーションをサポートしないモバイル デバイス用にプッシュ通知もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-146">Push notifications are also supported for mobile devices that do not support applications running in the background.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6c6b-147">他の製品との統合</span><span class="sxs-lookup"><span data-stu-id="e6c6b-147">Integration with other products</span></span></p></td>
<td><p><span data-ttu-id="e6c6b-148">Lync Server は他のいくつかの製品と統合され、ユーザーと管理者にさらに利点を提供します。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-148">Lync Server integrates with several other products to provide additional benefits to your users and administrators.</span></span></p>
<p><span data-ttu-id="e6c6b-149">会議ツールは Outlook に統合されており、開催者は1回のクリックで会議のスケジュールを設定したり、即時会議を開始したり、出席者が簡単に参加できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-149">Meeting tools are integrated into Outlook to enable organizers to schedule a meeting or start an impromptu conference with a single click and make it just as easy for attendees to join.</span></span></p>
<p><span data-ttu-id="e6c6b-150">プレゼンス情報は、Outlook と SharePoint に統合されています。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-150">Presence information is integrated into Outlook and SharePoint.</span></span></p>
<p><span data-ttu-id="e6c6b-151">Exchange ユニファイド メッセージング (UM) では、いくつかの統合機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-151">Exchange Unified Messaging (UM) provides several integration features.</span></span> <span data-ttu-id="e6c6b-152">ユーザーは、Lync Server 内に新しいボイスメールがあるかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-152">Users can see if they have new voice mail within Lync Server.</span></span> <span data-ttu-id="e6c6b-153">Outlook メッセージ内の再生ボタンをクリックして音声ボイス メールを聞いたり、通知メッセージ内でボイス メールのトランスクリプションを表示したりできます。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-153">They can click a play button in the Outlook message to hear the audio voice mail, or view a transcription of the voice mail in the notification message.</span></span></p>
<p><span data-ttu-id="e6c6b-154">さらに、Exchange 2013 で Lync Server 2013 を実行すると、統合連絡先ストアのようないくつかの新機能が有効になります。これには、両方の製品のクライアントがアクセスできるようにすることも、2013 Exchange の管理データベースに格納されている連絡先の高解像度の写真を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-154">Additionally, running Lync Server 2013 with Exchange 2013 enables several new features such as a unified contact store which can be accessed by clients of both products, as well as high-resolution photos for contacts which are stored in the Exchange 2013 database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6c6b-155">簡単な展開</span><span class="sxs-lookup"><span data-stu-id="e6c6b-155">Simple deployment</span></span></p></td>
<td><p><span data-ttu-id="e6c6b-156">サーバーとクライアントの計画と展開に役立つように、Lync Server ではトポロジビルダーが提供されています。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-156">To help you plan and deploy your servers and clients, Lync Server provides the Topology Builder.</span></span></p>
<p><span data-ttu-id="e6c6b-157">トポロジビルダーは、Lync Server のインストールコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-157">Topology Builder is an installation component of Lync Server.</span></span> <span data-ttu-id="e6c6b-158">トポロジビルダーを使用して、計画したトポロジを作成、調整、および発行します。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-158">You use Topology Builder to create, adjust and publish your planned topology.</span></span> <span data-ttu-id="e6c6b-159">また、サーバーのインストールを開始する前にトポロジを検証します。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-159">It also validates your topology before you begin server installations.</span></span> <span data-ttu-id="e6c6b-160">個々のサーバーに Lync Server をインストールすると、インストールプログラムによってサーバーがトポロジ内に配置されたとおりに展開されます。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-160">When you install Lync Server on individual servers, the installation program deploys the server as directed in the topology.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6c6b-161">簡単な管理</span><span class="sxs-lookup"><span data-stu-id="e6c6b-161">Simple management</span></span></p></td>
<td><p><span data-ttu-id="e6c6b-162">Lync Server を展開した後、次のような強力で合理的な管理ツールが提供されます。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-162">After you deploy Lync Server, it offers the following powerful and streamlined management tools:</span></span></p>
<ul>
<li><p><span data-ttu-id="e6c6b-163">構成の集中管理。変更を集中管理して展開全体にすばやくレプリケートできます。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-163">Central configuration management, which enables you to manage changes centrally and have them replicated quickly to the entire deployment.</span></span></p></li>
<li><p><span data-ttu-id="e6c6b-164">Lync Server コントロールパネル。管理者向けの web ベースのグラフィカルユーザーインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-164">Lync Server Control Panel, a web-based graphical user interface for administrators.</span></span> <span data-ttu-id="e6c6b-165">この web ベースの UI を使用すると、Lync Server 管理者は、自分のコンピューターに特別な管理ソフトウェアがインストールされていなくても、企業ネットワーク上のあらゆる場所からシステムを管理できます。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-165">With this web-based UI, Lync Server administrators can manage their systems from anywhere on the corporate network, without needing specialized management software installed on their computers.</span></span></p></li>
<li><p><span data-ttu-id="e6c6b-166">Lync Server 管理シェルコマンドライン管理ツール。これは、Windows PowerShell コマンドラインインターフェイスに基づいています。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-166">Lync Server Management Shell command-line management tool, which is based on the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="e6c6b-167">製品のすべての側面を管理するための豊富なコマンドセットを提供し、Lync Server 管理者が使い慣れたツールを使用して繰り返しタスクを自動化できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-167">It provides a rich command set for administration of all aspects of the product, and enables Lync Server administrators to automate repetitive tasks using a familiar tool.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e6c6b-168">IM およびプレゼンスの機能はすべての Lync Server 展開に自動的にインストールされますが、会議、エンタープライズ Voip、リモートユーザーアクセスを展開するかどうかを選択して、展開を組織のニーズに合わせて調整することができます。</span><span class="sxs-lookup"><span data-stu-id="e6c6b-168">While the IM and presence features are automatically installed in every Lync Server deployment, you can choose whether to deploy conferencing, Enterprise Voice, and remote user access, to tailor your deployment to your organization’s needs.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e6c6b-169">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e6c6b-169">In This Section</span></span>

  - [<span data-ttu-id="e6c6b-170">Lync Server 2013 の IM およびプレゼンス</span><span class="sxs-lookup"><span data-stu-id="e6c6b-170">IM and presence in Lync Server 2013</span></span>](lync-server-2013-im-and-presence.md)

  - [<span data-ttu-id="e6c6b-171">Lync Server 2013 の会議</span><span class="sxs-lookup"><span data-stu-id="e6c6b-171">Conferencing in Lync Server 2013</span></span>](lync-server-2013-conferencing.md)

  - [<span data-ttu-id="e6c6b-172">Lync Server 2013 のエンタープライズ Voip</span><span class="sxs-lookup"><span data-stu-id="e6c6b-172">Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice.md)

  - [<span data-ttu-id="e6c6b-173">Lync Server 2013 を使用したスケーラビリティ</span><span class="sxs-lookup"><span data-stu-id="e6c6b-173">Scalability with Lync Server 2013</span></span>](lync-server-2013-scalability.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


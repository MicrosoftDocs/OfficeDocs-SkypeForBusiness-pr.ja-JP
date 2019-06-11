---
title: 'Lync Server 2013: 概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Introduction to Lync Server
ms:assetid: 99dd6b65-e591-421f-852b-ee9fe9588998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398795(v=OCS.15)
ms:contentKeyID: 48184885
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df182c8d58d6f1e60b164fbb28299945f6a8cba3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction-to-lync-server-2013"></a><span data-ttu-id="83564-102">Lync Server 2013 の概要</span><span class="sxs-lookup"><span data-stu-id="83564-102">Introduction to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83564-103">_**最終更新日:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="83564-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="83564-104">Lync Server 2013 と、Lync 2013 などのクライアントソフトウェアを使用すると、ユーザーは新しい方法で接続し、物理的な場所に関係なく接続を維持することができます。</span><span class="sxs-lookup"><span data-stu-id="83564-104">Lync Server 2013 and its client software, such as Lync 2013, enable your users to connect in new ways and to stay connected, regardless of their physical location.</span></span> <span data-ttu-id="83564-105">Lync と Lync Server は、単一のクライアントインターフェイスでコミュニケーションを行い、統一されたプラットフォームとして展開し、単一の管理インフラストラクチャで管理するさまざまな方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="83564-105">Lync and Lync Server bring together the different ways that people communicate in a single client interface, are deployed as a unified platform, and are administered through a single management infrastructure.</span></span>

<span data-ttu-id="83564-106">この表と次のセクションでは、Lync Server でユーザーに提供される主な機能セットまたは*ワークロード*について説明します。</span><span class="sxs-lookup"><span data-stu-id="83564-106">This table and the following sections illustrate the major feature sets, or *workloads*, that Lync Server provides for your users.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83564-107">よる</span><span class="sxs-lookup"><span data-stu-id="83564-107">Workload</span></span></th>
<th><span data-ttu-id="83564-108">説明</span><span class="sxs-lookup"><span data-stu-id="83564-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83564-109">IM とプレゼンス</span><span class="sxs-lookup"><span data-stu-id="83564-109">IM and presence</span></span></p></td>
<td><p><span data-ttu-id="83564-110">インスタントメッセージング (IM) とプレゼンスを使用すると、ユーザーは簡単かつ効率的に相互に検索してコミュニケーションを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="83564-110">Instant messaging (IM) and presence help your users find and communicate with one another efficiently and effectively.</span></span></p>
<p><span data-ttu-id="83564-111">IM は、会話履歴を含むインスタントメッセージングプラットフォームであり、MSN、Windows Live、Yahoo!、AOL、Google Talk などのパブリック IM ネットワークのユーザーとのパブリック IM 接続をサポートします。</span><span class="sxs-lookup"><span data-stu-id="83564-111">IM provides an instant messaging platform with conversation history, and supports public IM connectivity with users of public IM networks such as MSN/Windows Live, Yahoo!, AOL, and Google Talk.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="83564-112">2012年9月1日以降、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規または更新契約の購入に使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="83564-112">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="83564-113">アクティブなライセンスを持っているお客様は、Yahoo! とのフェデレーションを継続できます。</span><span class="sxs-lookup"><span data-stu-id="83564-113">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="83564-114">サービスが終了するまでの Messenger。</span><span class="sxs-lookup"><span data-stu-id="83564-114">Messenger until the service shut down date.</span></span> <span data-ttu-id="83564-115">AOL および Yahoo! の2014年6月の終了日</span><span class="sxs-lookup"><span data-stu-id="83564-115">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="83564-116">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="83564-116">has been announced.</span></span> <span data-ttu-id="83564-117">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83564-117">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="83564-118">PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要な1か月あたりのユーザーごとのサブスクリプションライセンスです。</span><span class="sxs-lookup"><span data-stu-id="83564-118">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="83564-119">Messenger.</span><span class="sxs-lookup"><span data-stu-id="83564-119">Messenger.</span></span> <span data-ttu-id="83564-120">このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートによって決定されたものであり、その基となる契約は "巻停止" となります。</span><span class="sxs-lookup"><span data-stu-id="83564-120">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="83564-121">Lync は、組織間、および世界各地の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="83564-121">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="83564-122">Windows Live Messenger とのフェデレーションには、Lync 標準 CAL 以外の追加のユーザー/デバイスライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="83564-122">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="83564-123">Skype federation はこのリストに追加されます。 Lync ユーザーは、IM と音声を使用して、数百人の何百万ものユーザーに連絡できます。</span><span class="sxs-lookup"><span data-stu-id="83564-123">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div>
<p><span data-ttu-id="83564-124">プレゼンスは、ユーザーの個人の空き時間情報を設定して表示し、連絡<strong>可能</strong>か<strong>取り込み中</strong>などの一般的な状態を使用して通信を<strong></strong>指示します<strong></strong>.</span><span class="sxs-lookup"><span data-stu-id="83564-124">Presence establishes and displays a user’s personal availability and willingness to communicate through the use of common states such as <strong>Available</strong> or <strong>Busy</strong>, as well as more detailed states such as <strong>Be Right Back</strong> and <strong>Do Not Disturb</strong>.</span></span> <span data-ttu-id="83564-125">この豊富なプレゼンス情報を使うと、他のユーザーがすぐに連絡を選択できるようになります。</span><span class="sxs-lookup"><span data-stu-id="83564-125">This rich presence information enables other users to immediately make effective communication choices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83564-126">会議</span><span class="sxs-lookup"><span data-stu-id="83564-126">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="83564-127">Lync Server には、スケジュールされた会議と一時的会議の両方について、IM 会議、電話会議、web 会議、ビデオ会議、およびアプリケーション共有がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="83564-127">Lync Server includes support for IM conferencing, audio conferencing, web conferencing, video conferencing, and application sharing, for both scheduled and impromptu meetings.</span></span> <span data-ttu-id="83564-128">これらすべての種類の会議は、1つのクライアントでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="83564-128">All these meeting types are supported with a single client.</span></span> <span data-ttu-id="83564-129">Lync Server は、ダイヤルイン会議もサポートしているため、公衆交換電話網 (PSTN) の電話機のユーザーは、会議のオーディオ部分に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="83564-129">Lync Server also supports dial-in conferencing so that users of public switched telephone network (PSTN) phones can participate in the audio portion of conferences.</span></span></p>
<p><span data-ttu-id="83564-130">会議はリアルタイムでシームレスに変更され、増加する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="83564-130">Conferences can seamlessly change and grow in real time.</span></span> <span data-ttu-id="83564-131">たとえば、1人の会議を、少数のユーザー間でインスタントメッセージとして開始したり、デスクトップ共有を使用して音声会議に参加したり、会話フローを中断することなく、すばやく簡単に会話を始めたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="83564-131">For example, a single conference can start as just instant messages between a few users, and escalate to an audio conference with desktop sharing and a larger audience instantly, easily, and without interrupting the conversation flow.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83564-132">エンタープライズ VoIP</span><span class="sxs-lookup"><span data-stu-id="83564-132">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="83564-133">[<em>エンタープライズボイス</em>] は、Lync Server での Voip (Voice Over Internet Protocol) サービスです。</span><span class="sxs-lookup"><span data-stu-id="83564-133"><em>Enterprise Voice</em> is the Voice over Internet Protocol (VoIP) offering in Lync Server.</span></span> <span data-ttu-id="83564-134">従来の構内交換 (PBX) システムを拡張または交換するためのボイスオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="83564-134">It delivers a voice option to enhance or replace traditional private branch exchange (PBX) systems.</span></span> <span data-ttu-id="83564-135">エンタープライズボイスは、IP PBX の完全なテレフォニー機能に加えて、リッチプレゼンス、IM、共同作業、会議に統合されています。</span><span class="sxs-lookup"><span data-stu-id="83564-135">In addition to the complete telephony capabilities of an IP PBX, Enterprise Voice is integrated with rich presence, IM, collaboration, and meetings.</span></span> <span data-ttu-id="83564-136">通話の応答、保留、再開、転送、転送、転送すればなどの機能は直接サポートされますが、パーソナライズされた短縮ダイヤルキーは連絡先リストに置き換えられ、自動機能付きインターコムは IM に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="83564-136">Features such as call answer, hold, resume, transfer, forward and divert are supported directly, while personalized speed dialing keys are replaced by Contacts lists, and automatic intercom is replaced with IM.</span></span></p>
<p><span data-ttu-id="83564-137">エンタープライズボイスは、通話受付制御 (CAC)、支店の office survivability、およびデータの復元の拡張オプションを通じて高可用性をサポートします。</span><span class="sxs-lookup"><span data-stu-id="83564-137">Enterprise Voice supports high availability through call admission control (CAC), branch office survivability, and extended options for data resiliency.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83564-138">リモートユーザー向けのサポート</span><span class="sxs-lookup"><span data-stu-id="83564-138">Support for remote users</span></span></p></td>
<td><p><span data-ttu-id="83564-139">このようなリモートユーザーへの接続を提供するために、サーバーを<em>エッジサーバー</em>として展開することで、現在組織外のユーザーに対して Lync Server の完全な機能を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="83564-139">You can provide full Lync Server functionality for users who are currently outside your organization’s firewalls by deploying servers called <em>Edge Servers</em> to provide a connection for these remote users.</span></span> <span data-ttu-id="83564-140">これらのリモートユーザーは、Lync 2013 がインストールされているパーソナルコンピューター、電話、または web インターフェイスを使用して、会議に接続できます。</span><span class="sxs-lookup"><span data-stu-id="83564-140">These remote users can connect to conferences by using a personal computer with Lync 2013 installed, the phone, or a web interface.</span></span></p>
<p><span data-ttu-id="83564-141">エッジサーバーを展開すると、パートナー組織やベンダー組織と<em>フェデレーション</em>を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="83564-141">Deploying Edge Servers also enables you to <em>federate</em> with partner or vendor organizations.</span></span> <span data-ttu-id="83564-142">フェデレーション関係により、ユーザーはフェデレーションされたユーザーを連絡先リストに配置し、プレゼンス情報やインスタントメッセージをこれらのユーザーとやり取りして、音声通話、ビデオ通話、会議に招待することができます。</span><span class="sxs-lookup"><span data-stu-id="83564-142">A federated relationship enables your users to put federated users on their Contacts lists, exchange presence information and instant messages with these users, and invite them to audio calls, video calls, and conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83564-143">モバイルクライアントのサポート</span><span class="sxs-lookup"><span data-stu-id="83564-143">Mobile client support</span></span></p></td>
<td><p><span data-ttu-id="83564-144">さらに、Lync Server mobility services を使用すると、サポートされている Apple iOS、Android、Windows Phone、Nokia モバイルデバイスを使って Lync 機能にアクセスしたり、インスタントメッセージの送受信、連絡先の表示などの操作を実行したりすることができます。プレゼンスを表示します。</span><span class="sxs-lookup"><span data-stu-id="83564-144">Additionally, with Lync Server mobility services, your users can access Lync functionality when using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices and perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="83564-145">さらに、モバイルデバイスでは、クリックして電話会議に参加したり、勤務先の電話による通話、ボイスメール、不在着信など、一部のエンタープライズ音声機能をサポートしたりします。</span><span class="sxs-lookup"><span data-stu-id="83564-145">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="83564-146">プッシュ通知は、バックグラウンドで実行されているアプリケーションをサポートしていないモバイルデバイスでもサポートされます。</span><span class="sxs-lookup"><span data-stu-id="83564-146">Push notifications are also supported for mobile devices that do not support applications running in the background.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83564-147">他の製品との統合</span><span class="sxs-lookup"><span data-stu-id="83564-147">Integration with other products</span></span></p></td>
<td><p><span data-ttu-id="83564-148">Lync Server は、他のいくつかの製品と統合され、ユーザーと管理者にとってさらに利点をもたらします。</span><span class="sxs-lookup"><span data-stu-id="83564-148">Lync Server integrates with several other products to provide additional benefits to your users and administrators.</span></span></p>
<p><span data-ttu-id="83564-149">会議ツールは Outlook に統合されているため、開催者は1回のクリックで会議のスケジュールを設定したり、一時的な会議を開始したりできます。これにより、出席者が簡単に参加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="83564-149">Meeting tools are integrated into Outlook to enable organizers to schedule a meeting or start an impromptu conference with a single click and make it just as easy for attendees to join.</span></span></p>
<p><span data-ttu-id="83564-150">プレゼンス情報は Outlook と SharePoint に統合されています。</span><span class="sxs-lookup"><span data-stu-id="83564-150">Presence information is integrated into Outlook and SharePoint.</span></span></p>
<p><span data-ttu-id="83564-151">Exchange ユニファイドメッセージング (UM) には、複数の統合機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="83564-151">Exchange Unified Messaging (UM) provides several integration features.</span></span> <span data-ttu-id="83564-152">ユーザーは、Lync Server 内に新しいボイスメールがあるかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="83564-152">Users can see if they have new voice mail within Lync Server.</span></span> <span data-ttu-id="83564-153">Outlook メッセージの再生ボタンをクリックすると、音声のボイスメールを聞くことができます。また、通知メッセージのボイスメールの議事録を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="83564-153">They can click a play button in the Outlook message to hear the audio voice mail, or view a transcription of the voice mail in the notification message.</span></span></p>
<p><span data-ttu-id="83564-154">さらに、Exchange 2013 で Lync Server 2013 を実行すると、両方の製品のクライアントからアクセスできる統合連絡先ストア、および Exchange 2013 データベースに保存されている連絡先の高解像度写真など、いくつかの新機能が有効になります。</span><span class="sxs-lookup"><span data-stu-id="83564-154">Additionally, running Lync Server 2013 with Exchange 2013 enables several new features such as a unified contact store which can be accessed by clients of both products, as well as high-resolution photos for contacts which are stored in the Exchange 2013 database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83564-155">簡単な展開</span><span class="sxs-lookup"><span data-stu-id="83564-155">Simple deployment</span></span></p></td>
<td><p><span data-ttu-id="83564-156">サーバーとクライアントを計画して展開するために、Lync Server によってトポロジビルダーが提供されます。</span><span class="sxs-lookup"><span data-stu-id="83564-156">To help you plan and deploy your servers and clients, Lync Server provides the Topology Builder.</span></span></p>
<p><span data-ttu-id="83564-157">トポロジビルダーは、Lync Server のインストールコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="83564-157">Topology Builder is an installation component of Lync Server.</span></span> <span data-ttu-id="83564-158">トポロジビルダーを使用して、計画されたトポロジを作成、調整、公開します。</span><span class="sxs-lookup"><span data-stu-id="83564-158">You use Topology Builder to create, adjust and publish your planned topology.</span></span> <span data-ttu-id="83564-159">また、サーバーのインストールを開始する前にトポロジを検証することもできます。</span><span class="sxs-lookup"><span data-stu-id="83564-159">It also validates your topology before you begin server installations.</span></span> <span data-ttu-id="83564-160">個々のサーバーに Lync Server をインストールすると、インストールプログラムによって、トポロジで指示されたとおりにサーバーが展開されます。</span><span class="sxs-lookup"><span data-stu-id="83564-160">When you install Lync Server on individual servers, the installation program deploys the server as directed in the topology.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83564-161">簡単な管理</span><span class="sxs-lookup"><span data-stu-id="83564-161">Simple management</span></span></p></td>
<td><p><span data-ttu-id="83564-162">Lync Server を展開すると、次のような強力で合理化された管理ツールが提供されます。</span><span class="sxs-lookup"><span data-stu-id="83564-162">After you deploy Lync Server, it offers the following powerful and streamlined management tools:</span></span></p>
<ul>
<li><p><span data-ttu-id="83564-163">一元的な構成管理: 変更を一元的に管理し、展開全体に迅速に複製することができます。</span><span class="sxs-lookup"><span data-stu-id="83564-163">Central configuration management, which enables you to manage changes centrally and have them replicated quickly to the entire deployment.</span></span></p></li>
<li><p><span data-ttu-id="83564-164">Lync Server コントロールパネル。管理者向けの web ベースのグラフィカルユーザーインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="83564-164">Lync Server Control Panel, a web-based graphical user interface for administrators.</span></span> <span data-ttu-id="83564-165">この web ベースの UI を使用すると、Lync Server 管理者は、専用の管理ソフトウェアがコンピューターにインストールされていなくても、企業ネットワーク上の任意の場所からシステムを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="83564-165">With this web-based UI, Lync Server administrators can manage their systems from anywhere on the corporate network, without needing specialized management software installed on their computers.</span></span></p></li>
<li><p><span data-ttu-id="83564-166">Lync Server 管理シェルコマンドライン管理ツール。これは、Windows PowerShell コマンドラインインターフェイスに基づいています。</span><span class="sxs-lookup"><span data-stu-id="83564-166">Lync Server Management Shell command-line management tool, which is based on the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="83564-167">製品のすべての要素を管理するための豊富なコマンドセットを提供します。また、Lync Server の管理者が、使い慣れたツールを使用して繰り返し行うタスクを自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="83564-167">It provides a rich command set for administration of all aspects of the product, and enables Lync Server administrators to automate repetitive tasks using a familiar tool.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="83564-168">IM とプレゼンス機能は、すべての Lync Server 展開に自動的にインストールされますが、会議、エンタープライズ Voip、リモートユーザーアクセスを展開して、組織のニーズに合わせて展開するかどうかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="83564-168">While the IM and presence features are automatically installed in every Lync Server deployment, you can choose whether to deploy conferencing, Enterprise Voice, and remote user access, to tailor your deployment to your organization’s needs.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="83564-169">このセクション中</span><span class="sxs-lookup"><span data-stu-id="83564-169">In This Section</span></span>

  - [<span data-ttu-id="83564-170">Lync Server 2013 IM とプレゼンス</span><span class="sxs-lookup"><span data-stu-id="83564-170">IM and presence in Lync Server 2013</span></span>](lync-server-2013-im-and-presence.md)

  - [<span data-ttu-id="83564-171">Lync Server 2013 電話会議</span><span class="sxs-lookup"><span data-stu-id="83564-171">Conferencing in Lync Server 2013</span></span>](lync-server-2013-conferencing.md)

  - [<span data-ttu-id="83564-172">Lync Server 2013 のエンタープライズ VoIP</span><span class="sxs-lookup"><span data-stu-id="83564-172">Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice.md)

  - [<span data-ttu-id="83564-173">Lync Server 2013 のスケーラビリティ</span><span class="sxs-lookup"><span data-stu-id="83564-173">Scalability with Lync Server 2013</span></span>](lync-server-2013-scalability.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


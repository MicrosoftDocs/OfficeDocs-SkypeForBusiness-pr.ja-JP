---
title: Lync Server 2013 会議
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing
ms:assetid: 6129b7e0-9abd-488e-a54e-86094eb9df7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417161(v=OCS.15)
ms:contentKeyID: 48184274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25c015397b1c29bec50f05feeab4f21d54d3f1e5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencing-in-lync-server-2013"></a><span data-ttu-id="2b6b2-102">Lync Server 2013 の会議</span><span class="sxs-lookup"><span data-stu-id="2b6b2-102">Conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b6b2-103">_**トピックの最終更新日:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="2b6b2-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="2b6b2-104">Lync Server 2013 で統合された会議を使用すると、ユーザーは共同作業を行ったり、情報を共有したり、リアルタイムでの作業を調整したりできます。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-104">With unified conferencing in Lync Server 2013, users can collaborate, share information, and coordinate their efforts in real time.</span></span> <span data-ttu-id="2b6b2-105">すべてのユーザーは、自発的なコラボレーション、予約された会議、および会議ツールを幅広く使用できます。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-105">All your users can use the full breadth of spontaneous collaboration, scheduled meetings, and meeting tools.</span></span> <span data-ttu-id="2b6b2-106">音声およびビデオ会議機能は、インターネット接続のある任意の場所から使用できます。また、コンピューター外のユーザーは公衆交換電話網 (PSTN) 電話を使用してダイヤルインすることによって、電話会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-106">Voice and video conferencing capabilities can be used from any location with an Internet connection, and users away from a computer can participate in audio conferences by dialing in with a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="2b6b2-107">Outlook に統合された会議ツールを使用すると、開催者は1回のクリックで会議のスケジュールを設定したり、即時会議を開始したり、出席者が簡単に参加できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-107">Meeting tools integrated into Outlook enable organizers to schedule a meeting or start an impromptu conference with a single click, and also make it just as easy for attendees to join.</span></span> <span data-ttu-id="2b6b2-108">Web クライアントは、デスクトップ版の Lync を実行していない参加者に対して豊富な会議機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-108">A web client extends rich conference features to participants who are not running the desktop version of Lync.</span></span>

<div>

## <a name="audio-and-video-conferencing"></a><span data-ttu-id="2b6b2-109">音声ビデオ会議</span><span class="sxs-lookup"><span data-stu-id="2b6b2-109">Audio and Video Conferencing</span></span>

<span data-ttu-id="2b6b2-110">Lync Server は、タッチトーン呼び出し制御コマンドを使用した PSTN ダイヤルインサービスなど、従来のオーディオブリッジサービスのユーザーになじみのあるユーザー操作を提供します。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-110">Lync Server provides a user experience that is familiar to users of traditional audio bridge services including PSTN dial-in services with touch-tone call control commands.</span></span> <span data-ttu-id="2b6b2-111">同時に、一体型の統合コミュニケーション プラットフォームならではの強力なスケジュール機能、参加処理機能、および管理機能を備えています。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-111">At the same time, it incorporates powerful scheduling, joining, and management features available only with an integrated unified communications platform.</span></span>

<span data-ttu-id="2b6b2-112">1回のクリックで、ユーザーは Outlook から会議をスケジュールすることができます。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-112">With a single click, users can schedule a meeting from Outlook.</span></span> <span data-ttu-id="2b6b2-113">会議時間、場所、出席者などの詳細については、使い慣れた Outlook テンプレートに従います。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-113">Details, such as meeting time, location, and attendees, follow the familiar Outlook template.</span></span> <span data-ttu-id="2b6b2-114">また、ダイヤルイン番号、会議 ID、暗証番号 (PIN) のアラームといった電話会議特有の情報は自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-114">Additionally, conference call-specific information, such as dial-in number, meeting IDs, and personal identification number (PIN) reminders, are automatically populated.</span></span>

<span data-ttu-id="2b6b2-115">承認されたユーザーのみが通話に参加できるようにするために、Lync Server は参加者に対して複数レベルの認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-115">To help ensure that only the authorized people participate in a call, Lync Server provides multiple levels of authentication for participants.</span></span> <span data-ttu-id="2b6b2-116">Lync を使用して参加しているユーザーは、Active Directory ドメインサービスによって既に認証されており、PIN、パスコード、または会議 ID を入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-116">Users who join by using Lync are already authenticated by the Active Directory Domain Services and do not need to enter a PIN, pass code, or meeting ID.</span></span>

<span data-ttu-id="2b6b2-117">Lync はビデオを統合クライアントに組み込むことでビデオ会議のユーザーの操作性を簡素化します。これにより、ビデオとの会議のスケジュールをシームレスかつ簡単にすることができます。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-117">Lync simplifies the video conferencing user experience by incorporating video into the unified client so that scheduling a meeting with video or escalating to video spontaneously is seamless and easy.</span></span>

<span data-ttu-id="2b6b2-118">Lync Server を使用すると、1回のクリックでビデオを標準の通話に簡単に追加できます。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-118">Lync Server makes it easy to add video to a standard phone call in just one click.</span></span> <span data-ttu-id="2b6b2-119">複数のユーザーが参加しているビデオ通話や会議では、それぞれのユーザーは最大で他の 5 人のユーザーからのビデオを同時に表示することができ、プレゼンターは 1 つのビデオ ソースのみをすべての参加者に表示するよう選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-119">When there are multiple participants in a video call or a conference, each user can see video from up to five other users simultaneously, or a presenter can choose just one video source to be seen exclusively by everyone.</span></span>

<span data-ttu-id="2b6b2-120">高解像度ビデオ (解像度 1270 x 720、縦横比 16:9) および VGA ビデオ (解像度 640 x 480、縦横比 4:3) は、ハイエンドコンピューターで Lync を実行しているユーザー間のピアツーピア通話でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-120">High-definition video (resolution 1270 x 720; aspect ratio 16:9) and VGA video (resolution 640 x 480; aspect ratio 4:3) are supported for peer-to-peer calls between users running Lync on high-end computers.</span></span> <span data-ttu-id="2b6b2-121">同一会話内の各参加者の表示解像度は、個々のユーザーのハードウェアのビデオ性能によって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-121">The resolution viewed by each participant in a single conversation may differ, depending on the video capabilities of each user’s respective hardware.</span></span>

<span data-ttu-id="2b6b2-p108">IT 管理者はポリシーを設定して、コンピューターの性能やネットワーク帯域幅、所要解像度を提供可能なカメラの有無に合わせて、HD ビデオや VGA ビデオをクライアントで制限または無効化できます。 これらのポリシーは、インバンド プロビジョニングを通じて適用されます。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-p108">IT administrators can set policies to restrict or disable high-definition or VGA video on clients, depending on computer capability, network bandwidth, and the presence of a camera able to deliver the required resolution. These policies are enforced through in-band provisioning.</span></span>

</div>

<div>

## <a name="web-conferencing"></a><span data-ttu-id="2b6b2-124">Web 会議</span><span class="sxs-lookup"><span data-stu-id="2b6b2-124">Web conferencing</span></span>

<span data-ttu-id="2b6b2-125">Lync Server は、デスクトップ、アプリケーション、添付ファイル、ホワイトボード、投票、PowerPoint などの会議の共有機能を合理化された Lync に統合します。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-125">Lync Server integrates conferencing sharing features such as desktop, application, attachment, whiteboard, poll and PowerPoint into the streamlined Lync.</span></span> <span data-ttu-id="2b6b2-126">音声ビデオ会議と組み合わせることで臨場感の高い協調的なセッションを実施でき、進行が容易になります。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-126">Combined with audio or video conferencing, the result is a highly immersive and collaborative session that is simple to facilitate.</span></span>

<span data-ttu-id="2b6b2-127">PowerPoint プレゼンテーションを表示または表示するユーザーの全体的な操作を改善するために、Lync Server 2013 は Office Web Apps を採用して PowerPoint プレゼンテーションを処理します。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-127">To improve the overall experience of users presenting or viewing PowerPoint presentations, Lync Server 2013 employs Office Web Apps to handle PowerPoint presentations.</span></span> <span data-ttu-id="2b6b2-128">ユーザーは、Lync 会議のホワイトボードを使用して、画像を共有したり、テキストをコピーして貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-128">Users can share a picture or copy and paste text using a Whiteboard in the Lync meeting.</span></span> <span data-ttu-id="2b6b2-129">発表者は、Lync 会議で投票を実施して、出席者からのフィードバックを集めることができます。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-129">Presenters can conduct polls in the Lync meeting to solicit feedback from the attendees.</span></span>

<span data-ttu-id="2b6b2-130">デスクトップ共有によって、発表者は、すべてのビジュアル、アプリケーション、web ページ、ドキュメント、ソフトウェア、またはデスクトップの一部を、Lync からリアルタイムでリモート参加者にブロードキャストできます。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-130">Desktop sharing enables presenters to broadcast any visuals, applications, webpages, documents, software, or part of their desktops to remote participants in real time, right from Lync.</span></span> <span data-ttu-id="2b6b2-131">参加メンバーはマウスの動きやキーボードの入力をそのまま追うことができます。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-131">Audience members can follow along with mouse movements and keyboard input.</span></span> <span data-ttu-id="2b6b2-132">発表者は画面全体を共有するか一部のみを共有するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-132">Presenters can choose to share the entire screen or only a portion.</span></span> <span data-ttu-id="2b6b2-133">発表者はデスクトップを共有することにより、場所を問わず、参加者に対してインタラクティブな製品デモやソフトウェア デモを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-133">By sharing their desktops, presenters are able to engage with their audiences in interactive product or software demos from any location.</span></span>

<span data-ttu-id="2b6b2-p112">アプリケーション共有では、発表者が参加者の反応やテキスト メッセージによる質問を見逃すことなく、デスクトップ上のソフトウェアの制御を共有できます。 発表者はアプリケーションの制御を会議の参加者に任せることもできます。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-p112">Application sharing enables presenters to share control of software on their desktops without losing sight of participant feedback or text questions. Presenters can also delegate control of the application to meeting participants.</span></span>

</div>

<div>

## <a name="dial-in-conferencing"></a><span data-ttu-id="2b6b2-136">ダイヤルイン会議</span><span class="sxs-lookup"><span data-stu-id="2b6b2-136">Dial-in Conferencing</span></span>

<span data-ttu-id="2b6b2-137">パーソナルコンピューターを使用していないユーザーの場合は、Lync Server の電話会議に参加するために使用できるいくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-137">For users that are not using a personal computer, there are several methods available for joining a Lync Server conference call.</span></span> <span data-ttu-id="2b6b2-138">PSTN ユーザーの場合、アクセス番号をダイヤルして会議ブリッジにアクセスし、会議 ID を入力することができます。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-138">A PSTN user can dial an access number, access the meeting bridge, and then enter the meeting ID.</span></span> <span data-ttu-id="2b6b2-139">さらにセキュリティの高い会議の場合、ユーザーに PIN の入力を求め、Active Directory に対する認証を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-139">For more secure meetings, the user can also be required to enter his or her PIN to authenticate against Active Directory.</span></span> <span data-ttu-id="2b6b2-140">Lync Server は、Lync Phone Edition デバイスもサポートします。これは、Microsoft パートナーによって提供されるスタンドアロンの IP 電話デバイスです。</span><span class="sxs-lookup"><span data-stu-id="2b6b2-140">Lync Server also supports Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


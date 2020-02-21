---
title: 'Lync Server 2013: クライアント向けの新機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: What's new for clients
ms:assetid: 5c144677-4d58-4fc3-8445-74b76c9fcf07
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204933(v=OCS.15)
ms:contentKeyID: 48184253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc8ea4abd3608863dea1bf914f5d89cc0ad43fae
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="whats-new-for-clients-in-lync-server-2013"></a><span data-ttu-id="b2540-102">Lync Server 2013 のクライアントの新機能</span><span class="sxs-lookup"><span data-stu-id="b2540-102">What's new for clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2540-103">_**トピックの最終更新日:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="b2540-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="b2540-104">Microsoft Lync 2013 には、再設計されたユーザーインターフェイスと重要な新機能があります。</span><span class="sxs-lookup"><span data-stu-id="b2540-104">Microsoft Lync 2013 has a redesigned user interface and important new features.</span></span> <span data-ttu-id="b2540-105">管理者は、office のセットアッププログラムにクライアントを組み込み、組織での Office の展開とクライアントのカスタマイズをより効率的に行う方法を提供するようになりました。</span><span class="sxs-lookup"><span data-stu-id="b2540-105">For administrators, the client is now included with the Office setup program, providing a more streamlined approach to deploying Office and customizing clients in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b2540-106">Lync 2013 ユーザーインターフェイスの更新の図は、「Lync 2013 の新機能」を参照して<A href="https://go.microsoft.com/fwlink/?linkid=273885">https://go.microsoft.com/fwlink/?LinkId=273885</A>ください。</span><span class="sxs-lookup"><span data-stu-id="b2540-106">For an illustrated view of Lync 2013 user interface updates, see “What’s New in Lync 2013” at <A href="https://go.microsoft.com/fwlink/?linkid=273885">https://go.microsoft.com/fwlink/?LinkId=273885</A>.</span></span>



</div>

<div>

## <a name="integration-with-office-setup"></a><span data-ttu-id="b2540-107">Office セットアップとの統合</span><span class="sxs-lookup"><span data-stu-id="b2540-107">Integration with Office Setup</span></span>

<span data-ttu-id="b2540-108">Outlook メッセージングおよびコラボレーションクライアント内から会議管理をサポートする Lync 2013 クライアントおよび Lync 2013 用オンラインミーティングアドインは、両方とも Office 2013 セットアッププログラムに含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b2540-108">The Lync 2013 client and the Online Meeting Add-in for Lync 2013—which supports meeting management from within the Outlook messaging and collaboration client—are now both included with the Office 2013 Setup program.</span></span>

<span data-ttu-id="b2540-109">以前のバージョンの Lync および Office Communicator では、Windows インストーラーのプロパティを使用して Office のインストールをカスタマイズおよび制御できました。</span><span class="sxs-lookup"><span data-stu-id="b2540-109">In previous versions of Lync and Office Communicator, you could use Windows Installer properties to customize and control the Office installation.</span></span> <span data-ttu-id="b2540-110">Lync 2013 は Office セットアップと統合されているため、次の方法を使用して Lync 2013 セットアップをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="b2540-110">Because Lync 2013 is integrated with Office setup, you can use the following methods to customize Lync 2013 setup:</span></span>

  - <span data-ttu-id="b2540-111">Office カスタマイズ ツール (OCT) を使用する</span><span class="sxs-lookup"><span data-stu-id="b2540-111">Use the Office Customization Tool (OCT)</span></span>

  - <span data-ttu-id="b2540-112">Config.xml を使用してインストール タスクを実行する</span><span class="sxs-lookup"><span data-stu-id="b2540-112">Use the Config.xml to perform installation tasks</span></span>

  - <span data-ttu-id="b2540-113">セットアップ コマンド ライン オプションを使用する</span><span class="sxs-lookup"><span data-stu-id="b2540-113">Use Setup Command-Line Options</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b2540-114">Lync 2013 セットアッププログラムを実行しても、以前のバージョンの Lync または Office Communicator はアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="b2540-114">The Lync 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="b2540-115">Lync 2013 クライアントは、他の Lync または Office Communicator クライアントと共存してインストールします。</span><span class="sxs-lookup"><span data-stu-id="b2540-115">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span>



</div>

<span data-ttu-id="b2540-116">詳細については、「lync [Server での lync クライアントの展開 2013](lync-server-2013-deploying-lync-clients.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2540-116">For details, see [Deploying Lync clients in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span></span>

</div>

<div>

## <a name="group-policy-deployment"></a><span data-ttu-id="b2540-117">グループ ポリシーの展開</span><span class="sxs-lookup"><span data-stu-id="b2540-117">Group Policy Deployment</span></span>

<span data-ttu-id="b2540-118">Lync 2013 が Office セットアップに含まれるようになったため、Lync グループポリシー設定を展開する方法が変更されました。</span><span class="sxs-lookup"><span data-stu-id="b2540-118">Because Lync 2013 is now included in Office setup, the method for deploying Lync Group Policy settings has changed.</span></span> <span data-ttu-id="b2540-119">以前のバージョンの Lync および Office Communicator では、Communicator を使用してグループポリシー設定を定義することができましたが、Lync 2013 では、Office グループポリシーと共に提供される Lync ADMX および ADML 管理テンプレートを使用できます。管理用テンプレート。</span><span class="sxs-lookup"><span data-stu-id="b2540-119">In previous versions of Lync and Office Communicator, you could use the Communicator.adm to define Group Policy settings, whereas in Lync 2013 you can now use the Lync ADMX and ADML administrative templates that are provided along with the Office Group Policy Administrative Templates.</span></span>

<span data-ttu-id="b2540-120">詳細については、「[グループポリシーの設定 (Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2540-120">For details, see [Group Policy settings for Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span></span>

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a><span data-ttu-id="b2540-121">Outlook スケジュール アドインの更新</span><span class="sxs-lookup"><span data-stu-id="b2540-121">Outlook Scheduling Add-in Updates</span></span>

<span data-ttu-id="b2540-122">Lync 2013 用のオンラインミーティングアドインには、会議出席依頼のカスタマイズと新しい会議のオプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b2540-122">The Online Meeting Add-in for Lync 2013 includes meeting invite customization and new meeting options.</span></span>

  - <span data-ttu-id="b2540-123">管理者は、カスタム ロゴ、サポートの URL、法的免責事項の URL、またはカスタム フッター テキストを追加して、組織の会議の招待をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="b2540-123">Administrators can customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span> <span data-ttu-id="b2540-124">詳細については、「 [Lync Server 2013 でのオンラインミーティングアドインのカスタマイズ](lync-server-2013-customizing-the-online-meeting-add-in.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2540-124">For details, see [Customizing the Online Meeting Add-in in Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span></span>

  - <span data-ttu-id="b2540-125">新しい参加者ミュート制御により、会議の開催者は参加者の音声とビデオが既定でミュートされた会議をスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="b2540-125">New attendee mute controls allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span>

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a><span data-ttu-id="b2540-126">仮想デスクトップ インフラストラクチャ プラグイン</span><span class="sxs-lookup"><span data-stu-id="b2540-126">Virtual Desktop Infrastructure Plug-in</span></span>

<span data-ttu-id="b2540-127">Lync 2013 クライアントは、仮想デスクトップインフラストラクチャ (VDI) 環境で音声とビデオをサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="b2540-127">The Lync 2013 client now supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="b2540-128">ユーザーは音声またはビデオ デバイス (ヘッドセットやカメラなど) をローカル コンピューター (シン クライアントや異なる目的に使用されていたコンピューターなど) に接続できます。</span><span class="sxs-lookup"><span data-stu-id="b2540-128">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="b2540-129">ユーザーは、仮想マシンに接続して、仮想マシン上で実行されている Lync 2013 クライアントにサインインし、クライアントがローカルで実行している場合と同様に、リアルタイムの音声およびビデオ通信に参加できます。</span><span class="sxs-lookup"><span data-stu-id="b2540-129">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communication as though the client is running locally.</span></span> <span data-ttu-id="b2540-130">仮想デスクトップ環境では、次の機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b2540-130">The following features are supported in a virtual desktop environment:</span></span>

  - <span data-ttu-id="b2540-131">音声とビデオのデバイス統合。これには次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="b2540-131">Device integration for audio and video, including the following:</span></span>
    
      - <span data-ttu-id="b2540-132">デバイスからの通話コントロール</span><span class="sxs-lookup"><span data-stu-id="b2540-132">Call controls from the device</span></span>
    
      - <span data-ttu-id="b2540-133">デバイス上でのプレゼンス統合</span><span class="sxs-lookup"><span data-stu-id="b2540-133">Presence integration on the device</span></span>
    
      - <span data-ttu-id="b2540-134">複数の HID (ヒューマン インターフェイス デバイス) のサポート</span><span class="sxs-lookup"><span data-stu-id="b2540-134">Multiple HID (human interface device) support</span></span>

  - <span data-ttu-id="b2540-135">位置情報サービスと緊急サービスのサポート</span><span class="sxs-lookup"><span data-stu-id="b2540-135">Location and emergency services support.</span></span>

  - <span data-ttu-id="b2540-136">IM、音声、ビデオ、アプリケーション共有、デスクトップ共有、PowerPoint 共有、ホワイトボード、ファイル送信など、すべての Lync モダリティをサポートします。</span><span class="sxs-lookup"><span data-stu-id="b2540-136">Support for all Lync modalities, including IM, audio, video, application sharing, desktop sharing, PowerPoint sharing, whiteboard, and file transfer.</span></span>

  - <span data-ttu-id="b2540-137">1 対 1 の通話および電話会議での音声とビデオのサポート</span><span class="sxs-lookup"><span data-stu-id="b2540-137">Audio and video support in person-to-person calls and conference calls.</span></span>

<span data-ttu-id="b2540-138">VDI プラグインの展開については、「lync [Server 2013 での LYNC VDI プラグインの展開](lync-server-2013-deploying-the-lync-vdi-plug-in.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2540-138">For information about deploying the VDI plug-in, see [Deploying the Lync VDI plug-in in Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span></span>

</div>

<div>

## <a name="video-enhancements"></a><span data-ttu-id="b2540-139">ビデオの拡張機能</span><span class="sxs-lookup"><span data-stu-id="b2540-139">Video Enhancements</span></span>

<span data-ttu-id="b2540-140">いくつかの新機能により、会議参加者のビデオ エクスペリエンスが大幅に強化されています。</span><span class="sxs-lookup"><span data-stu-id="b2540-140">Several new features significantly enhance the video experience for conference participants.</span></span>

  - <span data-ttu-id="b2540-141">顔検出とスマート フレーミングによってビデオが強化されました。これらの機能により、参加者が常にフレームの中央に配置されるようにビデオが移動します。</span><span class="sxs-lookup"><span data-stu-id="b2540-141">Video is enhanced with face detection and smart framing, so that a participant’s video moves to help keep them centered in the frame.</span></span>

  - <span data-ttu-id="b2540-p107">2 者間通話とマルチパーティ会議で高解像度ビデオがサポートされるようになりました。ユーザーは最大 HD 1080P の解像度を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b2540-p107">High-definition video is now supported in two-party calls and multiparty conferences. Users can experience resolutions up to HD 1080P.</span></span>

  - <span data-ttu-id="b2540-144">参加者は、さまざまな会議レイアウトの中から選択できます。ギャラリー ビューでは、すべての参加者の写真またはビデオが表示されます。スピーカー ビューでは、会議コンテンツと現在の発言者のビデオまたは写真だけが表示されます。プレゼンテーション ビューでは、会議コンテンツだけが表示されます。コンパクト ビューでは、会議コントロールだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2540-144">Participants can select from different meeting layouts: Gallery View shows all participants’ pictures or videos; Speaker View shows the meeting content and only the current speaker’s video or picture; Presentation View shows meeting content only; Compact View shows just the meeting controls.</span></span>

  - <span data-ttu-id="b2540-p108">参加者は、新しいギャラリー機能を使用して、複数のビデオ フィードを同時に表示できます。会議の参加者が 5 人を超える場合は、最も活発な参加者のビデオ フィードだけが一番上の行に表示され、その他の参加者については写真が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2540-p108">With the new Gallery feature, participants can see multiple video feeds at the same time. If the conference has more than five participants, video feeds of only the most active participants appear in the top row, and pictures appear for the other participants.</span></span>

  - <span data-ttu-id="b2540-147">参加者は、ビデオ固定設定を使用して常に表示する 1 つ以上のビデオ フィードを選択できます。</span><span class="sxs-lookup"><span data-stu-id="b2540-147">Participants can use video pinning to select one or more of the available video feeds to be visible at all times.</span></span>

  - <span data-ttu-id="b2540-148">発表者は、ビデオ スポットライト機能を使用して、1 人の参加者のビデオ フィードを選択できます。この場合、会議の各参加者には発表者が選択した参加者だけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2540-148">Presenters can use the Video Spotlight feature to select one person’s video feed so that every participant in the meeting sees that participant only.</span></span>

</div>

<div>

## <a name="chat-room-integration"></a><span data-ttu-id="b2540-149">チャット ルームの統合</span><span class="sxs-lookup"><span data-stu-id="b2540-149">Chat Room Integration</span></span>

<span data-ttu-id="b2540-150">Lync 2013 は、既に Lync 2010 グループチャットで提供されていた機能を統合しました。</span><span class="sxs-lookup"><span data-stu-id="b2540-150">Lync 2013 now integrates the features previously provided by Lync 2010 Group Chat.</span></span> <span data-ttu-id="b2540-151">個別のグループ チャット クライアントは必要ではなくなります。</span><span class="sxs-lookup"><span data-stu-id="b2540-151">A separate group chat client is no longer required.</span></span>

  - <span data-ttu-id="b2540-152">Lync 2013 の中から、ユーザーはチャットルームを検索し、連絡先にチャットルームを追加したり、チャットルームのアクティビティを監視したり、メッセージを読んだり投稿したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="b2540-152">From within Lync 2013, users can search for chat rooms, add chat rooms to their contacts, monitor chat room activity, and read and post messages.</span></span>

  - <span data-ttu-id="b2540-153">トピック フィードを作成すると、チャット ルームのいずれかで特定のキーワードが含まれた投稿が追加された場合に通知を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="b2540-153">Users can create topic feeds so that they’ll be notified if someone in one of their chat rooms adds a post containing specific keywords.</span></span>

  - <span data-ttu-id="b2540-154">新しい [**常設チャット**] オプション ページでは、チャット ルームにメッセージが投稿されたときに適用する通知アラートと通知音を設定できます。</span><span class="sxs-lookup"><span data-stu-id="b2540-154">With the new **Persistent Chat** options page, users can set notification alerts and sounds that apply when people post messages to their chat rooms.</span></span>

</div>

<div>

## <a name="lync-web-app-updates"></a><span data-ttu-id="b2540-155">Lync Web App の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="b2540-155">Lync Web App Updates</span></span>

<span data-ttu-id="b2540-156">Lync Web App は、Lync Server 2013 会議用の Web ベースの会議クライアントです。</span><span class="sxs-lookup"><span data-stu-id="b2540-156">Lync Web App is the web-based conferencing client for Lync Server 2013 meetings.</span></span> <span data-ttu-id="b2540-157">このリリースでは、Lync Web App へのコンピューターの音声とビデオの追加によって、Lync クライアントがローカルにインストールされていないすべてのユーザーに対して、完全な会議機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="b2540-157">In this release, the addition of computer audio and video to Lync Web App provides a complete in-meeting experience for anyone who doesn’t have a Lync client installed locally.</span></span> <span data-ttu-id="b2540-158">会議の参加者は、すべてのコラボレーション/共有機能と発表者の会議コントロールにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b2540-158">Meeting participants have access to all collaboration and sharing features and presenter meeting controls.</span></span>

<span data-ttu-id="b2540-159">ユーザーが会議に参加しようとしたときに、ローカルにインストールされたクライアントがない場合は、Lync Web App が開きます。</span><span class="sxs-lookup"><span data-stu-id="b2540-159">When a user tries to join a meeting but doesn’t have a locally installed client, Lync Web App opens.</span></span> <span data-ttu-id="b2540-160">会議に参加するためのその他のオプションを許可する場合は、[ミーティング参加] ページを構成できます。「展開」のドキュメントの「 [Lync Server 2013 での会議参加ページの構成](lync-server-2013-configuring-the-meeting-join-page.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2540-160">If you want to allow additional options for joining the meeting, you can configure the Meeting Join page; see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) in the Deployment documentation.</span></span>

<span data-ttu-id="b2540-161">Lync Web App の機能強化により、Lync Server 2013 では、更新されたバージョンの出席者を使用できません。</span><span class="sxs-lookup"><span data-stu-id="b2540-161">Because of the enhancements to Lync Web App, an updated version of Attendee isn’t available for Lync Server 2013.</span></span> <span data-ttu-id="b2540-162">Lync Web App は、組織外の参加者向けのクライアントです。</span><span class="sxs-lookup"><span data-stu-id="b2540-162">Lync Web App is the client of choice for participants outside your organization.</span></span> <span data-ttu-id="b2540-163">ローカル クライアントをインストールする必要はありませんが、初めて使用するときに音声、ビデオ、共有の各機能でプラグインをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2540-163">No local client installation is required, although audio, video, and sharing features require a plug-in to be installed at first use.</span></span>

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a><span data-ttu-id="b2540-164">Lync 2013 for Mobile クライアントの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="b2540-164">Lync 2013 for Mobile Clients Updates</span></span>

<span data-ttu-id="b2540-165">拡張プレゼンス、連絡先、IM 機能に加えて、Lync 2013 モバイルクライアントはインターネットおよび携帯データ接続経由で音声およびビデオ通話を提供するようになりました。</span><span class="sxs-lookup"><span data-stu-id="b2540-165">In addition to enhanced presence, contacts, and IM capabilities, Lync 2013 mobile clients now provide voice and video calling over the Internet and cellular data connections.</span></span> <span data-ttu-id="b2540-166">予定表アイテムの会議リンクを1つタップするだけで、モバイルユーザーは Lync voice およびビデオ会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="b2540-166">With a single tap of the meeting link in a calendar item, mobile users can join Lync voice and video meetings.</span></span> <span data-ttu-id="b2540-167">Lync 2013 モバイルクライアントの詳細については、「 [Lync Server 2013 のモバイルクライアントの計画](lync-server-2013-planning-for-mobile-clients.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2540-167">For more information about Lync 2013 mobile clients, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a><span data-ttu-id="b2540-168">Lync 2013 ユーザーインターフェイスの更新</span><span class="sxs-lookup"><span data-stu-id="b2540-168">Lync 2013 User Interface Updates</span></span>

<div>

## <a name="accessibility-updates"></a><span data-ttu-id="b2540-169">ユーザー補助機能の更新</span><span class="sxs-lookup"><span data-stu-id="b2540-169">Accessibility Updates</span></span>

<span data-ttu-id="b2540-170">Lync 2013 には、いくつかの新しいユーザー補助機能が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="b2540-170">Lync 2013 incorporates several new accessibility features.</span></span>

  - <span data-ttu-id="b2540-171">Lync 2013 は高 DPI 解像度をサポートしており、ユーザーは125% および150% ドット/インチのテキストとグラフィックスを拡大できます。</span><span class="sxs-lookup"><span data-stu-id="b2540-171">Lync 2013 supports high DPI resolution, enabling users to scale text and graphics for 125% and 150% dots per inch.</span></span>

  - <span data-ttu-id="b2540-172">Lync はハイコントラストのサポートを提供しているため、Windows でハイコントラストのテーマを使用すると、ユーザーインターフェイスが完全に機能したままになります。</span><span class="sxs-lookup"><span data-stu-id="b2540-172">Lync provides high-contrast support so that the user interface remains fully functional when used with high contrast themes in Windows.</span></span>

  - <span data-ttu-id="b2540-173">Lync には、ユーザーがマウスを使用せずに重要な機能にアクセスできるように、100を超えるキーボードショートカットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="b2540-173">Lync offers more than 100 keyboard shortcuts so that users can access important functions without a mouse.</span></span> <span data-ttu-id="b2540-174">たとえば、タブを使用したり、フォーカスを設定したりしなくても、Alt キーを押しながら C キーを押すことで通話を受け入れ、Alt キーを押しながら I キーを押すことで通話を無視できます。</span><span class="sxs-lookup"><span data-stu-id="b2540-174">For example, users can press Alt+C to accept a call, or Alt + I to ignore it, without having to tab or set the focus.</span></span> <span data-ttu-id="b2540-175">また、キーボードを使用して、通話の終了 (Alt + Q キー)、OneNote の起動 (Ctrl + N キー)、[ツール] メニューを開く (Alt + T) などの操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="b2540-175">Pressing (Alt+Q) ends a call, (Ctrl+N) starts OneNote, and (Alt+T) opens the Tools menu.</span></span>

  - <span data-ttu-id="b2540-176">Lync 2013 での高度なスクリーンリーダーのサポートにより、スクリーンリーダーが有効になっているときに、すべての通知、着信要求、およびインスタントメッセージが読み上げられるようになります。</span><span class="sxs-lookup"><span data-stu-id="b2540-176">Extensive screen reader support in Lync 2013 ensures that all notifications, incoming requests, and instant messages are read aloud when a screen reader is enabled.</span></span>

</div>

<div>

## <a name="presence-while-sharing"></a><span data-ttu-id="b2540-177">共有時のプレゼンス</span><span class="sxs-lookup"><span data-stu-id="b2540-177">Presence While Sharing</span></span>

<span data-ttu-id="b2540-178">Lync は、ユーザーが共有していることを検出すると、ユーザーにプレゼンス状態の表示を自動的に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b2540-178">When Lync detects that a user is sharing, Lync automatically assigns the user a Presenting presence status.</span></span> <span data-ttu-id="b2540-179">送信者に "ワークグループ" の関係が割り当てられている場合を除き、このプレゼンス状態が割り当てられているときはすべての着信通信がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="b2540-179">This status blocks all incoming communications unless the sender is assigned the Workgroup privacy relationship.</span></span> <span data-ttu-id="b2540-180">ユーザーがセカンダリモニターで共有機能を完全に使用している場合、Lync は表示するプレゼンス状態を割り当てません。</span><span class="sxs-lookup"><span data-stu-id="b2540-180">If the user is using the sharing feature entirely on a secondary monitor, Lync does not assign a Presenting presence status.</span></span>

</div>

<div>

## <a name="conversation-window-updates"></a><span data-ttu-id="b2540-181">会話ウィンドウの更新</span><span class="sxs-lookup"><span data-stu-id="b2540-181">Conversation Window Updates</span></span>

<span data-ttu-id="b2540-182">再設計された会話ウィンドウにより、重要な機能に迅速にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b2540-182">The redesigned Conversation window provides quicker access to important features.</span></span>

  - <span data-ttu-id="b2540-p116">新しいタブ表示の会話機能により、すべての IM とチャット ルームを 1 つの会話ウィンドウに保持できるようになりました。会話ウィンドウの左側に並ぶタブを使用すると、アクティブなすべての会話を簡単に切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="b2540-p116">With the new tabbed conversations feature, users can now keep all their IMs and chat rooms in one Conversation window. The tabs along the left side of the Conversation window let users navigate easily among all active conversations.</span></span>

  - <span data-ttu-id="b2540-p117">ユーザーは、個々の会話を別のウィンドウにポップ アウトし、そのウィンドウのサイズを変更できます。また、ウィンドウをメインの会話ウィンドウに戻すこともできます。</span><span class="sxs-lookup"><span data-stu-id="b2540-p117">Users can pop out an individual conversation into a separate window, and then resize the window. They can also pop the window back into the main Conversation window.</span></span>

  - <span data-ttu-id="b2540-187">Lync 2013 は、ユーザーがサインアウトして Lync にサインインし直すと、ユーザーの会話を再度開きます。</span><span class="sxs-lookup"><span data-stu-id="b2540-187">Lync 2013 reopens a user’s conversations when the user signs out and signs back in to Lync.</span></span>

  - <span data-ttu-id="b2540-188">ユーザーは、IM、ビデオ、プログラム共有、デスクトップ共有、または Web 会議ツール (ホワイトボード、会議ノート、共有ノートブック、および添付ファイル) を会話にすばやく追加できます。</span><span class="sxs-lookup"><span data-stu-id="b2540-188">Users can quickly add IM, video, program sharing, desktop sharing, or web conferencing tools (whiteboard, meeting notes, shared notebooks, and attachments) to any conversation.</span></span>

  - <span data-ttu-id="b2540-189">ビデオやコンテンツを共有している会議では、会議のビデオや共有コンテンツをポップ アウトした後、ウィンドウのサイズを変更できます。</span><span class="sxs-lookup"><span data-stu-id="b2540-189">In a meeting where video or content is being shared, users can pop out the meeting video or shared content, and then resize the window.</span></span>

</div>

<div>

## <a name="lync-main-window-updates"></a><span data-ttu-id="b2540-190">Lync メインウィンドウの更新</span><span class="sxs-lookup"><span data-stu-id="b2540-190">Lync Main Window Updates</span></span>

<span data-ttu-id="b2540-191">合理化された新しい外観に、[**今日はどんなことがありますか?**] メモ フィールド、状態セレクター、[**場所の設定**] セレクターなどの、おなじみの機能が維持されています。</span><span class="sxs-lookup"><span data-stu-id="b2540-191">The new streamlined look retains familiar features such as the **What’s happening today?** note field, the status selector, and the **Set Your Location** selector.</span></span>

  - <span data-ttu-id="b2540-192">チャットルームが有効になっている場合、ユーザーには新しい**チャットルーム**のアイコンがメインの Lync ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2540-192">When chat rooms are enabled, users see a new **Chat Rooms** icon on the main Lync page.</span></span> <span data-ttu-id="b2540-193">ユーザーは、[**チャット ルーム**] アイコンを使用して、チャット ルームやフィルターにすばやくアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b2540-193">With the **Chat Rooms** icon, users can quickly access their chat rooms and filters.</span></span>

  - <span data-ttu-id="b2540-194">ユーザーは、表示アイコンをクリックすることで、［**連絡先**] ビュー、[**チャット ルーム**] ビュー、[**会話**] ビュー、または [**電話**] ビューに切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="b2540-194">Users can click the view icons to switch to the **Contacts** view, **Chat Rooms** view, **Conversations** view, or **Phone** view.</span></span>

  - <span data-ttu-id="b2540-195">ユーザーが Exchange 2013 に移行されている場合は、高解像度の画像をアップロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="b2540-195">If users have been migrated to Exchange 2013, they can upload a high resolution picture.</span></span>

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a><span data-ttu-id="b2540-196">連絡先ビューと連絡先カードの更新</span><span class="sxs-lookup"><span data-stu-id="b2540-196">Contacts View and Contact Card Updates</span></span>

<span data-ttu-id="b2540-197">Lync 2013 を使用する**と、ユーザーは連絡先ビューで**連絡先やグループをさまざまな方法で表示できます。</span><span class="sxs-lookup"><span data-stu-id="b2540-197">Lync 2013 gives users different ways to view contacts and groups in their **Contacts** view.</span></span>

  - <span data-ttu-id="b2540-198">新しい統合連絡先ストアを使用すると、ユーザーの Lync の連絡先が Exchange 2013 に移行された後、ユーザーは Lync 2013、Outlook、または Outlook Web App から連絡先にアクセスして管理できるようになり、それらのユーザーは Lync、Outlook、または Outlook Web App から連絡先を同期したままになります。</span><span class="sxs-lookup"><span data-stu-id="b2540-198">With the new unified contact store, after users' Lync contacts are migrated to Exchange 2013, the users can access and manage their contacts from Lync 2013, Outlook, or Outlook Web App, and their Favorites stay synchronized.</span></span> <span data-ttu-id="b2540-199">たとえば、ユーザーが Outlook のお気に入りに連絡先を追加すると、その連絡先は Lync 2013 の [お気に入り] グループに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2540-199">For example, if a user adds a contact to Favorites in Outlook, the contact appears in the Favorites group in Lync 2013.</span></span>

  - <span data-ttu-id="b2540-200">XMPP プロキシと XMPP ゲートウェイを追加し、構成している場合、ユーザーはインスタント メッセージングとプレゼンスの XMPP ベースのパートナーから連絡先を追加できます。</span><span class="sxs-lookup"><span data-stu-id="b2540-200">If you have added and configured the XMPP proxy and XMPP gateway, users can add contacts from XMPP-based partners for instant messaging and presence.</span></span>

  - <span data-ttu-id="b2540-201">新しい [**外部の連絡先の追加**] 機能を使用すると、組織外部の人々を簡単に追加できます。</span><span class="sxs-lookup"><span data-stu-id="b2540-201">A new **Add a Contact That’s Not in My Organization** feature gives users an easy way to add people who are external to the organization.</span></span>

  - <span data-ttu-id="b2540-202">ユーザーは、新しい**お気に入り**グループによって、すばやくアクセスできるように、頻繁に連絡している人たちのリストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b2540-202">A new **Favorites** group lets users build a list of people users contact most often for quicker access.</span></span>

  - <span data-ttu-id="b2540-p120">ユーザーは、新しい [**連絡先リスト**] オプション ページを使用して、連絡先の並べ替えと表示の方法を選択できます。連絡先の写真を表示する拡大された 2 行のビュー、または縮小された 1 行のビューを選択できます。また、連絡先をアルファベット順または状態で並べ替えることもできます。</span><span class="sxs-lookup"><span data-stu-id="b2540-p120">Users can use the new **Contacts List** options page to choose how users want to sort and display contacts. Users can select an expanded, two-line view that shows contacts’ pictures, or a condensed one-line view. Users can also sort contacts alphabetically or by availability.</span></span>

</div>

<div>

## <a name="conferencing-updates"></a><span data-ttu-id="b2540-206">会議機能の更新</span><span class="sxs-lookup"><span data-stu-id="b2540-206">Conferencing Updates</span></span>

<span data-ttu-id="b2540-207">Lync 2013 では、会議機能にいくつかの機能が強化されています。</span><span class="sxs-lookup"><span data-stu-id="b2540-207">Lync 2013 offers several enhancements to conferencing features.</span></span>

  - <span data-ttu-id="b2540-p121">会議の種類に応じて、会議のスケジュールを設定するときに、参加者をミュートしたり、ビデオ共有を許可または禁止したりできるようになりました。これらのオプションは、[**会議オプション**] ページに用意されています。参加者が 20 人を超える大規模な会議でこれらのオプションを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b2540-p121">Depending on the type of meeting, users can now mute the audience and allow or block video sharing when scheduling the meeting. These options are available on the **Meeting Options** page and are recommended for large meetings with more than 20 participants.</span></span>

  - <span data-ttu-id="b2540-210">会議室での使いやすい音声コントロールにより、ミュート、ミュート解除、デバイスの変更など、音声オプションを制御できます。</span><span class="sxs-lookup"><span data-stu-id="b2540-210">Easy to use audio controls in the meeting room allow the user to control audio options, such as mute, unmute, change device, and so on.</span></span>

  - <span data-ttu-id="b2540-211">プログラムを共有する場合、複数のプログラムを使用する必要があれば、共有するプログラムを複数選択できます。</span><span class="sxs-lookup"><span data-stu-id="b2540-211">When sharing programs, users can select multiple programs to share if they need to work with more than one program.</span></span>

  - <span data-ttu-id="b2540-212">PowerPoint ファイルをアップロードし、ビデオ コントロール (再生、一時停止、音声コントロールなど) を表示するスライドをマウスでポイントすることにより、ビデオ クリップが含まれているプレゼンテーションをアップロードできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b2540-212">Users can now upload presentations that contain video clips by uploading the PowerPoint file, and pointing the mouse over the slide to display video controls, such as play, pause, and audio controls.</span></span>

  - <span data-ttu-id="b2540-213">会議中に、[**その他のオプション** (**…**)] メニューの [**この通話を結合**] を使用すると、開いている別の会話を会議に結合できます。</span><span class="sxs-lookup"><span data-stu-id="b2540-213">While in a meeting, users can merge another open conversation into the meeting by using **Merge This Call Into** on the **More Options** (**…**) menu.</span></span>

  - <span data-ttu-id="b2540-214">参加者の名前を表示するには、[**View Participants**] ボタンをマウスでポイントするか、または [**参加者リストを表示**] をクリックして、パネルを会議の中にドッキングします。</span><span class="sxs-lookup"><span data-stu-id="b2540-214">To see the participants’ names, users can hover the mouse over the **View Participants** button, or click **Show Participant List** to dock the panel in the meeting.</span></span>

  - <span data-ttu-id="b2540-215">会議の種類に応じて、いくつかの異なるコンテンツ表示と参加者表示から選択できます。</span><span class="sxs-lookup"><span data-stu-id="b2540-215">Depending on the meeting type, users can select from several different content and participant views.</span></span>

  - <span data-ttu-id="b2540-p122">会議のレコーディングは、Windows Media Player (MP4) で再生される形式で自動的に保存されます。このファイルはだれとでも簡単に共有できます。また、レコーディング マネージャーの**公開**機能を使用して、そのレコーディングを共有の場所に投稿することもできます。</span><span class="sxs-lookup"><span data-stu-id="b2540-p122">Meeting recordings are automatically saved in a format that plays in Windows Media Player (MP4). Users can easily share the file with anyone, or use the **Publish** feature in recording manager to post the recording on a shared location.</span></span>

  - <span data-ttu-id="b2540-p123">OneNote により、会議での共同作業に新しい方法を使用できます。会議中に OneNote でメモをとり、会議の後に個人的に使用できます。また、共有ノートブックを使用し、会議の参加者とリアルタイムで共同編集することもできます。すべてのチーム メンバーが共有ノートにアクセスして、情報の提供やアイデアの交換を行ったり、ノートブックのページを仮想ホワイトボードとして使用したりできます。会議の参加者と共有コンテンツはノートに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="b2540-p123">OneNote enables new ways to collaborate in a meeting. During a meeting, users can take notes with OneNote for personal use after the meeting, or use shared notebooks and co-edit with meeting participants in real time. All team members can access the shared notes to contribute information, brainstorm ideas, or use the notebook pages as a virtual whiteboard. People and content shared in the meeting are automatically added to the Notes.</span></span>

  - <span data-ttu-id="b2540-p124">会議室の下部にある [**コンテンツを共有し、会議アクティビティをリードします**] を使用すると、コンテンツの種類を切り替えることができます。また、[**プレゼンテーション用コンテンツの管理**] メニューを使用して、共有するコンテンツを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="b2540-p124">Users can switch between content types using **Share content and lead meeting activities** at the bottom of the meeting room. Users can also use the **Manage Presentable Content** menu to choose which content they want to share.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b2540-224">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2540-224">See Also</span></span>


[<span data-ttu-id="b2540-225">Lync Server 2013 でのクライアントの計画</span><span class="sxs-lookup"><span data-stu-id="b2540-225">Planning for clients in Lync Server 2013</span></span>](lync-server-2013-planning-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


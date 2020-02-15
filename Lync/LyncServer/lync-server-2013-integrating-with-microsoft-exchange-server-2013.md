---
title: 'Lync Server 2013: Microsoft Exchange Server 2013 との統合'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49733697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dccf60dba1b729b1ffa808694fffcacc14e460ba
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="5f080-102">Microsoft Lync Server 2013 および Microsoft Exchange Server 2013 の統合</span><span class="sxs-lookup"><span data-stu-id="5f080-102">Integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f080-103">_**トピックの最終更新日:** 2014-07-09_</span><span class="sxs-lookup"><span data-stu-id="5f080-103">_**Topic Last Modified:** 2014-07-09_</span></span>

<span data-ttu-id="5f080-104">Exchange と Lync Server の統合と互換性については、長い歴史があります。</span><span class="sxs-lookup"><span data-stu-id="5f080-104">Exchange and Lync Server have a long history of integration and compatibility.</span></span> <span data-ttu-id="5f080-105">この統合は、それぞれのクライアント アプリケーションの中でも最も重要なものです。</span><span class="sxs-lookup"><span data-stu-id="5f080-105">This integration is most noticeable within their respective client application.</span></span> <span data-ttu-id="5f080-106">たとえば、Lync プレゼンス情報は Microsoft Outlook で報告できます。同様に、Lync は Outlook の予定表を使用して、そのプレゼンス情報を自動的に更新することができます。</span><span class="sxs-lookup"><span data-stu-id="5f080-106">For example, Lync presence information can be reported in Microsoft Outlook; likewise, Lync can use Outlook calendar to automatically update that presence information.</span></span> <span data-ttu-id="5f080-107">(たとえば、Lync は、予定が設定された会議があることを予定表に表示するときに、いつでも状態を [取り込み中] に変更できます。)Lync Server を実行するために Exchange を実行する必要はありませんが (またはその逆も可能)、2つの製品を一緒に使用することによって、"より良い" という用語の定義が epitomizes されることはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="5f080-107">(For example, Lync can change your status to Busy any time your calendar shows that you have a meeting scheduled.) Although you do not have to run Exchange in order to run Lync Server (or vice-versa) there's little doubt that using the two products together epitomizes the very definition of the term "better together."</span></span>

<span data-ttu-id="5f080-108">これは、Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 のリリースでは特に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="5f080-108">This is especially true with the release of Microsoft Lync Server 2013 and Microsoft Exchange Server 2013.</span></span> <span data-ttu-id="5f080-109">ユニファイドメッセージング、IM、プレゼンスなど、Microsoft Exchange Server 2010 および Microsoft Lync Server 2010 にある機能に加えて、サーバー製品の2013リリースにはいくつかの新機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5f080-109">In addition to features, such as unified messaging and IM and presence, that are found in Microsoft Exchange Server 2010 and Microsoft Lync Server 2010, the 2013 releases of the server products include a number of new capabilities.</span></span> <span data-ttu-id="5f080-110">以下はその一例です。</span><span class="sxs-lookup"><span data-stu-id="5f080-110">These capabilities include such things as:</span></span>

  - <span data-ttu-id="5f080-111">**Lync アーカイブの統合**。</span><span class="sxs-lookup"><span data-stu-id="5f080-111">**Lync Archiving Integration**.</span></span> <span data-ttu-id="5f080-112">Lync Server 2013 では、管理者はインスタントメッセージングと Web 会議のトランスクリプトを SQL Server にアーカイブすることもできます (これらのトランスクリプトが Lync Server 2010 にアーカイブされた場合と同じ)。</span><span class="sxs-lookup"><span data-stu-id="5f080-112">In Lync Server 2013 administrators still have the option of having instant messaging and Web conferencing transcripts archived to SQL Server (the same way these transcripts were archived in Lync Server 2010).</span></span> <span data-ttu-id="5f080-113">また、管理者は、exchange 2013 にトランスクリプトをアーカイブすることを選択できます。これらのトランスクリプトは、Exchange が通信をアーカイブするのと同じ方法で、個々のユーザーのメールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="5f080-113">Alternatively, however, administrators can choose to have transcripts archived to Exchange 2013, storing those transcripts in the individual user mailboxes in the same way in which Exchange archives communications.</span></span> <span data-ttu-id="5f080-114">これは、すべての電子通信 (Exchange と Lync Server の両方) に対して単一のリポジトリを使用しているため、アーカイブされた通信を検索して取得し、必要に応じて取得するのがはるかに簡単になります。</span><span class="sxs-lookup"><span data-stu-id="5f080-114">That means a single repository for all your electronic communications (from both Exchange and Lync Server), which makes it much easier to search for and retrieve those archived communications should the need arise.</span></span>

  - <span data-ttu-id="5f080-115">**統合連絡先ストア**。</span><span class="sxs-lookup"><span data-stu-id="5f080-115">**Unified Contact Store**.</span></span> <span data-ttu-id="5f080-116">Lync Server 2010 では、ユーザーは Outlook と Lync で個別の連絡先リストを保持する必要がありました。実際には、両方の製品で同じ連絡先が使用可能であることを確認するために、Outlook 用と Lync 用に1つずつ、重複する連絡先リストを保持する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="5f080-116">In Lync Server 2010, users had to maintain separate contact lists in Outlook and Lync; in fact, to ensure that you had the same contacts available in both products you had to maintain duplicate contact lists, one for Outlook and one for Lync.</span></span> <span data-ttu-id="5f080-117">ただし、Lync Server 2013 では、ユーザーの連絡先を Exchange 2013 および統合連絡先ストアに格納できます。</span><span class="sxs-lookup"><span data-stu-id="5f080-117">With Lync Server 2013, however, user contacts can be stored in Exchange 2013 and the unified contact store.</span></span> <span data-ttu-id="5f080-118">単一の連絡先ストアを使用すると、1つの連絡先セットだけを保持し、Lync 2013、Outlook 2013、および Outlook Web Access 2013 でその連絡先の同じセットを使用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5f080-118">Using a single contact store enables users to maintain just one set of contacts, with that same set of contacts being available in Lync 2013, Outlook 2013, and Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="5f080-119">**OWA からの Lync 会議のスケジュール**。</span><span class="sxs-lookup"><span data-stu-id="5f080-119">**Lync Meeting Scheduling from OWA**.</span></span> <span data-ttu-id="5f080-120">Lync Server 2013 と Exchange 2013 の統合により、ユーザーは Outlook Web Access 2013 から Lync 会議をスケジュールすることができます。</span><span class="sxs-lookup"><span data-stu-id="5f080-120">With Lync Server 2013 and Exchange 2013 integration, users can schedule Lync meetings from Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="5f080-121">**高解像度写真**</span><span class="sxs-lookup"><span data-stu-id="5f080-121">**High resolution photos**.</span></span> <span data-ttu-id="5f080-122">Lync 2010 は、連絡先の小さな写真しか表示できませんでした。これは、これらの写真は Active Directory に格納されており、Active Directory は、保存された写真に 48 48 ピクセルのサイズ制限を課すからです。</span><span class="sxs-lookup"><span data-stu-id="5f080-122">Lync 2010 could only display small photos of your contacts; that's because those photos were stored in Active Directory, and Active Directory imposes a 48 pixel by 48 pixel size limitation on stored photos.</span></span> <span data-ttu-id="5f080-123">ただし、Lync Server 2013 では、写真を Microsoft Exchange に保存することができます。これにより、高解像度の写真を648ピクセル、648ピクセルにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5f080-123">With Lync Server 2013, however, photos can be stored in Microsoft Exchange; that allows for high-resolution photos as large as 648 pixels by 648 pixels.</span></span> <span data-ttu-id="5f080-124">ご想像のとおり、Lync 2013 は、これらの高解像度の写真の表示を許可するようにアップグレードされています。</span><span class="sxs-lookup"><span data-stu-id="5f080-124">As you might expect, Lync 2013 has been upgraded to allow for the display of these high-resolution photographs.</span></span>

<span data-ttu-id="5f080-125">これらの新機能では、Lync Server 2013 と Exchange 2013 の両方を使用する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5f080-125">Keep in mind that these new features require the use of both Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="5f080-126">これに加えて、これらの新機能を十分に活用する必要があるユーザーは、Lync Server 2013 および Exchange 2013 のアカウントを持っており、最新バージョンのクライアントソフトウェア (Lync 2013 など) を使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f080-126">In addition to that, users who hope to take full advantage of these new capabilities must have accounts on Lync Server 2013 and Exchange 2013, and must be using the latest versions of the client software (e.g., Lync 2013).</span></span> <span data-ttu-id="5f080-127">たとえば、Lync Server 2010 に所属しているユーザーは、統合連絡先ストアを使用できません。同様に、Lync 2010 に高解像度写真を表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="5f080-127">For example, the unified contact store is not available to users who have been homed on Lync Server 2010; likewise, high-resolution photos cannot be displayed in Lync 2010.</span></span>

<span data-ttu-id="5f080-128">このドキュメントでは、Lync Server 2013 と Exchange 2013 の統合について説明します。</span><span class="sxs-lookup"><span data-stu-id="5f080-128">This documentation provides information on integrating Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="5f080-129">アーカイブ統合、統合連絡先ストアなど、新機能を有効にするための詳細な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="5f080-129">including step-by-step information on enabling new features such archiving Integration and the unified contact store.</span></span> <span data-ttu-id="5f080-130">このドキュメントでは、これら2つの製品の初期セットアップと構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="5f080-130">What this documentation does not do is discuss the initial setup and configuration of these two products.</span></span> <span data-ttu-id="5f080-131">Lync Server 2013 の展開の詳細については、「Lync Server [http://go.microsoft.com/fwlink/p/?LinkId=246127](http://go.microsoft.com/fwlink/p/?linkid=246127)2013 Tech Center」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f080-131">For details about deploying Lync Server 2013 see the Lync Server 2013 Tech Center at [http://go.microsoft.com/fwlink/p/?LinkId=246127](http://go.microsoft.com/fwlink/p/?linkid=246127).</span></span> <span data-ttu-id="5f080-132">Exchange 2013 の展開の詳細については、「Exchange [http://go.microsoft.com/fwlink/p/?LinkId=268528](http://go.microsoft.com/fwlink/p/?linkid=268528)2013 の技術センター」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f080-132">For details about deploying Exchange 2013 see the Exchange 2013 Tech Center at [http://go.microsoft.com/fwlink/p/?LinkId=268528](http://go.microsoft.com/fwlink/p/?linkid=268528).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5f080-133">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5f080-133">In This Section</span></span>

[<span data-ttu-id="5f080-134">Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 を統合するための前提条件</span><span class="sxs-lookup"><span data-stu-id="5f080-134">Prerequisites for integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[<span data-ttu-id="5f080-135">Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 でのパートナーアプリケーションの構成</span><span class="sxs-lookup"><span data-stu-id="5f080-135">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[<span data-ttu-id="5f080-136">Microsoft Exchange Server 2013 アーカイブを使用するように Microsoft Lync Server 2013 を構成する</span><span class="sxs-lookup"><span data-stu-id="5f080-136">Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving</span></span>](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[<span data-ttu-id="5f080-137">Microsoft SharePoint Server 2013 を構成して、アーカイブされた Microsoft Lync Server 2013 データを検索する</span><span class="sxs-lookup"><span data-stu-id="5f080-137">Configuring Microsoft SharePoint Server 2013 to search for archived Microsoft Lync Server 2013 data</span></span>](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[<span data-ttu-id="5f080-138">統合連絡先ストアを使用するように Microsoft Lync Server 2013 を構成する</span><span class="sxs-lookup"><span data-stu-id="5f080-138">Configuring Microsoft Lync Server 2013 to use the unified contact store</span></span>](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[<span data-ttu-id="5f080-139">Microsoft Lync Server 2013 で高解像度写真の使用を構成する</span><span class="sxs-lookup"><span data-stu-id="5f080-139">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</span></span>](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[<span data-ttu-id="5f080-140">Microsoft Lync Server 2013 ボイスメール用の Microsoft Exchange Server 2013 ユニファイドメッセージングの構成</span><span class="sxs-lookup"><span data-stu-id="5f080-140">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[<span data-ttu-id="5f080-141">Microsoft Lync Server 2013 と Microsoft Outlook Web App 2013 の統合</span><span class="sxs-lookup"><span data-stu-id="5f080-141">Integrating Microsoft Lync Server 2013 and Microsoft Outlook Web App 2013</span></span>](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


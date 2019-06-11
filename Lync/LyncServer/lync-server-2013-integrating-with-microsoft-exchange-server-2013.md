---
title: 'Lync Server 2013: Microsoft Exchange Server 2013 との統合'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49733697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ba140e4f7e33684a280a9d9c4b71f1d7e141a65
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="0baae-102">Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 の統合</span><span class="sxs-lookup"><span data-stu-id="0baae-102">Integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0baae-103">_**最終更新日:** 2014-07-09_</span><span class="sxs-lookup"><span data-stu-id="0baae-103">_**Topic Last Modified:** 2014-07-09_</span></span>

<span data-ttu-id="0baae-104">Exchange と Lync Server には、統合と互換性の長い履歴があります。</span><span class="sxs-lookup"><span data-stu-id="0baae-104">Exchange and Lync Server have a long history of integration and compatibility.</span></span> <span data-ttu-id="0baae-105">この統合は、それぞれのクライアントアプリケーションで最も顕著です。</span><span class="sxs-lookup"><span data-stu-id="0baae-105">This integration is most noticeable within their respective client application.</span></span> <span data-ttu-id="0baae-106">たとえば、Lync のプレゼンス情報は Microsoft Outlook で報告できます。同様に、Lync では、Outlook の予定表を使って、プレゼンス情報を自動的に更新することができます。</span><span class="sxs-lookup"><span data-stu-id="0baae-106">For example, Lync presence information can be reported in Microsoft Outlook; likewise, Lync can use Outlook calendar to automatically update that presence information.</span></span> <span data-ttu-id="0baae-107">(たとえば、会議がスケジュールされていることを予定表に示すときは、Lync によって状態が [取り込み中] に変更されることがあります)。Lync Server を実行するために Exchange を実行する必要はありませんが (またはその逆)、2つの製品を同時に使用することによって、"epitomizes" という用語の定義をまとめることはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="0baae-107">(For example, Lync can change your status to Busy any time your calendar shows that you have a meeting scheduled.) Although you do not have to run Exchange in order to run Lync Server (or vice-versa) there's little doubt that using the two products together epitomizes the very definition of the term "better together."</span></span>

<span data-ttu-id="0baae-108">これは、Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 のリリースに特に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="0baae-108">This is especially true with the release of Microsoft Lync Server 2013 and Microsoft Exchange Server 2013.</span></span> <span data-ttu-id="0baae-109">Microsoft Exchange Server 2010 および Microsoft Lync Server 2010 で利用できるユニファイドメッセージング、IM、プレゼンスなどの機能に加えて、サーバー製品の2013リリースには、多くの新機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0baae-109">In addition to features, such as unified messaging and IM and presence, that are found in Microsoft Exchange Server 2010 and Microsoft Lync Server 2010, the 2013 releases of the server products include a number of new capabilities.</span></span> <span data-ttu-id="0baae-110">これらの機能には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="0baae-110">These capabilities include such things as:</span></span>

  - <span data-ttu-id="0baae-111">**Lync アーカイブの統合**。</span><span class="sxs-lookup"><span data-stu-id="0baae-111">**Lync Archiving Integration**.</span></span> <span data-ttu-id="0baae-112">Lync Server 2013 管理者でも、インスタントメッセージと Web 会議のトランスクリプトを SQL Server にアーカイブするオプションがあります (これらのトランスクリプトが Lync Server 2010 でアーカイブされた場合と同じです)。</span><span class="sxs-lookup"><span data-stu-id="0baae-112">In Lync Server 2013 administrators still have the option of having instant messaging and Web conferencing transcripts archived to SQL Server (the same way these transcripts were archived in Lync Server 2010).</span></span> <span data-ttu-id="0baae-113">また、管理者は、exchange のアーカイブと同じ方法で、トランスクリプトを Exchange 2013 にアーカイブすることを選ぶことができます。これらのトランスクリプトは個々のユーザーのメールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="0baae-113">Alternatively, however, administrators can choose to have transcripts archived to Exchange 2013, storing those transcripts in the individual user mailboxes in the same way in which Exchange archives communications.</span></span> <span data-ttu-id="0baae-114">つまり、すべての電子通信 (Exchange と Lync Server の両方) について単一のリポジトリを意味します。これにより、アーカイブされた通信を検索して、必要に応じて取得しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="0baae-114">That means a single repository for all your electronic communications (from both Exchange and Lync Server), which makes it much easier to search for and retrieve those archived communications should the need arise.</span></span>

  - <span data-ttu-id="0baae-115">**統合連絡先ストア**。</span><span class="sxs-lookup"><span data-stu-id="0baae-115">**Unified Contact Store**.</span></span> <span data-ttu-id="0baae-116">Lync Server 2010 では、ユーザーは Outlook と Lync で個別の連絡先リストを管理する必要がありました。実際には、両方の製品で同じ連絡先が使用可能であることを確認するために、Outlook 用と Lync 用の連絡先リストの重複を管理する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="0baae-116">In Lync Server 2010, users had to maintain separate contact lists in Outlook and Lync; in fact, to ensure that you had the same contacts available in both products you had to maintain duplicate contact lists, one for Outlook and one for Lync.</span></span> <span data-ttu-id="0baae-117">ただし、Lync Server 2013 では、ユーザーの連絡先を Exchange 2013 とユニファイド連絡先ストアに保存できます。</span><span class="sxs-lookup"><span data-stu-id="0baae-117">With Lync Server 2013, however, user contacts can be stored in Exchange 2013 and the unified contact store.</span></span> <span data-ttu-id="0baae-118">1つの連絡先ストアを使用すると、ユーザーは1つの連絡先セットだけを保持できるため、Lync 2013、Outlook 2013、Outlook Web Access 2013 で利用できる連絡先と同じセットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0baae-118">Using a single contact store enables users to maintain just one set of contacts, with that same set of contacts being available in Lync 2013, Outlook 2013, and Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="0baae-119">**OWA からの Lync 会議のスケジュール設定**。</span><span class="sxs-lookup"><span data-stu-id="0baae-119">**Lync Meeting Scheduling from OWA**.</span></span> <span data-ttu-id="0baae-120">Lync Server 2013 および Exchange 2013 の統合機能を使用すると、ユーザーは Outlook Web Access 2013 から Lync 会議をスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="0baae-120">With Lync Server 2013 and Exchange 2013 integration, users can schedule Lync meetings from Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="0baae-121">**高解像度の写真**。</span><span class="sxs-lookup"><span data-stu-id="0baae-121">**High resolution photos**.</span></span> <span data-ttu-id="0baae-122">Lync 2010 では、連絡先の小さな写真しか表示できませんでした。このような写真は Active Directory に保存されており、Active Directory では、保存された写真に48ピクセルのサイズの制限48を設けています。</span><span class="sxs-lookup"><span data-stu-id="0baae-122">Lync 2010 could only display small photos of your contacts; that's because those photos were stored in Active Directory, and Active Directory imposes a 48 pixel by 48 pixel size limitation on stored photos.</span></span> <span data-ttu-id="0baae-123">ただし、Lync Server 2013 では、写真を Microsoft Exchange に保存することができます。これにより、648ピクセルから648ピクセルまでの高解像度の写真を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0baae-123">With Lync Server 2013, however, photos can be stored in Microsoft Exchange; that allows for high-resolution photos as large as 648 pixels by 648 pixels.</span></span> <span data-ttu-id="0baae-124">このような高解像度の写真が表示されるように、Lync 2013 はアップグレードされています。</span><span class="sxs-lookup"><span data-stu-id="0baae-124">As you might expect, Lync 2013 has been upgraded to allow for the display of these high-resolution photographs.</span></span>

<span data-ttu-id="0baae-125">これらの新機能には Lync Server 2013 と Exchange 2013 の両方を使用する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0baae-125">Keep in mind that these new features require the use of both Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="0baae-126">また、これらの新機能を最大限に活用したいユーザーは、Lync Server 2013 および Exchange 2013 上のアカウントを持っている必要があります。また、最新バージョンのクライアントソフトウェア (Lync 2013 など) を使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0baae-126">In addition to that, users who hope to take full advantage of these new capabilities must have accounts on Lync Server 2013 and Exchange 2013, and must be using the latest versions of the client software (e.g., Lync 2013).</span></span> <span data-ttu-id="0baae-127">たとえば、統合連絡先ストアは、Lync Server 2010 を使っているユーザーは使用できません。同様に、高解像度の写真を Lync 2010 で表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="0baae-127">For example, the unified contact store is not available to users who have been homed on Lync Server 2010; likewise, high-resolution photos cannot be displayed in Lync 2010.</span></span>

<span data-ttu-id="0baae-128">このドキュメントでは、Lync Server 2013 および Exchange 2013 の統合について説明します。</span><span class="sxs-lookup"><span data-stu-id="0baae-128">This documentation provides information on integrating Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="0baae-129">アーカイブ統合やユニファイド連絡先ストアなどの新機能を有効にする手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="0baae-129">including step-by-step information on enabling new features such archiving Integration and the unified contact store.</span></span> <span data-ttu-id="0baae-130">このドキュメントでは、これら2つの製品の初期設定と構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="0baae-130">What this documentation does not do is discuss the initial setup and configuration of these two products.</span></span> <span data-ttu-id="0baae-131">Lync Server 2013 の展開の詳細については、「Lync Server [http://go.microsoft.com/fwlink/p/?LinkId=246127](http://go.microsoft.com/fwlink/p/?linkid=246127)2013 の技術センター」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0baae-131">For details about deploying Lync Server 2013 see the Lync Server 2013 Tech Center at [http://go.microsoft.com/fwlink/p/?LinkId=246127](http://go.microsoft.com/fwlink/p/?linkid=246127).</span></span> <span data-ttu-id="0baae-132">Exchange 2013 の展開の詳細については、「Exchange [http://go.microsoft.com/fwlink/p/?LinkId=268528](http://go.microsoft.com/fwlink/p/?linkid=268528)2013 の技術センター」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0baae-132">For details about deploying Exchange 2013 see the Exchange 2013 Tech Center at [http://go.microsoft.com/fwlink/p/?LinkId=268528](http://go.microsoft.com/fwlink/p/?linkid=268528).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0baae-133">このセクション中</span><span class="sxs-lookup"><span data-stu-id="0baae-133">In This Section</span></span>

[<span data-ttu-id="0baae-134">Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 を統合するための前提条件</span><span class="sxs-lookup"><span data-stu-id="0baae-134">Prerequisites for integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[<span data-ttu-id="0baae-135">Microsoft Lync Server 2013 および Microsoft Exchange Server 2013 でパートナーアプリケーションを構成する</span><span class="sxs-lookup"><span data-stu-id="0baae-135">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[<span data-ttu-id="0baae-136">Microsoft Exchange Server 2013 アーカイブを使用するように Microsoft Lync Server 2013 を構成する</span><span class="sxs-lookup"><span data-stu-id="0baae-136">Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving</span></span>](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[<span data-ttu-id="0baae-137">Microsoft SharePoint Server 2013 を構成してアーカイブされた Microsoft Lync Server 2013 データを検索する</span><span class="sxs-lookup"><span data-stu-id="0baae-137">Configuring Microsoft SharePoint Server 2013 to search for archived Microsoft Lync Server 2013 data</span></span>](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[<span data-ttu-id="0baae-138">ユニファイド連絡先ストアを使用するように Microsoft Lync Server 2013 を構成する</span><span class="sxs-lookup"><span data-stu-id="0baae-138">Configuring Microsoft Lync Server 2013 to use the unified contact store</span></span>](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[<span data-ttu-id="0baae-139">Microsoft Lync Server 2013 で高解像度の写真を使用するように構成する</span><span class="sxs-lookup"><span data-stu-id="0baae-139">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</span></span>](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[<span data-ttu-id="0baae-140">Microsoft Lync Server 2013 用 Microsoft Exchange Server 2013 ユニファイドメッセージングの構成ボイスメール</span><span class="sxs-lookup"><span data-stu-id="0baae-140">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[<span data-ttu-id="0baae-141">Microsoft Lync Server 2013 と Microsoft Outlook Web App 2013 の統合</span><span class="sxs-lookup"><span data-stu-id="0baae-141">Integrating Microsoft Lync Server 2013 and Microsoft Outlook Web App 2013</span></span>](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


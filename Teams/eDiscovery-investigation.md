---
title: Microsoft Teams のコンテンツに対して電子情報開示の調査を行う
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: 訴訟手続きのためにすべての電子保持情報を提出する必要がある場合など、電子情報開示を実施するために必要な手続きについて説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54ccb21e33c6acc1747023fc7c3eb174040d5746
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2019
ms.locfileid: "30461805"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="87f9f-103">Microsoft Teams のコンテンツに対して電子情報開示の調査を行う</span><span class="sxs-lookup"><span data-stu-id="87f9f-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>
============================

<span data-ttu-id="87f9f-104">大企業は、多くの場合、提出書類のすべて電子的に格納されている情報 (ESI) を必要とするペナルティの法的手続きに公開されます。</span><span class="sxs-lookup"><span data-stu-id="87f9f-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="87f9f-p101">すべての 1 対 1 のチームまたはグループのチャットは、各ユーザーのメールボックスに、履歴として保存されたと、すべてのチャネル メッセージは、チームを表すグループのメールボックスを履歴として保存されました。アップロードされたファイルは、SharePoint Online およびビジネスのための OneDrive の電子的証拠開示機能で説明します。</span><span class="sxs-lookup"><span data-stu-id="87f9f-p101">All Teams 1:1 or group chats are journaled through to the respective users’ mailboxes, and all channel messages are journaled through to the group mailbox representing the team. Files uploaded are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

1.  <span data-ttu-id="87f9f-107">マイクロソフトのチームのコンテンツを電子的証拠開示調査を実施するには、[この](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da)リンクでは、手順 1 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87f9f-107">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2.  <span data-ttu-id="87f9f-108">IM とマイクロソフトのチームのデータが表示されます、出力をエクスポートする Excel の電子的証拠開示での会話やマウントすることができます、します。これらのメッセージを表示するのには Outlook の PST は、エクスポートを転記します。</span><span class="sxs-lookup"><span data-stu-id="87f9f-108">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can mount the .PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="87f9f-109">マウントするとします。チーム、チーム チャットで会話の履歴フォルダー内のすべての会話が保存されているメモの PST です。</span><span class="sxs-lookup"><span data-stu-id="87f9f-109">When mounting the .PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="87f9f-110">メッセージのタイトルは、チームおよびチャネルに配置します。</span><span class="sxs-lookup"><span data-stu-id="87f9f-110">The title of the message aligns to Team and Channel.</span></span> <span data-ttu-id="87f9f-111">下の画像を確認するには、製造仕様のチームのプロジェクトの 7 チャネル メッセージの数に Bob からのこのメッセージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="87f9f-111">From reviewing the image below, you can see this message from Bob who messaged the Project 7 channel of the Manufacturing Specs team.</span></span>

    ![チーム チャット Outlook でユーザーのメールボックス フォルダーのスクリーン ショット](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  <span data-ttu-id="87f9f-113">ユーザーのメールボックスのプライベート チャットは、会話履歴のチーム チャット フォルダーにも格納されています。</span><span class="sxs-lookup"><span data-stu-id="87f9f-113">To see private chats in a user’s Mailbox, they are also located inside the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-guest-to-guest-chats"></a><span data-ttu-id="87f9f-114">ゲストからゲストのチャットについては、電子的証拠開示</span><span class="sxs-lookup"><span data-stu-id="87f9f-114">eDiscovery of guest-to-guest chats</span></span>

<span data-ttu-id="87f9f-115">ゲストからゲストへのチャット、メールボックスを持たない (1xN のチャットは、ユーザーがホームのテナントがない) がないインデックスを作成して、結果として、電子的証拠開示では含まれない。</span><span class="sxs-lookup"><span data-stu-id="87f9f-115">Without a mailbox, guest-to-guest chats (1xN chats in which there are no home tenant users) would not be indexed, and as a result, would not be included in eDiscovery.</span></span> <span data-ttu-id="87f9f-116">ゲストからゲストのチャットの電子的証拠開示をさせるために、1xN データを格納するクラウド ベースのメールボックス (またはメールボックスの幻) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="87f9f-116">To facilitate eDiscovery for guest-to-guest chats, a cloud-based mailbox (or phantom mailbox) is created to store the 1xN data.</span></span> <span data-ttu-id="87f9f-117">チーム チャットのデータは、クラウド ベースのメールボックスに格納されている後、は、電子的証拠開示およびコンプライアンスのコンテンツの検索にインデックスされます。</span><span class="sxs-lookup"><span data-stu-id="87f9f-117">After the Teams chat data is stored in the cloud-based mailbox, it is indexed for eDiscovery and compliance content search.</span></span>

<span data-ttu-id="87f9f-118">次の図では、ゲストからゲストのチャット、メールボックスがない、電子的証拠開示のしくみを示しています。</span><span class="sxs-lookup"><span data-stu-id="87f9f-118">The following illustration shows how eDiscovery works for guest-to-guest chats in which there isn’t a mailbox.</span></span>

![guest-to-guest-chats-with-no-mailbox](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)

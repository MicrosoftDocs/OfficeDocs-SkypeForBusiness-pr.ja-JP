---
title: Microsoft Teams のコンテンツに対して電子情報開示の調査を行う
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: 訴訟手続きのためにすべての電子保持情報を提出する必要がある場合など、電子情報開示を実施するために必要な手続きについて説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6831ec2cef16e65e2fd8dd722d436c12b7548a5c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236360"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="39bb0-103">Microsoft Teams のコンテンツに対して電子情報開示の調査を行う</span><span class="sxs-lookup"><span data-stu-id="39bb0-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>
============================

<span data-ttu-id="39bb0-104">大企業は、多くの場合、電子的に保存されている情報 (ESI) の申請を要求する高ペナルティ法的手続きにさらされています。</span><span class="sxs-lookup"><span data-stu-id="39bb0-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="39bb0-105">すべての Teams 1:1 またはグループチャットは、それぞれのユーザーのメールボックスにジャーナリングされ、すべてのチャネルメッセージは、チームを表すグループメールボックスにジャーナリングされます。</span><span class="sxs-lookup"><span data-stu-id="39bb0-105">All Teams 1:1 or group chats are journaled through to the respective users’ mailboxes, and all channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="39bb0-106">アップロードされたファイルについては、SharePoint Online と OneDrive for business の電子情報開示機能の下に記載されています。</span><span class="sxs-lookup"><span data-stu-id="39bb0-106">Files uploaded are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

1.  <span data-ttu-id="39bb0-107">Microsoft Teams のコンテンツで電子情報開示の調査を実施するには、[この](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da)リンクの手順1を確認してください。</span><span class="sxs-lookup"><span data-stu-id="39bb0-107">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2.  <span data-ttu-id="39bb0-108">Microsoft Teams のデータは、Excel eDiscovery のエクスポート出力で IM または会話として表示され、をマウントすることができます。[Outlook の PST からエクスポート後のメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="39bb0-108">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can mount the .PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="39bb0-109">をマウントします。[PST] チームの場合は、すべてのスレッドが [会話履歴] の下にあるチームチャットフォルダーに保存されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="39bb0-109">When mounting the .PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="39bb0-110">メッセージのタイトルは、チームとチャネルに揃えて配置されます。</span><span class="sxs-lookup"><span data-stu-id="39bb0-110">The title of the message aligns to Team and Channel.</span></span> <span data-ttu-id="39bb0-111">以下の画像を確認すると、製造仕様チームのプロジェクト7チャネルを送信先しているボブからのメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39bb0-111">From reviewing the image below, you can see this message from Bob who messaged the Project 7 channel of the Manufacturing Specs team.</span></span>

    ![Outlook のユーザーのメールボックス内のチームチャットフォルダーのスクリーンショット](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  <span data-ttu-id="39bb0-113">ユーザーのメールボックスのプライベート チャットは、会話履歴のチーム チャット フォルダーにも格納されています。</span><span class="sxs-lookup"><span data-stu-id="39bb0-113">To see private chats in a user’s Mailbox, they are also located inside the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-guest-to-guest-chats"></a><span data-ttu-id="39bb0-114">ゲスト間のチャットの電子情報開示</span><span class="sxs-lookup"><span data-stu-id="39bb0-114">eDiscovery of guest-to-guest chats</span></span>

<span data-ttu-id="39bb0-115">メールボックスがなくても、ゲスト間のチャット (ホームテナントのユーザーがいない1xN のチャット) にはインデックスが作成されず、結果として電子情報開示に含まれません。</span><span class="sxs-lookup"><span data-stu-id="39bb0-115">Without a mailbox, guest-to-guest chats (1xN chats in which there are no home tenant users) would not be indexed, and as a result, would not be included in eDiscovery.</span></span> <span data-ttu-id="39bb0-116">ゲスト間チャットの電子情報開示を容易にするために、クラウドベースのメールボックス (またはファントムのメールボックス) を作成して、1xN データを保存します。</span><span class="sxs-lookup"><span data-stu-id="39bb0-116">To facilitate eDiscovery for guest-to-guest chats, a cloud-based mailbox (or phantom mailbox) is created to store the 1xN data.</span></span> <span data-ttu-id="39bb0-117">チームチャットデータがクラウドベースのメールボックスに保存された後、電子情報開示およびコンプライアンスコンテンツ検索のインデックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="39bb0-117">After the Teams chat data is stored in the cloud-based mailbox, it is indexed for eDiscovery and compliance content search.</span></span>

<span data-ttu-id="39bb0-118">次の図は、メールボックスがないゲスト間チャットでの電子情報開示の動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="39bb0-118">The following illustration shows how eDiscovery works for guest-to-guest chats in which there isn’t a mailbox.</span></span>

![ゲスト間-チャット-メールボックスなし](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)

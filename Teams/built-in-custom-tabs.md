---
title: Microsoft Teams で組み込みタブとカスタム タブを使用する
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/20/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
f1.keywords:
- NOCSH
search.appverid: MET150
description: 組み込みタブやカスタム タブを使用して会話、ファイル、地図などの機能を追加する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: f98024b10cf6fc191e9225a447903ff6dc25d6ff
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203720"
---
<a name="use-built-in-and-custom-tabs-in-microsoft-teams"></a><span data-ttu-id="92568-103">Microsoft Teams で組み込みタブとカスタム タブを使用する</span><span class="sxs-lookup"><span data-stu-id="92568-103">Use built-in and custom tabs in Microsoft Teams</span></span>
==================================================

<span data-ttu-id="92568-104">タブを使用すると、チームのメンバーはチャネル内の専用スペースまたはチャットでサービスとコンテンツにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="92568-104">Tabs allow team members to access services and content in a dedicated space within a channel or in a chat.</span></span> <span data-ttu-id="92568-105">これにより、チームはチャネルやチャットのコンテキストのみでツールやデータを直接操作することや、ツールやデータについて会話することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="92568-105">This lets the team work directly with tools and data, and have conversations about the tools and data, all within the context of the channel or chat.</span></span>

<span data-ttu-id="92568-106">所有者とチーム メンバーは、チャネル、プライベート チャット、およびグループ チャットにタブを追加して、クラウド サービスの統合に役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="92568-106">Owners and team members can add tabs to a channel, private chat, and group chat to help integrate their cloud services.</span></span> <span data-ttu-id="92568-107">タブは、ユーザーにとって必要なデータや頻繁に操作するデータへのアクセスと管理を簡単にするために追加できます。</span><span class="sxs-lookup"><span data-stu-id="92568-107">Tabs can be added to help users easily access and manage the data they need or interact with the most.</span></span> <span data-ttu-id="92568-108">これは、Power BI レポート、ダッシュボード、またはトレーニング ビデオを公開する [Microsoft Stream](https://go.microsoft.com/fwlink/?linkid=855785) ビデオ チャネルです。</span><span class="sxs-lookup"><span data-stu-id="92568-108">This can be a Power BI report, a dashboard, or even a [Microsoft Stream](https://go.microsoft.com/fwlink/?linkid=855785) video channel where you publish training videos.</span></span>

![タブにある色々なコンテンツの 3 つのスクリーンショット](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image4.png)

>[!Note]
> <span data-ttu-id="92568-p103">Microsoft Stream の使用から[会議の記録用の OneDrive for Business および SharePoint ](tmr-meeting-recording-change.md)への変更は段階的なアプローチになります。リリース時には、この機能にオプトインできるようになります。Stream を使い続けるには、11 月にオプトアウトする必要があります。また、2021 年初頭には、すべてのお客様に、新しい会議の記録に OneDrive と SharePoint を使用するように要請する予定です。</span><span class="sxs-lookup"><span data-stu-id="92568-p103">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

## <a name="work-with-tabs"></a><span data-ttu-id="92568-112">タブを操作する</span><span class="sxs-lookup"><span data-stu-id="92568-112">Work with tabs</span></span>

- <span data-ttu-id="92568-113">新しいチャネルでは、[会話] と [ファイル] という 2 つのタブが既定で用意されています。</span><span class="sxs-lookup"><span data-stu-id="92568-113">With every new channel, two tabs are provisioned by default: Conversations and Files.</span></span>

    ![マーケティング チームの会話セクションのスクリーンショット。](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image1.png)
- <span data-ttu-id="92568-115">すべてのプライベート チャットには、[会話]、[ファイル]、[組織]、および [アクティビティ] のタブが既定で用意されています。</span><span class="sxs-lookup"><span data-stu-id="92568-115">With every private chat, four tabs are provisioned by default: Conversations, Files, Organization, and Activity.</span></span>

    ![チャットのタブのスクリーンショット。](media/Use_built-in_and_custom_tabs_add_tabs_to_a_chat.png)

- <span data-ttu-id="92568-117">所有者とチーム メンバーは、チャネルまたはチャットの上部にある [**タブの追加**] (![[タブの追加] ボタンのスクリーンショット、+ 記号を表示](media/Use_built-in_and_custom_tabs_add_a_tab_button.png)) をクリックして</span><span class="sxs-lookup"><span data-stu-id="92568-117">Owners and team members can add more tabs to a channel or chat by clicking **Add a tab** ![Screenshot of the Add a tab button, showing a + sign.](media/Use_built-in_and_custom_tabs_add_a_tab_button.png)</span></span> <span data-ttu-id="92568-118">チャネルまたはチャットにより多くのタブを追加できます。</span><span class="sxs-lookup"><span data-stu-id="92568-118">at the top of the channel or chat.</span></span>

- <span data-ttu-id="92568-119">Excel、PowerPoint、Word、および PDF ファイルは、タブに変換する前に [**ファイル**] タブにアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="92568-119">Excel, PowerPoint, Word, and PDF files must be uploaded to the **Files** tab before they can be converted to tabs.</span></span> <span data-ttu-id="92568-120">以下に示すように、既存のアップロードされたファイルは、一度のクリック操作でタブに変換できます。</span><span class="sxs-lookup"><span data-stu-id="92568-120">Any existing uploaded file can be converted to a tab with a single click, as shown below.</span></span>

    ![PowerPoint ファイルが選択された [ファイル] タブのスクリーンショット。](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image2.png)

- <span data-ttu-id="92568-122">Web サイトを追加するには、URLの先頭に **https** 接頭辞を付けて、交換される情報のセキュリティを確保する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92568-122">To add a website, the URL must start with an **https** prefix so information that's exchanged remains secure.</span></span>

- <span data-ttu-id="92568-123">チーム メンバーがチャネルまたはチャットにカスタム タブを追加しようとすると、詳細な手順が提供されます。</span><span class="sxs-lookup"><span data-stu-id="92568-123">Detailed instructions are provided when a team member tries to add a custom tab to their channel or chat.</span></span> <span data-ttu-id="92568-124">チャネルにカスタム タブを追加すると、**タブの会話** が作成され、チーム メンバーはそこでコンテンツに関する集中的なディスカッションを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="92568-124">When a custom tab is added to a channel, a **Tab conversation** is created that allows team members to have focused discussions about the content.</span></span>

    ![右側にあるタブの会話が含まれているカスタム タブのスクリーンショット。](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image3.png)

## <a name="develop-custom-tabs"></a><span data-ttu-id="92568-126">ユーザー設定のタブを開発する</span><span class="sxs-lookup"><span data-stu-id="92568-126">Develop custom tabs</span></span>

<span data-ttu-id="92568-127">組み込みのタブに加えて、独自のタブを設計して開発することもできます。このタブは、Teams に統合することも、別のコミュニティと共有することもできます。</span><span class="sxs-lookup"><span data-stu-id="92568-127">In addition to the built-in tabs, you can design and develop your own tabs to integrate to Teams or share with the rest of the community.</span></span> <span data-ttu-id="92568-128">詳細については、「[開発者向けドキュメント](/microsoftteams/platform/tabs/what-are-tabs)」を参照してください:</span><span class="sxs-lookup"><span data-stu-id="92568-128">See our [developer documentation](/microsoftteams/platform/tabs/what-are-tabs) for more information.</span></span>

![Microsoft Teams のサンプル カスタム タブのスクリーンショット。](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image5.png)

---

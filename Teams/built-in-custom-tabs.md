---
title: "Microsoft チームで組み込みおよびユーザー設定のタブを使用します。"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "スレッド、ファイル、マップなどの機能を組み込む組み込みおよびユーザー設定のタブを使用する方法について説明します。"
ms.openlocfilehash: c4b76efc6c845eea36d4fc7ed9e4c34b0ec5e58e
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="use-built-in-and-custom-tabs-in-microsoft-teams"></a><span data-ttu-id="96890-103">Microsoft チームで組み込みおよびユーザー設定のタブを使用します。</span><span class="sxs-lookup"><span data-stu-id="96890-103">Use built-in and custom tabs in Microsoft Teams</span></span>
==================================================

<span data-ttu-id="96890-p101">タブには、チャンネル内の専用キャンバス上のサービスにアクセスするチーム メンバーができるようにします。これにより、チームの直接ツールと入力すると、データとは、チャンネルのコンテキストでの会話を作業できます。新しいチャネルごとに、2 つのタブを既定では、準備一覧されているの下にある、イメージに表示されます。</span><span class="sxs-lookup"><span data-stu-id="96890-p101">Tabs allow team members to access services on a dedicated canvas within a channel. This lets the team work directly with the tools and data you provide, and to have conversations about them, in the channel’s context. With every new channel, two tabs are provisioned by default, as listed and shown in the image, below:</span></span>

-   <span data-ttu-id="96890-107">スレッド</span><span class="sxs-lookup"><span data-stu-id="96890-107">Conversations</span></span>

-   <span data-ttu-id="96890-108">ファイル</span><span class="sxs-lookup"><span data-stu-id="96890-108">Files</span></span>

![マーケティング チームの [会話] セクションのスクリーン ショット。](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image1.png)

1.  <span data-ttu-id="96890-110">チーム メンバーと所有者の場合は、そのクラウド サービスの統合のために、各チャンネルにその他のタブを追加できます。</span><span class="sxs-lookup"><span data-stu-id="96890-110">Owners and team members can add additional tabs, to each channel, to help integrate their cloud services.</span></span>

2.  <span data-ttu-id="96890-p102">Excel、PowerPoint、Word および PDF ファイルは前のタブに変換されることに、、[**ファイル] タブの [**にアップロードする必要があります。または、いずれかの既存のアップロード、ファイルに変換できる 1 回のクリック] タブ次のようにします。</span><span class="sxs-lookup"><span data-stu-id="96890-p102">Excel, PowerPoint, Word and PDF files must be uploaded to the **Files tab** before they can be converted to tabs. Alternatively, any existing uploaded, files can be converted into tabs with a single click, as shown below.</span></span>

    ![選択されている PowerPoint ファイルを使用して、[ファイル] タブのスクリーン ショット。](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image2.png)

3.  <span data-ttu-id="96890-114">Web サイトを追加するには、URL は必要があります交換情報がセキュリティで保護されたが保持されるよう**https プレフィックス**を起動します。</span><span class="sxs-lookup"><span data-stu-id="96890-114">To add a website, the URL must start with an **https prefix,** so that any information exchanged remains secure.</span></span>

4.  <span data-ttu-id="96890-115">チーム メンバーが、そのチャンネルにユーザー設定] タブを追加しようとすると、詳細な指示が提供されます。</span><span class="sxs-lookup"><span data-stu-id="96890-115">Detailed instructions are provided when a team member attempts to add a custom tab into their channel.</span></span>

5.  <span data-ttu-id="96890-116">チャンネルに、ユーザー設定] タブが追加されると、チーム メンバーが、コンテンツについてのディスカッションに重点を置いたができるようにする**] タブの [会話**が作成されます。</span><span class="sxs-lookup"><span data-stu-id="96890-116">When a Custom tab is added into a channel, a **Tab conversation** is created that allows team members to have focused discussions about the content.</span></span>

    ![ウィンドウの右上にある] タブの [会話のカスタム タブのスクリーン ショット。](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image3.png)

6.  <span data-ttu-id="96890-p103">ユーザーが簡単にアクセスし、必要がありますが、または最もよくやり取りするデータを管理するためにチャンネルにその他のタブを追加できます。Power BI レポート、ダッシュ ボード、またはも[Microsoft ストリーム](https://go.microsoft.com/fwlink/?linkid=855785)ビデオ チャンネルのトレーニング ビデオを発行することができます。</span><span class="sxs-lookup"><span data-stu-id="96890-p103">Additional tabs can be added to channels to help users easily access and manage the data they need or interact with the most. This can be a Power BI report, a dashboard, or even a [Microsoft Stream](https://go.microsoft.com/fwlink/?linkid=855785) video channel where you publish training videos.</span></span>

    ![タブのさまざまなコンテンツの 3 つのスクリーン ショット。](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image4.png)

<a name="develop-custom-tabs"></a><span data-ttu-id="96890-121">カスタム タブを作成します。</span><span class="sxs-lookup"><span data-stu-id="96890-121">Develop custom tabs</span></span>
-------------------

<span data-ttu-id="96890-122">に加えて、組み込みのタブ、組織が簡単に設計および Microsoft チームに統合されており、コミュニティの残りの部分と共有できる、それぞれのタブを開発することができます。</span><span class="sxs-lookup"><span data-stu-id="96890-122">In addition to the built-in tabs, organizations can easily design and develop their own tabs, that can be integrated into Microsoft Teams, or shared with the rest of the community.</span></span>

<span data-ttu-id="96890-123">Microsoft 開発ネットワーク設計し、独自のタブを作成する[詳細な手順](https://go.microsoft.com/fwlink/?linkid=855786)を提供します。ダウンロードし、Microsoft が開発した[サンプルのタブ](https://go.microsoft.com/fwlink/?linkid=855787)を配置します。</span><span class="sxs-lookup"><span data-stu-id="96890-123">The Microsoft Developer Network provides [detailed instructions](https://go.microsoft.com/fwlink/?linkid=855786) to design and build your own tabs; and download and deploy [sample tabs](https://go.microsoft.com/fwlink/?linkid=855787) developed by Microsoft.</span></span>

![Microsoft のチームでの例のカスタム タブのスクリーン ショット。](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image5.png)

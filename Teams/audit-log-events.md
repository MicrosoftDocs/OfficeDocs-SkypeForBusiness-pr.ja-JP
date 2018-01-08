---
title: "Microsoft Teams でイベントの監査ログを検索する"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "監査ログから Microsoft Teams データを取得する方法について説明します。"
ms.openlocfilehash: bea1a808fd92d3b43caf8ee61152a999ca3af8a3
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/20/2017
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="8f0db-103">Microsoft Teams でイベントの監査ログを検索する</span><span class="sxs-lookup"><span data-stu-id="8f0db-103">Search the audit log for events in Microsoft Teams</span></span>
==================================================

<span data-ttu-id="8f0db-p101">監査ログにより、Office 365 サービス全体の重要なイベントをアドホック検索できます。具体的に Microsoft Teams の場合は、次のようなイベントがキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="8f0db-p101">The Audit Log provides ad-hoc search capabilities into notable events across Office 365 services. For Microsoft Teams specifically, below are a few examples of events captured:</span></span>

-   <span data-ttu-id="8f0db-106">チームの作成</span><span class="sxs-lookup"><span data-stu-id="8f0db-106">Team Creation</span></span>

-   <span data-ttu-id="8f0db-107">チームの削除</span><span class="sxs-lookup"><span data-stu-id="8f0db-107">Team Deletion</span></span>

-   <span data-ttu-id="8f0db-108">追加されたチャネル</span><span class="sxs-lookup"><span data-stu-id="8f0db-108">Added Channel</span></span>

-   <span data-ttu-id="8f0db-109">変更された設定</span><span class="sxs-lookup"><span data-stu-id="8f0db-109">Changed Setting</span></span>

<span data-ttu-id="8f0db-110">Office 365 全体についての完全なイベント リストは広範囲に及びます。リストは[ここ](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities)で入手することができます。</span><span class="sxs-lookup"><span data-stu-id="8f0db-110">The complete event list across Office 365 is quite extensive and can be found [here](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities).</span></span>

<span data-ttu-id="8f0db-p102">監査の内容を調査する前に、監査を有効にする必要があります。監査を有効にするには、*セキュリティとコンプライアンス*管理センターに移動します。[*Search for activity (アクティビティの検索)*] で [**Start recording now (すぐにレコーディングを開始)** をクリックします。24 時間後に [*Search & Investigation (検索と調査)*] タブの下にある [*監査ログの検索*] で監査データが利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="8f0db-p102">Before you can dig into audit insights, auditing must first be enabled. To enable Auditing, navigate to the *Security & Compliance* Admin Center. Under *Search for activity*, click on **Start recording now**. After 24hrs, audit data will be available via *Audit Log Search* located under the *Search & Investigation* tab.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="8f0db-115">利用できる監査データは、監査を有効にした時点以降のデータのみです。</span><span class="sxs-lookup"><span data-stu-id="8f0db-115">Audit data is only available from the point at which Auditing was enabled.</span></span>



![セキュリティとコンプライアンス センターの [Audit log search (監査ログの検索)] ページのスクリーンショット。](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image2.png)

<span data-ttu-id="8f0db-117">監査ログから Microsoft Teams データを取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8f0db-117">Now, let’s look at how to retrieve Microsoft Teams data from the Audit Log:</span></span>

1.  <span data-ttu-id="8f0db-p103">監査ログ情報を取得するには [セキュリティとコンプライアンス管理センター](https://go.microsoft.com/fwlink/?linkid=855775)に移動します。[*Search & Investigation (検索と調査)*] タブで [**Audit log search (監査ログの検索)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f0db-p103">To retrieve Audit Log information, navigate to the [Security & Compliance Admin Center](https://go.microsoft.com/fwlink/?linkid=855775). Under *Search & Investigation*, select **Audit log search.**</span></span>

    <span data-ttu-id="8f0db-p104">a.  Microsoft Teams では、選択可能な監査アクティビティを次のように定義しています。</span><span class="sxs-lookup"><span data-stu-id="8f0db-p104">a.  Microsoft Teams has defined audit activities that can be selected as shown below.</span></span>

![セキュリティとコンプライアンス センターの [Audit log search (監査ログの検索)] ページのスクリーンショット。](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)

2.  <span data-ttu-id="8f0db-p105">関心のあるアクティビティを選択したら、Microsoft Teams 情報の取得の対象とするデータ範囲とユーザーを指定します。[**検索**] をクリックして、結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="8f0db-p105">After selecting the activities of interest, supply a date range and users to retrieve Microsoft Teams information from. Click **Search** to retrieve the results.</span></span>

3.  <span data-ttu-id="8f0db-125">この情報は、必要に応じて Excel にエクスポートしたり、フィルタリングできます。</span><span class="sxs-lookup"><span data-stu-id="8f0db-125">This information can be exported to Excel and filtered as needed.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="8f0db-126">これまで監査が有効でなかった場合は、監査を有効にしないと、データが監査ログに表示されません。</span><span class="sxs-lookup"><span data-stu-id="8f0db-126">If auditing has not been enabled previously, that needs to be enabled before data will appear in the Audit Log.</span></span>



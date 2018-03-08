---
title: "Microsoft チームのイベントの監査ログを検索します。"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 01/22/2018
ms.topic: article
ms.service: msteams
description: "監査ログの Office 365 から Microsoft チームのデータを取得する方法について説明します。"
ms.openlocfilehash: 229ddc5fb1e8a775524564c27ffeecce96483fe1
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="9a283-103">Microsoft チームのイベントの監査ログを検索します。</span><span class="sxs-lookup"><span data-stu-id="9a283-103">Search the audit log for events in Microsoft Teams</span></span>
==================================================

<span data-ttu-id="9a283-p101">監査ログは、Office 365 サービスで特定の活動を調査するのに役立ちます。チームが、監査するアクティビティの一部は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9a283-p101">The audit log can help you investigate specific activities across Office 365 services. For Teams, here are some of the activities that are audited:</span></span>

-   <span data-ttu-id="9a283-106">チームの作成</span><span class="sxs-lookup"><span data-stu-id="9a283-106">Team creation</span></span>

-   <span data-ttu-id="9a283-107">チームの削除</span><span class="sxs-lookup"><span data-stu-id="9a283-107">Team deletion</span></span>

-   <span data-ttu-id="9a283-108">チャンネルの追加</span><span class="sxs-lookup"><span data-stu-id="9a283-108">Added channel</span></span>

-   <span data-ttu-id="9a283-109">設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="9a283-109">Changed setting</span></span>

<span data-ttu-id="9a283-110">Office 365 で監査する活動の一覧を表示するには、 [[Office 365 のセキュリティとコンプライアンス センターの監査ログの検索](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c?=&PickTab=Activities&ad=US#PickTab=Activities)をお読みください。</span><span class="sxs-lookup"><span data-stu-id="9a283-110">To see the complete list of activities that are audited in Office 365, read [Search the audit log in the Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c?=&PickTab=Activities&ad=US#PickTab=Activities).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="9a283-111">チームで監査を有効にします。</span><span class="sxs-lookup"><span data-stu-id="9a283-111">Turn on auditing in Teams</span></span>

<span data-ttu-id="9a283-p102">監査データを表示、前に、最初に、[**セキュリティとコンプライアンス センター**(https://protection.office.com) で監査があります。監査の有効化については、[有効にする Office 365 のオンとオフを切り替える監査ログの検索](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a283-p102">Before you can look at audit data, you have to first turn on auditing in the **Security & Compliance Center**(https://protection.office.com). For help turning on auditing, read [Turn Office 365 audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="9a283-114">監査データには、に対して監査を有効にするポイントからできるだけです。</span><span class="sxs-lookup"><span data-stu-id="9a283-114">Audit data is only available from the point at which you turned on Auditing.</span></span>



## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="9a283-115">監査ログからチームのデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="9a283-115">Retrieve Teams data from the audit log</span></span>

1.  <span data-ttu-id="9a283-p103">監査ログを取得するには、[[セキュリティとコンプライアンス センター](https://go.microsoft.com/fwlink/?linkid=855775)に移動します。**検索と調査**、**監査ログの検索対象**を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a283-p103">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775). Under **Search & Investigation**, select **Audit log search**.</span></span>

![[セキュリティとコンプライアンス センターの監査ログの検索ページのスクリーン ショット。](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)

2.  <span data-ttu-id="9a283-119">**検索**を使用して、アクティビティ、日付、またはユーザーを監査するフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="9a283-119">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>

3.  <span data-ttu-id="9a283-120">詳細分析用の結果を Excel にエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="9a283-120">Export your results to Excel for further analysis.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="9a283-121">監査データを監査ログに表示されるは、監査がオンの場合だけです。</span><span class="sxs-lookup"><span data-stu-id="9a283-121">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="9a283-122">ビデオ: TechTip: チームで監査ログの検索を使用します。</span><span class="sxs-lookup"><span data-stu-id="9a283-122">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="9a283-123">Ansuman Acharya、チームのプログラム マネージャーは、[Office 365 のセキュリティとコンプライアンス センター チームの監査ログ レポートを検索を行う彼に示すように参加します。</span><span class="sxs-lookup"><span data-stu-id="9a283-123">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span> 


> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]







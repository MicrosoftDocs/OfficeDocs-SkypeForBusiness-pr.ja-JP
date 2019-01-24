---
title: Microsoft Teams での保持ポリシーの既知の問題
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: Microsoft Teams の保持ポリシーに関する既知の問題の最新リストです。
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2b6d71a1b2422dfadfbc7ae0fb87e607fd288152
ms.sourcegitcommit: 5e8d04bbc3eb1a57fed893e5ff929674b4297851
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2018
ms.locfileid: "25004587"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a><span data-ttu-id="77f32-103">Microsoft Teams での保持ポリシーの既知の問題</span><span class="sxs-lookup"><span data-stu-id="77f32-103">Known issues for retention policies in Microsoft Teams</span></span>

<span data-ttu-id="77f32-104">現在追跡および調査されている Teams の保持ポリシーに関する既知の問題を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="77f32-104">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="77f32-105">Teams のチャネル メッセージの場所の行にある [チームの選択] の下で、Teams ではない Office 365 グループが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="77f32-105">Under Choose Teams in the Teams Channel messages location row, you may see Office 365 Groups that are not also Teams.</span></span> <span data-ttu-id="77f32-106">この問題は、今後解決される予定です。</span><span class="sxs-lookup"><span data-stu-id="77f32-106">This will be addressed in the future.</span></span>

- <span data-ttu-id="77f32-107">Teams のチャットの場所の行にある [ユーザーの選択] の下で、ゲストやメールボックスのユーザーでない人が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="77f32-107">Under Choose Users in the Teams Chat location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="77f32-108">保持ポリシーはゲストのために設定されるものではありませんので、現在これらの表示をリストから削除するよう取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="77f32-108">Retention policies are not meant to be set for guests, and we are working to remove these from the list.</span></span>

- <span data-ttu-id="77f32-109">Exchange Life Cycle アシスタント (ELC) は毎日実行しますが、その SLA は 7 日間です。</span><span class="sxs-lookup"><span data-stu-id="77f32-109">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="77f32-110">このため、60 日以上経過したアイテムを削除する Teams の保持ポリシーを設定している場合、それらのアイテムは最大 67 日間保持される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="77f32-110">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="77f32-111">これは新しい状況ではなく、Exchange の様式によるものです。</span><span class="sxs-lookup"><span data-stu-id="77f32-111">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="77f32-112">多くの場合において、遅延はありません。</span><span class="sxs-lookup"><span data-stu-id="77f32-112">Of course, in most cases, there is no delay.</span></span>


| | | |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |<span data-ttu-id="77f32-114">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="77f32-114">Decision point</span></span>         |<span data-ttu-id="77f32-p104">組織で必要とされているセキュリティとコンプライアンスの機能を教えてください。組織はセキュリティとコンプライアンスのビジネス要件を満たすために必要なライセンスを所有していますか?</span><span class="sxs-lookup"><span data-stu-id="77f32-p104">What security and compliance features does your organization require? Does your organization have the required licenses to meet Security and Compliance business requirements?</span></span>         |
|![次のステップ アイコン。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |<span data-ttu-id="77f32-118">次のステップ</span><span class="sxs-lookup"><span data-stu-id="77f32-118">Next steps</span></span>         |<span data-ttu-id="77f32-119">必須のセキュリティとコンプライアンスの機能を文書化します。</span><span class="sxs-lookup"><span data-stu-id="77f32-119">Document the required security and compliance features in the table below.</span></span>         |

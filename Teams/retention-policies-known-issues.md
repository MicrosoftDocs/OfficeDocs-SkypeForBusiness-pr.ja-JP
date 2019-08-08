---
title: Microsoft Teams での保持ポリシーの既知の問題
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anach
description: Microsoft Teams の保持ポリシーに関する既知の問題の最新リストです。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b13fc5347338b28c877b224f758c79513e379391
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243610"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a><span data-ttu-id="611e1-103">Microsoft Teams での保持ポリシーの既知の問題</span><span class="sxs-lookup"><span data-stu-id="611e1-103">Known issues for retention policies in Microsoft Teams</span></span>

<span data-ttu-id="611e1-104">現在追跡および調査されている Teams の保持ポリシーに関する既知の問題を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="611e1-104">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="611e1-105">Teams のチャネル メッセージの場所の行にある [チームの選択] の下で、Teams ではない Office 365 グループが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="611e1-105">Under Choose Teams in the Teams Channel messages location row, you may see Office 365 Groups that are not also Teams.</span></span> <span data-ttu-id="611e1-106">この問題は、今後解決される予定です。</span><span class="sxs-lookup"><span data-stu-id="611e1-106">This will be addressed in the future.</span></span>

- <span data-ttu-id="611e1-107">Teams のチャットの場所の行にある [ユーザーの選択] の下で、ゲストやメールボックスのユーザーでない人が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="611e1-107">Under Choose Users in the Teams Chat location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="611e1-108">保持ポリシーはゲストのために設定されるものではありませんので、現在これらの表示をリストから削除するよう取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="611e1-108">Retention policies are not meant to be set for guests, and we are working to remove these from the list.</span></span>

- <span data-ttu-id="611e1-109">Exchange Life Cycle アシスタント (ELC) は毎日実行しますが、その SLA は 7 日間です。</span><span class="sxs-lookup"><span data-stu-id="611e1-109">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="611e1-110">このため、60 日以上経過したアイテムを削除する Teams の保持ポリシーを設定している場合、それらのアイテムは最大 67 日間保持される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="611e1-110">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="611e1-111">これは新しい状況ではなく、Exchange の様式によるものです。</span><span class="sxs-lookup"><span data-stu-id="611e1-111">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="611e1-112">多くの場合において、遅延はありません。</span><span class="sxs-lookup"><span data-stu-id="611e1-112">Of course, in most cases, there is no delay.</span></span>


| | | |
|---------|---------|---------|
|![判断ポイントを表すアイコン](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |<span data-ttu-id="611e1-114">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="611e1-114">Decision point</span></span>         |<span data-ttu-id="611e1-p104">組織で必要とされているセキュリティとコンプライアンスの機能を教えてください。組織はセキュリティとコンプライアンスのビジネス要件を満たすために必要なライセンスを所有していますか?</span><span class="sxs-lookup"><span data-stu-id="611e1-p104">What security and compliance features does your organization require? Does your organization have the required licenses to meet Security and Compliance business requirements?</span></span>         |
|![次の手順を示すアイコン](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |<span data-ttu-id="611e1-118">次のステップ</span><span class="sxs-lookup"><span data-stu-id="611e1-118">Next steps</span></span>         |<span data-ttu-id="611e1-119">必須のセキュリティとコンプライアンスの機能を文書化します。</span><span class="sxs-lookup"><span data-stu-id="611e1-119">Document your required security and compliance features.</span></span>         |

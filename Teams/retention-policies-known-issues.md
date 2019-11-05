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
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5565409ea2f3dbb83754ced08a78e12283b1601c
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968338"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a><span data-ttu-id="1e5ed-103">Microsoft Teams での保持ポリシーの既知の問題</span><span class="sxs-lookup"><span data-stu-id="1e5ed-103">Known issues for retention policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="1e5ed-104">プライベートチャネルメッセージの保持の構成はまだサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="1e5ed-104">We don’t yet support configuration for retention of private channel messages.</span></span> <span data-ttu-id="1e5ed-105">プライベートチャネルで共有されているファイルの保持はサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1e5ed-105">Retention of files shared in private channels is supported.</span></span>

<span data-ttu-id="1e5ed-106">現在追跡および調査されている Teams の保持ポリシーに関する既知の問題を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="1e5ed-106">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="1e5ed-107">Teams のチャネル メッセージの場所の行にある [チームの選択] の下で、Teams ではない Office 365 グループが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="1e5ed-107">Under Choose Teams in the Teams Channel messages location row, you may see Office 365 Groups that are not also Teams.</span></span> <span data-ttu-id="1e5ed-108">この問題は、今後解決される予定です。</span><span class="sxs-lookup"><span data-stu-id="1e5ed-108">This will be addressed in the future.</span></span>

- <span data-ttu-id="1e5ed-109">Teams のチャットの場所の行にある [ユーザーの選択] の下で、ゲストやメールボックスのユーザーでない人が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="1e5ed-109">Under Choose Users in the Teams Chat location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="1e5ed-110">保持ポリシーはゲストのために設定されるものではありませんので、現在これらの表示をリストから削除するよう取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="1e5ed-110">Retention policies are not meant to be set for guests, and we are working to remove these from the list.</span></span>

- <span data-ttu-id="1e5ed-111">Exchange Life Cycle アシスタント (ELC) は毎日実行しますが、その SLA は 7 日間です。</span><span class="sxs-lookup"><span data-stu-id="1e5ed-111">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="1e5ed-112">このため、60 日以上経過したアイテムを削除する Teams の保持ポリシーを設定している場合、それらのアイテムは最大 67 日間保持される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1e5ed-112">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="1e5ed-113">これは新しい状況ではなく、Exchange の様式によるものです。</span><span class="sxs-lookup"><span data-stu-id="1e5ed-113">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="1e5ed-114">多くの場合において、遅延はありません。</span><span class="sxs-lookup"><span data-stu-id="1e5ed-114">Of course, in most cases, there is no delay.</span></span>


| | | |
|---------|---------|---------|
|![判断ポイントを表すアイコン](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |<span data-ttu-id="1e5ed-116">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="1e5ed-116">Decision point</span></span>         |<span data-ttu-id="1e5ed-p105">組織で必要とされているセキュリティとコンプライアンスの機能を教えてください。組織はセキュリティとコンプライアンスのビジネス要件を満たすために必要なライセンスを所有していますか?</span><span class="sxs-lookup"><span data-stu-id="1e5ed-p105">What security and compliance features does your organization require? Does your organization have the required licenses to meet Security and Compliance business requirements?</span></span>         |
|![次の手順を示すアイコン](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |<span data-ttu-id="1e5ed-120">次のステップ</span><span class="sxs-lookup"><span data-stu-id="1e5ed-120">Next steps</span></span>         |<span data-ttu-id="1e5ed-121">必須のセキュリティとコンプライアンスの機能を文書化します。</span><span class="sxs-lookup"><span data-stu-id="1e5ed-121">Document your required security and compliance features.</span></span>         |

---
title: マイクロソフトのチームでの保存ポリシーの既知の問題
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: マイクロソフトのチーム ・ リテンション ・ ポリシーの既知の問題の現在のリストです。
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2b6d71a1b2422dfadfbc7ae0fb87e607fd288152
ms.sourcegitcommit: 5e8d04bbc3eb1a57fed893e5ff929674b4297851
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2018
ms.locfileid: "25004587"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a><span data-ttu-id="9a9e5-103">マイクロソフトのチームでの保存ポリシーの既知の問題</span><span class="sxs-lookup"><span data-stu-id="9a9e5-103">Known issues for retention policies in Microsoft Teams</span></span>

<span data-ttu-id="9a9e5-104">次既知の問題をされているチームのリテンション ・ ポリシーの追跡し、調査します。</span><span class="sxs-lookup"><span data-stu-id="9a9e5-104">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="9a9e5-105">選択チームのチャネル メッセージの場所の行で、チームでもないチームには、Office 365 のグループを参照してください可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9a9e5-105">Under Choose Teams in the Teams Channel messages location row, you may see Office 365 Groups that are not also Teams.</span></span> <span data-ttu-id="9a9e5-106">これは、将来的に解決されます。</span><span class="sxs-lookup"><span data-stu-id="9a9e5-106">This will be addressed in the future.</span></span>

- <span data-ttu-id="9a9e5-107">チームのチャットの場所の行で [ユーザーの選択] の下、来園者とユーザーのメールボックスではないを表示ことがあります。</span><span class="sxs-lookup"><span data-stu-id="9a9e5-107">Under Choose Users in the Teams Chat location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="9a9e5-108">リテンション ・ ポリシーを来園者を設定する必要はないし、これらの一覧から削除することに努めています。</span><span class="sxs-lookup"><span data-stu-id="9a9e5-108">Retention policies are not meant to be set for guests, and we are working to remove these from the list.</span></span>

- <span data-ttu-id="9a9e5-109">Exchange のライフ サイクルのアシスタント (ELC) は毎日実行されるが、7 日間の SLA。</span><span class="sxs-lookup"><span data-stu-id="9a9e5-109">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="9a9e5-110">結果として、60 日より古いアイテムを削除するのには、チームの保持ポリシーがあれば、これらの項目でした永続化を 67 日間のことができます。</span><span class="sxs-lookup"><span data-stu-id="9a9e5-110">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="9a9e5-111">新しい状況ではありません - 交換モデルに依存しています。</span><span class="sxs-lookup"><span data-stu-id="9a9e5-111">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="9a9e5-112">もちろん、ほとんどの場合、時間はかかりません。</span><span class="sxs-lookup"><span data-stu-id="9a9e5-112">Of course, in most cases, there is no delay.</span></span>


| | | |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |<span data-ttu-id="9a9e5-114">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="9a9e5-114">Decision point</span></span>         |<span data-ttu-id="9a9e5-p104">組織で必要とされているセキュリティとコンプライアンスの機能を教えてください。組織はセキュリティとコンプライアンスのビジネス要件を満たすために必要なライセンスを所有していますか?</span><span class="sxs-lookup"><span data-stu-id="9a9e5-p104">What security and compliance features does your organization require? Does your organization have the required licenses to meet Security and Compliance business requirements?</span></span>         |
|![次のステップ アイコン。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |<span data-ttu-id="9a9e5-118">次のステップ</span><span class="sxs-lookup"><span data-stu-id="9a9e5-118">Next steps</span></span>         |<span data-ttu-id="9a9e5-119">必要なセキュリティとコンプライアンスの機能を文書化します。</span><span class="sxs-lookup"><span data-stu-id="9a9e5-119">Document your required security and compliance features.</span></span>         |

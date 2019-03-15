---
title: Microsoft Teams での保持ポリシーの既知の問題
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: anach
description: Microsoft Teams の保持ポリシーに関する既知の問題の最新リストです。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e64bcb2959060b8237f06a1986f15a093eb321a2
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2019
ms.locfileid: "30641153"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a><span data-ttu-id="0ad07-103">Microsoft Teams での保持ポリシーの既知の問題</span><span class="sxs-lookup"><span data-stu-id="0ad07-103">Known issues for retention policies in Microsoft Teams</span></span>

<span data-ttu-id="0ad07-104">現在追跡および調査されている Teams の保持ポリシーに関する既知の問題を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="0ad07-104">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="0ad07-105">Under Choose Teams in the Teams Channel messages location row, you may see Office 365 Groups that are not also Teams.</span><span class="sxs-lookup"><span data-stu-id="0ad07-105">Under Choose Teams in the Teams Channel messages location row, you may see Office 365 Groups that are not also Teams.</span></span> <span data-ttu-id="0ad07-106">This will be addressed in the future.</span><span class="sxs-lookup"><span data-stu-id="0ad07-106">This will be addressed in the future.</span></span>

- <span data-ttu-id="0ad07-107">Under Choose Users in the Teams Chat location row, you may see guests and non-mailbox users.</span><span class="sxs-lookup"><span data-stu-id="0ad07-107">Under Choose Users in the Teams Chat location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="0ad07-108">Retention policies are not meant to be set for guests, and we are working to remove these from the list.</span><span class="sxs-lookup"><span data-stu-id="0ad07-108">Retention policies are not meant to be set for guests, and we are working to remove these from the list.</span></span>

- <span data-ttu-id="0ad07-109">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span><span class="sxs-lookup"><span data-stu-id="0ad07-109">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="0ad07-110">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span><span class="sxs-lookup"><span data-stu-id="0ad07-110">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="0ad07-111">This isn't a new situation - it follows the Exchange model.</span><span class="sxs-lookup"><span data-stu-id="0ad07-111">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="0ad07-112">Of course, in most cases, there is no delay.</span><span class="sxs-lookup"><span data-stu-id="0ad07-112">Of course, in most cases, there is no delay.</span></span>


| | | |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |<span data-ttu-id="0ad07-114">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="0ad07-114">Decision point</span></span>         |<span data-ttu-id="0ad07-p104">組織で必要とされているセキュリティとコンプライアンスの機能を教えてください。組織はセキュリティとコンプライアンスのビジネス要件を満たすために必要なライセンスを所有していますか?</span><span class="sxs-lookup"><span data-stu-id="0ad07-p104">What security and compliance features does your organization require? Does your organization have the required licenses to meet Security and Compliance business requirements?</span></span>         |
|![次のステップ アイコン。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |<span data-ttu-id="0ad07-118">次のステップ</span><span class="sxs-lookup"><span data-stu-id="0ad07-118">Next steps</span></span>         |<span data-ttu-id="0ad07-119">必須のセキュリティとコンプライアンスの機能を文書化します。</span><span class="sxs-lookup"><span data-stu-id="0ad07-119">Document your required security and compliance features.</span></span>         |

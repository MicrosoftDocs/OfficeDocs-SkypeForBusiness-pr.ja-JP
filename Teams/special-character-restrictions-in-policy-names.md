---
title: チーム ポリシー内の特殊文字の制限は?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- me.teamsadmincenter.policies.naming.error
description: ポリシーおよびその修正を行うことができますの名前に特殊文字を含むが、どのような問題を参照してください。
ms.openlocfilehash: 43e2daba187bb3a381fe617e088518129d918d09
ms.sourcegitcommit: 2b15226723c299fe94f1a012aa21222173fe3af8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2018
ms.locfileid: "20192165"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="03f0b-103">チーム ポリシー内の特殊文字の制限は?</span><span class="sxs-lookup"><span data-stu-id="03f0b-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="03f0b-104">**チームで作成したポリシーの名前に特殊文字を使用できますが、しないことを強くお勧めします。**</span><span class="sxs-lookup"><span data-stu-id="03f0b-104">**Although you can use special characters in the names of policies you created in Teams, we strongly recommend that you don't.**</span></span>

<span data-ttu-id="03f0b-105">ポリシー名の会議、チャット、および prescense を作成し、チームで他の作業などの特殊文字を持つことができます @、#、$。</span><span class="sxs-lookup"><span data-stu-id="03f0b-105">Policy names that you create for meetings, chat and prescense, and other things in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="03f0b-106">ただし、ビジネス管理センターは、マイクロソフトのチームと Skype で名前を変更するしようとしている場合することはできませんにします。</span><span class="sxs-lookup"><span data-stu-id="03f0b-106">However, if you are wanting to make changes to the name in the Microsoft Teams and Skype for Business admin center, you won't be able to.</span></span> <span data-ttu-id="03f0b-107">Windows PowerShell と適切なポリシーのコマンドレットを使用して、変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03f0b-107">You must use Windows PowerShell and the correct policy cmdlet to make changes.</span></span>

<span data-ttu-id="03f0b-108">などの特殊文字を含む会議ポリシーがあり、名前を変更または名前から特殊文字を削除する場合は、セット CsMeetingPolicy コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03f0b-108">For example, if you have a meeting policy with special characters and you want to change the name or remove the special characters from the name, you will need to use the Set-CsMeetingPolicy cmdlet.</span></span> 

<span data-ttu-id="03f0b-109">これを実行する必要がありますポリシー コマンドレットの一覧を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="03f0b-109">Here is a list of the policy cmdlets that you may need to do this:</span></span>
1. <span data-ttu-id="03f0b-110">セット CsMeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="03f0b-110">Set-CsMeetingPolicy</span></span>
2. <span data-ttu-id="03f0b-111">セット CsAppPolicy</span><span class="sxs-lookup"><span data-stu-id="03f0b-111">Set-CsAppPolicy</span></span>
3. <span data-ttu-id="03f0b-112">セット-\*</span><span class="sxs-lookup"><span data-stu-id="03f0b-112">Set-\*</span></span>



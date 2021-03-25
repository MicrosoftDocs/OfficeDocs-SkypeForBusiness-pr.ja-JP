---
title: Skype for Business Server で会議ディレクトリを作成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: '概要: Skype for Business Server で会議ディレクトリを作成する方法について学習します。'
ms.openlocfilehash: e4d73cc73a5c3c343e8a4734923cf80fb2590211
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119476"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a><span data-ttu-id="1aba1-103">Skype for Business Server で会議ディレクトリを作成する</span><span class="sxs-lookup"><span data-stu-id="1aba1-103">Create conference directories in Skype for Business Server</span></span>
 
<span data-ttu-id="1aba1-104">**概要:** Skype for Business Server で会議ディレクトリを作成する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="1aba1-104">**Summary:** Learn how to create conference directories in Skype for Business Server.</span></span>
  
<span data-ttu-id="1aba1-105">会議ディレクトリは、Skype for Business を使用するときに参加者が会議に参加するために使用する英数字会議 ID と、ダイヤルイン会議参加者が会議に参加するために使用する数値専用の会議 ID との間のマッピングを維持します。</span><span class="sxs-lookup"><span data-stu-id="1aba1-105">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Skype for Business, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> 
  
## <a name="create-a-conference-directory"></a><span data-ttu-id="1aba1-106">会議ディレクトリの作成</span><span class="sxs-lookup"><span data-stu-id="1aba1-106">Create a conference directory</span></span>

<span data-ttu-id="1aba1-107">複数の会議ディレクトリを作成すると、作成する会議の数がよほど多くならない限り電話会議 ID を短く保つことができます。</span><span class="sxs-lookup"><span data-stu-id="1aba1-107">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> 
  
<span data-ttu-id="1aba1-108">ユーザーあたりの電話会議の数が一般的な組織の場合、プール内の 999 ユーザーごとに 1 つの会議ディレクトリを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1aba1-108">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="1aba1-109">このガイドラインを使用すると、通常、会議の ID を小さくすることができます。</span><span class="sxs-lookup"><span data-stu-id="1aba1-109">Using this guideline, the conference IDs can generally be kept small.</span></span> <span data-ttu-id="1aba1-110">ただし、(プール全体の) 会議ディレクトリの数が 9 を超えると、会議 ID の長さが増えて、追加の会議がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="1aba1-110">However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>
  
<span data-ttu-id="1aba1-111">会議 ID の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1aba1-111">The format of a conference ID is as follows:</span></span> 
  
```console
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

<span data-ttu-id="1aba1-112">会議ディレクトリを作成するには **、New-CsConferenceDirectory コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="1aba1-112">To create a conference directory, use the **New-CsConferenceDirectory** cmdlet.</span></span> <span data-ttu-id="1aba1-113">たとえば、次のコマンドを実行すると、ID 42 を持つ会議ディレクトリが作成されます。このディレクトリは、次の atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="1aba1-113">For example, the following command creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

<span data-ttu-id="1aba1-114">詳細については [、「New-CsConferenceDirectory」を参照してください](/powershell/module/skype/new-csconferencedirectory?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="1aba1-114">For more information, see [New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span></span>

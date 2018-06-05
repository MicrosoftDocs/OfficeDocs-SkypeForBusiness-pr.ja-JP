---
title: Skype for Business Server 2015 での電話会議ディレクトリの作成
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: '概要: ビジネス サーバー 2015 の Skype での会議ディレクトリを作成する方法を説明します。'
ms.openlocfilehash: 861172a76da68d39fd9f8213de6e45a892aa1780
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568746"
---
# <a name="create-conference-directories-in-skype-for-business-server-2015"></a><span data-ttu-id="29cb6-103">Skype for Business Server 2015 での電話会議ディレクトリの作成</span><span class="sxs-lookup"><span data-stu-id="29cb6-103">Create conference directories in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="29cb6-104">**の概要:** ビジネス サーバー 2015 の Skype での会議ディレクトリを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="29cb6-104">**Summary:** Learn how to create conference directories in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="29cb6-105">会議ディレクトリは、ビジネス用の Skype を使用する場合、会議に参加する参加者が使用する英数字のミーティング ID と、ダイヤルイン会議の参加者が会議に参加するのには使用する数値のみの会議 ID 間のマッピングを維持します。</span><span class="sxs-lookup"><span data-stu-id="29cb6-105">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Skype for Business, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> 
  
## <a name="create-a-conference-directory"></a><span data-ttu-id="29cb6-106">電話会議ディレクトリを作成する</span><span class="sxs-lookup"><span data-stu-id="29cb6-106">Create a conference directory</span></span>

<span data-ttu-id="29cb6-107">複数の電話会議ディレクトリを作成すると、作成する電話会議の数がよほど多くならない限り、電話会議 ID を短く保つことができます。</span><span class="sxs-lookup"><span data-stu-id="29cb6-107">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> 
  
<span data-ttu-id="29cb6-p101">ユーザーあたりの電話会議の数が標準的である組織の場合は、プール内の 999 ユーザーごとに 1 つの電話会議ディレクトリを作成することをお勧めします。このガイドラインを使用すると、一般に電話会議 ID が短く保たれます。ただし、(すべてのプールでの) 電話会議ディレクトリの数が 9 よりも多くなると、会議 ID の長さは、追加の電話会議に対応して長くなります。</span><span class="sxs-lookup"><span data-stu-id="29cb6-p101">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool. Using this guideline, the conference IDs can generally be kept small. However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>
  
<span data-ttu-id="29cb6-111">電話会議 ID の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="29cb6-111">The format of a conference ID is as follows:</span></span> 
  
```
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

<span data-ttu-id="29cb6-p102">電話会議ディレクトリを作成するには、**New-CsConferenceDirectory** コマンドレットを使用します。たとえば、以下では、ID が 42 で、プール atl-cs-001.litwareinc.com でホストされる電話会議ディレクトリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="29cb6-p102">To create a conference directory, use the **New-CsConferenceDirectory** cmdlet. For example, the following command creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
  
```
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

<span data-ttu-id="29cb6-114">詳細については、[新規 CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29cb6-114">For more information, see [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span></span>
  


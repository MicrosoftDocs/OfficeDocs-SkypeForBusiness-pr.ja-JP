---
title: 勧め会議ディレクトリを作成する
description: 勧め電話会議ディレクトリを作成します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: (Recommended) Create Conference Directories
ms:assetid: 787f4c94-1c96-468a-a74d-e06b7bd4b8a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn832056(v=OCS.15)
ms:contentKeyID: 63146389
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b14982893fbc14a87818875a787d0f776da84ae3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563663"
---
# <a name="recommended-create-conference-directories"></a><span data-ttu-id="aada8-103">勧め会議ディレクトリを作成する</span><span class="sxs-lookup"><span data-stu-id="aada8-103">(Recommended) Create Conference Directories</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aada8-104">_**トピックの最終更新日:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="aada8-104">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="aada8-105">会議ディレクトリは、Lync 2013 を使用するときに参加者が会議への参加に使用する英数字のミーティング ID と、ダイヤルイン会議の参加者が会議に参加するために使用する数字のみの会議 id のマッピングを維持します。</span><span class="sxs-lookup"><span data-stu-id="aada8-105">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="aada8-106">電話会議 ID の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aada8-106">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="aada8-107">複数の会議ディレクトリを作成すると、作成する会議の数がよほど多くならない限り電話会議 ID を短く保つことができます。</span><span class="sxs-lookup"><span data-stu-id="aada8-107">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="aada8-108">ユーザーあたりの電話会議の数が一般的な組織の場合、プール内の 999 ユーザーごとに 1 つの会議ディレクトリを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="aada8-108">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="aada8-109">このガイドラインを使用すると、一般に電話会議 ID が短く保たれます。</span><span class="sxs-lookup"><span data-stu-id="aada8-109">Using this guideline the conference IDs can generally be kept small.</span></span> <span data-ttu-id="aada8-110">ただし、(プール間の) 電話会議ディレクトリの数が9を超えると、追加の会議をサポートするために会議 ID の長さが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="aada8-110">However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>

<div>

## <a name="creating-a-conference-directory"></a><span data-ttu-id="aada8-111">会議ディレクトリの作成</span><span class="sxs-lookup"><span data-stu-id="aada8-111">Creating a conference directory</span></span>

1.  <span data-ttu-id="aada8-112">Lync Server 管理シェルで、次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="aada8-112">In Lync Server Management Shell, type the following cmdlet:</span></span>
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    <span data-ttu-id="aada8-113">たとえば、次の例では、id が42の会議ディレクトリを作成します。これは、プール atl-cs-001.litwareinc.com でホストされます。</span><span class="sxs-lookup"><span data-stu-id="aada8-113">For example, the following creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aada8-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="aada8-114">See Also</span></span>


[<span data-ttu-id="aada8-115">Lync Server 2013 でのダイヤルイン会議の要件</span><span class="sxs-lookup"><span data-stu-id="aada8-115">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="aada8-116">Get-csconferencedirectory</span><span class="sxs-lookup"><span data-stu-id="aada8-116">New-CsConferenceDirectory</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsConferenceDirectory)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


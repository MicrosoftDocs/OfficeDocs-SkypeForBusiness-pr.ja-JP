---
title: 勧め会議ディレクトリを作成する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: (Recommended) Create Conference Directories
ms:assetid: 787f4c94-1c96-468a-a74d-e06b7bd4b8a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn832056(v=OCS.15)
ms:contentKeyID: 63146389
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37f4a0dbd2caf7e9a04354e0b0670dcbb47adb1b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recommended-create-conference-directories"></a><span data-ttu-id="d582a-102">勧め会議ディレクトリを作成する</span><span class="sxs-lookup"><span data-stu-id="d582a-102">(Recommended) Create Conference Directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d582a-103">_**トピックの最終更新日:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="d582a-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="d582a-104">会議ディレクトリは、Lync 2013 を使用するときに参加者が会議への参加に使用する英数字のミーティング ID と、ダイヤルイン会議の参加者が会議に参加するために使用する数字のみの会議 id のマッピングを維持します。</span><span class="sxs-lookup"><span data-stu-id="d582a-104">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="d582a-105">電話会議 ID の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d582a-105">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="d582a-106">複数の会議ディレクトリを作成すると、作成する会議の数がよほど多くならない限り電話会議 ID を短く保つことができます。</span><span class="sxs-lookup"><span data-stu-id="d582a-106">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="d582a-107">ユーザーあたりの電話会議の数が一般的な組織の場合、プール内の 999 ユーザーごとに 1 つの会議ディレクトリを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d582a-107">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="d582a-108">このガイドラインを使用すると、一般に電話会議 ID が短く保たれます。</span><span class="sxs-lookup"><span data-stu-id="d582a-108">Using this guideline the conference IDs can generally be kept small.</span></span> <span data-ttu-id="d582a-109">ただし、(プール間の) 電話会議ディレクトリの数が9を超えると、追加の会議をサポートするために会議 ID の長さが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="d582a-109">However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>

<div>

## <a name="creating-a-conference-directory"></a><span data-ttu-id="d582a-110">会議ディレクトリの作成</span><span class="sxs-lookup"><span data-stu-id="d582a-110">Creating a conference directory</span></span>

1.  <span data-ttu-id="d582a-111">Lync Server 管理シェルで、次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="d582a-111">In Lync Server Management Shell, type the following cmdlet:</span></span>
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    <span data-ttu-id="d582a-112">たとえば、次の例では、id が42の会議ディレクトリを作成します。これは、プール atl-cs-001.litwareinc.com でホストされます。</span><span class="sxs-lookup"><span data-stu-id="d582a-112">For example, the following creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d582a-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="d582a-113">See Also</span></span>


[<span data-ttu-id="d582a-114">Lync Server 2013 でのダイヤルイン会議の要件</span><span class="sxs-lookup"><span data-stu-id="d582a-114">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="d582a-115">Get-csconferencedirectory</span><span class="sxs-lookup"><span data-stu-id="d582a-115">New-CsConferenceDirectory</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsConferenceDirectory)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


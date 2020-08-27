---
title: Microsoft Teams の Cortana 音声アシスタント
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: チームで Cortana の音声アシスタントを使用する方法について説明します。
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f820bf6c44eae2cfbdb13a683d017be2f93d6756
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255551"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="ac856-103">Teams の Cortana 音声アシスタンス</span><span class="sxs-lookup"><span data-stu-id="ac856-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="ac856-104">Cortana の音声アシスタンスは、米国のユーザーに対してのみ Microsoft Teams iOS および Android モバイルアプリでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ac856-104">Cortana voice assistance is supported on Microsoft Teams iOS and Android mobile apps only for users in the United States.</span></span> <span data-ttu-id="ac856-105">現時点では、GCC、GCC-高、DoD、EDU テナントでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="ac856-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="ac856-106">今後のリリースの一部として、追加の言語と地域への拡張が行われます。</span><span class="sxs-lookup"><span data-stu-id="ac856-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

<span data-ttu-id="ac856-107">Teams モバイルアプリの Cortana 音声アシスタンスでは、Microsoft 365 エンタープライズユーザーは、会話、共同作業、会議関連のタスクをスムーズに行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ac856-107">Cortana voice assistance in the Teams mobile app enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="ac856-108">ユーザーは、Teams モバイルアプリの右上にある [マイク] ボタンをクリックして Cortana に音声通話を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ac856-108">Users can speak to Cortana by clicking on the microphone button located in the upper right of the Teams mobile app.</span></span> <span data-ttu-id="ac856-109">外出先でも、チームメンバーとすばやく連絡を取るために、ユーザーは &#8220;call Megan&#8221;、または次の会議&#8221; にメッセージを送信 &#8220;などのクエリにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ac856-109">To quickly connect with their team while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="ac856-110">また、ユーザーは次の&#8221; 会議に参加することを &#8220;指示して、音声アシスタンスを使用してファイルを共有したり、予定表を確認したりすることで会議に参加することもできます。</span><span class="sxs-lookup"><span data-stu-id="ac856-110">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="ac856-111">これらの音声アシスタンスのエクスペリエンスは、[オンラインサービス利用規約 (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)に反映された、Office 365 のプライバシー、セキュリティ、およびコンプライアンスの保証に完全に準拠する[Cortana のエンタープライズ評価サービス](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide)を使用して提供されます。</span><span class="sxs-lookup"><span data-stu-id="ac856-111">These voice assistance experiences are delivered using [Cortana enterprise-grade services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365’s privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="ac856-112">この画像は、モバイルデバイスの Cortana でチャットを送信する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ac856-112">The image shows sending a chat in Cortana on a mobile device.</span></span>

![Cortana のチャットセッションが表示された、モバイル画面の一連の画像](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="ac856-114">管理者の制御と制限</span><span class="sxs-lookup"><span data-stu-id="ac856-114">Admin control and Limitations</span></span>

<span data-ttu-id="ac856-115">Teams での Cortana の音声サポートは、オンラインサービス利用規約 (OST) に反映された Office 365 エンタープライズレベルのプライバシー、セキュリティ、およびコンプライアンスの約束に完全に準拠するサービスを使用して提供されます。</span><span class="sxs-lookup"><span data-stu-id="ac856-115">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="ac856-116">この機能は、テナントに対して既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="ac856-116">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="ac856-117">テナント管理者は、ポリシー (TeamsCortanaPolicy) を使用してチームで Cortana の音声アシスタンスを使用できるように、テナント内のユーザーを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="ac856-117">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="ac856-118">このポリシーは、ユーザーアカウントレベルまたはテナントレベルで設定できます。</span><span class="sxs-lookup"><span data-stu-id="ac856-118">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="ac856-119">管理者は、このポリシーコントロール内の CortanaVoiceInvocationMode フィールドを使って、Cortana が無効になっているか、プッシュボタンでの呼び出し専用であるか、またはスリープ解除 (サポートされているデバイスに適用可能) であるかを判断することができます。</span><span class="sxs-lookup"><span data-stu-id="ac856-119">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push button invocation only, or with wake word invocation as well (applicable to devices that support it).</span></span>

<span data-ttu-id="ac856-120">管理者は、次の PowerShell コマンドレットを使用してこのポリシーを管理できます (ポリシーは現在、Microsoft Teams 管理センターでは利用できません)。</span><span class="sxs-lookup"><span data-stu-id="ac856-120">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="ac856-121">新規-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="ac856-121">New-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="ac856-122">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="ac856-122">Get-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="ac856-123">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="ac856-123">Grant-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="ac856-124">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="ac856-124">Set-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="ac856-125">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="ac856-125">Remove-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="ac856-126">たとえば、次のコマンドは、Microsoft Teams の Cortana 音声アシスタントが無効になっている &#8220;EmployeeCortanaPolicy&#8221; という名前の新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ac856-126">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistant in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="ac856-127">この例では、&#8220;EmployeeCortanaPolicy&#8221; という名前の既存のポリシーを更新して、Microsoft Teams で Cortana の音声アシスタントを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ac856-127">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistant in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="ac856-128">ユーザーは Teams の Cortana マイクボタンをタップして Cortana を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="ac856-128">Users will be able to invoke Cortana by tapping on the Cortana mic button in Teams.</span></span> <span data-ttu-id="ac856-129">Word のスリープ解除 (&#8220;コルタナ&#8221;) の呼び出しは無効になります。</span><span class="sxs-lookup"><span data-stu-id="ac856-129">Wake word (&#8220;Hey Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="ac856-130">次の例は、プッシュボタンと word の両方の呼び出しを使って、ポリシーを更新し、Cortana の音声アシスタントを有効にする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ac856-130">This example shows updating the policy and enabling Cortana voice assistant with both push button and wake-word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> <span data-ttu-id="ac856-131">英語での Microsoft 365 Enterprise ユーザーの最初のリリースの時点では、Teams モバイルアプリは、word ライセンスのスリープ解除をサポートしていませんが、今後サポートされる予定です。</span><span class="sxs-lookup"><span data-stu-id="ac856-131">At the time of the initial release for Microsoft 365 Enterprise users in the US in English, the Teams mobile app will not support wake word activation, but it will be supported in the future.</span></span>

## <a name="user-control"></a><span data-ttu-id="ac856-132">ユーザーコントロール</span><span class="sxs-lookup"><span data-stu-id="ac856-132">User control</span></span>

<span data-ttu-id="ac856-133">個々のユーザーは、[マイク] ボタンをクリックして、Teams のモバイルアプリで Cortana の音声アシスタンスを試すことができます。</span><span class="sxs-lookup"><span data-stu-id="ac856-133">Individual users can try out Cortana voice assistance in the Teams mobile app by clicking the microphone button.</span></span> <span data-ttu-id="ac856-134">また、Teams のモバイルアプリの設定を使用して、自分のデバイスに対して Cortana の Cortana を有効にするかどうかを制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="ac856-134">They can also control whether Cortana in Teams is enabled for their device using a setting in the Teams mobile app.</span></span>

1. <span data-ttu-id="ac856-135">Teams モバイルアプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="ac856-135">Open the Teams mobile app.</span></span>

2. <span data-ttu-id="ac856-136">[ **設定**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac856-136">Go to **Settings**.</span></span>

3. <span data-ttu-id="ac856-137">[ **Cortana**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ac856-137">Select **Cortana**.</span></span>

4. <span data-ttu-id="ac856-138">デバイスで Cortana 音声アシスタンスが必要かどうかに応じて、トグルを **[オン** ] または [ **オフ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac856-138">Move the toggle to **On** or **Off**, depending on whether you want Cortana voice assistance on the device.</span></span>

---
title: Microsoft Teams の Cortana の音声サポート
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Teams で Cortana の音声アシスタンスを使用する方法について説明します。
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
ms.openlocfilehash: b93ac825d25e7fdb619c2e949fbef0ba517a3fe9
ms.sourcegitcommit: 5a27802a533db13429813a02626de458f4011780
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2020
ms.locfileid: "48785391"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="fe15d-103">Teams の Cortana 音声アシスタンス</span><span class="sxs-lookup"><span data-stu-id="fe15d-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="fe15d-104">Cortana の音声アシスタンスは、Microsoft Teams iOS および Android モバイルアプリでサポートされています。また、Microsoft Teams では、米国のユーザーに対してのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe15d-104">Cortana voice assistance is supported in Microsoft Teams iOS and Android mobile apps, and on Microsoft Teams displays, only for users in the United States.</span></span> <span data-ttu-id="fe15d-105">現時点では、GCC、GCC-高、DoD、EDU テナントでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="fe15d-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="fe15d-106">今後のリリースの一部として、追加の言語と地域への拡張が行われます。</span><span class="sxs-lookup"><span data-stu-id="fe15d-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

<span data-ttu-id="fe15d-107">Teams のモバイルアプリおよび Microsoft Teams の表示デバイスでの Cortana の音声サポート Microsoft 365 Enterprise ユーザーは、音声読み上げの言語を使用して、コミュニケーション、共同作業、会議関連のタスクを効率化できます。</span><span class="sxs-lookup"><span data-stu-id="fe15d-107">Cortana voice assistance in the Teams mobile app and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="fe15d-108">ユーザーは、Teams のモバイルアプリの右上にある [マイク] ボタンを選択するか、または Microsoft Teams のディスプレイで Cortana&#8221; &#8220;と言って、Cortana と話すことができます。</span><span class="sxs-lookup"><span data-stu-id="fe15d-108">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams display.</span></span> <span data-ttu-id="fe15d-109">ユーザーは、自分のチームと簡単に連絡を取ることができます。外出先でも、&#8220;call Megan&#8221;、または次の会議&#8221; へのメッセージの送信 &#8220;などのクエリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fe15d-109">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="fe15d-110">また、ユーザーは次の&#8221; 会議に参加することを &#8220;指示して、音声アシスタンスを使用してファイルを共有したり、予定表を確認したりすることで会議に参加することもできます。</span><span class="sxs-lookup"><span data-stu-id="fe15d-110">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="fe15d-111">これらの音声アシスタンスのエクスペリエンスは、[オンラインサービス利用規約 (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)に反映された、Office 365 のプライバシー、セキュリティ、およびコンプライアンスの保証に完全に準拠する[Cortana のエンタープライズ評価サービス](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide)を使用して提供されます。</span><span class="sxs-lookup"><span data-stu-id="fe15d-111">These voice assistance experiences are delivered using [Cortana enterprise-grade services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="fe15d-112">この画像は、モバイルデバイスで Cortana を使ってチャットを送信する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="fe15d-112">The image shows sending a chat using Cortana on a mobile device.</span></span>

![Cortana のチャットセッションが表示された、モバイル画面の一連の画像](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="fe15d-114">管理者の制御と制限</span><span class="sxs-lookup"><span data-stu-id="fe15d-114">Admin control and limitations</span></span>

<span data-ttu-id="fe15d-115">Teams での Cortana の音声サポートは、オンラインサービス利用規約 (OST) に反映された Office 365 エンタープライズレベルのプライバシー、セキュリティ、およびコンプライアンスの約束に完全に準拠するサービスを使用して提供されます。</span><span class="sxs-lookup"><span data-stu-id="fe15d-115">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="fe15d-116">この機能は、テナントに対して既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="fe15d-116">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="fe15d-117">テナント管理者は、ポリシー (TeamsCortanaPolicy) を使用してチームで Cortana の音声アシスタンスを使用できるように、テナント内のユーザーを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="fe15d-117">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="fe15d-118">このポリシーは、ユーザーアカウントレベルまたはテナントレベルで設定できます。</span><span class="sxs-lookup"><span data-stu-id="fe15d-118">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="fe15d-119">管理者は、このポリシーコントロール内で CortanaVoiceInvocationMode フィールドを使って、Cortana が無効になっているか、プッシュボタンでの呼び出しのみで有効になっているか、またはスリープ解除 (Microsoft Teams の表示などのデバイスに適用可能) であるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="fe15d-119">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="fe15d-120">管理者は、次の PowerShell コマンドレットを使用してこのポリシーを管理できます (ポリシーは現在、Microsoft Teams 管理センターでは利用できません)。</span><span class="sxs-lookup"><span data-stu-id="fe15d-120">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="fe15d-121">新規-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="fe15d-121">New-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="fe15d-122">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="fe15d-122">Get-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="fe15d-123">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="fe15d-123">Grant-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="fe15d-124">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="fe15d-124">Set-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="fe15d-125">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="fe15d-125">Remove-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="fe15d-126">たとえば、次のコマンドは、Microsoft Teams の Cortana 音声アシスタンスが無効になっている &#8220;EmployeeCortanaPolicy&#8221; という名前の新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="fe15d-126">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="fe15d-127">この例では、&#8220;EmployeeCortanaPolicy&#8221; という名前の既存のポリシーを更新して、Microsoft Teams で Cortana の音声サポートを有効にして、プッシュボタン呼び出しのみを有効にしています。</span><span class="sxs-lookup"><span data-stu-id="fe15d-127">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="fe15d-128">ユーザーは Teams で Cortana マイクボタンを選択して Cortana を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="fe15d-128">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="fe15d-129">Word のスリープ解除 (&#8220;Cortana の&#8221; または &#8220;Cortana&#8221;) の呼び出しは無効になります。</span><span class="sxs-lookup"><span data-stu-id="fe15d-129">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="fe15d-130">次の例では、ポリシーを更新し、プッシュボタンとスリープ解除の両方の呼び出しで Cortana 音声アシスタンスを有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="fe15d-130">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> <span data-ttu-id="fe15d-131">英語での Microsoft 365 Enterprise ユーザーの最初のリリースの時点では、Teams モバイルアプリは、word ライセンスのスリープ解除をサポートしていませんが、今後サポートされる予定です。</span><span class="sxs-lookup"><span data-stu-id="fe15d-131">At the time of the initial release for Microsoft 365 Enterprise users in the US in English, the Teams mobile app will not support wake word activation, but it will be supported in the future.</span></span> <span data-ttu-id="fe15d-132">Word のスリープ解除は、Microsoft Teams の最初のリリースでの表示デバイスで動作します。</span><span class="sxs-lookup"><span data-stu-id="fe15d-132">Wake word activation will work on Microsoft Teams display devices at initial release.</span></span>

## <a name="user-control"></a><span data-ttu-id="fe15d-133">ユーザーコントロール</span><span class="sxs-lookup"><span data-stu-id="fe15d-133">User control</span></span>

<span data-ttu-id="fe15d-134">個々のユーザーは、[マイク] ボタンを選択して、Teams のモバイルアプリで Cortana の音声アシスタンスを試すことができます。</span><span class="sxs-lookup"><span data-stu-id="fe15d-134">Individual users can try out Cortana voice assistance in the Teams mobile app by selecting the microphone button.</span></span> <span data-ttu-id="fe15d-135">Microsoft Teams で Cortana の音声サポートを試すには、「Cortana &#8220;を言ってください。 &#8221;、Teams のモバイルアプリまたは Microsoft Teams のディスプレイの設定を使って、自分のデバイスに対して Cortana の Cortana が有効になっているかどうかを制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="fe15d-135">They can try out Cortana voice assistance on Microsoft Teams display devices by simply saying &#8220;Cortana.&#8221; They can also control whether Cortana in Teams is enabled for their device using a setting in the Teams mobile app or on the Microsoft Teams display.</span></span>

1. <span data-ttu-id="fe15d-136">Teams モバイルアプリを開くか、Microsoft Teams ディスプレイの [環境 (ホーム)] 画面に移動します。</span><span class="sxs-lookup"><span data-stu-id="fe15d-136">Open the Teams mobile app, or go to the ambient (home) screen of the Microsoft Teams display.</span></span>

2. <span data-ttu-id="fe15d-137">Teams モバイルアプリで、[ **設定** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="fe15d-137">In the Teams mobile app, go to **Settings** .</span></span> <span data-ttu-id="fe15d-138">Microsoft Teams の表示で、ユーザーアバターを選択し、[設定] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe15d-138">On the Microsoft Teams display, select the user avatar, and then select Settings.</span></span> <span data-ttu-id="fe15d-139">Cortana が有効になっている場合は、Cortana &#8220;、[設定] に移動し &#8221;</span><span class="sxs-lookup"><span data-stu-id="fe15d-139">If Cortana is enabled, say, &#8220;Cortana, go to Settings.&#8221;</span></span>

3. <span data-ttu-id="fe15d-140">[ **Cortana** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fe15d-140">Select **Cortana** .</span></span>

4. <span data-ttu-id="fe15d-141">デバイスで Cortana 音声アシスタンスが必要かどうかに応じて、トグルを **[オン** ] または [ **オフ** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="fe15d-141">Move the toggle to **On** or **Off** , depending on whether you want Cortana voice assistance on the device.</span></span>

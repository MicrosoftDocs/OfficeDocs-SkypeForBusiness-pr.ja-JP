---
title: Cortanaでの音声アシスタンスのMicrosoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: 音声サポートを使用してCortanaする方法についてTeams
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b343a3f69d2b0f97f9d7d3054951719da2e9e43
ms.sourcegitcommit: b7da2655607a17cde9537ed9e00db29b4c1a68df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2021
ms.locfileid: "53219144"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="62b8c-103">Cortanaでの音声アシスタンスのTeams</span><span class="sxs-lookup"><span data-stu-id="62b8c-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="62b8c-104">Cortanaは、iOS および Android 用の Microsoft Teams モバイル アプリと、米国、英国、カナダ、インド、オーストラリアのユーザー向け Microsoft Teams ディスプレイでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="62b8c-104">Cortana voice assistance is supported in Microsoft Teams mobile apps for iOS and Android and Microsoft Teams displays for users in the United States, United Kingdom, Canada, India, and Australia.</span></span> <span data-ttu-id="62b8c-105">Microsoft Teams ミーティングのWindowsは、米国内のユーザーに対してのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="62b8c-105">Microsoft Teams Rooms on Windows is only supported for users in the United States.</span></span> <span data-ttu-id="62b8c-106">Cortana、GCC GCC-High、DoD、および米国以外の EDU テナントでは、音声アシスタンスは現在使用できません。</span><span class="sxs-lookup"><span data-stu-id="62b8c-106">Cortana voice assistance isn't currently available for GCC, GCC-High, DoD, and non-US EDU tenants.</span></span> <span data-ttu-id="62b8c-107">Cortanaアプリの音声アシスタンスTeams、en-US の EDU のお客様が利用できます。</span><span class="sxs-lookup"><span data-stu-id="62b8c-107">Cortana voice assistance in the Teams mobile app is now available for EDU customers in en-US.</span></span> <span data-ttu-id="62b8c-108">追加の言語と地域への拡張は、将来のリリースの一環として行う予定です。</span><span class="sxs-lookup"><span data-stu-id="62b8c-108">Expansion to additional languages and regions will happen as part of future releases.</span></span>

> [!Note]
> <span data-ttu-id="62b8c-109">Cortanaでの音声アシスタンスMicrosoft Teams ミーティングプレビューの下でリリースされます。</span><span class="sxs-lookup"><span data-stu-id="62b8c-109">Cortana voice assistance in Microsoft Teams Rooms is released under Preview.</span></span> <span data-ttu-id="62b8c-110">プレビュー リリースではCortana Rally マイクを接続しているデバイスでは、言語 EN-US を使用する米国でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="62b8c-110">In its preview release, Cortana is supported only in the US with language EN-US on devices that have connected Rally microphones.</span></span>

<span data-ttu-id="62b8c-111">Cortana Teams モバイル アプリ、Windows の Microsoft Teams ミーティング、Microsoft Teams ディスプレイ デバイスで音声アシスタンスを使用すると、Microsoft 365 Enterprise ユーザーは話し言葉の自然言語を使用して、コミュニケーション、コラボレーション、会議関連のタスクを効率化できます。</span><span class="sxs-lookup"><span data-stu-id="62b8c-111">Cortana voice assistance in the Teams mobile app, on Microsoft Teams Rooms on Windows, and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="62b8c-112">ユーザーは、Teams モバイル アプリの右上にあるマイク ボタンを選択するか、Microsoft Teams Room で &#8220;Cortana&#8221; と言うか、Microsoft Teams ディスプレイを使用するときに、Cortana と話し合います。</span><span class="sxs-lookup"><span data-stu-id="62b8c-112">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams Room or when using a Microsoft Teams display.</span></span> <span data-ttu-id="62b8c-113">チームにハンズフリーですばやく接続し、移動中に、ユーザーは &#8220;通話 Megan&#8221; や &#8220;などのクエリを言って、次の会議&#8221; にメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="62b8c-113">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="62b8c-114">ユーザーは、次の会議に参加&#8220;、音声&#8221;を使ってファイルの共有、予定表の確認などと言って会議に参加することもできます。</span><span class="sxs-lookup"><span data-stu-id="62b8c-114">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="62b8c-115">これらの音声アシスタンス エクスペリエンスは[、Office 365](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide)のプライバシー、セキュリティ、およびコンプライアンスの約束に完全に準拠する Cortana エンタープライズ レベルのサービスを使用して提供されます 。これは[、Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)に反映されます。</span><span class="sxs-lookup"><span data-stu-id="62b8c-115">These voice assistance experiences are delivered using [Cortana enterprise-grade services](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="62b8c-116">この画像は、モバイル デバイス上のCortanaを使用してチャットを送信する場合を示しています。</span><span class="sxs-lookup"><span data-stu-id="62b8c-116">The image shows sending a chat using Cortana on a mobile device.</span></span>

![一連のモバイル画面で、チャット セッションCortana表示](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="62b8c-118">管理者の制御と制限事項</span><span class="sxs-lookup"><span data-stu-id="62b8c-118">Admin control and limitations</span></span>

<span data-ttu-id="62b8c-119">Cortana Teams の音声アシスタンスは、online Services Terms (OST) に反映されている Office 365 エンタープライズ レベルのプライバシー、セキュリティ、コンプライアンスの約束に完全に準拠するサービスを使用して提供されます。</span><span class="sxs-lookup"><span data-stu-id="62b8c-119">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="62b8c-120">この機能は、テナントに対して既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="62b8c-120">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="62b8c-121">テナント管理者は、ポリシー (TeamsCortanaPolicy) を使用して、Cortanaの音声Teamsを使用できるユーザーを制御できます。</span><span class="sxs-lookup"><span data-stu-id="62b8c-121">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="62b8c-122">このポリシーは、ユーザー アカウント レベルまたはテナント レベルで設定されます。</span><span class="sxs-lookup"><span data-stu-id="62b8c-122">This policy is set at either a user account level or tenant level.</span></span> <span data-ttu-id="62b8c-123">管理者は、このポリシー コントロール内の CortanaVoiceInvocationMode フィールドを使用して、Cortana を無効にするか、プッシュ ボタン呼び出しでのみ有効にするか、ウェイク ワード呼び出しで有効にするか (Microsoft Teams ディスプレイなど、それをサポートするデバイスにも適用されます) を判断できます。</span><span class="sxs-lookup"><span data-stu-id="62b8c-123">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push-button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="62b8c-124">管理者は、次の PowerShell コマンドレットを使用してこのポリシーを管理できます (ポリシーは現在、管理センター Microsoft Teamsできません)。</span><span class="sxs-lookup"><span data-stu-id="62b8c-124">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="62b8c-125">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="62b8c-125">New-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="62b8c-126">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="62b8c-126">Get-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [<span data-ttu-id="62b8c-127">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="62b8c-127">Grant-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="62b8c-128">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="62b8c-128">Set-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="62b8c-129">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="62b8c-129">Remove-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="62b8c-130">たとえば、次のコマンドでは、employeeCortanaPolicy &#8220;という名前の新しいポリシーが作成&#8221;、Cortana での音声アシスタンスMicrosoft Teams無効になります。</span><span class="sxs-lookup"><span data-stu-id="62b8c-130">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="62b8c-131">この例では、&#8220;employeeCortanaPolicy&#8221; という名前の既存のポリシーを更新し、プッシュ ボタン呼び出しのみを使用して Microsoft Teams で Cortana 音声アシスタンスを有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="62b8c-131">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push-button invocation only.</span></span> <span data-ttu-id="62b8c-132">ユーザーは、アプリの [マイク] Cortanaを選択してCortanaを呼び出Teams。</span><span class="sxs-lookup"><span data-stu-id="62b8c-132">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="62b8c-133">ウェイク ワード (&#8220;Hey Cortana&#8221; または &#8220;Cortana&#8221;) 呼び出しは無効になります。</span><span class="sxs-lookup"><span data-stu-id="62b8c-133">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="62b8c-134">この例では、ポリシーを更新し、プッシュ ボタンとウェイク Cortanaの両方で音声アシスタンスを有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="62b8c-134">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

<span data-ttu-id="62b8c-135">現在、英語で米国内のユーザー Microsoft 365 Enterpriseの最初のリリースでは、次の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="62b8c-135">At the time, of the initial release for Microsoft 365 Enterprise users in the US in English, the following are available functions:</span></span>

- <span data-ttu-id="62b8c-136">モバイル Teamsウェイク ワードのアクティブ化はサポートされませんが、今後サポートされる予定です。</span><span class="sxs-lookup"><span data-stu-id="62b8c-136">The Teams mobile app won't support wake word activation, but it will be supported in the future.</span></span>  

- <span data-ttu-id="62b8c-137">Microsoft Teams ミーティングデバイスWindowsおよびMicrosoft Teamsデバイスでは、ウェイク ワードのアクティブ化がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="62b8c-137">Microsoft Teams Rooms on Windows and Microsoft Teams display devices will support wake word activation.</span></span>

## <a name="user-control"></a><span data-ttu-id="62b8c-138">ユーザー コントロール</span><span class="sxs-lookup"><span data-stu-id="62b8c-138">User control</span></span>

<span data-ttu-id="62b8c-139">個々のユーザーは、さまざまなデバイスCortana音声アシスタンスを試用できます。</span><span class="sxs-lookup"><span data-stu-id="62b8c-139">Individual users can try Cortana voice assistance in different devices:</span></span>

- <span data-ttu-id="62b8c-140">モバイル アプリのマイク ボタンTeams選択します。</span><span class="sxs-lookup"><span data-stu-id="62b8c-140">Select the microphone button in the Teams mobile app.</span></span>

- <span data-ttu-id="62b8c-141">[マイク] ボタンを選択するか、または [Cortana] とMicrosoft Teams ミーティング。</span><span class="sxs-lookup"><span data-stu-id="62b8c-141">Select the microphone button or say "Cortana" in Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="62b8c-142">デバイスを表示Cortana "Microsoft Teams" と言います。</span><span class="sxs-lookup"><span data-stu-id="62b8c-142">Say "Cortana" on Microsoft Teams displays devices.</span></span>

<span data-ttu-id="62b8c-143">デバイスの設定をCortanaをTeamsデバイスで有効にするかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="62b8c-143">You can control whether Cortana in Teams is enabled for your device by using a setting in the device.</span></span>

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a><span data-ttu-id="62b8c-144">TeamsアプリまたはディスプレイMicrosoft Teams表示</span><span class="sxs-lookup"><span data-stu-id="62b8c-144">Teams mobile app or the Microsoft Teams display</span></span>

  1. <span data-ttu-id="62b8c-145">モバイル アプリTeams開きます。</span><span class="sxs-lookup"><span data-stu-id="62b8c-145">Open the Teams mobile app.</span></span>

  2. <span data-ttu-id="62b8c-146">[設定 **Cortana]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="62b8c-146">Select **Settings** > **Cortana**.</span></span>

  3. <span data-ttu-id="62b8c-147">トグルを [オン] **または [オフ]** に **移動します**。</span><span class="sxs-lookup"><span data-stu-id="62b8c-147">Move the toggle **On** or **Off**.</span></span>

### <a name="microsoft-teams-display"></a><span data-ttu-id="62b8c-148">Microsoft Teams表示</span><span class="sxs-lookup"><span data-stu-id="62b8c-148">Microsoft Teams display</span></span>

  1. <span data-ttu-id="62b8c-149">画面の周囲 (ホーム) 画面に移動Microsoft Teamsします。</span><span class="sxs-lookup"><span data-stu-id="62b8c-149">Go to the ambient (home) screen of the Microsoft Teams display.</span></span>

  2. <span data-ttu-id="62b8c-150">ユーザーのアバターを選択し、[] を **設定。**</span><span class="sxs-lookup"><span data-stu-id="62b8c-150">Select the user avatar, and then select **Settings**.</span></span> <span data-ttu-id="62b8c-151">有効Cortana場合は、"Cortana に移動設定。</span><span class="sxs-lookup"><span data-stu-id="62b8c-151">If Cortana is enabled, say, "Cortana, go to Settings."</span></span>

  3. <span data-ttu-id="62b8c-152">トグルを [オン] **または [オフ]** に **移動します**。</span><span class="sxs-lookup"><span data-stu-id="62b8c-152">Move the toggle **On** or **Off**.</span></span>
  
### <a name="microsoft-teams-rooms-on-windows"></a><span data-ttu-id="62b8c-153">Microsoft Teams ミーティングのWindows</span><span class="sxs-lookup"><span data-stu-id="62b8c-153">Microsoft Teams Rooms on Windows</span></span>

<span data-ttu-id="62b8c-154">デバイス レベルで変更を行う方法は、テナント Cortanaで有効になっている場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="62b8c-154">Making changes at the device level is available if Cortana is enabled at the tenant level.</span></span> <span data-ttu-id="62b8c-155">Cortanaは既定でオフにリリースされます。</span><span class="sxs-lookup"><span data-stu-id="62b8c-155">Cortana will be released OFF by default.</span></span>

<span data-ttu-id="62b8c-156">デバイス レベルCortanaを有効にするには、次の XML 属性を SkypeSettings XML ファイルに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62b8c-156">To enable Cortana at the device level, these XML attributes must be added in the SkypeSettings XML file:</span></span>

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

<span data-ttu-id="62b8c-157">会議レベルで変更を行う方法は、デバイス Cortana有効になっている場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="62b8c-157">Making changes at the meeting level is available if Cortana is enabled at the device level.</span></span>

<span data-ttu-id="62b8c-158">会議中Cortana音声アシスタンスを有効にするには、[オン] または [オフ]**を\*\*\*\*切り替えます**。</span><span class="sxs-lookup"><span data-stu-id="62b8c-158">To enable Cortana voice assistance during a meeting, move the toggle **On** or **Off**.</span></span> <span data-ttu-id="62b8c-159">会議が終了すると、Cortana設定に戻ります。</span><span class="sxs-lookup"><span data-stu-id="62b8c-159">Once the meeting ends, Cortana returns to the device level settings set.</span></span>

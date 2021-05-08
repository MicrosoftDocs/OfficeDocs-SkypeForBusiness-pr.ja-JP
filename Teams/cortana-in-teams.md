---
title: Cortana の音声アシスタンス (Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Cortana 音声アシスタンスを使用して音声サポートを使用する方法についてTeams
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
ms.openlocfilehash: 2f8e24bd9035d45639ac4211435355fe7b792a2d
ms.sourcegitcommit: b782ca2ef946ae25e847c2d1847a89993a8edef8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "51886736"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="d9a22-103">Cortana の音声アシスタンス (Teams</span><span class="sxs-lookup"><span data-stu-id="d9a22-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="d9a22-104">Cortana 音声アシスタンスは、iOS および Android 用の Microsoft Teams モバイル アプリおよび米国、英国、カナダ、インド、オーストラリアのユーザー向け Microsoft Teams ディスプレイでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d9a22-104">Cortana voice assistance is supported in Microsoft Teams mobile apps for iOS and Android and Microsoft Teams displays for users in the United States, United Kingdom, Canada, India, and Australia.</span></span>  <span data-ttu-id="d9a22-105">Microsoft Teams ミーティングのWindowsは、米国内のユーザーに対してのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d9a22-105">Microsoft Teams Rooms on Windows is only supported for users in the United States.</span></span> <span data-ttu-id="d9a22-106">Cortana 音声アシスタンスは現在、GCC、GCC-High、DoD、EDU テナントでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="d9a22-106">Cortana voice assistance isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="d9a22-107">追加の言語と地域への拡張は、将来のリリースの一環として行う予定です。</span><span class="sxs-lookup"><span data-stu-id="d9a22-107">Expansion to additional languages and regions will happen as part of future releases.</span></span>

> [!Note]
> <span data-ttu-id="d9a22-108">Microsoft Teams Rooms の Cortana 音声アシスタンスは、プレビューの下でリリースされます。</span><span class="sxs-lookup"><span data-stu-id="d9a22-108">Cortana voice assistance in Microsoft  Teams  Rooms is released under Preview.</span></span> <span data-ttu-id="d9a22-109">プレビュー リリースでは、Cortana は Rally マイクを接続しているデバイスでは、米国でのみ言語 EN-US でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d9a22-109">In its preview release, Cortana is supported only in the US with language EN-US on devices that have connected Rally microphones.</span></span>

<span data-ttu-id="d9a22-110">Teams モバイル アプリ、Windows の Microsoft Teams ミーティング、Microsoft Teams ディスプレイ デバイスでの Cortana 音声アシスタンスにより、Microsoft 365 Enterprise ユーザーは、話し言葉の自然言語を使用して、コミュニケーション、コラボレーション、会議関連のタスクを効率化できます。</span><span class="sxs-lookup"><span data-stu-id="d9a22-110">Cortana voice assistance in the Teams mobile app, on Microsoft Teams Rooms on Windows, and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="d9a22-111">ユーザーは、Teams モバイル アプリの右上にあるマイク ボタンを選択するか、Microsoft Teams Room で &#8220;Cortana&#8221; と言うか、Microsoft Teams ディスプレイを使用するときに Cortana と話します。</span><span class="sxs-lookup"><span data-stu-id="d9a22-111">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams Room or when using a Microsoft Teams display.</span></span> <span data-ttu-id="d9a22-112">チームにハンズフリーですばやく接続し、移動中に、ユーザーは &#8220;通話 Megan&#8221; や &#8220;などのクエリを言って、次の会議&#8221; にメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="d9a22-112">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="d9a22-113">ユーザーは、次の会議に参加&#8220;、音声&#8221;を使ってファイルの共有、予定表の確認などと言って会議に参加することもできます。</span><span class="sxs-lookup"><span data-stu-id="d9a22-113">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="d9a22-114">これらの音声アシスタンス エクスペリエンスは[、Office 365](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide)のプライバシー、セキュリティ、およびコンプライアンスの約束に完全に準拠する Cortana エンタープライズ レベルのサービスを使用して提供されます 。これは[、Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)に反映されます。</span><span class="sxs-lookup"><span data-stu-id="d9a22-114">These voice assistance experiences are delivered using [Cortana enterprise-grade services](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="d9a22-115">画像は、モバイル デバイスで Cortana を使用してチャットを送信する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d9a22-115">The image shows sending a chat using Cortana on a mobile device.</span></span>

![Cortana チャット セッションを示す一連のモバイル画面](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="d9a22-117">管理者の制御と制限事項</span><span class="sxs-lookup"><span data-stu-id="d9a22-117">Admin control and limitations</span></span>

<span data-ttu-id="d9a22-118">Teams の Cortana 音声アシスタンスは、Office 365 エンタープライズ レベルのプライバシー、セキュリティ、およびコンプライアンスの約束に完全に準拠するサービスを使用して配信されます。これは、Online Services Terms (OST) に反映されます。</span><span class="sxs-lookup"><span data-stu-id="d9a22-118">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="d9a22-119">この機能は、テナントに対して既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="d9a22-119">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="d9a22-120">テナント管理者は、ポリシー (TeamsCortanaPolicy) を使用して、テナント内Teams Cortana 音声アシスタンスを使用できるユーザーを制御できます。</span><span class="sxs-lookup"><span data-stu-id="d9a22-120">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="d9a22-121">このポリシーは、ユーザー アカウント レベルまたはテナント レベルで設定できます。</span><span class="sxs-lookup"><span data-stu-id="d9a22-121">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="d9a22-122">管理者は、このポリシー コントロール内の CortanaVoiceInvocationMode フィールドを使用して、Cortana が無効になっているか、プッシュ ボタン呼び出しでのみ有効になっているか、ウェイク ワード呼び出しでのみ有効になっているかを判断できます (Microsoft Teams ディスプレイなど、それをサポートするデバイスにも適用されます)。</span><span class="sxs-lookup"><span data-stu-id="d9a22-122">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push-button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="d9a22-123">管理者は、次の PowerShell コマンドレットを使用してこのポリシーを管理できます (ポリシーは現在、管理センター Microsoft Teamsできません)。</span><span class="sxs-lookup"><span data-stu-id="d9a22-123">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="d9a22-124">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="d9a22-124">New-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="d9a22-125">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="d9a22-125">Get-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [<span data-ttu-id="d9a22-126">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="d9a22-126">Grant-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="d9a22-127">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="d9a22-127">Set-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="d9a22-128">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="d9a22-128">Remove-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="d9a22-129">たとえば、次のコマンドを実行すると、EmployeeCortanaPolicy &#8220;という名前の新しいポリシーが&#8221;作成されます。ここで、Microsoft Teams の Cortana 音声アシスタンスは無効になります。</span><span class="sxs-lookup"><span data-stu-id="d9a22-129">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="d9a22-130">この例では、&#8220;employeeCortanaPolicy&#8221; という名前の既存のポリシーを更新し、プッシュ ボタン呼び出しのみを使用して Microsoft Teams で Cortana 音声アシスタンスを有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d9a22-130">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="d9a22-131">ユーザーは、Cortana の [Cortana マイク] ボタンを選択して Cortana を呼び出Teams。</span><span class="sxs-lookup"><span data-stu-id="d9a22-131">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="d9a22-132">ウェイク ワード (&#8220;Cortana&#8221; または Cortana &#8220;) の呼び&#8221;呼び出しは無効になります。</span><span class="sxs-lookup"><span data-stu-id="d9a22-132">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="d9a22-133">この例では、ポリシーを更新し、プッシュ ボタンとウェイク ワード呼び出しの両方で Cortana 音声アシスタンスを有効にしています。</span><span class="sxs-lookup"><span data-stu-id="d9a22-133">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

<span data-ttu-id="d9a22-134">現在、英語で米国内のユーザー Microsoft 365 Enterpriseの最初のリリースでは、次の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9a22-134">At the time, of the initial release for Microsoft 365 Enterprise users in the US in English, the following are available functions:</span></span>

- <span data-ttu-id="d9a22-135">モバイル Teamsウェイク ワードのアクティブ化はサポートされませんが、今後サポートされる予定です。</span><span class="sxs-lookup"><span data-stu-id="d9a22-135">The Teams mobile app won't support wake word activation, but it will be supported in the future.</span></span>  

- <span data-ttu-id="d9a22-136">Microsoft Teams ミーティングデバイスWindowsおよびMicrosoft Teamsデバイスでは、ウェイク ワードのアクティブ化がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d9a22-136">Microsoft Teams Rooms on Windows and Microsoft Teams display devices will support wake word activation.</span></span>

## <a name="user-control"></a><span data-ttu-id="d9a22-137">ユーザー コントロール</span><span class="sxs-lookup"><span data-stu-id="d9a22-137">User control</span></span>

<span data-ttu-id="d9a22-138">個々のユーザーは、さまざまなデバイスで Cortana 音声アシスタンスを試用できます。</span><span class="sxs-lookup"><span data-stu-id="d9a22-138">Individual users can try out Cortana voice assistance in different devices:</span></span>

- <span data-ttu-id="d9a22-139">モバイル アプリのマイク ボタンTeams選択します。</span><span class="sxs-lookup"><span data-stu-id="d9a22-139">Select the microphone button in the Teams mobile app.</span></span>

- <span data-ttu-id="d9a22-140">[マイク] ボタンを選択するか、[Cortana] と音声をMicrosoft Teams ミーティング。</span><span class="sxs-lookup"><span data-stu-id="d9a22-140">Select the microphone button or say "Cortana" in Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="d9a22-141">ディスプレイ デバイスで "Cortana" Microsoft Teamsします。</span><span class="sxs-lookup"><span data-stu-id="d9a22-141">Say "Cortana" on Microsoft Teams display devices.</span></span>

<span data-ttu-id="d9a22-142">デバイスの設定を使用して、Teamsの Cortana を有効にするかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="d9a22-142">You can control whether Cortana in Teams is enabled for your device by using a setting in the device.</span></span>

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a><span data-ttu-id="d9a22-143">TeamsアプリまたはディスプレイMicrosoft Teams表示</span><span class="sxs-lookup"><span data-stu-id="d9a22-143">Teams mobile app or the Microsoft Teams display</span></span>

  1. <span data-ttu-id="d9a22-144">モバイル アプリTeams開きます。</span><span class="sxs-lookup"><span data-stu-id="d9a22-144">Open the Teams mobile app.</span></span>

  2. <span data-ttu-id="d9a22-145">  >  **[Cortana 設定] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d9a22-145">Select **Settings** > **Cortana**.</span></span>

  3. <span data-ttu-id="d9a22-146">トグルを [オン] **または [オフ]** に **移動します**。</span><span class="sxs-lookup"><span data-stu-id="d9a22-146">Move the toggle **On** or **Off**.</span></span>

### <a name="microsoft-teams-display"></a><span data-ttu-id="d9a22-147">Microsoft Teams表示</span><span class="sxs-lookup"><span data-stu-id="d9a22-147">Microsoft Teams display</span></span>

  1. <span data-ttu-id="d9a22-148">画面の周囲 (ホーム) 画面に移動Microsoft Teamsします。</span><span class="sxs-lookup"><span data-stu-id="d9a22-148">Go to the ambient (home) screen of the Microsoft Teams display.</span></span>

  2. <span data-ttu-id="d9a22-149">ユーザーのアバターを選択し、[] を **設定。**</span><span class="sxs-lookup"><span data-stu-id="d9a22-149">Select the user avatar, and then select **Settings**.</span></span> <span data-ttu-id="d9a22-150">Cortana が有効になっている場合は、"Cortana、設定" と言います。</span><span class="sxs-lookup"><span data-stu-id="d9a22-150">If Cortana is enabled, say, "Cortana, go to Settings."</span></span>

  3. <span data-ttu-id="d9a22-151">トグルを [オン] **または [オフ]** に **移動します**。</span><span class="sxs-lookup"><span data-stu-id="d9a22-151">Move the toggle **On** or **Off**.</span></span>
  
### <a name="microsoft-teams-rooms-on-windows"></a><span data-ttu-id="d9a22-152">Microsoft Teams ミーティングのWindows</span><span class="sxs-lookup"><span data-stu-id="d9a22-152">Microsoft Teams Rooms on Windows</span></span>

<span data-ttu-id="d9a22-153">デバイス レベルで変更を行う場合は、Cortana がテナント レベルで有効になっている場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9a22-153">Making changes at the device level is available if Cortana is enabled at the tenant level.</span></span> <span data-ttu-id="d9a22-154">Cortana は既定でオフにリリースされます。</span><span class="sxs-lookup"><span data-stu-id="d9a22-154">Cortana will be released OFF by default.</span></span>

<span data-ttu-id="d9a22-155">デバイス レベルで Cortana を有効にするには、次の XML 属性を SkypeSettings XML ファイルに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9a22-155">To enable Cortana at the device level, these XML attributes must be added in the SkypeSettings XML file:</span></span>

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

<span data-ttu-id="d9a22-156">Cortana がデバイス レベルで有効になっている場合は、会議レベルで変更を行います。</span><span class="sxs-lookup"><span data-stu-id="d9a22-156">Making changes at the meeting level is available if Cortana is enabled at the device level.</span></span>

<span data-ttu-id="d9a22-157">会議中に Cortana 音声アシスタンスを有効にするには、[オン] または [オフ] の切り替 **えスイッチを\*\*\*\*移動します**。</span><span class="sxs-lookup"><span data-stu-id="d9a22-157">To enable Cortana voice assistance during a meeting, move the toggle **On** or **Off**.</span></span> <span data-ttu-id="d9a22-158">会議が終了すると、Cortana はデバイス レベルの設定セットに戻ります。</span><span class="sxs-lookup"><span data-stu-id="d9a22-158">Once the meeting ends, Cortana returns to the device level settings set.</span></span>

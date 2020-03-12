---
title: Skype for Business Server 2015 での共有線の外観の展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: このトピックでは、Skype for Business Server 2015 (2015 年11月の累積的な更新プログラム) で共有回線の外観 (SLA) を展開する方法について説明します。 SLA は、共有番号と呼ばれる特定の番号で複数の通話を処理するための機能です。
ms.openlocfilehash: 6ad7d6fca40975990fdd6f6ed01bbb89c185e9e7
ms.sourcegitcommit: a34a827dfdad05b281e2e5ec5a80fc4e67fc89e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604224"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="3384d-104">Skype for Business Server 2015 での共有線の外観の展開</span><span class="sxs-lookup"><span data-stu-id="3384d-104">Deploy Shared Line Appearance in Skype for Business Server 2015</span></span>

<span data-ttu-id="3384d-105">このトピックでは、Skype for Business Server 2015 (2015 年11月の累積的な更新プログラム) で共有回線の外観 (SLA) を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3384d-105">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> <span data-ttu-id="3384d-106">SLA は、共有番号と呼ばれる特定の番号で複数の通話を処理するための機能です。</span><span class="sxs-lookup"><span data-stu-id="3384d-106">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="3384d-107">この機能の詳細については、「 [Skype For Business Server 2015 で共有線の外観を計画する](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3384d-107">For more information about this feature, see [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span></span>

<span data-ttu-id="3384d-108">共有回線の外観 (SLA) は、Skype for Business Server の新機能 (2015 年11月の累積的な更新プログラム) です。</span><span class="sxs-lookup"><span data-stu-id="3384d-108">Shared Line Appearance (SLA) is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> <span data-ttu-id="3384d-109">この機能を有効にするには、最初にこの累積的な更新プログラムを展開しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="3384d-109">To enable this feature, you must have first deployed this cumulative update.</span></span>

### <a name="install-shared-line-appearance"></a><span data-ttu-id="3384d-110">共有線の外観をインストールする</span><span class="sxs-lookup"><span data-stu-id="3384d-110">Install Shared Line Appearance</span></span>

1. <span data-ttu-id="3384d-111">Skype for Business Server、2015年11月の累積的な更新プログラム`SkypeServerUpdateInstaller.exe`を展開した後、プール内の各フロントエンドサーバーで修正プログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="3384d-111">After Skype for Business Server, November 2015 Cumulative Update is deployed, run the  `SkypeServerUpdateInstaller.exe` patch on each Front End Server in the pool.</span></span>

2. <span data-ttu-id="3384d-112">インストーラーによって、最新バージョンの SLA アプリケーションが展開されますが、既定ではアプリケーションが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="3384d-112">The installer will deploy the latest version of the SLA application, however, the application is not enabled by default.</span></span> <span data-ttu-id="3384d-113">次の手順に従って、これを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3384d-113">It is enabled by following the steps outlined below:</span></span>

    <span data-ttu-id="3384d-114">a.</span><span class="sxs-lookup"><span data-stu-id="3384d-114">a.</span></span> <span data-ttu-id="3384d-115">各プールに対して次のコマンドを実行して、SLA をサーバーアプリケーションとして登録します。</span><span class="sxs-lookup"><span data-stu-id="3384d-115">Register SLA as a server application by running the following command for each pool:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   <span data-ttu-id="3384d-116">ここで、% FQDN% はプールの完全修飾ドメイン名です。</span><span class="sxs-lookup"><span data-stu-id="3384d-116">where %FQDN% is the fully qualified domain name of the pool.</span></span>

    <span data-ttu-id="3384d-117">b.</span><span class="sxs-lookup"><span data-stu-id="3384d-117">b.</span></span> <span data-ttu-id="3384d-118">次のコマンドを実行して、SLA コマンドレットの RBAC の役割を更新します。</span><span class="sxs-lookup"><span data-stu-id="3384d-118">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

    <span data-ttu-id="3384d-119">c.</span><span class="sxs-lookup"><span data-stu-id="3384d-119">c.</span></span> <span data-ttu-id="3384d-120">SLA がインストールされて有効になっているすべてのプールで、すべてのフロントエンドサーバー (RTCSRV サービス) を再起動します。</span><span class="sxs-lookup"><span data-stu-id="3384d-120">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="3384d-121">SLA グループを作成してユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="3384d-121">Create an SLA group and add users to it</span></span>

1. <span data-ttu-id="3384d-122">[Set-csslaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps)コマンドレットを使用して、SLA グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="3384d-122">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    <span data-ttu-id="3384d-123">Set-csslaconfiguration コマンドレットは、エンタープライズ Voip アカウント SLAGroup1 を SLA エンティティとしてマークし、SLAGroup1 の数が SLA グループの番号になります。</span><span class="sxs-lookup"><span data-stu-id="3384d-123">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group.</span></span> <span data-ttu-id="3384d-124">SLAGroup1 へのすべての呼び出しは、SLA グループ全体を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3384d-124">All calls to SLAGroup1 will ring the entire SLA group.</span></span>

    <span data-ttu-id="3384d-125">次の例では、既存のエンタープライズ Voip ユーザー SLAGroup1 の SLA グループを作成し、SLAGroup1 に割り当てられた番号を SLA のメインライン番号として使用します。</span><span class="sxs-lookup"><span data-stu-id="3384d-125">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>

    <span data-ttu-id="3384d-126">このコマンドは、新しい SLA グループの同時呼び出しの最大数を3に設定し、それを超える通話がビジー信号を聞くことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="3384d-126">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    <span data-ttu-id="3384d-127">Set-csslaconfiguration を使用して、新しい SLA グループを作成したり、既存のものを変更したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="3384d-127">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3384d-128">には、有効な既存`-Identity`のエンタープライズ voip ユーザーアカウントを指定する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3384d-128">Note that what you specify for  `-Identity` must be a valid existing Enterprise Voice-enabled user account.</span></span>

2. <span data-ttu-id="3384d-129">[CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps)コマンドレットを使用して、グループに代理人を追加します。</span><span class="sxs-lookup"><span data-stu-id="3384d-129">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    <span data-ttu-id="3384d-130">次の例では、ユーザーを SLA グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="3384d-130">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="3384d-131">グループに追加される各ユーザーは、有効なエンタープライズ Voip が有効なユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3384d-131">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    <span data-ttu-id="3384d-132">グループに追加するユーザーごとにコマンドレットを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="3384d-132">Repeat the cmdlet for each user you want to add to the group.</span></span> <span data-ttu-id="3384d-133">ユーザーは1つの SLA グループにのみ属することができます。</span><span class="sxs-lookup"><span data-stu-id="3384d-133">Users can only belong to a single SLA group.</span></span>

### <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="3384d-134">SLA グループの通話中オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="3384d-134">Configure the SLA group Busy Option</span></span>

- <span data-ttu-id="3384d-135">[Set-csslaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps)コマンドレットを使用して、SLA グループの通話中オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="3384d-135">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    <span data-ttu-id="3384d-136">次の例では、電話番号202-555-1234 に同時に転送される通話の最大数を超える呼び出しを設定します。</span><span class="sxs-lookup"><span data-stu-id="3384d-136">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="3384d-137">ターゲットは、電話番号ではなく、組織内のユーザーの場合があります。その場合、転送された通話を受信するユーザーの構文は、代理人`sip:<NameofDelegate@domain>`を指定した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="3384d-137">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate:  `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="3384d-138">その他の使用可能`BusyOption`な`Voicemail`パラメーターは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3384d-138">The other possible parameter for  `BusyOption` is `Voicemail`:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="3384d-139">SLA グループの不在着信オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="3384d-139">Configure the SLA group Missed Call Option</span></span>

1. <span data-ttu-id="3384d-140">[Set-csslaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps)コマンドレットを使用して、SLA グループの不在着信オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="3384d-140">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. <span data-ttu-id="3384d-141">次の例では、不在着信をという名前`sla_forward_number`のユーザーに転送するように指定します。</span><span class="sxs-lookup"><span data-stu-id="3384d-141">The following example specifies that missed calls are to be forwarded to the user named  `sla_forward_number`.</span></span> <span data-ttu-id="3384d-142">`-MissedCallOption`パラメーターの有効なオプションは`Forward`、 `BusySignal`、、また`Disconnect`はです。</span><span class="sxs-lookup"><span data-stu-id="3384d-142">The valid options for the  `-MissedCallOption` parameter are `Forward`,  `BusySignal`, or  `Disconnect`.</span></span> <span data-ttu-id="3384d-143">を選択`Forward`する場合は、ユーザーまたは`-MissedCallForwardTarget`電話番号をターゲットとするパラメーターも含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="3384d-143">If you choose  `Forward`, you must also include the  `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="3384d-144">グループから代理人を削除する</span><span class="sxs-lookup"><span data-stu-id="3384d-144">Remove a delegate from a group</span></span>

- <span data-ttu-id="3384d-145">[CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps)コマンドレットを使用して、グループから代理人を削除します。</span><span class="sxs-lookup"><span data-stu-id="3384d-145">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    <span data-ttu-id="3384d-146">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3384d-146">For example:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a><span data-ttu-id="3384d-147">SLA グループを削除する</span><span class="sxs-lookup"><span data-stu-id="3384d-147">Delete an SLA group</span></span>

- <span data-ttu-id="3384d-148">[Set-csslaconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps)コマンドレットを使用して、SLA グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="3384d-148">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    <span data-ttu-id="3384d-149">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3384d-149">For example:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```



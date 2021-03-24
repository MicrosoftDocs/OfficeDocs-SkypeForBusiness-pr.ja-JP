---
title: Skype for Business Server 2015 での共有回線の外観の展開
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: このトピックでは、Skype for Business Server 2015、2015 年 11 月の累積的な更新プログラムで共有回線の外観 (SLA) を展開する方法について説明します。 SLA は、共有番号と呼ばれる特定の番号で複数の呼び出しを処理する機能です。
ms.openlocfilehash: 7758354b7c4be123cb9b5a482af3304b069931a8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104913"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="eb5e6-104">Skype for Business Server 2015 での共有回線の外観の展開</span><span class="sxs-lookup"><span data-stu-id="eb5e6-104">Deploy Shared Line Appearance in Skype for Business Server 2015</span></span>

<span data-ttu-id="eb5e6-105">このトピックでは、Skype for Business Server 2015、2015 年 11 月の累積的な更新プログラムで共有回線の外観 (SLA) を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-105">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> <span data-ttu-id="eb5e6-106">SLA は、共有番号と呼ばれる特定の番号で複数の呼び出しを処理する機能です。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-106">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="eb5e6-107">この機能の詳細については [、「Plan for Shared Line appearance in Skype for Business Server 2015」を参照してください](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-107">For more information about this feature, see [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span></span>

<span data-ttu-id="eb5e6-108">共有回線の外観 (SLA) は、Skype for Business Server 2015 年 11 月の累積的な更新プログラムの新機能です。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-108">Shared Line Appearance (SLA) is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> <span data-ttu-id="eb5e6-109">この機能を有効にするには、最初にこの累積的な更新プログラムを展開している必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-109">To enable this feature, you must have first deployed this cumulative update.</span></span>

### <a name="install-shared-line-appearance"></a><span data-ttu-id="eb5e6-110">共有行の外観をインストールする</span><span class="sxs-lookup"><span data-stu-id="eb5e6-110">Install Shared Line Appearance</span></span>

1. <span data-ttu-id="eb5e6-111">Skype for Business Server の後、2015 年 11 月の累積的な更新プログラムが展開された後、プール内の各フロント エンド サーバーで更新プログラム  `SkypeServerUpdateInstaller.exe` を実行します。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-111">After Skype for Business Server, November 2015 Cumulative Update is deployed, run the  `SkypeServerUpdateInstaller.exe` patch on each Front End Server in the pool.</span></span>

2. <span data-ttu-id="eb5e6-112">インストーラーは SLA アプリケーションの最新バージョンを展開しますが、アプリケーションは既定では有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-112">The installer will deploy the latest version of the SLA application, however, the application is not enabled by default.</span></span> <span data-ttu-id="eb5e6-113">この機能は、以下に示す手順に従って有効になります。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-113">It is enabled by following the steps outlined below:</span></span>

    <span data-ttu-id="eb5e6-114">a.</span><span class="sxs-lookup"><span data-stu-id="eb5e6-114">a.</span></span> <span data-ttu-id="eb5e6-115">プールごとに次のコマンドを実行して、SLA をサーバー アプリケーションとして登録します。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-115">Register SLA as a server application by running the following command for each pool:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   <span data-ttu-id="eb5e6-116">ここで、%FQDN% はプールの完全修飾ドメイン名です。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-116">where %FQDN% is the fully qualified domain name of the pool.</span></span>

    <span data-ttu-id="eb5e6-117">b.</span><span class="sxs-lookup"><span data-stu-id="eb5e6-117">b.</span></span> <span data-ttu-id="eb5e6-118">次のコマンドを実行して、SLA コマンドレットの RBAC ロールを更新します。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-118">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

    <span data-ttu-id="eb5e6-119">c.</span><span class="sxs-lookup"><span data-stu-id="eb5e6-119">c.</span></span> <span data-ttu-id="eb5e6-120">SLA がインストールされ有効になっているすべてのプールで、すべてのフロントエンド サーバー (RTCSRV サービス) を再起動します。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-120">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="eb5e6-121">SLA グループを作成し、そのグループにユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="eb5e6-121">Create an SLA group and add users to it</span></span>

1. <span data-ttu-id="eb5e6-122">[Set-CsSlaConfiguration コマンドレットを使用して SLA グループを作成](/powershell/module/skype/set-csslaconfiguration?view=skype-ps)します。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-122">Create the SLA group by using the [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    <span data-ttu-id="eb5e6-123">このSet-CsSlaConfiguration、SLAGroup1 エンタープライズ VoIP SLAGroup1 を SLA エンティティとしてマークし、SLAGroup1 の数が SLA グループの番号になります。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-123">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group.</span></span> <span data-ttu-id="eb5e6-124">SLAGroup1 へのすべての呼び出しは、SLA グループ全体を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-124">All calls to SLAGroup1 will ring the entire SLA group.</span></span>

    <span data-ttu-id="eb5e6-125">次の使用例は、SLAGroup1 という既存のユーザーの SLA グループエンタープライズ VoIP作成し、SLAGroup1 に割り当てられた番号を SLA メインライン番号として使用します。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-125">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>

    <span data-ttu-id="eb5e6-126">このコマンドは、新しい SLA グループの同時呼び出しの最大数を 3 に設定し、それを超える通話でビジー信号を聞き取る場合に設定します。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-126">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    <span data-ttu-id="eb5e6-127">新しい SLA グループSet-CsSlaConfiguration既存の SLA グループを変更する場合は、このグループを使用します。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-127">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eb5e6-128">指定する項目は、有効な既存のユーザー アカウント  `-Identity` エンタープライズ VoIP必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-128">Note that what you specify for  `-Identity` must be a valid existing Enterprise Voice-enabled user account.</span></span>

2. <span data-ttu-id="eb5e6-129">[Add-CsSlaDelegates](/powershell/module/skype/add-cssladelegates?view=skype-ps)コマンドレットを使用してグループに代理人を追加します。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-129">Add delegates to the group by using the [Add-CsSlaDelegates](/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    <span data-ttu-id="eb5e6-130">次の使用例は、SLA グループにユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-130">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="eb5e6-131">グループに追加する各ユーザーは、有効なユーザーエンタープライズ VoIP必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-131">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    <span data-ttu-id="eb5e6-132">グループに追加するユーザーごとにコマンドレットを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-132">Repeat the cmdlet for each user you want to add to the group.</span></span> <span data-ttu-id="eb5e6-133">ユーザーは 1 つの SLA グループにのみ属できます。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-133">Users can only belong to a single SLA group.</span></span>

### <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="eb5e6-134">SLA グループのビジー オプションの構成</span><span class="sxs-lookup"><span data-stu-id="eb5e6-134">Configure the SLA group Busy Option</span></span>

- <span data-ttu-id="eb5e6-135">[Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps)コマンドレットを使用して SLA グループのビジー オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-135">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    <span data-ttu-id="eb5e6-136">次の使用例は、電話番号 202-555-1234 に転送する同時呼び出しの最大数を超える呼び出しを設定します。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-136">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="eb5e6-137">ターゲットは、電話番号の代わりに組織内のユーザーである可能性があります。その場合、転送された呼び出しを受信するユーザーの構文は、代理人を指定した場合と同じです  `sip:<NameofDelegate@domain>` 。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-137">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate:  `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="eb5e6-138">もう 1 つのパラメーターは  `BusyOption` 次の場合です `Voicemail` 。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-138">The other possible parameter for  `BusyOption` is `Voicemail`:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="eb5e6-139">SLA グループの [通話不足] オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="eb5e6-139">Configure the SLA group Missed Call Option</span></span>

1. <span data-ttu-id="eb5e6-140">[Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps)コマンドレットを使用して、SLA グループの [Missed Call Option] を構成します。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-140">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. <span data-ttu-id="eb5e6-141">次の使用例は、呼び出しの欠落をという名前のユーザーに転送する場合に指定します  `sla_forward_number` 。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-141">The following example specifies that missed calls are to be forwarded to the user named  `sla_forward_number`.</span></span> <span data-ttu-id="eb5e6-142">パラメーターの有効なオプション  `-MissedCallOption` は、 `Forward`  `BusySignal` または  `Disconnect` です。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-142">The valid options for the  `-MissedCallOption` parameter are `Forward`,  `BusySignal`, or  `Disconnect`.</span></span> <span data-ttu-id="eb5e6-143">選択した場合  `Forward` は、ユーザーまたは電話番号をターゲットとして  `-MissedCallForwardTarget` パラメーターも含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-143">If you choose  `Forward`, you must also include the  `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="eb5e6-144">グループから代理人を削除する</span><span class="sxs-lookup"><span data-stu-id="eb5e6-144">Remove a delegate from a group</span></span>

- <span data-ttu-id="eb5e6-145">[Remove-CsSlaDelegates](/powershell/module/skype/remove-cssladelegates?view=skype-ps)コマンドレットを使用して、グループから代理人を削除します。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-145">Remove a delegate from a group by using the [Remove-CsSlaDelegates](/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    <span data-ttu-id="eb5e6-146">例:</span><span class="sxs-lookup"><span data-stu-id="eb5e6-146">For example:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a><span data-ttu-id="eb5e6-147">SLA グループを削除する</span><span class="sxs-lookup"><span data-stu-id="eb5e6-147">Delete an SLA group</span></span>

- <span data-ttu-id="eb5e6-148">[Remove-CsSlaConfiguration コマンドレット](/powershell/module/skype/remove-csslaconfiguration?view=skype-ps)を使用して SLA グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-148">Delete an SLA group by using the [Remove-CsSlaConfiguration](/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    <span data-ttu-id="eb5e6-149">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="eb5e6-149">For example:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```
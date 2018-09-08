---
title: Skype for Business Server 2015 で回線共有機能を展開する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: ここでは、Skype for Business Server 2015 の累積的な更新プログラム (2015 年 11 月) で回線共有機能 (SLA) を展開する方法について説明します。SLA は、共有番号と呼ばれる特定の電話番号で複数の通話を処理するための機能です。
ms.openlocfilehash: 6083bd408804a633d7de904c794767bd07499b6a
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2018
ms.locfileid: "23891353"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="68bc9-104">Skype for Business Server 2015 で回線共有機能を展開する</span><span class="sxs-lookup"><span data-stu-id="68bc9-104">Deploy Shared Line Appearance in Skype for Business Server 2015</span></span>

<span data-ttu-id="68bc9-p102">ここでは、Skype for Business Server 2015 の累積的な更新プログラム (2015 年 11 月) で回線共有機能 (SLA) を展開する方法について説明します。SLA は、共有番号と呼ばれる特定の電話番号で複数の通話を処理するための機能です。</span><span class="sxs-lookup"><span data-stu-id="68bc9-p102">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update. SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="68bc9-107">この機能の詳細については、 [Skype のビジネス サーバー 2015 の線の外観を共有の予定](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68bc9-107">For more information about this feature, see [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span></span>

<span data-ttu-id="68bc9-108">2015年 11 月はビジネス サーバーでは、Skype の新機能、共有行の外観 (SLA) 累積的な更新です。</span><span class="sxs-lookup"><span data-stu-id="68bc9-108">Shared Line Appearance (SLA) is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> <span data-ttu-id="68bc9-109">この機能を有効にするには、まずこの累積的な更新プログラムを展開しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="68bc9-109">To enable this feature, you must have first deployed this cumulative update.</span></span>

### <a name="install-shared-line-appearance"></a><span data-ttu-id="68bc9-110">回線共有機能のインストール</span><span class="sxs-lookup"><span data-stu-id="68bc9-110">Install Shared Line Appearance</span></span>

1. <span data-ttu-id="68bc9-111">ビジネス サーバー、2015年 11 月累積的な更新を展開すると、Skype の後を実行、 `SkypeServerUpdateInstaller.exe` 、プール内のそれぞれのフロント エンド サーバーに修正プログラムです。</span><span class="sxs-lookup"><span data-stu-id="68bc9-111">After Skype for Business Server, November 2015 Cumulative Update is deployed, run the  `SkypeServerUpdateInstaller.exe` patch on each Front End Server in the pool.</span></span>

2. <span data-ttu-id="68bc9-p104">インストーラーによって SLA アプリケーションの最新バージョンが展開されますが、アプリケーションは既定で有効ではありません。以下の手順で有効にします。</span><span class="sxs-lookup"><span data-stu-id="68bc9-p104">The installer will deploy the latest version of the SLA application, however, the application is not enabled by default. It is enabled by following the steps outlined below:</span></span>

    <span data-ttu-id="68bc9-114">a.</span><span class="sxs-lookup"><span data-stu-id="68bc9-114">a.</span></span> <span data-ttu-id="68bc9-115">各プールで次のコマンドを実行して、SLA をサーバー アプリケーションとして登録します。</span><span class="sxs-lookup"><span data-stu-id="68bc9-115">Register SLA as a server application by running the following command for each pool:</span></span>

   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   https://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled                $true -Priority (Get-CsServerApplication -Identity              'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   <span data-ttu-id="68bc9-116">%FQDN% は、プールの完全修飾ドメイン名です。</span><span class="sxs-lookup"><span data-stu-id="68bc9-116">where %FQDN% is the fully qualified domain name of the pool.</span></span>

    <span data-ttu-id="68bc9-117">b.</span><span class="sxs-lookup"><span data-stu-id="68bc9-117">b.</span></span> <span data-ttu-id="68bc9-118">次のコマンドを実行して、SLA コマンドレッドの RBAC の役割を更新します。</span><span class="sxs-lookup"><span data-stu-id="68bc9-118">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>

   ```
   Update-CsAdminRole
   ```

    <span data-ttu-id="68bc9-119">c.</span><span class="sxs-lookup"><span data-stu-id="68bc9-119">c.</span></span> <span data-ttu-id="68bc9-120">SLA がインストールされて有効になっているすべてのプールで、すべてのフロントエンド サーバー (RTCSRV サービス) を再起動します。</span><span class="sxs-lookup"><span data-stu-id="68bc9-120">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>

  ```
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
  ```

### <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="68bc9-121">SLA グループを作成してユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="68bc9-121">Create an SLA group and add users to it</span></span>

1. <span data-ttu-id="68bc9-122">[セット CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps)コマンドレットを使用して、SLA のグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="68bc9-122">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
  ```

    <span data-ttu-id="68bc9-p108">Set-CsSlaConfiguration コマンドレットを実行すると、エンタープライズ VoIP アカウントである SLAGroup1 が SLA エンティティとしてマークされ、SLAGroup1 の番号が SLA グループの番号になります。SLAGroup1 に電話をかけると常に、SLA グループ全体に着信します。</span><span class="sxs-lookup"><span data-stu-id="68bc9-p108">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group. All calls to SLAGroup1 will ring the entire SLA group.</span></span>

    <span data-ttu-id="68bc9-125">次の例では、既存のエンタープライズ VoIP ユーザーである SLAGroup1 の SLA グループを作成し、SLAGroup1 に割り当てられる番号を SLA の主線番号として使用します。</span><span class="sxs-lookup"><span data-stu-id="68bc9-125">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>

    <span data-ttu-id="68bc9-126">このコマンドを実行すると、新しい SLA グループの最大同時通話数が 3 に設定され、4 件目以上の通話に対しては話中音が流れるようになります。</span><span class="sxs-lookup"><span data-stu-id="68bc9-126">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>

  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
  ```

    <span data-ttu-id="68bc9-127">Set-CsSlaConfiguration を使用して、新しい SLA グループの作成や既存の SLA グループの変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="68bc9-127">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>

    > [!NOTE]
    > <span data-ttu-id="68bc9-128">何に指定することに注意してください`-Identity`既存ユーザーのエンタープライズ VoIP を有効にしたアカウントを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="68bc9-128">Note that what you specify for  `-Identity` must be a valid existing Enterprise Voice-enabled user account.</span></span>

2. <span data-ttu-id="68bc9-129">グループにデリゲートを追加するには、[追加 CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="68bc9-129">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet:</span></span>

  ```
  Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
  ```

    <span data-ttu-id="68bc9-130">次の例では、SLA グループにユーザーを追加しています。</span><span class="sxs-lookup"><span data-stu-id="68bc9-130">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="68bc9-131">グループに追加する各ユーザーは、有効なエンタープライズ VoIP が有効なユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="68bc9-131">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>

  ```
  Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
  ```

    <span data-ttu-id="68bc9-p110">グループに追加したい各ユーザーについてコマンドレットを繰り返し実行します。ユーザーは、単一の SLA グループにのみ属することができます。</span><span class="sxs-lookup"><span data-stu-id="68bc9-p110">Repeat the cmdlet for each user you want to add to the group. Users can only belong to a single SLA group.</span></span>

### <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="68bc9-134">SLA グループの通話中オプションの構成</span><span class="sxs-lookup"><span data-stu-id="68bc9-134">Configure the SLA group Busy Option</span></span>

- <span data-ttu-id="68bc9-135">SLA が構成[セット CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps)コマンドレットを使用して、ビジー状態のオプションをグループ化します。</span><span class="sxs-lookup"><span data-stu-id="68bc9-135">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    <span data-ttu-id="68bc9-136">電話番号 202-555-1234 に転送するのには、同時呼び出しの最大数を超える呼び出しを設定する例を次にします。</span><span class="sxs-lookup"><span data-stu-id="68bc9-136">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="68bc9-137">ターゲットは、電話番号の代わりに、組織内のユーザーである可能性があります。転送された呼び出しを受信する人のための構文は、代理人を指定する場合と同じ場合は、: `sip:<NameofDelegate@domain>`。</span><span class="sxs-lookup"><span data-stu-id="68bc9-137">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate:  `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="68bc9-138">他の可能なパラメーターの`BusyOption`、 `Voicemail`。</span><span class="sxs-lookup"><span data-stu-id="68bc9-138">The other possible parameter for  `BusyOption` is `Voicemail`:</span></span>

  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="68bc9-139">SLA グループの不在着信オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="68bc9-139">Configure the SLA group Missed Call Option</span></span>

1. <span data-ttu-id="68bc9-140">[セット CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps)コマンドレットを使用して、SLA グループ喪失の呼び出しのオプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="68bc9-140">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
  ```

2. <span data-ttu-id="68bc9-141">次の例は、不在着信がという名前のユーザーに転送されることを指定します。 `sla_forward_number`。</span><span class="sxs-lookup"><span data-stu-id="68bc9-141">The following example specifies that missed calls are to be forwarded to the user named  `sla_forward_number`.</span></span> <span data-ttu-id="68bc9-142">有効なオプション、`-MissedCallOption`パラメーターは、 `Forward`、 `BusySignal`、または`Disconnect`。</span><span class="sxs-lookup"><span data-stu-id="68bc9-142">The valid options for the  `-MissedCallOption` parameter are `Forward`,  `BusySignal`, or  `Disconnect`.</span></span> <span data-ttu-id="68bc9-143">選択する場合は、`Forward`も含める必要があります、 `-MissedCallForwardTarget` 、パラメーター、ユーザーまたは電話番号、ターゲットとして。</span><span class="sxs-lookup"><span data-stu-id="68bc9-143">If you choose  `Forward`, you must also include the  `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>

  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
  ```

### <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="68bc9-144">グループから代理人を削除する</span><span class="sxs-lookup"><span data-stu-id="68bc9-144">Remove a delegate from a group</span></span>

- <span data-ttu-id="68bc9-145">[削除 CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps)コマンドレットを使用してグループからデリゲートを削除します。</span><span class="sxs-lookup"><span data-stu-id="68bc9-145">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet:</span></span>

  ```
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    <span data-ttu-id="68bc9-146">例:</span><span class="sxs-lookup"><span data-stu-id="68bc9-146">For example:</span></span>

  ```
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a><span data-ttu-id="68bc9-147">SLA グループを削除する</span><span class="sxs-lookup"><span data-stu-id="68bc9-147">Delete an SLA group</span></span>

- <span data-ttu-id="68bc9-148">[削除 CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps)コマンドレットを使用して、SLA のグループを削除します。</span><span class="sxs-lookup"><span data-stu-id="68bc9-148">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    <span data-ttu-id="68bc9-149">例:</span><span class="sxs-lookup"><span data-stu-id="68bc9-149">For example:</span></span>

  ```
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```



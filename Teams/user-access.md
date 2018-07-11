---
title: Microsoft Teams へのユーザー アクセスを管理する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: ユーザーごとにユーザーレベル アクセスを有効または無効にする方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: a612420808af06a773d206573f02d805aac06b15
ms.sourcegitcommit: 8c3dcfc564c489f4d33bd5f391a5a66b99ded07e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "20265884"
---
<a name="manage-user-access-to-microsoft-teams"></a>Microsoft Teams へのユーザー アクセスを管理する
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

ユーザー レベルでは、マイクロソフトのチームへのアクセスを有効またはの割り当てまたはチームの Microsoft 製品のライセンスを削除して、ユーザーごとに無効にすることができます。

現時点では、チーム、またはチームの機能のサブセット オンまたはオフにライセンス以外では、個々 のユーザー レベルのポリシーのオプションはありません。

> [!NOTE]
>オンにするチーム、会社のすべてのユーザーのプロジェクトおよびその他の動的なイニシアティブの実施はチームを形成することができますようにすることをお勧めします。 決定する場合でも、パイロットがありますされるため、すべてのユーザーに対して有効になっているチームが、ユーザーのパイロット グループへの通信のみを対象とすると便利です。

## <a name="manage-directly-through-the-office-365-admin-center"></a>Office 365 の管理ページを使用して直接管理します。

チームのユーザー レベルのライセンスは、Office 365 管理センターのユーザーの管理インターフェイスを使用して直接管理されます。 管理者は、新しいユーザーの新しいユーザー アカウントを作成するときに、または既存のアカウントを持つユーザーにライセンスを割り当てることができます。 管理者は、マイクロソフトのチームのライセンスを管理するために Office 365 のグローバル管理者またはユーザー管理者の権限が必要です。

E3 または E5 といったライセンス SKU をユーザーに割り当てる場合、Microsoft Teams ライセンスが自動的に割り当てられ、そのユーザーには Microsoft Teams が有効化されます。管理者はすべての Office 365 サービスとライセンスを細かく制御できます。特定のユーザーまたはグループの Microsoft Teams ライセンスを有効または無効にすることができます。

![Office 365 管理センターの [製品ライセンス] セクションのスクリーンショット。](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

チームのユーザー ライセンスは、いつでも無効にできます。 ライセンスを無効にすると、マイクロソフトのチームへのユーザー アクセスが禁止され、ユーザーが Office 365 アプリケーション起動ツールをクリックし、ホームページでチームを表示しなくなります。

![Microsoft Teams が選択されていることを示す Office 365 管理センターの [製品ライセンス] セクションのスクリーンショット。](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a>PowerShell を使用して管理します。

PowerShell からワークロード ライセンスとして Teams を有効または無効にすることは、別のワークロードとして実行されます。 Microsoft Teams ではサービス プランの名前は TEAMS1 になります。 (詳細については、「[Office 365 PowerShell を使用してサービスへのアクセスを無効にする](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell)」をご覧ください。)

**サンプル:** クイック サンプルだけに特定のライセンスの種類のすべてのユーザーのチームを無効する方法を次に示します。 まずこの方法を行い、次にパイロットで使用する目的でアクセスが必要なユーザーに対して個別に有効にする必要があります。

組織内で利用可能なサブスクリプションの種類を表示するには、次のコマンドを使用します。

      Get-MsolAccountSku

組織名と自分の学校で使用するプランを含むプランの名前を記入します (例: ContosoSchool:ENTERPRISEPACK_STUDENT)。次に、次のコマンドを実行します。

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
チームを名前付きのプランのアクティブなライセンスを持つすべてのユーザーを無効にするには、次のコマンドを実行します。

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |判断ポイント         |<ul><li>チームの契約時に、組織の計画は、組織全体にわたって何ですか。  パイロット (開く)</li></ul>         |
|![次のステップ アイコン。](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |次のステップ         |<ul><li>閉じられたパイロットで関与促進を行う場合は、ライセンスまたは対象を絞った通信のいずれかの手段で実施するかを決定します。</li><li>によって意思決定を行うパイロット ・ チームを (必要な場合) にアクセスを許可されているユーザーのみを確認する手順を実行します。</li><li>ユーザーの人は (表示されません) のガイドラインをドキュメント チームへのアクセスがあります。</li></ul>         |

## <a name="manage-via-office-sku-level-switch"></a>Office Sku レベル スイッチ経由で管理します。
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

1.  グローバル管理者の権限を持つアカウントで [Office 365 管理センター](https://go.microsoft.com/fwlink/?linkid=854614)にサインインします。

2.  [**設定**]  >  [**サービスとアドイン**] に移動します。

    ![Office 365 管理センターの、[サービスとアドイン] が選択されている [設定] セクションのスクリーンショット。 ](media/Set_up_Microsoft_Teams_in_your_Office_365_organization_image1.png)

3.  [サービスとアドイン] ページで **[Microsoft Teams]** をクリックします。

    ![[Microsoft Teams] が選択されている [サービスとアドイン] ページのスクリーンショット。](media/Set_up_Microsoft_Teams_in_your_Office_365_organization_image2.png)

4.  組織に対して Teams を有効にするには、ライセンス選択ウィンドウで各ライセンスを選択してからトグルを [**オン**] に設定して [**保存**] をクリックします。

    ![トグルがオンに設定されて Microsoft Teams が有効になっていることを示す Microsoft Teams の設定ページのスクリーンショット。](media/Services-and-addins-control-Microsoft-Teams.PNG)

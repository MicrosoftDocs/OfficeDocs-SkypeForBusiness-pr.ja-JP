---
title: Microsoft Teams へのユーザー アクセスを管理する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: ユーザーごとにユーザーレベル アクセスを有効または無効にする方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83d2b0710b811431546f0df9931d3a0b867d2b2b
ms.sourcegitcommit: 28dd9b8ca3de35a73e4d6923eff5546925435b8b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "30683885"
---
<a name="manage-user-access-to-microsoft-teams"></a>Microsoft Teams へのユーザー アクセスを管理する
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

ユーザー レベルでは、マイクロソフトのチームへのアクセスを有効またはの割り当てまたはチームの Microsoft 製品のライセンスを削除して、ユーザーごとに無効にすることができます。

メッセージング ポリシー、管理、チーム管理センターから、チーム内のユーザーに利用可能などのようなチャットとチャネルのメッセージング機能を制御するために使用します。 既定のポリシーを使用したり、組織内のユーザーの 1 つまたは複数のカスタム メッセージング ポリシーを作成できます。 詳細については、[チーム内のメッセージング ポリシーの管理](messaging-policies-in-teams.md)を参照してください。

> [!NOTE]
>オンにするチーム、会社のすべてのユーザーのプロジェクトおよびその他の動的なイニシアティブの実施はチームを形成することができますようにすることをお勧めします。 決定する場合でも、パイロットがありますされるため、すべてのユーザーに対して有効になっているチームが、ユーザーのパイロット グループへの通信のみを対象とすると便利です。

## <a name="manage-teams-through-the-office-365-admin-center"></a>Office 365 管理センターを使用してチームを管理します。

チームのユーザー レベルのライセンスは、Office 365 管理センターのユーザーの管理インターフェイスを使用して直接管理されます。 管理者は、新しいユーザーの新しいユーザー アカウントを作成するときに、または既存のアカウントを持つユーザーにライセンスを割り当てることができます。 管理者は、マイクロソフトのチームのライセンスを管理するために Office 365 のグローバル管理者またはユーザー管理者の権限が必要です。

E3 または E5 といったライセンス SKU をユーザーに割り当てる場合、Microsoft Teams ライセンスが自動的に割り当てられ、そのユーザーには Microsoft Teams が有効化されます。管理者はすべての Office 365 サービスとライセンスを細かく制御できます。特定のユーザーまたはグループの Microsoft Teams ライセンスを有効または無効にすることができます。

![Office 365 管理センターの [製品ライセンス] セクションのスクリーンショット。](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

チームのユーザー ライセンスは、いつでも無効にできます。 ライセンスを無効にすると、マイクロソフトのチームへのユーザー アクセスが禁止され、ユーザーが Office 365 アプリケーション起動ツールをクリックし、ホームページでチームを表示しなくなります。

![Microsoft Teams が選択されていることを示す Office 365 管理センターの [製品ライセンス] セクションのスクリーンショット。](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a>PowerShell を使用して管理します。

> [!IMPORTANT]
> MsolLicenseOptions では新しいがない限り、以前に無効にされたすべてのサービスを有効にする、カスタマイズされたスクリプトでは identitied explictitly です。 例として、両方の Exchange & 135、139、445、チームの無効化中に無効になっている影響を与えるのままにする場合はする必要があります各自にこのスクリプトに影響を与えるが有効になりますが認められたユーザーの両方の Exchange &。 この機能を管理するために GUI を利用する場合を参照してください: [Office 365 のライセンスのレポートおよび管理ツールを一括で削除するライセンスを割り当てる](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)

PowerShell からワークロード ライセンスとして Teams を有効または無効にすることは、別のワークロードとして実行されます。 Microsoft Teams ではサービス プランの名前は TEAMS1 になります。 GCC のサービス計画の名前は TEAMS_GOV です。 GCC の高いサービス プラン名の TEAMS_GCCHIGH。 DoD サービス計画の名前は TEAMS_DOD の (「」を参照[へのアクセスを無効にするには、Office 365 の PowerShell でサービス](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell)の詳細についてです。)

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
|![次のステップ アイコン。](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |次のステップ         |<ul><li>かどうか、ライセンスを使用して実行するか、通信を対象としたかどうか、試験運用が終了したを使用して契約時を決定します。</li><li>によって意思決定を行うパイロット ・ チームを (必要な場合) にアクセスを許可されているユーザーのみを確認する手順を実行します。</li><li>ユーザーの人は (表示されません) のガイドラインをドキュメント チームへのアクセスがあります。</li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a>Office 365 テナントのレベルでチームを管理します。
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]


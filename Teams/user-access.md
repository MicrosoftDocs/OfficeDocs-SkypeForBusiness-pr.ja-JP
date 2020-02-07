---
title: Microsoft Teams へのユーザー アクセスを管理する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.reviewer: ritikag
search.appverid: MET150
description: ユーザーごとにユーザーレベル アクセスを有効または無効にする方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 379573e7c671c3a5bca906cc3986bce068921b07
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41833657"
---
<a name="manage-user-access-to-microsoft-teams"></a>Microsoft Teams へのユーザー アクセスを管理する
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

ユーザーレベルでは、microsoft Teams 製品ライセンスを割り当てまたは削除することで、ユーザーごとに Microsoft Teams へのアクセスを有効または無効にすることができます。

Teams 管理センターから管理されるメッセージポリシーを使用して、Teams のユーザーが利用できるチャットおよびチャネルメッセージング機能を制御します。 組織内のユーザーに対して、既定のポリシーを使用するか、1つ以上のカスタムメッセージポリシーを作成することができます。 詳細については、「 [Teams のメッセージングポリシーを管理する」](messaging-policies-in-teams.md)を参照してください。

> [!NOTE]
>組織内のすべてのユーザーに対して Teams を有効にすることをお勧めします。これにより、チームはプロジェクトやその他の動的なイニシアチブの organically を形成することができます。 パイロットを決定している場合でも、チームをすべてのユーザーに対して有効にしておくことをお勧めしますが、ユーザーのパイロットグループとの通信のみを対象としています。

## <a name="manage-teams-through-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターを使用してチームを管理する

Teams のユーザーレベルのライセンスは、Microsoft 365 管理センターのユーザー管理インターフェイスを使用して直接管理されます。 管理者は、新しいユーザーアカウントが作成されたとき、または既存のアカウントを持つユーザーに対して、新しいユーザーにライセンスを割り当てることができます。 管理者は、Microsoft Teams のライセンスを管理するための Office 365 グローバル管理者またはユーザー管理者の権限を持っている必要があります。

E3 または E5 といったライセンス SKU をユーザーに割り当てる場合、Microsoft Teams ライセンスが自動的に割り当てられ、そのユーザーには Microsoft Teams が有効化されます。管理者はすべての Office 365 サービスとライセンスを細かく制御できます。特定のユーザーまたはグループの Microsoft Teams ライセンスを有効または無効にすることができます。

![管理センターの [製品ライセンス] セクションのスクリーンショット。](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

Teams ユーザーライセンスは、いつでも無効にすることができます。 ライセンスを無効にすると、ユーザーは Microsoft Teams へのアクセスを許可されなくなり、Office 365 アプリ起動ツールとホームページで Teams を表示することはできなくなります。

![[製品のライセンス] セクションで選択された Teams を示すスクリーンショット。](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a>PowerShell を使用して管理する

> [!IMPORTANT]
> MsolLicenseOptions を使うと、カスタマイズしたスクリプトで明示的に指定されていない限り、以前に無効になっていたすべてのサービスを有効にできます。 たとえば、チームを無効にしている間も Exchange & Sway を無効にする必要がある場合は、この操作をスクリプトに含めるか、または両方とも Exchange & Sway が有効になるように、特定のユーザーに対して行う必要があります。 GUI を使ってこの機能を管理する方法については、「 [Office 365 ライセンスレポートと管理ツール-一括](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)してライセンスを削除する」を参照してください。

PowerShell からワークロード ライセンスとして Teams を有効または無効にすることは、別のワークロードとして実行されます。 Microsoft Teams ではサービス プランの名前は TEAMS1 になります。 GCC の場合、サービスプラン名は TEAMS_GOV です。 GCC 高の場合、サービスプラン名は TEAMS_GCCHIGH。 DoD の場合、サービスプラン名は TEAMS_DOD (詳細については、「 [Office 365 PowerShell でサービスへのアクセスを無効](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell)にする」を参照してください。)

**サンプル:** 次に示すのは、特定のライセンスの種類のすべてのユーザーに対して Teams を無効にする方法の簡単なサンプルです。 まずこの方法を行い、次にパイロットで使用する目的でアクセスが必要なユーザーに対して個別に有効にする必要があります。

組織内で利用可能なサブスクリプションの種類を表示するには、次のコマンドを使用します。

      Get-MsolAccountSku

組織名と自分の学校で使用するプランを含むプランの名前を記入します (例: ContosoSchool:ENTERPRISEPACK_STUDENT)。次に、次のコマンドを実行します。

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
指定したプランのアクティブなライセンスを持つすべてのユーザーのチームを無効にするには、次のコマンドを実行します。

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![判断ポイントを表すアイコン](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |判断ポイント         |<ul><li>組織全体でのチームのオンボードの計画はどのようなものですか?  (パイロットまたはオープン)</li></ul>         |
|![次の手順を示すアイコン](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |次のステップ         |<ul><li>終了したパイロットによるオンボードの場合は、ライセンスまたは対象指定の通信を使用するかどうかを決定します。</li><li>決定に応じて、チームへのアクセスが許可されているパイロットユーザー (必要な場合) だけを確認するための手順を実行します。</li><li>Teams へのアクセス権を持つ (または使用しない) ユーザーを対象としたガイドラインを文書化します。</li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a>Office 365 テナントレベルでチームを管理する
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]


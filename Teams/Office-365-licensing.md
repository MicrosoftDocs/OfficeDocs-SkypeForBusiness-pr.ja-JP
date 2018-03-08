---
title: "チームの Microsoft office 365 のライセンス"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "別の Office 365 のライセンスについて説明し、どのプレゼンスがユーザーの Microsoft チームと有効または無効にする方法を有効にします。"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 1ae50ce803281135f61e2d4ae4be7a5a8eac57bc
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="office-365-licensing-for-microsoft-teams"></a>チームの Microsoft office 365 のライセンス
========================================

次の Office 365 サブスクリプションの場合は、チームのユーザーを有効にします。

|Small Business プラン  |Enterprise プラン  |教育機関向けプラン  |
|---------|---------|---------|
|Office 365 Business Essentials     |Office 365 Enterprise E1         |Office 365 Education         |
|Office 365 Business Premium     |Office 365 Enterprise E3         |Office 365 Education Plus         |
|     |Office 365 Enterprise E4 の (廃止)         |Office 365 Education E3 が (廃止)         |
|     |Office 365 Enterprise E5         |Office 365 Education E5   
      |Office 365 Enterprise F1 |  |

> [!NOTE]
> チームは、非営利組織で利用できるもできます。行政機関向けのライセンスは現在サポートされていませんが、今後の調査します。
        


チーム**中核的な**機能では、別の Office 365 サブスクリプションの相違点がない、コンプライアンス機能の空き時間情報が正しいサブスクリプション レベルに依存しています。(参照[情報の保護のライセンス](https://support.office.com/en-us/article/Plan-for-Office-365-security-and-information-protection-capabilities-3d4ac4a1-3920-4ff9-918f-011f3ce60408)の詳細については)。

チーム web クライアント、デスクトップ クライアントおよびモバイル アプリへのアクセスを対象になるすべてのサポートされているサブスクリプション プランします。

チームは、スタンドアロン サービスとしてできません。

<a name="teams-license"></a>チームのライセンス
-------------

既定では、チーム ライセンスは対象の Office 365 サブスクリプションを持つすべてのユーザーに対して有効にします。

![Microsoft チームが表示されている、Office 365 管理センターで、[ライセンス] セクションで、設定のスクリーン ショット。](media/Understand_Office_365_Licensing__for_Microsoft_Teams_image2.png)


チームでは、組織内で全体のライセンスの種類のオンとオフを切り替えることができ、ゲスト ユーザーを除くすべてのライセンスの種類の既定でオンにします。**Office 365 管理センターで、チームのスイッチを使用して、ライセンスの種類の一部のみのチームにすることはできません**。一部の組織のチームを有効にし、無効に他のユーザー (たとえば、チームのユーザーのあるパイロット環境を計画している) 場合、チーム ライセンス スイッチのすべてのユーザーを有効にする場合は、これを無効に個別のユーザー向けです。

![ユーザー/ライセンスの種類では、Office 365 管理センターで [ライセンス] セクションの Microsoft チームが表示されているチームのスクリーン ショット。](media/Understand_Office_365_Licensing__for_Microsoft_Teams_image3.png)


**ヒント:**  有効にして、その他の作業負荷と同じように、PowerShell 経由での作業負荷のライセンスが行われるように、チームを無効にします。サービス プラン名は、Microsoft チーム TEAMS1 です。(参照[サービスを Office 365 PowerShell へのアクセスを無効にする](https://technet.microsoft.com/en-us/library/dn771769.aspx)詳細については)。

**サンプル:**以下は、方法は無効にする Microsoft チームのすべてのユーザー ライセンスを特定の種類のクイック サンプルだけです。まず、個別に有効にするパイロットのためのアクセス権を持つユーザーの必要があります。

*表示するには、組織内である場合、サブスクリプションのタイプは、次のコマンドを使用します。*

      Get-MsolAccountSku

*組織名を含む、計画と計画 (ContosoSchool:ENTERPRISEPACK_STUDENT) などの学校用の名前を入力して、[次のコマンドを実行します。*

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
*すべてのユーザーの名前付き、プランのアクティブなライセンスと Microsoft チームを無効にするには、次のコマンドを実行します。*

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
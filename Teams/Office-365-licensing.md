---
title: "Microsoft Teams 用の Office 365 ライセンス | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "さまざまな Office 365 ライセンスについて、どのライセンスで Microsoft Teams のユーザーが有効になるかについて、およびライセンスを有効にしたり無効にしたりする方法について説明します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 9853bab16fead0ed4da766a6d9d59f2f93b34191
ms.sourcegitcommit: e8b96ddf6a6eaea4598b116f1e33c71911b337bb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/08/2017
---
<a name="office-365-licensing-for-microsoft-teams"></a>Microsoft Teams 用の Office 365 ライセンス
========================================

Teams のユーザーを有効にする Office 365 サブスクリプションを次に示します。

|Small Business プラン  |Enterprise プラン  |Education プラン  |
|---------|---------|---------|
|Office 365 Business Essentials     |Office 365 Enterprise E1         |Office 365 Education         |
|Office 365 Business Premium     |Office 365 Enterprise E3         |Office 365 Education Plus         |
|     |Office 365 Enterprise E4 (廃止)         |Office 365 Education E3 (廃止)         |
|     |Office 365 Enterprise E5         |Office 365 Education E5   
      |Office 365 Enterprise F1 |  |

> [!NOTE]
> Teams は非営利団体でも利用できます。 政府機関のライセンスは現時点ではサポートされていませんが、将来的にサポートするための調査が実施されています。
        


Teams の**重要な**機能に関しては、Office 365 サブスクリプションのタイプ間で違いはありません。コンプライアンス機能の利用可否は適切なサブスクリプション レベルに依存します。 (詳しくは、「[情報保護ライセンス](https://support.office.com/en-us/article/Plan-for-Office-365-security-and-information-protection-capabilities-3d4ac4a1-3920-4ff9-918f-011f3ce60408)」をご覧ください。)

サポートされているすべてのサブスクリプション プランは、Teams の Web クライアント、デスクトップ クライアント、モバイル アプリにアクセスする資格を持ちます。

Teams はスタンドアロンのサービスとして利用できません。

<a name="teams-license"></a>Teams のライセンス
-------------

既定では、Teams ライセンスは、資格のある Office 365 サブスクリプションを持つすべてのユーザーで有効になります。

![Microsoft Teams が有効になっていることを示す Office 365 管理センターのライセンス セクションの設定を示すスクリーンショット。](media/Understand_Office_365_Licensing__for_Microsoft_Teams_image2.png)


Teams は組織内での全体ライセンスの種類について、オンまたはオフにすることができます。また、ゲスト ユーザーを除くすべての種類のライセンスについて、既定でオンになります。 **Office 365 管理センターの Teams スイッチを使用することにより、一部の種類のライセンスについて Teams をオンにすることはできません。** 組織の一部に対して Teams をオンにして、それ以外についてはオフにしようとする場合 (たとえば一部の選ばれたユーザーのみでの Teams のパイロットを計画している場合など) は、Teams のライセンスのスイッチを全員に対してオンにしてから、個別のユーザーに対してオフにします。

![Microsoft Teams が有効であることを示している、Office 365 管理センターのライセンス セクションの Teams ユーザー/ライセンスの種類の設定を示すスクリーンショット。](media/Understand_Office_365_Licensing__for_Microsoft_Teams_image3.png)


**ヒント:**   PowerShell からワークロード ライセンスとして Teams を有効または無効にすることは、別のワークロードとして実行されます。 Microsoft Teams ではサービス プランの名前は TEAMS1 になります。 (詳細については、「[Office 365 PowerShell を使用してサービスへのアクセスを無効にする](https://technet.microsoft.com/en-us/library/dn771769.aspx)」をご覧ください。)

**例:** 特定のライセンスの種類でのユーザー全員の Microsoft Teams を無効にする方法について以下に簡単な例を示します。 まずこの方法を行い、次にパイロットで使用する目的でアクセスが必要なユーザーに対して個別に有効にする必要があります。

*組織内で利用可能なサブスクリプションの種類を表示するには、次のコマンドを使用します。*

      Get-MsolAccountSku

*組織名と自分の学校で使用するプランを含むプランの名前を記入します (例: ContosoSchool:ENTERPRISEPACK_STUDENT)。次に、次のコマンドを実行します。*

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
*名前を付けたプランのアクティブなライセンスがあるすべてのユーザーに対して Microsoft Teams を無効にするには、次のコマンドを実行します。*

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
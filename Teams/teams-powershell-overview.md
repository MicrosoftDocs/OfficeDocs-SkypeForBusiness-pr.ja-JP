---
title: Teams での PowerShell の概要
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/06/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: PowerShell コマンドレットの構造など、Microsoft Teams を管理するための PowerShell コントロールの使用方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c74f27af718b10aa033c51d4b42d1a3d15bcbc1b
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "44690953"
---
# <a name="teams-powershell-overview"></a>Teams での PowerShell の概要

Microsoft Teams には、IT 管理者が Microsoft Teams 管理センター、PowerShell コントロール、Graph Api を介して製品を管理するための豊富なツール セットが用意されています。 このガイドでは、IT 管理者が使用できるよう PowerShell コマンドレットを構成する方法について説明し、追加のドキュメントへのリンクを提供します。 Teams 管理者ロールが異なる場合は、異なるコマンドレットにアクセスできます。 詳細については、「[Microsoft Teams 管理者ロールを使用して Teams を管理する](using-admin-roles.md)」を参照してください。

## <a name="which-modules-do-you-need-to-use"></a>使用する必要があるモジュール

Teams を管理するための PowerShell コントロールは、次の 2 つの異なる PowerShell モジュールにあります。 
- [Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams/): Teams PowerShell モジュールには、チームの作成と管理に必要なすべてのコマンドレットが含まれています。  
- [Skype for Business PowerShell モジュール](https://www.microsoft.com/download/details.aspx?id=39366): Skype for Business PowerShell モジュールには、ポリシー、構成、その他の Teams のツールを管理するコマンドレットが含まれています。 

PowerShell コントロールのリファレンス ドキュメントには、調査中のコマンドレットが含まれるモジュールが表示されます (最終的には、2 つのモジュールが結合されます)。

## <a name="what-can-each-admin-role-do"></a>管理者の役割がそれぞれできること

「[Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md)」を読み、別の管理者ロールが使用できる PowerShell コマンドレットを把握します。

## <a name="creating-and-managing-teams-via-powershell"></a>PowerShell によるチームの作成と管理

チームを作成し管理するためのコマンドレットは、[Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams/)にあります。 

Teams は Microsoft 365 グループによってサポートされているため、チームを作成するときにグループを作成します。 コア チームとその設定を操作するためのコマンドレット (``new-team``、``get-team``、``set-team``)、チームのユーザーを管理するためのコマンドレット (``add-teamuser``、``remove-teamuser``)、およびチームのチャネルを管理するためのコマンドレット (``new-teamchannel``、``remove-teamchannel``) のセットが用意されています。 これらのコマンドレットはすべてエンド ユーザーとして実行できますが、自分が所有している、またはメンバーであるチームのみが機能します。 グローバル管理者または Teams サービス管理者であれば、組織内のすべてのチームに実行できます。

> Microsoft Teams PowerShell モジュールのコマンドレットで使用されている **GroupId** は、Exchange PowerShell モジュールで ``Get-UnifiedGroup`` により返された **Identity** プロパティと同じです。

### <a name="differences-between-preview-and-generally-available-microsoft-teams-powershell-module"></a>プレビュー版と一般公開版の Microsoft Teams PowerShell モジュールの違い

通常使用可能なバージョンの PowerShell モジュールがリリースされたときに、次の表に示すように、ベータ版モジュールのみにいくつかのコマンドレットが残りました。

| コマンドレット | プレビュー版で使用可能 | 1.0 で使用可能 |
|------- | -------------------- | ------------------------------ |
| Add-TeamUser | はい | はい |
| Connect-MicrosoftTeams | はい | はい |
| Disconnect-MicrosoftTeams | はい | はい |
| Get-Team | はい | はい |
| Get-TeamChannel | はい | はい |
| Get-TeamFunSettings | 1.0 以前のリリースのみ | いいえ |
| Get-TeamGuestSettings | 1.0 以前のリリースのみ | いいえ |
| Get-TeamHelp | はい | はい |
| Get-TeamMemberSettings | 1.0 以前のリリースのみ | いいえ |
| Get-TeamMessagingSettings | 1.0 以前のリリースのみ | いいえ |
| Get-TeamUser | はい | はい |
| New-Team | はい | はい |
| New-TeamChannel | はい | はい |
| Remove-Team | はい | はい |
| Remove-TeamChannel | はい | はい |
| Remove-TeamUser | はい | はい |
| Set-Team | はい | はい |
| Set-TeamChannel | はい | はい |
| Set-TeamFunSettings | 1.0 以前のリリースのみ | いいえ |
| Set-TeamGuestSettings | 1.0 以前のリリースのみ | いいえ |
| Set-TeamMemberSettings | 1.0 以前のリリースのみ | いいえ |
| Set-TeamMessagingSettings | 1.0 以前のリリースのみ | いいえ |
| Set-TeamPicture | はい | いいえ、計画済み |


## <a name="managing-policies-via-powershell"></a>PowerShell によるポリシーの管理

[Skype for Business コマンドレット モジュール](https://www.microsoft.com/download/details.aspx?id=39366)のコマンドレットを使用して、個々のユーザーのポリシーを管理します。

> [!NOTE]
> Skype for Business Online に接続すると、PowerShell セッションでコマンドレットを使用できるようになります。 詳細については、「 [Microsoft 365 または Office 365 PowerShell を使用して Skype For Business Online を管理](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)する」を参照してください。 

ポリシーは、個々のユーザーに細かく適用できる設定のまとまりです。 各ポリシーの種類にはポリシーそのものの作成、表示、削除、更新を行い、これらのポリシーをユーザーに割り当てるための独自のコマンドレットのセットがあります。 一般的な構成は次のとおりです。

- コマンドの取得 (例 ``Get-CsTeamsMeetingPolicy`` ): 組織内で割り当てることができるポリシードキュメントを返します。これは、使用するために Microsoft によって作成されたポリシーと、作成したカスタムポリシーの両方を返します。
   > 組織で作成したカスタムポリシーのみを検索する場合は、を使用でき ``-Filter "tag:*"`` ます。

- NEW コマンド (例: ``New-CsTeamsMeetingPolicy``): 組織の新しいポリシーを作成し、組織内のユーザーに割り当てられるようになります。 すべてのポリシーがカスタム ポリシーの作成をサポートするわけではありません。 多くの場合、組織で使用するポリシーに、サポート対象の設定の組み合わせがあることを確認するためです。

- SET コマンド (例: ``Set-CsTeamsMeetingPolicy``): 特定のポリシーに特定の値を設定できます。 ポリシーによっては、set コマンドが使用できない、またはポリシーでカスタマイズできないパラメーターが含まれるものがあります。 各 PowerShell の説明では、カスタマイズできないパラメーターが呼び出されます。 
   > カスタム ポリシーが割り当てられていない組織内のユーザーに既定で割り当てられるポリシーを編集するには、``Set-Cs<PolicyName> -Identity Global`` を実行します。

- REMOVE コマンド (例: ``Remove-CsTeamsMeetingPolicy``): このコマンドレットを使用して、テナントに作成されたカスタム ポリシーを削除できます。 組織内の少なくとも 1 人のユーザーに割り当てられているカスタム ポリシーを削除した場合、そのユーザーはグローバル ポリシーに戻ります。
   > 組織内のグローバルポリシーを実際に削除することはできませんが、組織内のグローバルポリシーを Microsoft が提供する既定の設定にリセットする場合は、実行でき ``Remove-Cs<PolicyName> -Identity Global`` ます。

- GRANT コマンド (例: ``Grant-CsTeamsMeetingPolicy``): 特定のユーザーにポリシーを割り当てることができます。
   > カスタム ポリシーの割り当てを削除し、組織の既定のポリシーにユーザーを戻すには、``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` を実行します。

> [!TIP]
> すべてのポリシーでカスタムポリシーを作成することはできません。一部のポリシーには、カスタマイズできない設定があります (そのため、設定を表示することはできますが、and でカスタム値を設定することはできません ``set-`` ``new-`` )。 顧客がパラメーターを使用できない場合は、特定のコマンドレットのドキュメントが呼び出されます。

共通パラメーター:

- **Identity**: ``Get-``、``Set-``、``New-``、``Remove-`` の場合、**Identity** パラメーターは常に特定のポリシー インスタンスを参照します。 ``Grant`` の場合、**Identity** パラメーターは、ポリシーが適用されている特定のユーザー オブジェクトを参照します。

<!--more info here?-->

## <a name="managing-configurations-via-powershell"></a>PowerShell による構成の管理

構成管理用のコマンドレットは、[Skype for Business コマンドレット モジュール](https://www.microsoft.com/download/details.aspx?id=39366)内にあります。

構成は、ユーザー レベルで指定できないサービスで維持されている設定のバケットです。 設定は常に組織全体に適用されます。 グローバル構成は、組織で唯一の有効な構成です。 各構成の種類には、次の 2 つの主なコマンドレットが用意されています。

- ``Get-Cs<ConfigurationName>`` (例: ``Get-CsTeamsClientConfiguration``): 

- SET コマンド (例:``Set-CsTeamsClientConfiguration`` ): その種類の構成でプロパティを設定します。 変更するパラメーターを指定します。
   > 変更している構成は、**Id グローバル**を指定するか、または実行 ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` して、次の2つの方法のいずれかで参照できます。

## <a name="other-powershell-tools"></a>その他の PowerShell ツール

各ポリシーの設定の詳細な説明を含む、Microsoft Teams と Skype for Business を管理するためのすべての PowerShell コントロールの使用方法に関する詳細な手順については、「[Microsoft Teams コマンドレット リファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps)」と、「[Skype for Business コマンドレット リファレンス](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)」を参照してください。

## <a name="learn-more"></a>詳細情報

- [Microsoft Teams コマンドレット リファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps)
- [Skype for Business コマンドレット リファレンス](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
- [Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md)

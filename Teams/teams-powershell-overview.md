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
description: Microsoft Teams を管理するための PowerShell コントロールの使用方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: a83e8114020ef400ba983f483727436bbd383736
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570126"
---
# <a name="teams-powershell-overview"></a>Teams での PowerShell の概要

Microsoft Teams には、IT 管理者が Microsoft Teams 管理センター、PowerShell コントロール、Graph Api を通じて製品を管理するための豊富なツールセットが用意されています。 このガイドでは、IT 管理者が使用する PowerShell コマンドレットの構造について説明し、さらに多くのドキュメントへのポインターを提供します。 チームの管理者の役割によって、異なるコマンドレットにアクセスできることに注意してください。 詳細については、「 [Microsoft teams の管理者ロールを使用してチームを管理する](using-admin-roles.md)」を参照してください。

## <a name="which-modules-do-you-need-to-use"></a>どのモジュールを使用する必要がありますか?

チームを管理するための PowerShell コントロールは、次の2つの異なる PowerShell モジュールに含まれています。 
- [Microsoft Teams powershell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams/): teams powershell モジュールには、teams の作成と管理に必要なすべてのコマンドレットが含まれています。  
- [Skype For Business powershell モジュール](https://www.microsoft.com/en-us/download/details.aspx?id=39366): Skype For business powershell モジュールには、ポリシー、構成、その他のチームツールを管理するためのコマンドレットが含まれています。 

PowerShell コントロールのリファレンスドキュメントでは、調査中のコマンドレットが含まれているモジュールを確認できます。 (最終的に、2つのモジュールが結合されます)。

## <a name="what-can-each-admin-role-do"></a>各管理者ロールでできること

「 [Microsoft Teams の管理者ロールを使用](using-admin-roles.md)してチームを管理する」を参照し、管理者ロールによって利用できる PowerShell コマンドレットについて理解してください。

## <a name="creating-and-managing-teams-via-powershell"></a>PowerShell を使用した teams の作成と管理

チームを作成して管理するためのコマンドレットは、 [Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams/)に含まれています。 

Teams は O365 グループによってサポートされているため、チームを作成するときにグループを作成します。 コアチームとその設定``new-team``(、 ``get-team`` ``set-team``)、チームユーザー``add-teamuser``の管理 (、 ``remove-teamuser``)、およびチーム``new-teamchannel`` ``remove-teamchannel``のチャネルを管理するコマンドレットを操作するための一連のコマンドレットが用意されています。 これらのコマンドレットはすべてエンドユーザーとして実行できますが、自分が所有している、またはメンバーであるチームでのみ機能します。 グローバル管理者または Teams のサービス管理者である場合は、組織内のすべてのチームに対して行動することができます。

> Microsoft Teams PowerShell モジュールのコマンドレットで使用される**GroupId**は、Exchange **** PowerShell モジュール``Get-UnifiedGroup``で返される Identity プロパティと同じです。

### <a name="differences-between-preview-and-generally-available-microsoft-teams-powershell-module"></a>プレビューと通常利用可能な Microsoft Teams PowerShell モジュールの違い

PowerShell モジュールの一般的なバージョンをリリースすると、次の表で説明するように、ベータ版のモジュールにいくつかのコマンドレットが残されました。

| コマンドレット | プレビューで利用可能 | 1.0 で利用可能 |
|------- | -------------------- | ------------------------------ |
| チームの追加ユーザー | はい | はい |
| Connect-Microsoft Teams | はい | はい |
| 切断-Microsoft Teams | はい | はい |
| チームの取得 | はい | はい |
| チームの取得チャネル | はい | はい |
| Get-TeamFunSettings | 1.0 より前のリリースのみ | いいえ |
| チームのゲスト設定を取得する | 1.0 より前のリリースのみ | いいえ |
| チームヘルプ | はい | はい |
| チームメンバーの設定を取得する | 1.0 より前のリリースのみ | いいえ |
| チームの Messagingsettings を取得する | 1.0 より前のリリースのみ | いいえ |
| チームのユーザーを取得する | はい | はい |
| 新規-チーム | はい | はい |
| 新しいチームチャネル | はい | はい |
| チームの削除 | はい | はい |
| チームの削除のチャネル | はい | はい |
| チームのユーザーの削除 | はい | はい |
| 設定-チーム | はい | はい |
| Set-TeamChannel | はい | はい |
| Set-TeamFunSettings | 1.0 より前のリリースのみ | いいえ |
| チームのゲスト設定を設定する | 1.0 より前のリリースのみ | いいえ |
| 設定-TeamMemberSettings | 1.0 より前のリリースのみ | いいえ |
| 設定-TeamMessagingSettings | 1.0 より前のリリースのみ | いいえ |
| 設定-TeamPicture | はい | いいえ、計画済み |


## <a name="managing-policies-via-powershell"></a>PowerShell を使用したポリシーの管理

ポリシーを管理するためのコマンドレットは、 [Skype For business コマンドレットモジュール](https://www.microsoft.com/en-us/download/details.aspx?id=39366)に含まれています。

> [!NOTE]
> Skype for Business Online に接続すると、コマンドレットは PowerShell セッションで利用可能になります。 詳細については、「 [Office 365 PowerShell を使って Skype For Business Online を管理](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)する」を参照してください。 

ポリシーとは、個々のユーザーに適用できる設定のグループです。 各ポリシーの種類には、ポリシー自体を作成、表示、削除、更新するための独自のコマンドレットのセットがあり、ユーザーにポリシーを割り当てることができます。 一般的な構造は次のとおりです。

- コマンドの取得 (例``Get-CsTeamsMeetingPolicy``): 組織内で割り当てることができるポリシードキュメントを返します。これは、使用するために Microsoft によって作成されたポリシーと、作成したカスタムポリシーの両方を返します。
   > 組織で作成したカスタムポリシーのみを検索する場合は、を使用``-Filter "tag:*"``できます。

- 新しいコマンド (など``New-CsTeamsMeetingPolicy``): 組織内のユーザーに割り当てることができる新しいポリシーを作成することができます。 すべてのポリシーでカスタムポリシーの作成がサポートされるわけではありません。 多くの場合、組織で使用しているポリシーの設定の組み合わせがサポートされていることを確認します。

- 次のコマンドを``Set-CsTeamsMeetingPolicy``設定します (例:)。指定したポリシーで特定の値を設定できます。 一部のポリシーでは、set コマンドを使用できないものや、ポリシーでカスタマイズできないパラメーターを含むものもあります。 各 PowerShell の説明では、カスタマイズできないパラメーターを呼び出します。 
   > カスタムポリシーが割り当てられていない組織内のユーザーに既定で割り当てられるポリシーを編集するには``Set-Cs<PolicyName> -Identity Global``、を実行します。

- コマンドの削除 (など``Remove-CsTeamsMeetingPolicy``): このコマンドレットを使用して、テナントで作成されたカスタムポリシーを削除できます。 組織内の1人以上のユーザーに割り当てられているカスタムポリシーを削除すると、そのユーザーはグローバルポリシーに戻ります。
   > 組織内のグローバルポリシーを実際に削除することはできませんが、組織内のグローバルポリシーを Microsoft が提供する既定の設定にリセットする場合``Remove-Cs<PolicyName> -Identity Global``は、実行できます。

- [ ``Grant-CsTeamsMeetingPolicy``GRANT] コマンド (例:): 特定のユーザーにポリシーを割り当てることができます。
   > カスタムポリシーの割り当てを削除して、ユーザーが組織の既定のポリシーに戻すようにする``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``には、を実行します。

> [!TIP]
> すべてのポリシーでカスタムポリシーを作成することはできません。一部のポリシーには、カスタマイズできない設定があります (そのため、設定``set-``を``new-``表示することはできますが、and でカスタム値を設定することはできません)。 ユーザーがパラメーターを使用できない場合は、特定のコマンドレットのドキュメントが呼び出されます。

一般的なパラメーター:

- **Identity**: For ``Get-``、 ``Set-``, ``New-``、and ``Remove-``、 **identity**パラメーターは、常に特定のポリシーインスタンスを参照します。 の``Grant``場合、 **Identity**パラメーターは、ポリシーが適用されている特定のユーザーオブジェクトを参照します。

<!--more info here?-->

## <a name="managing-configurations-via-powershell"></a>PowerShell を使用した構成の管理

構成を管理するためのコマンドレットは、 [Skype For business コマンドレットモジュール](https://www.microsoft.com/en-us/download/details.aspx?id=39366)に含まれています。

構成は、サービスに保持されている設定のバケットであり、ユーザーレベルで指定することはできません。 設定は組織全体で常に適用されます。 グローバル構成は、組織内で唯一の有効な構成です。 各構成の種類には、2つの主なコマンドレットが用意されています。

- ``Get-Cs<ConfigurationName>``(など``Get-CsTeamsClientConfiguration``): 

- コマンド (例: ``Set-CsTeamsClientConfiguration``) を設定します。その型の構成でプロパティを設定します。 変更するパラメーターを指定します。
   > 変更している構成は、**Id グローバル**を指定するか、または実行``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>``して、次の2つの方法のいずれかで参照できます。

## <a name="other-powershell-tools"></a>その他の PowerShell ツール

Microsoft [teams コマンドレットリファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps)および skype for business の各ポリシーの設定の詳細な説明など、microsoft Teams と Skype for business を管理するためのすべての PowerShell コントロールの使用方法について、詳細な手順を参照してください。 [Business コマンドレットリファレンス](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)。

## <a name="learn-more"></a>詳細情報

- [Microsoft Teams コマンドレット リファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps)
- [Skype for Business コマンドレットリファレンス](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
- [Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md)

---
title: Microsoft Teams PowerShell で Teams を管理する
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Teams PowerShell を使用して Microsoft Teams を管理する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8494f7951a051f95f9b934d04f274a020446b6cd
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2021
ms.locfileid: "51617749"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>Microsoft Teams PowerShell で Teams を管理する

この記事では、Microsoft Teams PowerShell を使用して Teams と Skype for Business を管理する方法について説明します。 

このガイダンスと Microsoft Teams コマンドレット リファレンスと [Skype](/powershell/teams/?view=teams-ps) for Business コマンドレット リファレンス [を組み合わせて使用します](/powershell/skype/intro?view=skype-ps)。

## <a name="create-and-manage-teams-using-powershell"></a>PowerShell を使用してチームを作成および管理する

チームを作成し管理するためのコマンドレットは、[Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams/)にあります。

Teams は 365 Officeに支え、チームを作成するときにグループを作成します。 コア チームとその設定を操作するためのコマンドレット (``new-team``、``get-team``、``set-team``)、チームのユーザーを管理するためのコマンドレット (``add-teamuser``、``remove-teamuser``)、およびチームのチャネルを管理するためのコマンドレット (``new-teamchannel``、``remove-teamchannel``) のセットが用意されています。 これらのコマンドレットはすべてエンド ユーザーとして実行できますが、自分が所有している、またはメンバーであるチームのみが機能します。 グローバル管理者または Teams サービス管理者であれば、組織内のすべてのチームに実行できます。

```powershell
New-Team -DisplayName "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> Microsoft Teams PowerShell モジュールのコマンドレットで使用されている **GroupId** は、Exchange PowerShell モジュールで ``Get-UnifiedGroup`` により返された **Identity** プロパティと同じです。

## <a name="manage-policies-via-powershell"></a>PowerShell でポリシーを管理する

> [!NOTE]
> - Skype for Business Online Connector は Teams PowerShell に統合されています。 現在、パブリック プレビューで利用できます。 Teams に適用される Skype for Business Online コマンドレットは、Teams PowerShell モジュールでネイティブで使用できます。 インストール手順は、Teams [PowerShell のインストールに関する記事を参照](teams-powershell-install.md) してください。
>
> - Skype for Business Online に接続すると、PowerShell セッションでコマンドレットを使用できるようになります。 詳細については、「[Office 365 PowerShell を使用して Skype for Business Online を管理する](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)」を参照してください。

Skype for Business コマンドレット モジュールでポリシーを管理するための [コマンドレットを見つける](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)。

ポリシーは、個々のユーザーに細かく適用できる設定のまとまりです。 各ポリシーの種類にはポリシーそのものの作成、表示、削除、更新を行い、これらのポリシーをユーザーに割り当てるための独自のコマンドレットのセットがあります。 一般的な構成は次のとおりです。

- **GET** コマンド (例: 組織内で割り当て可能なポリシー ドキュメント) を返します。このドキュメントには、ユーザーが使用できる Microsoft が作成したポリシーや、作成したカスタム ポリシーが含まれます。 ``Get-CsTeamsMeetingPolicy``
   - 組織で作成したカスタム ポリシーのみを検索するには、次を使用します ``-Filter "tag:*"`` 。

- **新** しいコマンド (例: 組織のユーザーに割り当てる新 ``New-CsTeamsMeetingPolicy`` しいポリシーを作成します)。 すべてのポリシーがカスタム ポリシーの作成をサポートするわけではありません。 多くの場合、組織で使用するポリシーに、サポート対象の設定の組み合わせがあることを確認するためです。

- **SET** コマンド (例: ``Set-CsTeamsMeetingPolicy`` 特定のポリシーに特定の値を設定します)。 一部のポリシーには、使用できない SET コマンドや、ポリシーでカスタマイズできないパラメーターが含まれています。 PowerShell の説明では、カスタマイズできないパラメーターが示されます。 
   - カスタム ポリシーが割り当てられていない組織内のユーザーに既定で割り当てられるポリシーを編集するには、``Set-Cs<PolicyName> -Identity Global`` を実行します。

- **REMOVE** コマンド (例: テナントで作成されたカスタム ``Remove-CsTeamsMeetingPolicy`` ポリシー) を削除します。 組織内の少なくとも 1 人のユーザーに割り当てられているカスタム ポリシーを削除した場合、そのユーザーはグローバル ポリシーに戻ります。
   - 実際には組織のグローバル ポリシーを削除できないが、組織のグローバル ポリシーを Microsoft が提供する既定の設定にリセットする場合は、実行します ``Remove-Cs<PolicyName> -Identity Global`` 。

- **GRANT** コマンド (例 ``Grant-CsTeamsMeetingPolicy`` : 特定のユーザーにポリシーを割り当てる)。
   - カスタム ポリシーの割り当てを削除し、組織の既定のポリシーにユーザーを戻すには、``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` を実行します。

> [!TIP]
> すべてのポリシーでカスタム ポリシーの作成が許可されているわけではなく、一部のポリシーにはカスタマイズできない設定が含まれています (そのため、設定は表示できますが、``set-`` と``new-`` の間にカスタム値を設定できません)。 各コマンドレットのドキュメントでは、パラメーターが顧客が使用できるかどうかが示されます。

共通パラメーター:

- **Identity**: ``Get-``、``Set-``、``New-``、``Remove-`` の場合、**Identity** パラメーターは常に特定のポリシー インスタンスを参照します。 ``Grant`` の場合、**Identity** パラメーターは、ポリシーが適用されている特定のユーザー オブジェクトを参照します。

## <a name="manage-configurations-via-powershell"></a>PowerShell で構成を管理する

Skype for Business コマンドレット モジュールで構成を管理するための [コマンドレットを見つける](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)。

構成は、サービスで維持される設定のバケットで、ユーザー レベルでは指定できない設定です。 設定は常に組織全体に適用されます。 グローバル構成は、組織で唯一の有効な構成です。 各構成の種類には、次の 2 つの主なコマンドレットが用意されています。

- ``Get-Cs<ConfigurationName>`` (例: ``Get-CsTeamsClientConfiguration``):

- SET コマンド (例:``Set-CsTeamsClientConfiguration`` ): その種類の構成でプロパティを設定します。 変更するパラメーターを指定します。
   > **Identity Global** の指定、または ``Get-Cs<ConfigurationName>`` | ``Set-Cs<ConfigurationName>`` の実行のいずれかの方法で変更を行っている構成を参照できます。

## <a name="what-can-each-admin-role-do"></a>管理者の役割がそれぞれできること

「Microsoft [Teams 管理者ロールを使用して Teams を管理](using-admin-roles.md) する」を参照して、各 PowerShell コマンドレットを実行できる管理者ロールを理解します。

## <a name="related-topics"></a>関連トピック

[Teams Powershell のインストール](teams-powershell-install.md)

[Teams PowerShell のリリース ノート](teams-powershell-release-notes.md)

[Teams コマンドレット リファレンス](/powershell/teams/?view=teams-ps)

[Skype for Business コマンドレット リファレンス](/powershell/skype/intro?view=skype-ps)

[Teams 管理者ロールを使用してTeams を管理します](using-admin-roles.md)
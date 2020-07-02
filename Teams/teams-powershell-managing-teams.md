---
title: Microsoft Teams PowerShell を使用してチームを管理する
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
ms.openlocfilehash: c217cea4a9ad800c1f31f8dcfae9c88ee281188c
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944126"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>Microsoft Teams PowerShell を使用してチームを管理する

この記事では、Microsoft Teams PowerShell を使用してチームと Skype for Business を管理する方法について説明します。 

このガイダンスは、 [Microsoft Teams コマンドレットリファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps)および[Skype for business コマンドレットリファレンス](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)と組み合わせて使用してください。

## <a name="create-and-manage-teams-using-powershell"></a>PowerShell を使用してチームを作成して管理する

チームを作成し管理するためのコマンドレットは、[Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams/)にあります。

Teams は Office 365 グループによってサポートされているので、チームを作成するときにグループを作成します。 コア チームとその設定を操作するためのコマンドレット (``new-team``、``get-team``、``set-team``)、チームのユーザーを管理するためのコマンドレット (``add-teamuser``、``remove-teamuser``)、およびチームのチャネルを管理するためのコマンドレット (``new-teamchannel``、``remove-teamchannel``) のセットが用意されています。 これらのコマンドレットはすべてエンド ユーザーとして実行できますが、自分が所有している、またはメンバーであるチームのみが機能します。 グローバル管理者または Teams サービス管理者であれば、組織内のすべてのチームに実行できます。

```powershell
New-Team -Name "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department
```

> Microsoft Teams PowerShell モジュールのコマンドレットで使用されている **GroupId** は、Exchange PowerShell モジュールで ``Get-UnifiedGroup`` により返された **Identity** プロパティと同じです。

## <a name="manage-policies-via-powershell"></a>PowerShell を使用してポリシーを管理する

> [!NOTE]
> - Skype for Business Online Connector は Teams PowerShell に統合されています。 現在、パブリックプレビューで利用できます。 現時点では、Teams に適用される Skype for Business Online のコマンドレットは、Teams PowerShell モジュールでネイティブで利用できます。 インストールの手順については、「 [Teams PowerShell のインストール](teams-powershell-install.md)」の記事を参照してください。
>
> - Skype for Business Online に接続すると、PowerShell セッションでコマンドレットを使用できるようになります。 詳細については、「[Office 365 PowerShell を使用して Skype for Business Online を管理する](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)」を参照してください。

[Skype For business コマンドレットモジュール](https://www.microsoft.com/download/details.aspx?id=39366)でポリシーを管理するためのコマンドレットを見つけます。

ポリシーは、個々のユーザーに細かく適用できる設定のまとまりです。 各ポリシーの種類にはポリシーそのものの作成、表示、削除、更新を行い、これらのポリシーをユーザーに割り当てるための独自のコマンドレットのセットがあります。 一般的な構成は次のとおりです。

- **GET**コマンド (など): Microsoft によって作成されたポリシーや、作成した ``Get-CsTeamsMeetingPolicy`` カスタムポリシーなど、組織内で割り当てることができるポリシードキュメントが返されます。
   - 組織で作成したカスタムポリシーのみを検索するには、を使用 ``-Filter "tag:*"`` します。

- **新しい**コマンド (など ``New-CsTeamsMeetingPolicy`` ): 組織のユーザーに割り当てる新しいポリシーを作成します。 すべてのポリシーがカスタム ポリシーの作成をサポートするわけではありません。 多くの場合、組織で使用するポリシーに、サポート対象の設定の組み合わせがあることを確認するためです。

- **SET**コマンド (例:) は、特定の ``Set-CsTeamsMeetingPolicy`` ポリシーの特定の値を設定します。 一部のポリシーでは、SET コマンドが利用できない場合や、ポリシーでカスタマイズできないパラメーターが含まれている場合があります。 PowerShell の説明には、カスタマイズできないパラメーターが示されます。 
   - カスタム ポリシーが割り当てられていない組織内のユーザーに既定で割り当てられるポリシーを編集するには、``Set-Cs<PolicyName> -Identity Global`` を実行します。

- コマンドの**削除**(など ``Remove-CsTeamsMeetingPolicy`` ): テナントで作成されたカスタムポリシーを削除します。 組織内の少なくとも 1 人のユーザーに割り当てられているカスタム ポリシーを削除した場合、そのユーザーはグローバル ポリシーに戻ります。
   - 組織内のグローバルポリシーを実際に削除することはできませんが、組織内のグローバルポリシーを Microsoft が提供する既定の設定にリセットする場合は、を実行 ``Remove-Cs<PolicyName> -Identity Global`` します。

- [ **GRANT** ] コマンド (例 ``Grant-CsTeamsMeetingPolicy`` :): 特定のユーザーにポリシーを割り当てます。
   - カスタム ポリシーの割り当てを削除し、組織の既定のポリシーにユーザーを戻すには、``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` を実行します。

> [!TIP]
> すべてのポリシーでカスタム ポリシーの作成が許可されているわけではなく、一部のポリシーにはカスタマイズできない設定が含まれています (そのため、設定は表示できますが、``set-`` と``new-`` の間にカスタム値を設定できません)。 各コマンドレットのドキュメントは、ユーザーが使用できるパラメーターかどうかを呼び出します。

共通パラメーター:

- **Identity**: ``Get-``、``Set-``、``New-``、``Remove-`` の場合、**Identity** パラメーターは常に特定のポリシー インスタンスを参照します。 ``Grant`` の場合、**Identity** パラメーターは、ポリシーが適用されている特定のユーザー オブジェクトを参照します。

## <a name="manage-configurations-via-powershell"></a>PowerShell を使用した構成の管理

[Skype For business コマンドレットモジュール](https://www.microsoft.com/en-us/download/details.aspx?id=39366)で構成を管理するためのコマンドレットについて説明します。

構成は、サービスに保持されている設定のバケットであり、ユーザーレベルで指定することはできません。 設定は常に組織全体に適用されます。 グローバル構成は、組織で唯一の有効な構成です。 各構成の種類には、次の 2 つの主なコマンドレットが用意されています。

- ``Get-Cs<ConfigurationName>`` (例: ``Get-CsTeamsClientConfiguration``):

- SET コマンド (例:``Set-CsTeamsClientConfiguration`` ): その種類の構成でプロパティを設定します。 変更するパラメーターを指定します。
   > **Identity Global** の指定、または ``Get-Cs<ConfigurationName>`` | ``Set-Cs<ConfigurationName>`` の実行のいずれかの方法で変更を行っている構成を参照できます。

## <a name="what-can-each-admin-role-do"></a>管理者の役割がそれぞれできること

「 [Microsoft Teams の管理者ロールを使用](using-admin-roles.md)してチームを管理し、各 PowerShell コマンドレットを実行できる管理者ロールについて理解する」を参照してください。

## <a name="related-topics"></a>関連項目

[Teams PowerShell のインストール](teams-powershell-install.md)

[Teams PowerShell リリースノート](teams-powershell-release-notes.md)

[Teams コマンドレット リファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Skype for Business コマンドレット リファレンス](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Teams 管理者ロールを使用してTeams を管理します](using-admin-roles.md)
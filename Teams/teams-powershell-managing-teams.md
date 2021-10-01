---
title: PowerShell Teamsを使用Microsoft Teams管理する
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
description: PowerShell を使用してMicrosoft Teams管理Teams説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86d5069794d160d4c4241a67f0c8d45fc9cac708
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2021
ms.locfileid: "60046023"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>PowerShell Teamsを使用Microsoft Teams管理する

この記事では、PowerShell を使用して、Microsoft Teamsを管理する方法Teams説明Skype for Business。

このガイダンスは、Microsoft Teams コマンドレット リファレンス[および](/powershell/teams/?view=teams-ps)Skype for Business[リファレンスと組み合わせて使用します](/powershell/skype/intro?view=skype-ps)。

管理センターでTeams管理Teams Azure Cloud Shell を使用Teams管理[する」を参照してください](#manage-teams-with-azure-cloud-shell)。

## <a name="create-and-manage-teams-using-powershell"></a>PowerShell を使用してチームを作成および管理する

チームを作成し管理するためのコマンドレットは、[Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams/)にあります。

TeamsグループによってOffice 365されるので、チームを作成するときにグループを作成します。 コア チームとその設定を操作するためのコマンドレット (``new-team``、``get-team``、``set-team``)、チームのユーザーを管理するためのコマンドレット (``add-teamuser``、``remove-teamuser``)、およびチームのチャネルを管理するためのコマンドレット (``new-teamchannel``、``remove-teamchannel``) のセットが用意されています。 これらのコマンドレットはすべてエンド ユーザーとして実行できますが、自分が所有している、またはメンバーであるチームのみが機能します。 グローバル管理者または管理者Teams、組織内のすべてのチームに対して行動できます。

```powershell
New-Team -DisplayName "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> [!NOTE]
> Microsoft Teams PowerShell モジュールのコマンドレットで使用されている **GroupId** は、Exchange PowerShell モジュールで ``Get-UnifiedGroup`` により返された **Identity** プロパティと同じです。

## <a name="manage-teams-with-azure-cloud-shell"></a>Azure Cloud Shell Teamsを管理する

Cloud Shell は、認証された、ブラウザーでアクセス可能な対話型シェルで、リソースを管理できます。 Cloud Shell の詳細については、Azure Cloud Shell に関 [するページを参照してください](/azure/cloud-shell/overview)。

Azure Cloud Shell にアクセスし、PowerShell を使用してTeamsを管理するには、Teamsにサインインします。

1. 右上隅にある Cloud Shell アイコンを選択します。

    ![Cloud Shell アイコンTeams付き管理センター ヘッダーのスクリーンショット。](media/cloud-shell-icon-select.png)

1. メッセージが表示されたら **、[PowerShell] を選択します**。

    ![Azure Cloud Shell プロンプトのスクリーンショット。](media/cloud-shell.png)

1. 次のコマンドを実行して、PowerShell Teams開始します。

    ```powershell
    Connect-MicrosoftTeams
    ```

これらの手順を完了すると、PowerShell コマンドをTeamsできます。

> [!IMPORTANT]
> Cs* コマンドレットを使用する場合は、まず コマンドを使用して Teamsに接続する必要 ``Connect-MicrosoftTeams -UseDeviceAuthentication`` があります。

## <a name="manage-policies-via-powershell"></a>PowerShell を使用してポリシーを管理する

> [!NOTE]
> - Skype for Businessオンライン コネクタは、PowerShell Teams統合されています。 現在、パブリック プレビューで使用できます。 その後、Skype for Businessに適用される Teams Online コマンドレットは、PowerShell モジュールでネイティブTeams使用できます。 インストール手順については[、PowerShell のインストールに関するTeams記事を参照](teams-powershell-install.md)してください。
> - Skype for Business Online に接続すると、PowerShell セッションでコマンドレットを使用できるようになります。 詳細については、「[Office 365 PowerShell を使用して Skype for Business Online を管理する](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)」を参照してください。

Skype for Business コマンドレット モジュールでポリシーを[管理するためのコマンドレットを探します](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)。

ポリシーは、個々のユーザーに細かく適用できる設定のまとまりです。 各ポリシーの種類にはポリシーそのものの作成、表示、削除、更新を行い、これらのポリシーをユーザーに割り当てるための独自のコマンドレットのセットがあります。 一般的な構成は次のとおりです。

- **GET** コマンド (例: ): 使用する Microsoft によって作成されたポリシーや、作成したカスタム ポリシーなど、組織内で割り当て可能なポリシー ドキュメントを返します。 ``Get-CsTeamsMeetingPolicy``
  - 組織で作成したカスタム ポリシーのみを検索するには、 を使用します ``-Filter "tag:*"`` 。

- **新** しいコマンド (例: ): 組織内のユーザーに割り当てる組織の新しいポリシー ``New-CsTeamsMeetingPolicy`` を作成します。 すべてのポリシーがカスタム ポリシーの作成をサポートするわけではありません。 多くの場合、組織で使用するポリシーに、サポート対象の設定の組み合わせがあることを確認するためです。

- **SET** コマンド (例: ``Set-CsTeamsMeetingPolicy`` ): 特定のポリシーの特定の値を設定します。 一部のポリシーには SET コマンドが使用できないか、ポリシーでカスタマイズできないパラメーターが含まれています。 PowerShell の説明では、カスタマイズできないパラメーターが示されます。
  - カスタム ポリシーが割り当てられていない組織内のユーザーに既定で割り当てられるポリシーを編集するには、``Set-Cs<PolicyName> -Identity Global`` を実行します。

- **REMOVE** コマンド (例: ): テナントに作成されたカスタム ``Remove-CsTeamsMeetingPolicy`` ポリシーを削除します。 組織内の少なくとも 1 人のユーザーに割り当てられているカスタム ポリシーを削除した場合、そのユーザーはグローバル ポリシーに戻ります。
  - 組織のグローバル ポリシーを実際に削除する必要がありますが、組織のグローバル ポリシーを Microsoft が提供する既定の設定にリセットする場合は、 を実行します ``Remove-Cs<PolicyName> -Identity Global`` 。

- **GRANT** コマンド (例 ``Grant-CsTeamsMeetingPolicy`` : ): 特定のユーザーにポリシーを割り当てる。
  - カスタム ポリシーの割り当てを削除し、組織の既定のポリシーにユーザーを戻すには、``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` を実行します。

> [!TIP]
> すべてのポリシーでカスタム ポリシーの作成が許可されているわけではなく、一部のポリシーにはカスタマイズできない設定が含まれています (そのため、設定は表示できますが、``set-`` と``new-`` の間にカスタム値を設定できません)。 各コマンドレットのドキュメントでは、顧客がパラメーターを使用できるかどうかが示されています。

共通パラメーター:

- **Identity**: ``Get-``、``Set-``、``New-``、``Remove-`` の場合、**Identity** パラメーターは常に特定のポリシー インスタンスを参照します。 ``Grant`` の場合、**Identity** パラメーターは、ポリシーが適用されている特定のユーザー オブジェクトを参照します。

## <a name="manage-configurations-via-powershell"></a>PowerShell を使用して構成を管理する

構成を管理するためのコマンドレットは、Skype for Business[モジュールで確認してください](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)。

構成は、ユーザー レベルで指定できない、サービスで保持される設定のバケットです。 設定は常に組織全体に適用されます。 グローバル構成は、組織で唯一の有効な構成です。 各構成の種類には、次の 2 つの主なコマンドレットが用意されています。

- ``Get-Cs<ConfigurationName>`` (例: ``Get-CsTeamsClientConfiguration``):

- SET コマンド (例:``Set-CsTeamsClientConfiguration`` ): その種類の構成でプロパティを設定します。 変更するパラメーターを指定します。
    > [!NOTE]
    > **Identity Global** の指定、または ``Get-Cs<ConfigurationName>`` | ``Set-Cs<ConfigurationName>`` の実行のいずれかの方法で変更を行っている構成を参照できます。

## <a name="what-can-each-admin-role-do"></a>管理者の役割がそれぞれできること

各 PowerShell[コマンドレットMicrosoft Teams実行できる](using-admin-roles.md)管理者ロールをTeams管理者ロールを使用して管理する方法に関するページを参照してください。

## <a name="related-topics"></a>関連トピック

[Teams Powershell のインストール](teams-powershell-install.md)

[Teams PowerShell のリリース ノート](teams-powershell-release-notes.md)

[Teams コマンドレット リファレンス](/powershell/teams/?view=teams-ps)

[Skype for Business コマンドレット リファレンス](/powershell/skype/intro?view=skype-ps)

[Teams 管理者ロールを使用してTeams を管理します](using-admin-roles.md)

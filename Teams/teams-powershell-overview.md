---
title: チーム PowerShell の概要
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/06/2018
ms.topic: article
ms.service: msteams
description: PowerShell のコントロールを使用して、マイクロソフトのチームを管理するために説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 181655609fd031da177a21e10684186ca5c52066
ms.sourcegitcommit: ab4476127222d9f0aa9ee503132ff9bdabcaf9bc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "24025278"
---
# <a name="teams-powershell-overview"></a>チーム PowerShell の概要

マイクロソフトのチームでは、マイクロソフトのチームとビジネス管理センター、PowerShell コントロール、およびグラフの Api の Skype を通じて製品を管理する IT 管理者のためのツールの豊富なセットがあります。 このガイドでは、当社の PowerShell コマンドレットを使用して、IT 管理者を構成する方法について説明し、さらにドキュメントへのポインターを提供します。 さまざまなチームの管理者のロールに別のコマンドレットへのアクセスがあることに注意してください。 詳細については、[チームを管理する管理者の役割を使用してマイクロソフトのチーム](using-admin-roles.md)を参照してください。

## <a name="which-modules-do-you-need-to-use"></a>モジュールを使用するのには必要ですか。

PowerShell の 2 つの異なるモジュールでは、マイクロソフトのチームを管理するための PowerShell コントロール:[マイクロソフト チームの PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3)(パブリック プレビュー) と[ビジネスの PowerShell モジュールの Skype](https://www.microsoft.com/en-us/download/details.aspx?id=39366)です。 チームの PowerShell モジュールには、すべてのコマンドレットを作成し、ビジネスの PowerShell モジュールの Skype には、ポリシー、構成、およびその他のチームのツールを管理するためのコントロールが含まれていますが、チームを管理する必要がありますが含まれています。 PowerShell のコントロールの参照ドキュメントが送信されます、調査しているコマンドレットがどのモジュールに含まれています。 (最終的には、2 つのモジュール結合されます。)

## <a name="what-can-each-admin-role-do"></a>できます各管理者の役割は何ですか。

PowerShell コマンドレットの別の管理者の役割が利用できるようになりますを理解する[チームを管理する管理者の役割を使用してマイクロソフトのチーム](using-admin-roles.md)を参照してください。

## <a name="creating-and-managing-teams-via-powershell"></a>作成して、PowerShell を使用してチームを管理します。

[マイクロソフト チームの PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3)では、コマンドレットを作成して、チームを管理するのです。 

チームによって支えられて O365 グループでは、これとチームを作成する、グループを作成します。 コア ・ チームとその設定を操作するために用意されているコマンドレットのセットがある (``new-team``、 ``get-team``、 ``set-teamfunsettings``)、およびチームのチャネルを管理するためのコマンドレット (``new-teamchannel``、 ``remove-teamchannel``)。 エンド ・ ユーザーとして実行できるすべてのこれらのコマンドレットが所有する、またはのメンバーをチームにのみ動作します。 場合は、グローバル管理者またはチームのサービス管理者は、組織内のすべてのチームを操作することができます。

> マイクロソフト チームの PowerShell モジュールのコマンドレットで使用されている**グループ Id**は、 **Identity**プロパティによって返される``Get-UnifiedGroup``Exchange PowerShell モジュールにします。

## <a name="managing-policies-via-powershell"></a>PowerShell を使用してポリシーの管理

ポリシーを管理するためのコマンドレットは、[コマンドレットのビジネス モジュールの Skype](https://www.microsoft.com/en-us/download/details.aspx?id=39366)では。

ポリシーは、個々 のユーザーに細かく適用できる設定のグループです。 各ポリシーの種類には、コマンドレットを作成、表示、削除、および自体には、ポリシーの更新およびユーザーにこれらのポリシーを割り当てるのための独自のセットがあります。 一般的な構造は次のとおりです。

- GET コマンド (たとえば、 ``Get-CsTeamsMeetingPolicy``): 組織のポリシーを使用する Microsoft によって作成されると作成したカスタム ポリシーの両方を割り当てることで利用可能なポリシーのドキュメントを返します。
   > 使用することができます、組織で作成したカスタム ポリシーのみを検索する場合は、 ``-Filter "tag:*"``。

- 新しいコマンド (たとえば、 ``New-CsTeamsMeetingPolicy``): を使用して見ることが、組織内のユーザーに割り当てられる利用可能な組織の新しいポリシーを作成します。 一部のポリシーは、カスタム ポリシーの作成をサポートします。 多くの場合これは、組織内で使用するポリシーは、サポートされている設定の組み合わせであることを確認すること。

- 一連のコマンド (たとえば、 ``Set-CsTeamsMeetingPolicy``): 指定されたポリシーの特定の値を設定することができます。 いくつかのポリシー設定のコマンドが使用可能なしたりしないでポリシーの設定を変更できないパラメーターが含まれています。 PowerShell のそれぞれの説明は、どのパラメーターをカスタマイズすることはできませんを呼び出します。 
   > 既定で割り当てられる割り当てられているカスタム ポリシーがない、組織内のユーザーにポリシーを編集するのには次のように実行します。 ``Set-Cs<PolicyName> -Identity Global``。

- 削除] コマンド (たとえば、 ``Remove-CsTeamsMeetingPolicy``): テナントで作成されたカスタム ポリシーを削除するのには、このコマンドレットを使用することができます。 場合は、組織内の少なくとも 1 つのユーザーに割り当てられているカスタム ポリシーを削除すると、そのユーザーはグローバル ポリシーをクリアテキストです。
   > 実際には、組織のグローバル ポリシーを削除できませんが、実行することがマイクロソフトから提供された既定の設定を組織内のグローバル ポリシーをリセットする場合は、 ``Remove-Cs<PolicyName> -Identity Global``。

- GRANT コマンド (たとえば、 ``Grant-CsTeamsMeetingPolicy``): 特定のユーザーにポリシーを割り当てることができます。
   > 実行するカスタム ポリシーの割り当てを削除して、組織内の既定のポリシーにユーザーを``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``。

> [!TIP]
> すべてのポリシーを作成するには、カスタム ポリシーを許可する、およびいくつかのポリシー設定でカスタマイズすることはできません (設定を表示することができますが、中にカスタム値を設定することはできませんので``set-``と``new-``)。 パラメーターが顧客によって使用可能な場合は、特定のコマンドレットのドキュメント呼び出します。

共通のパラメーター:

- **Id**: の``Get-``、 ``Set-``、 ``New-``、および``Remove-``、 **Id**パラメーターは常に特定のポリシーのインスタンスを参照してください。 ``Grant``、 **Id**パラメーターは、ポリシーの適用先の特定のユーザー オブジェクトを参照します。

<!--more info here?-->

## <a name="managing-configurations-via-powershell"></a>PowerShell を使用して構成を管理します。

構成を管理するためのコマンドレットは、[コマンドレットのビジネス モジュールの Skype](https://www.microsoft.com/en-us/download/details.aspx?id=39366)では。

構成は、ユーザー レベルで指定することはできませんが、サービスで保持されている設定のバケットです。 設定は、組織全体で常に適用されます。 グローバル設定は、組織内で唯一の効果的な構成です。 構成タイプごとに主な 2 つのコマンドレットではあります。

- ``Get-Cs<ConfigurationName>``(たとえば、 ``Get-CsTeamsClientConfiguration``)。 

- 一連のコマンド (たとえば、 ``Set-CsTeamsClientConfiguration``): その種類の構成のプロパティを設定します。 変更するパラメーターを指定します。
   > 2 つの方法のいずれかに変更する構成を参照することができます: を指定する -**ユーザーのグローバル**、または実行によって``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>``。

## <a name="other-powershell-tools"></a>他の PowerShell ツール

マイクロソフトのチームとの[マイクロソフトのチームのコマンドレットのリファレンス](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps)と Skype の[で、各ポリシーの設定の詳細な説明を含む、ビジネス用の Skype を管理するための PowerShell のすべてのコントロールを使用する方法の詳細な手順を表示します。ビジネス コマンドレット参照](https://docs.microsoft.com/en-us/powershell/skype/intro?view=skype-ps)。

## <a name="learn-more"></a>詳細情報

- [マイクロソフト チーム コマンドレットのリファレンス](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps)
- [Skype ビジネス コマンドレット参照](https://docs.microsoft.com/en-us/powershell/skype/intro?view=skype-ps)
- [マイクロソフト チームの管理者の役割を使用して、チームを管理するには](using-admin-roles.md)

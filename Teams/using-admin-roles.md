---
title: Microsoft Teams の管理者ロールを使用して Teams を管理する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/19/2018
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
ms.reviewer: islubin
description: 異なる管理者ロールを使用して Teams を管理する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 677249ba27c79352207a4fffa65480a0a7d484cd
ms.sourcegitcommit: 188c57e6b6c707edb694bb922556dea1c4724846
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "30955015"
---
# <a name="use-microsoft-teams-admin-roles-to-manage-teams"></a>Microsoft Teams の管理者ロールを使用して Teams を管理する

Azure Active Directory (Azure AD) を使用して、Microsoft Teams を管理するために必要な、異なるレベルのアクセス権限を持つ管理者を指定することができます。 管理者は Teams 全体のワークロードを管理できる場合もあれば、通話品質の問題のトラブルシューティングや組織のテレフォニーのニーズを管理するために委任されたアクセス許可を持つ場合もあります。 

## <a name="teams-roles-and-capabilities"></a>Teams でのロールと能力

利用できる Teams の管理者ロールには 4 種類あり、Teams サービス管理者、Teams 通信管理者、Teams 通信サポート スペシャリスト、および Teams 通信サポート エンジニアが含まれます。 次の表を確認し、それぞれのロールに許可されている操作および、管理者が Microsoft Teams 管理センターや PowerShell で使用できるツールについて理解してください。

<!-- add Global admin role? -->

| ロール | 実行可能なタスク | アクセス可能なツール |
|----- | ------------------ | ------------------------------ |
| Teams サービス管理者 | Teams サービスの管理、および Office 365 グループの管理と作成 | 次の機能を含む、Microsoft Teams 管理センターのすべての機能および関連する PowerShell コントロール:<br><br> 会議ポリシー、構成、会議ブリッジ<sup>1、3</sup> などを含む、会議の管理<br><br> 通話ポリシーや電話番号の在庫管理と割り当て<sup>1</sup> などを含む、音声通話の管理<br><br> メッセージング ポリシー<sup>1、3</sup> を含む、メッセージングの管理<br><br> フェデレーション、Teams のアップグレード、Teams クライアントの設定<sup>1、3</sup> などを含む、組織全体にわたる設定の管理<br><br> メンバーシップ (PowerShell 経由でサポートされるグループ管理や Teams 管理センターでのチーム管理)<sup>2、3</sup> を含む、組織でのチームの管理および関連する設定の管理　<br><br> ユーザー プロファイル ページの確認および高度なトラブルシューティング ツールセット<sup>3</sup> を使用したユーザーの通話品質の問題のトラブルシューティング <br><br> 通話品質の低下による影響を受けたユーザーに対する、通話品質ダッシュボード (CQD) に表示されるデータを使用した、テナントの通話品質および信頼性の確認、監視、およびトラブルシューティング。 新しいレポートの作成および必要に応じたレポートの更新および削除。 CQD 構築データのアップロードおよび更新 |
| Teams 通信管理者 | Teams サービス内の通話機能および会議機能の管理 | 会議ポリシー、構成、会議ブリッジ<sup>1、3</sup> などを含む、会議の管理<br><br> 通話ポリシーや電話番号の在庫管理と割り当て<sup>1</sup> などを含む、音声通話の管理<br><br> ユーザー プロファイル ページの確認および高度なトラブルシューティング ツールセット<sup>3</sup> を使用したユーザーの通話品質の問題のトラブルシューティング <br><br> 通話品質の低下による影響を受けたユーザーに対する、通話品質ダッシュボード (CQD) に表示されるデータを使用した、テナントの通話品質および信頼性の確認、監視、およびトラブルシューティング。 新しいレポートの作成および必要に応じたレポートの更新および削除。 CQD 構築データのアップロードおよび更新 |
| Teams 通信サポート エンジニア | **高度な**ツールを使用した、Teams 内での通信に関する問題のトラブルシューティング。 | ユーザー プロファイル ページの確認および高度なトラブルシューティング ツールセット<sup>3</sup> を使用したユーザーの通話品質の問題のトラブルシューティング <br><br> 通話品質の低下による影響を受けたユーザーに対する、通話品質ダッシュボード (CQD) に表示されるデータを使用した、テナントの通話品質および信頼性の確認、監視、およびトラブルシューティング |
| Teams 通信サポート スペシャリスト | **基本的な**ツールを使用した、Teams 内での通信に関する問題のトラブルシューティング。| 通話分析で通話をトラブルシューティングするための、ユーザー プロファイル ページへのアクセス。 検索されている特定のユーザーのユーザー情報のみを表示可能。<sup>3</sup> <br><br> 通話品質ダッシュボード (CQD) に表示されるデータを使用した、テナントの通話品質および信頼性の確認、監視、およびトラブルシューティング。  

<sup>1</sup> [PowerShell - Skype for Business モジュール](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
<sup>2</sup> [PowerShell - Microsoft Teams モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3</sup> [Microsoft Teams 管理センター](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>4</sup> Azure Active Directory Admin Center <<note that these are going to come later because they’re related to O365 Group management>> 
<sup>5</sup> Microsoft 365 Admin Center <<note that these are going to come later because they’re related to O365 Group management>> 
-->
Microsoft Teams を管理するために使用可能な管理ツールの詳細については、「[Microsoft Teamsを管理する](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)」を参照してください。

制限、仕様、および Teams に適用されるその他の要件の詳細については、「[Microsoft Teams の制限および仕様](limits-specifications-teams.md)」を参照してください。

## <a name="assign-users-to-each-role"></a>ユーザーをロールに割り当てる

Azure Active Directory でこれらのロールにユーザーはを割り当てることができます。 Azure Active Directory でユーザーに管理者ロールを割り当てる方法については、「[Azure Active Directory でユーザーを管理者ロールに割り当てる](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)」を参照してください。

## <a name="cmdlets-available-for-each-role"></a>各ロールが使用可能なコマンドレット

これらの管理者ロール用の PowerShell ツールのほとんどは、Skype for Business PowerShell モジュール内にあります。これらの管理者ロールがアクセス権を持つコマンドレットの一部は、Skype for Business Online でも利用される、共通の設定を制御できる点にご注意ください。 Skype for Business PowerShell モジュールの特定のロールで現在使用可能なコマンドレットの一覧を表示するには、以下の手順を実行します。

1. ユーザーにそのロール割を割り当てます。そのユーザーに他のロールが割り当てられていないことを確認します。
2. Skype for Business PowerShell モジュールに接続します:<br>
   a. $session = new-csonlinesession<br>
   b. Import-pssession $session<br>
   c. **Get-Module** を使用して、インポートされたセッションの名前 (ランダムに生成された名前) を特定します。<br>
3. **Get-Command -Module** <*上記の名前*> を使用して、利用可能なすべてのコマンドレットを特定します。

### <a name="related-topics"></a>関連トピック

- [Microsoft Teams PowerShell の概要](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
- [Microsoft Teams でチーム所有者とメンバーを割り当てる](https://docs.microsoft.com/microsoftteams/assign-roles-permissions)


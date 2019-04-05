---
title: Microsoft Teams の管理者ロールを使用して Teams を管理します
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
description: 異なった管理者ロールを使用してTeamsの管理について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 677249ba27c79352207a4fffa65480a0a7d484cd
ms.sourcegitcommit: 188c57e6b6c707edb694bb922556dea1c4724846
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "30955015"
---
# <a name="use-microsoft-teams-admin-roles-to-manage-teams"></a>Microsoft Teams の管理者ロールを使用して Teams を管理します

Azure Active Directory (Azure AD) を使用して、Microsoft Teamsを管理するためのさまざまなレベルのアクセスが必要な管理者を指定することができます。 管理者はTeams全体のワークロードを管理することも、通話品質の問題のトラブルシューティングや組織のテレフォニーのニーズを管理するため権限委譲することもできます。 

## <a name="teams-roles-and-capabilities"></a>Teamsの役割ロールと能力

使用できる 4 つのTeamsの管理者ロールがあります: Teams サービス管理者、Teamsのコミュニケーション管理者、Teamsのコミュニケーションサポートスペシャリスト、およびTeamsのコミュニケーションサポートエンジニア です。 次の表を検討し、各ロールができること、および管理者がMicrosoft Teams管理センターおよびPowerShellで使用できるツールが何かを理解してください。

<!-- add Global admin role? -->

| ロール | これらのタスクを実行できます | 以下のツールにアクセスできます |
|----- | ------------------ | ------------------------------ |
| Teams サービス管理者 | Teams サービスの管理、および Office 365 グループの作成と管理 | Microsoft Teams管理センターおよび関連するPowerShellコントロールのすべて:<br><br> 会議の管理。会議ポリシー、構成、会議ブリッジ<sup>1,3</sup>なども含まれます<br><br> 音声の管理。通話ポリシー、電話番号の在庫管理と割り当て、<sup>1</sup>なども含まれます<br><br> メッセージングの管理。メッセージング ポリシー<sup>1,3</sup>なども含まれます<br><br> 組織全体にわたる設定の管理。フェデレーション、Teams のアップグレード、Teams クライアントの設定<sup>1,3</sup>なども含まれます<br><br> 組織およびメンバーシップ (PowerShell でサポートされているグループの管理、Teamsの管理センターでチームの管理) を含む関連の設定でチームを管理します <sup>23</sup><br><br> 高度なトラブルシューティングツールセット<sup>3</sup>を使用して、ユーザープロファイルページを表示し、ユーザー通話の品質の問題をトラブルシューティングします <br><br> 通話品質ダッシュボード（CQD）に表示されるデータを使用し、通話品質の低下による影響を受けたユーザーまで、テナントの通話品質および信頼性へのアクセス、監視、およびトラブルシューティングを行います。 新しいレポートを作成、更新および必要に応じてレポートを削除します。 アップロードし、CQD 構築データを更新します。 |
| Teams 通信管理者 | Teams サービス内の通話および会議の機能の管理します | 会議の管理。会議ポリシー、構成、会議ブリッジ<sup>1,3</sup>なども含まれます<br><br> 音声の管理。通話ポリシー、電話番号の在庫管理と割り当て、<sup>1</sup>なども含まれます<br><br> 高度なトラブルシューティングツールセット<sup>3</sup>を使用して、ユーザープロファイルページを表示し、ユーザー通話の品質の問題をトラブルシューティングします <br><br> 通話品質ダッシュボード（CQD）に表示されるデータを使用し、通話品質の低下による影響を受けたユーザーまで、テナントの通話品質および信頼性へのアクセス、監視、およびトラブルシューティングを行います。 新しいレポートを作成、更新および必要に応じてレポートを削除します。 アップロードし、CQD 構築データを更新します。 |
| Teams 通信サポート エンジニア | **高度な**ツールを使用した Teams 内での通信に関する問題のトラブルシューティング。 | 高度なトラブルシューティングツールセット<sup>3</sup>を使用して、ユーザープロファイルページを表示し、ユーザー通話の品質の問題をトラブルシューティングします <br><br> 通話品質ダッシュボード（CQD）に表示されるデータを使用し、通話品質の低下による影響を受けたユーザーまで、テナントの通話品質および信頼性へのアクセス、監視、およびトラブルシューティングを行います。 |
| Teams 通信サポート スペシャリスト | **基本的な**ツールを使用した Teams 内での通信に関する問題のトラブルシューティング。| 通話分析での通話をトラブルシューティングするためのユーザー プロファイル ページへのアクセス。 検索されている特定のユーザーのユーザー情報のみを表示可能。<sup>3</sup> <br><br> 通話品質ダッシュボード（CQD）に表示されるデータを使用し、テナントの通話品質および信頼性へのアクセス、監視、およびトラブルシューティングを行います。  

<sup>1</sup> [PowerShell - Skype for Business module](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
<sup>2</sup> [PowerShell - Microsoft Teams module](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3</sup> [Microsoft Teams 管理センター](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>4</sup> Azure Active Directory Admin Center <<note that these are going to come later because they’re related to O365 Group management>> 
<sup>5</sup> Microsoft 365 Admin Center <<note that these are going to come later because they’re related to O365 Group management>> 
-->
Microsoft Teamsを管理するために使用可能な管理ツールの詳細については、次を参照してください。[Microsoft Teamsを管理する](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)。

制限、仕様、およびTeamsで適用されるその他の要件について詳しくは、以下を参照してください[Limits and specifications for Microsoft Teams](limits-specifications-teams.md)。

## <a name="assign-users-to-each-role"></a>ユーザーをロールに割り当てます

ユーザーは、Azure Active Directory でこれらのロールに割り当てることができます。 Azure Active Directory でユーザーに管理者ロールを割り当てる方法については、[Azure Active Directory でユーザーを管理者ロールに割り当てる](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)を参照してください。

## <a name="cmdlets-available-for-each-role"></a>各ロールの使用可能なコマンドレット

これらの管理者ロール用のほとんどのPowerShellツールは、Skype for Business PowerShellモジュール内にあります。これらの管理者ロールがSkype for Business Onlineにも使用される共有設定を制御するためのアクセス権を持つコマンドレットもあります。 Skype for Business PowerShellモジュールの特定のロールで現在使用可能なコマンドレットの一覧を表示するには、以下の手順を実行します。

1. ユーザーにそのロール割を割り当てる一方、ユーザーにその他のロールがないことを確認します。
2. Skype for Business PowerShell moduleに接続します:<br>
   a. $session = new-csonlinesession<br>
   b. Import-pssession $session<br>
   c. **Get-Module**を使用してインポートされたセッションの名前を識別します（これはランダムに生成された名前になります）。<br>
3. **Get-Command -Module** <*上記の名前*> を使用して、利用可能なすべてのコマンドレットを特定します

### <a name="related-topics"></a>関連トピック

- [Microsoft Teams PowerShell の概要](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
- [Microsoft Teams でチーム所有者とメンバーを割り当てる](https://docs.microsoft.com/microsoftteams/assign-roles-permissions)


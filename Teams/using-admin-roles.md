---
title: Microsoft Teams の管理者ロールを使用して Teams を管理する
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/19/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.errorpage.needadminpermsforadmincenter.assignadminrolesarticle
- ms.teamsadmincenter.errorpage.needadminperms.assignadminrolesarticle
- ms.teamsadmincenter.signin.error.nopermissions
- ms.teamsadmincenter.directrouting.cqd
- seo-marvel-apr2020
ms.reviewer: islubin
description: 管理ロールを使用して、Teams を管理するために異なるレベルのアクセス権が必要な管理者を指定する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: feccaa2662189016c721a2bf11629598d90f0501
ms.sourcegitcommit: e29e38bf00536400e5826fc55bc86dfd6ed761f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "50558396"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Microsoft Teams の管理者ロールを使用して Teams を管理する

Azure Active Directory (Azure AD) を使用して、Microsoft Teams を管理するために必要な、異なるレベルのアクセス権限を持つ管理者を指定することができます。 管理者は Teams 全体のワークロードを管理できる場合もあれば、通話品質の問題のトラブルシューティングや組織のテレフォニーのニーズを管理するために委任されたアクセス許可を持つ場合もあります。

## <a name="teams-roles-and-capabilities"></a>Teams でのロールと能力

Teams サービス管理者、Teams 通信管理者、Teams 通信サポートスペシャリスト、Teams 通信サポート エンジニア、Teams デバイス管理者など、利用できる Teams 管理者の役割が複数あります。 次の表を確認し、それぞれのロールに許可されている操作および、管理者が Microsoft Teams 管理センターや PowerShell で使用できるツールについて理解してください。

この手順を実行するには、管理者である必要があります。アクセス許可を取得する手順については、この記事を参照してください。

<!-- add Global admin role? -->

| ロール                                    | 実行可能なタスク                                                           | アクセス可能なツール                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Teams サービス管理者             | Teams サービスを管理し、Microsoft 365 グループを管理および作成します。        | 次の機能を含む、Microsoft Teams 管理センターのすべての機能および関連する PowerShell コントロール:<ul><li> 会議ポリシー、構成、会議ブリッジなどの会議を管理します。<sup>1,3</sup></li><li>通話ポリシー、電話番号インベントリ、割り当てなど、音声を管理します。<sup>1</sup></li><li>メッセージング ポリシーを含むメッセージングを管理します。<sup>1,3</sup></li><li>フェデレーション、チームのアップグレード、チームクライアント設定など、組織全体の設定を管理します。<sup>1,3</sup></li><li>組織内のチームと、メンバーシップ (PowerShell でサポートされるグループ管理、Teams 管理センターのチーム管理など) を管理します。<sup>2,3</sup></li><li>Teams 認定デバイスを管理し、構成ポリシーを設定して割り当てる。<sup>2</sup></li><li>高度なトラブルシューティング ツールセットを使用して、ユーザー プロファイル ページを表示し、ユーザーの通話品質に関する問題のトラブルシューティングを行います。<sup>3</sup> </li><li>Microsoft Teams 管理センターのすべてのレポートにアクセスする</li><li> 通話品質の低下による影響を受けたユーザーに対する、通話品質ダッシュボード (CQD) に表示されるデータを使用した、テナントの通話品質および信頼性の確認、監視、およびトラブルシューティング。 新しい通話品質レポートを作成し、必要に応じて通話品質レポートを更新および削除します。 CQD の建物データをアップロードして更新します。</li><li> [Microsoft Teams 管理センターでテナント アプリ カタログにアプリを発行する](manage-apps.md)</li></ul> |
| Teams 通信管理者      | Teams サービス内で通話機能と会議機能を管理します。               | 会議ポリシー、構成、会議ブリッジなどの会議を管理します。<sup>1,3</sup><br><br> 通話ポリシー、電話番号インベントリ、割り当てなど、音声を管理します。<sup>1</sup><br><br> 高度なトラブルシューティング ツールセットを使用して、ユーザー プロファイル ページを表示し、ユーザーの通話品質の問題のトラブルシューティングを行います。<sup>3</sup> <br><br> 通話品質ダッシュボード (CQD) で公開されている低品質のユーザーに公開されたデータを使用して、テナントの通話品質と信頼性にアクセス、監視、トラブルシューティングを行います。 新しい通話品質レポートを作成し、必要に応じて通話品質レポートを更新および削除します。 CQD の建物データをアップロードして更新します。|
| Teams 通信サポート エンジニア   | **高度な** ツールを使用した、Teams 内での通信に関する問題のトラブルシューティング。 | 高度なトラブルシューティング ツールセットを使用して、ユーザー プロファイル ページを表示し、ユーザーの通話品質に関する問題のトラブルシューティングを行います。<sup>3</sup> <br><br> 通話品質ダッシュボード (CQD) で公開されているデータを使用して、低品質の通話の影響を受け取るユーザーに対して、テナントの通話品質と信頼性にアクセス、監視、トラブルシューティングを行います。 |
| Teams 通信サポート スペシャリスト | **基本的な** ツールを使用した、Teams 内での通信に関する問題のトラブルシューティング。    | 通話分析での通話のトラブルシューティングを行うユーザー プロファイル ページにアクセスします。 検索されている特定のユーザーのユーザー情報のみを表示可能。<sup>3</sup> <br><br> 通話品質ダッシュボード (CQD) で公開されているデータを使用して、テナントの通話品質と信頼性にアクセス、監視、トラブルシューティングを行います。 |
| Teams デバイス管理者              | Teams サービスで使用するように構成されたデバイスを管理します。                    | デバイスの構成と更新の管理、接続されている周辺機器のデバイスの正常性と状態の確認、構成プロファイルの設定と適用、デバイスの再起動を行います。<p>Teams デバイス管理者の役割は、通話品質データや通話分析へのアクセスを提供しない。 通話品質データまたは通話分析を表示するには、Teams コミュニケーション管理者の役割が割り当てられている必要があります。 |

<sup>1</sup> [PowerShell - Skype for Business モジュール](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
<sup>2</sup> [PowerShell - Microsoft Teams モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3</sup> [Microsoft Teams 管理センター](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>4</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>5</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
Microsoft Teams を管理するために使用可能な管理ツールの詳細については、「[Microsoft Teamsを管理する](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)」を参照してください。

制限、仕様、および Teams に適用されるその他の要件の詳細については、「[Microsoft Teams の制限および仕様](limits-specifications-teams.md)」を参照してください。

## <a name="assign-users-to-each-role"></a>ユーザーをロールに割り当てる

Azure AD でこれらのロールにユーザーを割り当AD。 Azure Active Directory でユーザーに管理ロールを割り当てる方法については、「Azure [Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)でユーザーを管理者ロールに割り当てる」をAD参照してください。

## <a name="cmdlets-available-for-each-role"></a>各ロールが使用可能なコマンドレット

これらの管理者ロールの PowerShell ツールの多くが Teams PowerShell モジュールに組み込まれています。また、これらの管理者ロールが Skype for Business Online でも使用する共有設定を制御するためのアクセス権を持つコマンドレットの一部に注意することが重要です。 

コマンドレットの完全な一覧を表示するには、次のコマンドを実行します。

```powershell
Get-Command -Module MicrosoftTeams
 ```

### <a name="related-topics"></a>関連トピック

- [Microsoft Teams PowerShell の概要](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
- [Microsoft Teams でチーム所有者とメンバーを割り当てる](https://docs.microsoft.com/microsoftteams/assign-roles-permissions)

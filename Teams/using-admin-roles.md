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
description: 管理者ロールを使用して、Teams を管理するために必要な、異なるレベルのアクセス権限を持つ管理者を指定する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: c227abe677d75d06fd6577ccbfc8057c82f00002
ms.sourcegitcommit: 39378888464ade3cb45879a449143f40f202f3e9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64456960"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Microsoft Teams の管理者ロールを使用して Teams を管理する

Azure Active Directory (Azure AD) を使用して、Microsoft Teams を管理するために必要な、異なるレベルのアクセス権限を持つ管理者を指定することができます。 管理者は Teams 全体のワークロードを管理できる場合もあれば、通話品質の問題のトラブルシューティングや組織のテレフォニーのニーズを管理するために委任されたアクセス許可を持つ場合もあります。

## <a name="teams-roles-and-capabilities"></a>Teams でのロールと能力

利用できる Teams の管理者ロールにはいくつかの種類があり、Teams 管理者、Teams 通信管理者、Teams 通信サポート スペシャリスト、Teams 通信サポート エンジニア、および Teams デバイス管理者が含まれます。 次の表を確認し、それぞれのロールに許可されている操作および、管理者が Microsoft Teams 管理センターや PowerShell で使用できるツールについて理解してください。

> [!NOTE]
> Skype for Business Online 管理者は、PowerShell を使用して **Teams** と **Skype for Business Online** の両方のアプリ ポリシーを管理できます。

これに従うには、管理者である必要があります。アクセス許可を取得する手順については、この記事を参照してください。

<!-- add Global admin role? -->

| 役割                                    | 実行可能なタスク                                                           | アクセス可能なツール                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Teams 管理者             | Teams サービスの管理、および Microsoft 365 グループの管理と作成を行います。        | 次の機能を含む、Microsoft Teams 管理センターのすべての機能および関連する PowerShell コントロール:<ul><li> 会議ポリシー、構成、会議ブリッジなどを含む会議の管理。<sup>1、2</sup></li><li>通話ポリシーや電話番号の在庫管理と割り当てなどを含む音声通話の管理。<sup>1、3</sup></li><li>メッセージング ポリシーなどを含むメッセージングの管理。<sup>1、2</sup></li><li>フェデレーション、Teams のアップグレード、Teams クライアントの設定を含む組織全体にわたる設定を管理する。<sup>1、2</sup></li><li>メンバーシップ (PowerShell 経由でサポートされるグループ管理や Teams 管理センターでのチーム管理) を含む、組織でのチームの管理および関連する設定の管理。<sup>1、2</sup></li><li>Teams 認定デバイスを管理し、構成ポリシーを設定して割り当てる。<sup>1</sup></li><li>ユーザー プロファイル ページの確認および高度なトラブルシューティング ツールセットを使用したユーザーの通話品質の問題のトラブルシューティング。<sup>2</sup> </li><li>Microsoft Teams 管理センターですべてのレポートにアクセスする</li><li> 通話品質の低下による影響を受けたユーザーに対する、通話品質ダッシュボード (CQD) に表示されるデータを使用した、テナントの通話品質および信頼性の確認、監視、およびトラブルシューティング。 新しい通話品質レポートを作成し、通話品質レポートを必要に応じて更新および削除します。 CQD 構築データをアップロードおよび更新します。</li><li> [Microsoft Teams 管理センターのテナント アプリ カタログにアプリを公開する](manage-apps.md)</li></ul> |
| Teams 通信管理者      | Teams サービス内の通話機能および会議機能を管理します。               | 会議ポリシー、構成、会議ブリッジなどを含む会議の管理。<sup>1、2</sup><br><br> 通話ポリシーや電話番号の在庫管理と割り当てなどを含む音声通話の管理。<sup>1、3</sup><br><br> ユーザー プロファイル ページの確認および高度なトラブルシューティング ツールセットを使用したユーザーの通話品質の問題のトラブルシューティング。<sup>2</sup> <br><br> 通話品質の低下による影響を受けたユーザーに対する、通話品質ダッシュボード (CQD) に表示されるデータを使用した、テナントの通話品質および信頼性の確認、監視、およびトラブルシューティング。 新しい通話品質レポートを作成し、通話品質レポートを必要に応じて更新および削除します。 CQD 構築データをアップロードおよび更新します。|
| Teams 通信サポート エンジニア   | **高度な** ツールを使用した、Teams 内での通信に関する問題のトラブルシューティング。 | ユーザー プロファイル ページの確認および高度なトラブルシューティング ツールセットを使用したユーザーの通話品質の問題のトラブルシューティング。<sup>2</sup> <br><br> 通話品質の低下による影響を受けたユーザーに対する、通話品質ダッシュボード (CQD) に表示されるデータを使用した、テナントの通話品質および信頼性の確認、監視、およびトラブルシューティング。 |
| Teams 通信サポート スペシャリスト | **基本的な** ツールを使用した、Teams 内での通信に関する問題のトラブルシューティング。    | 通話分析で通話をトラブルシューティングするための、ユーザー プロファイル ページへのアクセス。 検索されている特定のユーザーのユーザー情報のみを表示可能。<sup>2</sup> <br><br> 通話品質ダッシュボード (CQD) に表示されるデータを使用した、テナントの通話品質および信頼性の確認、監視、およびトラブルシューティング。 |
| Teams デバイス管理者              | Teams サービスで使用するように構成されたデバイスを管理します。                    | デバイスの構成と更新を管理し、接続された周辺機器のデバイスの正常性と状態を確認し、構成プロファイルを設定および適用し、デバイスを再起動します。<p>Teams デバイス管理者の役割には、通話品質データまたは通話分析へのアクセスがありません。 品質通話データまたは通話分析を表示するには、Teams コミュニケーション管理者の役割が割り当てられている必要があります。 |

<sup>1</sup> [PowerShell - Microsoft Teams モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams/) (一般公開 1.1.6 以降は、Skype for Business Online Connector と統合されています)。<br>
<sup>2</sup> [Microsoft Teams 管理センター](./manage-teams-skypeforbusiness-admin-center.md)
<sup>3</sup> Teams 管理者アカウントには、有効なライセンスが必要です。
<!-- <sup>3</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>4</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
Microsoft Teams を管理するために使用可能な管理ツールの詳細については、「[Microsoft Teamsを管理する](./manage-teams-skypeforbusiness-admin-center.md)」を参照してください。

制限、仕様、および Teams に適用されるその他の要件の詳細については、「[Microsoft Teams の制限および仕様](limits-specifications-teams.md)」を参照してください。

## <a name="assign-users-to-each-role"></a>ユーザーをロールに割り当てる

Azure AD でこれらのロールにユーザーはを割り当てることができます。 Azure AD でユーザーに管理者ロールを割り当てる方法については、「[Azure Active Directory でユーザーを管理者ロールに割り当てる](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)」を参照してください。

## <a name="cmdlets-available-for-each-role"></a>各ロールが使用可能なコマンドレット

これらの管理者ロール用の PowerShell ツールのほとんどは、Teams PowerShell モジュール内にあります。これらの管理者ロールがアクセス権を持つコマンドレットの一部は、Skype for Business Online でも使用される共通の設定を制御できる点に注意してください。 

コマンドレットの完全な一覧を表示するには、次のように入力します。

```powershell
Get-Command -Module MicrosoftTeams
 ```

### <a name="related-articles"></a>関連記事

- [Microsoft Teams PowerShell の概要](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](/powershell/module/teams/)
- [Microsoft Teams でチーム所有者とメンバーを割り当てる](./assign-roles-permissions.md)

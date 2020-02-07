---
title: Microsoft Teams の管理者ロールを使用してチームを管理する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/19/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.errorpage.needadminpermsforadmincenter.assignadminrolesarticle
- ms.teamsadmincenter.errorpage.needadminperms.assignadminrolesarticle
- ms.teamsadmincenter.signin.error.nopermissions
- ms.teamsadmincenter.directrouting.cqd
ms.reviewer: islubin
description: 異なる管理者ロールを使用して Teams を管理する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4de271016d3edc4b3153d3cb316c9b1a91580a8b
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836747"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Microsoft Teams の管理者ロールを使用してチームを管理する

Azure Active Directory (Azure AD) を使用して、Microsoft Teams を管理するために必要な、異なるレベルのアクセス権限を持つ管理者を指定することができます。 管理者は Teams 全体のワークロードを管理できる場合もあれば、通話品質の問題のトラブルシューティングや組織のテレフォニーのニーズを管理するために委任されたアクセス許可を持つ場合もあります。 

## <a name="teams-roles-and-capabilities"></a>Teams でのロールと能力

利用できる Teams の管理者ロールには 4 種類あり、Teams サービス管理者、Teams 通信管理者、Teams 通信サポート スペシャリスト、および Teams 通信サポート エンジニアが含まれます。 次の表を確認し、それぞれのロールに許可されている操作および、管理者が Microsoft Teams 管理センターや PowerShell で使用できるツールについて理解してください。



<!-- add Global admin role? -->

| ロール | 実行可能なタスク | アクセス可能なツール |
|----- | ------------------ | ------------------------------ |
| Teams サービス管理者 | Teams サービスを管理し、Office 365 グループの管理と作成を行う | 次の機能を含む、Microsoft Teams 管理センターのすべての機能および関連する PowerShell コントロール:<ul><li> 会議のポリシー、構成、会議ブリッジなどの会議を管理します。<sup>1、3</sup></li><li>通話ポリシー、電話番号のインベントリ、割り当てなど、音声を管理します。<sup>1</sup></li><li>メッセージングポリシーなどのメッセージングを管理する。<sup>1、3</sup></li><li>フェデレーション、チームのアップグレード、teams クライアントの設定など、すべての組織全体の設定を管理します。 s<sup>1、3</sup></li><li>組織内のチームと、メンバーシップ (PowerShell でサポートされているグループ管理と Teams 管理センターのチーム管理) を含む設定を管理します。<sup>23</sup></li><li>高度なトラブルシューティングツールセットを使用して、ユーザープロファイルページを表示し、ユーザーの通話品質の問題のトラブルシューティングを行います。<sup>3</sup> </li><li> 通話品質の低下による影響を受けたユーザーに対する、通話品質ダッシュボード (CQD) に表示されるデータを使用した、テナントの通話品質および信頼性の確認、監視、およびトラブルシューティング。 新しいレポートの作成および必要に応じたレポートの更新および削除。 CQD のデータの作成と更新を行います。</li><li> [Teams クライアントからテナントアプリカタログにアプリを公開する](https://docs.microsoft.com/microsoftteams/tenant-apps-catalog-teams)</li></ul> |
| Teams 通信管理者 | Teams サービス内の通話と会議の機能を管理します。 | 会議のポリシー、構成、会議ブリッジなどの会議を管理します。<sup>1、3</sup><br><br> 通話ポリシー、電話番号のインベントリ、割り当てなど、音声を管理します。<sup>1</sup><br><br> ユーザープロファイルページを表示し、高度なトラブルシューティングツールセットを使用して、ユーザーの通話品質の問題のトラブルシューティングを行います。<sup>3</sup> <br><br> 通話品質ダッシュボード (CQD) に公開されているデータを使用して、テナントの通話品質と信頼性の問題を解決し、通話品質の低下による影響を受けます。 新しいレポートの作成および必要に応じたレポートの更新および削除。 CQD のデータの作成と更新を行います。|
| Teams 通信サポート エンジニア | **高度な**ツールを使用した、Teams 内での通信に関する問題のトラブルシューティング。 | 高度なトラブルシューティングツールセットを使用して、ユーザープロファイルページを表示し、ユーザーの通話品質の問題のトラブルシューティングを行います。<sup>3</sup> <br><br> 通話品質ダッシュボード (CQD) に公開されているデータを使用して、テナントの通話品質と信頼性の問題を解決し、通話品質の低下による影響を受けます。 |
| Teams 通信サポート スペシャリスト | **基本的な**ツールを使用した、Teams 内での通信に関する問題のトラブルシューティング。| 通話分析での通話のトラブルシューティングのための [ユーザープロファイルのアクセス] ページ。 検索されている特定のユーザーのユーザー情報のみを表示可能。<sup>3</sup> <br><br> 通話品質ダッシュボード (CQD) で公開されたデータを使用して、テナントの通話品質と信頼性のアクセス、監視、トラブルシューティングを行います。  

<sup>1</sup> [PowerShell - Skype for Business モジュール](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
<sup>2</sup> [PowerShell - Microsoft Teams モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3</sup> [Microsoft Teams 管理センター](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>4</sup> Azure Active Directory admin center <<note that these are going to come later because they’re related to O365 Group management>> 
<sup>5</sup> Microsoft 365 Admin Center <<note that these are going to come later because they’re related to O365 Group management>> 
-->
Microsoft Teams を管理するために使用可能な管理ツールの詳細については、「[Microsoft Teamsを管理する](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)」を参照してください。

制限、仕様、および Teams に適用されるその他の要件の詳細については、「[Microsoft Teams の制限および仕様](limits-specifications-teams.md)」を参照してください。

## <a name="assign-users-to-each-role"></a>ユーザーをロールに割り当てる

Azure AD でこれらのロールにユーザーを割り当てることができます。 Azure AD のユーザーに管理者ロールを割り当てる方法については、「 [Azure Active Directory でユーザーを管理者ロールに割り当てる](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)」を参照してください。

## <a name="cmdlets-available-for-each-role"></a>各ロールが使用可能なコマンドレット

これらの管理者ロール用の PowerShell ツールのほとんどは、Skype for Business PowerShell モジュールに含まれています。また、これらの管理者ロールの一部のコマンドレットは、Skype for Business Online にも使用されている共有設定を制御するためのアクセス権を持っていることに注意する必要があります。 Skype for business の管理者の役割は、Skype for Business PowerShell モジュールのすべてのコマンドレットにもアクセスできます。

Skype for Business PowerShell モジュールの特定のロールで現在使用可能なコマンドレットの一覧を表示するには、以下の手順を実行します。

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


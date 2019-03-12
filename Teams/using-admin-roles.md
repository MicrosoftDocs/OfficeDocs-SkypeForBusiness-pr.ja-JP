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
description: チームを管理するために別の管理者の役割を使用するについて説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 62b8de5d5e96177476ef07a8a91566d9757364d1
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "30542512"
---
# <a name="use-microsoft-teams-admin-roles-to-manage-teams"></a>Microsoft Teams の管理者ロールを使用して Teams を管理する

Azure Active Directory (AD の Azure) を使用すると、マイクロソフトのチームを管理するためのさまざまなレベルのアクセスを必要としている管理者を指定できます。 管理者は、チーム全体の作業の負荷を管理できますか、ことができますが委任されたアクセス許可の品質の問題や、組織のテレフォニーのニーズを管理する呼び出しのトラブルシューティングをします。 

## <a name="teams-roles-and-capabilities"></a>チームの役割と機能

チーム管理者の 4 つの役割がある利用可能な: チーム サービス管理者、チーム コミュニケーションの管理者、チーム コミュニケーションのサポート ・ スペシャ リスト、およびチーム通信エンジニア リングをサポートします。 各役割で何ができるかを理解するには、次の表を確認し、マイクロソフト チームの管理の中心および PowerShell で使用するツールを管理者です。

<!-- add Global admin role? -->

| 役割 | これらのタスクを実行することができます。 | 次のツールにアクセスできます。 |
|----- | ------------------ | ------------------------------ |
| Teams サービス管理者 | マイクロソフト チーム サービスを管理し、管理し、Office 365 のグループを作成 | マイクロソフトのチーム管理センターとを含む、PowerShell の関連付けられたコントロール内のすべて。<br><br> ミーティングのポリシー、構成、および会議のブリッジ<sup>1, 3</sup>を含めて、会議を管理します。<br><br> ポリシーの呼び出しなど、音声を管理し、電話番号の在庫および割り当て<sup>1</sup><br><br> メッセージング、メッセージング ポリシー<sup>1, 3</sup>などの管理します。<br><br> フェデレーション、チームのアップグレード、およびクライアントの設定<sup>1, 3</sup>のチームを含む、すべての組織全体の設定を管理します。<br><br> 組織と、関連付けられている設定、メンバーシップ (グループ管理チームの管理を展開する管理ポータルで、PowerShell でサポートされている) <sup>23</sup>を含むチームを管理します。<br><br> ユーザー プロファイル ページを表示し、高度なトラブルシューティング ツールセット<sup>3</sup>を使用して、ユーザーの呼び出しの品質に関する問題のトラブルシューティング <br><br> アクセス、監視およびトラブルシューティングのテナントの呼び出しの品質と信頼性のデータを使用して呼び出し品質ダッシュ ボード (救難) でを公開します。 新しいレポートを作成、更新し、必要に応じてレポートを削除します。 アップロードし、データを構築する救難を更新 |
| Teams 通信管理者 | Microsoft Teams サービス内の通話および会議の機能の管理 | ミーティングのポリシー、構成、および会議のブリッジ<sup>1, 3</sup>を含めて、会議を管理します。<br><br> ポリシーの呼び出しなど、音声を管理し、電話番号の在庫および割り当て<sup>1</sup><br><br> ユーザー プロファイル ページを表示し、高度なトラブルシューティング ツールセット<sup>3</sup>を使用して、ユーザーの呼び出しの品質に関する問題のトラブルシューティング |
| Teams 通信サポート エンジニア | **高度な**ツールを使用して、チーム内での通信に関する問題をトラブルシューティングします。 | ユーザー プロファイル ページを表示し、高度なトラブルシューティング ツールセット<sup>3</sup>を使用して、ユーザーの呼び出しの品質に関する問題のトラブルシューティング |
| チーム ・ コミュニケーション ・ サポート ・ スペシャ リスト | **基本的な**ツールを使用して、チーム内での通信に関する問題をトラブルシューティングします。| トラブルシューティングのユーザー プロファイルのページへのアクセスは、分析機能の呼び出しで呼び出されます。 検索されている特定のユーザーのユーザー情報のみを表示可能。<sup>3</sup>

<sup>1</sup> [PowerShell の Skype ビジネス モジュールの](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
<sup>2</sup> [PowerShell のマイクロソフト チーム モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3</sup> [マイクロソフトのチーム管理センター](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>4</sup> Azure Active Directory Admin Center <<note that these are going to come later because they’re related to O365 Group management>> 
<sup>5</sup> Microsoft 365 Admin Center <<note that these are going to come later because they’re related to O365 Group management>> 
-->
マイクロソフトのチームを管理するために利用可能な管理ツールの詳細については、[マイクロソフトのチームを管理する](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)を参照してください。

## <a name="assign-users-to-each-role"></a>各ロールにユーザーを割り当てる

Azure Active Directory 内のこれらのロールにユーザーを割り当てることができます。 Azure Active Directory 内のユーザーに管理者の役割を割り当てる方法については、 [Azure Active Directory の管理者ロールにユーザーを割り当てる](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)を参照してください。

## <a name="cmdlets-available-for-each-role"></a>役割ごとに利用可能なコマンドレット

PowerShell ツールは、これらの管理者の役割のほとんどは、ビジネスの PowerShell モジュールでは、Skype でライブし、ビジネス オンラインの Skype にも活用できる設定を共有いくつかのコマンドレットがこれらの管理者の役割は、コントロールへのアクセスであることに注意してくださいすることが重要です。 ビジネスの PowerShell モジュールの Skype で指定されたロールに現在利用可能なコマンドレットの完全な一覧を表示するには、次の手順を実行します。

1. ユーザーにそのロールを割り当てる、ユーザーに他の役割がないかどうかを確認します。
2. ビジネスの PowerShell モジュールの Skype に接続します。<br>
   a. $session = csonlinesession で新しい<br>
   b. $Session のインポート-pssession<br>
   c. (ランダムに生成された名前であるが)、インポートしたセッションの名前を識別するのにには、 **Get モジュール**を使用します。<br>
3. 使用**Get のコマンド ・ モジュール** <利用可能なすべてのコマンドレットを識別する*名前を上から*_gt

### <a name="related-topics"></a>関連項目

- [マイクロソフト チーム PowerShell の概要](teams-powershell-overview.md)
- [マイクロソフト チーム PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
- [Microsoft Teams でチーム所有者とメンバーを割り当てる](https://docs.microsoft.com/microsoftteams/assign-roles-permissions)


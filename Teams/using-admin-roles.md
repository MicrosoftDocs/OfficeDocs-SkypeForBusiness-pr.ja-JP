---
title: マイクロソフト チームの管理者の役割を使用して、チームを管理するには
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/19/2018
ms.topic: article
ms.service: msteams
description: チームを管理するために異なる管理役割を使用するについて説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 279fed07554589fda4d302b893e5136815963399
ms.sourcegitcommit: ab4476127222d9f0aa9ee503132ff9bdabcaf9bc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "24025277"
---
# <a name="use-microsoft-teams-admin-roles-to-manage-teams"></a>マイクロソフト チームの管理者の役割を使用して、チームを管理するには

Azure Active Directory (AD の Azure) を使用すると、マイクロソフトのチームを管理するためのさまざまなレベルのアクセスを必要としている管理者を指定できます。 管理者は、チーム全体の作業の負荷を管理できますか、ことができますが委任されたアクセス許可の品質の問題や、組織のテレフォニーのニーズを管理する呼び出しのトラブルシューティングをします。 

## <a name="teams-roles-and-capabilities"></a>チームの役割と機能

チーム管理者の 4 つの役割がある利用可能な: チーム サービス管理者、チーム コミュニケーションの管理者、チーム コミュニケーションのサポート ・ スペシャ リスト、およびチーム通信エンジニア リングをサポートします。 各役割で何ができるかを理解するには、次の表を確認し、チームと Skype のビジネス管理センターおよび PowerShell の使用するツールを管理者です。

<!-- add Global admin role? -->

| 役割 | これらのタスクを実行することができます。 | 次のツールにアクセスできます。 |
|----- | ------------------ | ------------------------------ |
| チーム サービス管理者 | マイクロソフト チーム サービスの管理し管理、および Office 365 のグループ (2018年 10 月 Office 365 のグループを管理するアクセス許可を集められることに注意してください) を作成 | マイクロソフトのチームとビジネス管理センターを含め、関連付けられているコントロールの PowerShell の Skype 内のすべて。<br><br> ミーティングのポリシー、構成、および会議のブリッジ<sup>1, 3</sup>を含めて、会議を管理します。<br><br> ポリシーの呼び出しなど、音声を管理し、電話番号の在庫および割り当て<sup>1</sup><br><br> メッセージング、メッセージング ポリシー<sup>1, 3</sup>などの管理します。<br><br> フェデレーション、チームのアップグレード、およびクライアントの設定<sup>1, 3</sup>のチームを含む、すべての組織全体の設定を管理します。<br><br> 組織との関連を含む設定 (2018年 10 月で受信) のメンバーシップの<sup>23</sup>のチームを管理します。<br><br> ユーザー プロファイル ページを表示し、高度なトラブルシューティング ツールセット<sup>3</sup>を使用して、ユーザーの呼び出しの品質に関する問題のトラブルシューティング |
| チーム通信管理者 | 通話およびマイクロソフトのチームのサービス内での会議機能を管理します。 | ミーティングのポリシー、構成、および会議のブリッジ<sup>1, 3</sup>を含めて、会議を管理します。<br><br> ポリシーの呼び出しなど、音声を管理し、電話番号の在庫および割り当て<sup>1</sup><br><br> ユーザー プロファイル ページを表示し、高度なトラブルシューティング ツールセット<sup>1, 3</sup>を使用して、ユーザーの呼び出しの品質に関する問題のトラブルシューティング |
| チーム ・ コミュニケーション ・ サポート ・ エンジニア | **高度な**ツールを使用して、チーム内での通信に関する問題をトラブルシューティングします。 | トラブルシューティングのユーザー プロファイルのページへのアクセスは、分析機能の呼び出しで呼び出されます。 完全な呼び出しレコードの情報を表示できます。<sup>3</sup> |
| チーム ・ コミュニケーション ・ サポート ・ スペシャ リスト | **基本的な**ツールを使用して、チーム内での通信に関する問題をトラブルシューティングします。| トラブルシューティングのユーザー プロファイルのページへのアクセスは、分析機能の呼び出しで呼び出されます。 のみ、検索対象の特定のユーザーのユーザー情報を表示できます。<sup>3</sup>

<sup>1</sup> [PowerShell の Skype ビジネス モジュールの](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
<sup>2</sup> [PowerShell のマイクロソフト チーム モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3</sup> [マイクロソフト チームと Skype のビジネス管理センター](https://docs.microsoft.com/en-us/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>4</sup> Azure Active Directory Admin Center <<note that these are going to come later because they’re related to O365 Group management>> 
<sup>5</sup> Microsoft 365 Admin Center <<note that these are going to come later because they’re related to O365 Group management>> 
-->
マイクロソフトのチームを管理するために利用可能な管理ツールの詳細については、[マイクロソフトのチームを管理する](https://docs.microsoft.com/en-us/microsoftteams/manage-teams-skypeforbusiness-admin-center)を参照してください。

## <a name="assign-users-to-each-role"></a>各ロールにユーザーを割り当てる

Azure Active Directory 内のこれらのロールにユーザーを割り当てることができます。 Azure Active Directory 内のユーザーに管理者の役割を割り当てる方法については、 [Azure Active Directory の管理者ロールにユーザーを割り当てる](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)を参照してください。

## <a name="cmdlets-available-for-each-role"></a>役割ごとに利用可能なコマンドレット

PowerShell ツールは、これらの管理者の役割のほとんどは、ビジネスの PowerShell モジュールでは、Skype でライブし、ビジネス オンラインの Skype にも活用できる設定を共有いくつかのコマンドレットがこれらの管理者の役割は、コントロールへのアクセスであることに注意してくださいすることが重要です。 ビジネスの PowerShell モジュールの Skype で指定されたロールに現在利用可能なコマンドレットの完全な一覧を表示するには、次の手順を実行します。

1. ユーザーにそのロールを割り当てる、ユーザーに他の役割がないかどうかを確認します。
2. ビジネスの PowerShell モジュールの Skype に接続します。<br>
   a. $session = csonlinesession で新しい<br>
   b. $Session のインポート-pssession<br>
   c. (ランダムに生成された名前であるが)、インポートしたセッションの名前を識別するのにには、 **Get モジュール**を使用します。<br>
3. 使用**Get のコマンド ・ モジュール** <*上の名前*> 利用可能なすべてのコマンドレットを識別するには

### <a name="related-topics"></a>関連トピック

- [マイクロソフト チーム PowerShell の概要](teams-powershell-overview.md)
- [マイクロソフト チーム PowerShell](https://docs.microsoft.com/en-us/powershell/module/teams/?view=teams-ps)
- [チーム所有者およびマイクロソフトのチームのメンバーを割り当てる](https://docs.microsoft.com/en-us/microsoftteams/assign-roles-permissions)


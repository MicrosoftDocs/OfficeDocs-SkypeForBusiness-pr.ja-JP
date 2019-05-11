---
title: Microsoft Teams の主要機能を構成するための使用開始チェックリスト
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: チームを構成する場合、コア、to do のタスクと活動このチェックリストに従います。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ba1561416b403709439c7d239dd0023c0f946ab6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33898905"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>マイクロソフト チームの中核的な機能を構成します。

| いいえ | 活動またはタスク | 説明 | 完了状態 | その他の情報 |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | チームのすべての前提条件がお客様の環境に含まれていることを検証します。 | チームは、エンド ・ ツー ・ エンドのコラボレーション ソリューションを構築するには、他のプラットフォームに依存します。 展開、Exchange、SharePoint Online では、およびビジネスのための OneDrive が正しく構成されていることを確認して、IT チームと協力します。 | | [Microsoft Teams との SharePoint Online と OneDrive for Business の連携](sharepoint-onedrive-interact.md) <br/><br/>[Exchange と Microsoft Teams の連携](exchange-teams-interact.md) |
| 2  | テナントのチームが有効になっていることを検証します。 | チームに既定ではすべての組織になっています。 テナントでは、チームが有効になっていることを確認するのには Office 365 管理センターの**サービス & のアドイン**のページを確認し、必要な場合に有効にします。 | | [Office 365 を使用する組織で Microsoft Teams をセットアップする](office-365-set-up.md) |
| 3  | ロールとアクセス許可を構成します。 | チームは、2 種類のロールをサポート: メンバーおよび所有者。 <br/><br/>メンバーをチームに追加すると、所有者が所有者のロールにメンバー昇格させることもできます。 ベスト プラクティスとして、各チームに割り当てられている 2 つ以上の所有者があることをお勧めします。 <br/><br/>既定では、チームを作成 Exchange オンラインでホストされているメールボックスを持っている組織内の全員ことができます。 新しいチームを作成したユーザーでは、そのチームの所有者のロールが自動的に付与します。 <br/><br/>必要がある場合、新しいチームを作成する特定のユーザーにのみ Office 365 のグループの設定を構成できます。 | | [Microsoft Teams で役割と権限を割り当てる](assign-roles-permissions.md) <br/><br/>[Office 365 グループと Microsoft Teams](office-365-groups.md) <br/><br/>[Office 365 のグループを作成できるユーザーを管理します。](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | テナント全体にわたるチームの設定を構成します。 | テナントのレベルでいくつかのチームの設定を構成できます。 チームが有効になっているユーザーは、テナント構成からこれらの設定を継承します。<ul><li>General</li><li>電子メールの統合</li><li>アプリ</li><li>カスタム クラウド ストレージ</li><li>通話と会議</li><li>メッセージング </li></ul>| | [組織のMicrosoft Teams の設定を管理する](enable-features-office-365.md) |
| 5  | ゲスト アクセスを構成するオプション。 | チームとチャネルへのアクセス権を付与して、組織外のユーザーと共同作業するには、チームでのゲスト アクセスを使用します。 ゲスト アクセスは、チーム内のテナント レベルの設定です。 これは、既定でオフは。 <br/>ゲスト アクセスを有効にして、組織がその機能を使用する予定がある場合は、テナント全体のゲストの設定を構成します。 | | [Microsoft Teams でのゲスト アクセス](guest-access.md) |
| 6  | チームの名前付けポリシーを構成するオプション。 | チームでは、ユーザーが作成またはチーム名を編集するときに Office 365 のグループの名前付けポリシーを活用します。 <br/><br/>既定では、名前付けの制限は適用されません、ユーザーがチームを作成するとき。 <br/><br/>チーム名のルールを適用する場合は、Office 365 のグループが、組織に適用するポリシーの名前を構成します。 必須のプレフィックスとサフィックスを設定し、ブロックされている単語を指定できます。 | | [Microsoft Teams でチームを作成するときの Office 365 グループの計画](plan-office-365-groups.md) <br/><br/>[グループの名前付けポリシーを office 365](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | チームの SMTP ドメインの Exchange を構成します。 | チームを使用して、オンラインの Exchange SMTP ドメインを使用してチーム メンバーに通知を送信するのには-email.teams.microsoft.com-ときにして追加または削除されました。 <br/><br/>Exchange インフラストラクチャの承認済みドメインの一覧にこの SMTP ドメインを追加することを確認します。 | | [Microsoft Teams SMTP ドメインを承認済みドメインとして Exchange Online に追加する](smtp-accepted-domain.md) |
| 8  | 構成し、チームへのユーザー アクセスの管理 | チームのすべてのユーザーを有効にすることを強くお勧めを許可またはの割り当てまたはチームの製品のライセンスを削除して、ユーザー単位でのチームへのアクセスを禁止できます。 | | [Microsoft Teams へのユーザー アクセスを管理する](user-access.md) |
| 9  | ユーザーにライセンスを割り当てる | オーディオ会議、電話システム、および計画を呼び出すような機能をユーザーにライセンスを割り当てる | | [Skype for Business と Microsoft Teams のライセンスを割り当てる](assign-teams-licenses.md) <br/><br/>[MyAdvisor – ユーザーの有効化スクリプト](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_2_0_6,5_2_0_3) |
| 10 | オプション: 使用の PowerShell チームを管理するには | Office 365 の管理センターではなく、PowerShell コマンドレットを使用するには、チームの設定を管理します。 | | [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) |

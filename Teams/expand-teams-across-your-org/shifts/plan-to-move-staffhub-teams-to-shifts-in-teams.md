---
title: Microsoft Teams での StaffHub teams のシフトへの移行を計画する
author: LanaChin
ms.author: v-lanac
ms.reviewer: gumariam,aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams で StaffHub teams をシフトに移行する計画を立てる方法についてのガイダンスを取得します。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: ad0043b1599ac7ce90599a03d786d756cf16e684
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008149"
---
# <a name="plan-to-move-your-staffhub-teams-to-shifts-in-microsoft-teams"></a>Microsoft Teams での StaffHub teams のシフトへの移行を計画する

> [!IMPORTANT]
> 2019 年 12 月 31 日より、Microsoft StaffHub が廃止されます。 Microsoft では、StaffHub の機能を Microsoft Teams に組み込む作業に取り組んでいます。 現在、Teams にはシフト アプリのスケジュール管理機能が含まれています。今後、他の機能もロールアウトされる予定です。 StaffHub は、2019 年 12 月 31 日以降すべてのユーザーがご利用できなくなります。 ユーザーが StaffHub を開くと、Teams をダウンロードするように求めるメッセージが表示されます。 詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。 

変更の計画を開始すると、StaffHub から Teams への移行が開始されます。 チームへの移行が成功したことを確認するために、一般的な切り替え計画を示すサンプルタイムラインを作成しました。 このサンプルタイムラインでは、移動の準備を行うための計画アクティビティの概要を示しています。これにより、組織の StaffHub teams を Teams に移動することができます。

StaffHub から Teams への移行を計画する場合は、タイムラインをガイダンスとして使用し、組織のニーズに合わせてカスタマイズします。 タイムラインの手順にリンクされているリソースを必ず確認してください。

## <a name="prepare-to-move-your-staffhub-teams-to-teams"></a>StaffHub teams を Teams に移行する準備を行う

|ステップ |ガイダンス  |設備 |
|---------|---------|---------|
|1    |関係者の準備と特定         |         |
|両面     |StaffHub からチームとチームのオンボードへの切り替えに関するドキュメントを確認する         |[StaffHub](microsoft-staffhub-to-be-retired.md)<br><br>[Teams での StaffHub teams のシフトへの移動](move-staffhub-teams-to-shifts-in-teams.md)<br><br>[Teams の使用を開始する](../../get-started-with-teams-quick-start.md)         |
|3    |組織で Office 365 グループを有効にする        |[Office 365 グループとチーム](../../Office-365-groups.md)      |
|4    |前提条件が満たされていることを確認する         |[前提条件を満たしていることを確認する](move-staffhub-teams-to-shifts-in-teams.md#check-that-prerequisites-are-met)       |
|5   |組織内の StaffHub ユーザーに Teams ライセンスを割り当てる|[Teams のライセンスを割り当てる](move-staffhub-teams-to-shifts-in-teams.md#assign-teams-licenses)<br><br>[Teams へのユーザー アクセスを管理する](../../user-access.md)      |
|6    |StaffHub PowerShell モジュールをインストールする        |[StaffHub PowerShell モジュールをインストールする](install-the-staffhub-powershell-module.md)        |
|7     |チームに移動するためのタイムラインを特定し、StaffHub ユーザーを特定する       |[レポートを実行してアクティブな StaffHub の使用状況を表示する](run-report-to-show-staffhub-usage.md) |
|個     |Azure AD アカウントを持っていない StaffHub ユーザーを特定します (StaffHub に "非アクティブ" と表示されます)。アカウントをリンクさせる     |[リンクがない StaffHub チーム メンバーの Azure AD アカウントをリンクする](move-staffhub-teams-to-shifts-in-teams.md#link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one)        |
|ファイブ    |組織に合わせてカスタマイズされたユーザーのトレーニングコンテンツを作成する         |[Teams のユーザー準備計画を準備する](../../upgrade-user-readiness.md)     |
|常用    |Teams でのシフトへの切り替えについて StaffHub ユーザーと通信する         |[StaffHub for Teams からユーザーへのメール通信のサンプル](staffhub-to-teams-email-template.md)         |
|折り     |Teams クライアントをインストールする         |[Teams のクライアントを取得する](../../get-clients.md) |
|以内    |ユーザーに FirstLineWorker アプリセットアップポリシーを割り当てます (または、カスタムアプリセットアップポリシーを作成して割り当てる)、シフトアプリを Teams クライアントにピン留めします。  |[FirstLineWorker アプリのセットアップ ポリシーをユーザーに割り当てる](move-staffhub-teams-to-shifts-in-teams.md#assign-the-firstlineworker-app-setup-policy-to-users)         |
|14     |シフトやチームの使い方についてユーザーを教育する         |[Teams にユーザーをオンボードする](move-staffhub-teams-to-shifts-in-teams.md#onboard-users-to-teams)<br><br>[ヘルプドキュメントのシフト](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)<br><br>[Teams のヘルプ ドキュメント](https://support.office.com/teams)<br><br>[Teams のトレーニング用ビデオ](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)       |
|14     |StaffHub teams のリストを確認して、それらのチームのすべてのユーザーを Teams に移動する必要があることを確認します。 スケジュールを設定しないユーザーを削除します。 |         |

## <a name="move-your-organizations-staffhub-teams-to-teams"></a>組織の StaffHub teams を Teams に移動する

|ステップ |ガイダンス |設備  |
|---------|---------|---------|
|1  |パイロットチームを特定して1つのチームを移動する          |[特定のStaffHub チームを移動する](move-staffhub-teams-to-shifts-in-teams.md#move-a-staffhub-team)          |
|両面    |パイロットチームを検証して、移動の問題を特定します。 必要に応じてトレーニングドキュメントを更新します。         |         |
|3     |追加のパイロットチームを特定し、5 ~ 10 チームに移動する         |[StaffHub チームを移動する](move-staffhub-teams-to-shifts-in-teams.md#go-beyond-your-pilot-and-move-all-staffhub-teams)         |
|4     |残りの StaffHub teams を特定し、段階的なアプローチでそれらを移動する         |[StaffHub チームを移動する](move-staffhub-teams-to-shifts-in-teams.md#go-beyond-your-pilot-and-move-all-staffhub-teams)         |
|5     |シフトやチームのサポートを継続する         |         |
|6     |セルフサービスパスワードリセットが有効になっている場合は、Teams でサポートされているログオンの問題に関するレポートを実行します。       |[セルフサービスによるパスワードのリセットのセットアップに関するレポートを実行する](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-reporting)        |
